---
title: ファイルのアクセス許可
description: WSL が Windows でファイルのアクセス許可を特定する方法について
keywords: BashOnWindows, bash, wsl, wsl2, windows, linux 用 windows サブシステム, windowssubsystem, ubuntu, debian, suse, windows 10, ファイル, アクセス許可
ms.date: 01/14/2020
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.localizationpriority: high
ms.openlocfilehash: 3de8553baf616ee8d5d45f0738615f83df952942
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413223"
---
# <a name="file-permissions-for-wsl"></a><span data-ttu-id="94add-104">WSL のファイルのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="94add-104">File Permissions for WSL</span></span>

<span data-ttu-id="94add-105">このページでは、特に NT ファイル システム上の Windows 内のリソースにアクセスした際に、Linux 用 Windows サブシステム全体で Linux のファイルのアクセス許可がどのように解釈されるかについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="94add-105">This page details how Linux file permissions are interpreted across the Windows Subsystem for Linux, especially when accessing resources inside of Windows on the NT file system.</span></span> <span data-ttu-id="94add-106">このドキュメントでは、[Linux ファイル システムのアクセス許可の構造](https://wiki.archlinux.org/index.php/File_permissions_and_attributes)と [umask コマンド](https://en.wikipedia.org/wiki/Umask)について基本的な知識があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="94add-106">This documentation assumes a basic understanding of the [Linux file system permissions structure](https://wiki.archlinux.org/index.php/File_permissions_and_attributes) and the [umask command](https://en.wikipedia.org/wiki/Umask).</span></span>

<span data-ttu-id="94add-107">WSL から Windows ファイルにアクセスした際、ファイルのアクセス許可は Windows のアクセス許可から計算されるか、WSL によってファイルに追加されたメタデータから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="94add-107">When accessing Windows files from WSL the file permissions are either calculated from Windows permissions, or are read from metadata that has been added to the file by WSL.</span></span> <span data-ttu-id="94add-108">このメタデータは、既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="94add-108">This metadata is not enabled by default.</span></span>

## <a name="wsl-metadata-on-windows-files"></a><span data-ttu-id="94add-109">Windows ファイルの WSL メタデータ</span><span class="sxs-lookup"><span data-stu-id="94add-109">WSL metadata on Windows files</span></span>

<span data-ttu-id="94add-110">WSL のマウント オプションとしてメタデータが有効な場合、Windows NT ファイルの拡張属性を追加および解釈することで、Linux ファイル システムのアクセス許可を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="94add-110">When metadata is enabled as a mount option in WSL, extended attributes on Windows NT files can be added and interpreted to supply Linux file system permissions.</span></span>

<span data-ttu-id="94add-111">WSL では、次の 4 つの NTFS 拡張属性を追加できます。</span><span class="sxs-lookup"><span data-stu-id="94add-111">WSL can add four NTFS extended attributes:</span></span>

| <span data-ttu-id="94add-112">属性名</span><span class="sxs-lookup"><span data-stu-id="94add-112">Attribute Name</span></span> | <span data-ttu-id="94add-113">説明</span><span class="sxs-lookup"><span data-stu-id="94add-113">Description</span></span> |
| --- | --- |
| <span data-ttu-id="94add-114">$LXUID</span><span class="sxs-lookup"><span data-stu-id="94add-114">$LXUID</span></span> | <span data-ttu-id="94add-115">ユーザー所有者 ID</span><span class="sxs-lookup"><span data-stu-id="94add-115">User Owner ID</span></span> |
| <span data-ttu-id="94add-116">$LXGID</span><span class="sxs-lookup"><span data-stu-id="94add-116">$LXGID</span></span> | <span data-ttu-id="94add-117">グループ所有者 ID</span><span class="sxs-lookup"><span data-stu-id="94add-117">Group Owner ID</span></span> |
| <span data-ttu-id="94add-118">$LXMOD</span><span class="sxs-lookup"><span data-stu-id="94add-118">$LXMOD</span></span> | <span data-ttu-id="94add-119">ファイル モード (ファイル システムのアクセス許可の 8 進数と種類。例: 0777)</span><span class="sxs-lookup"><span data-stu-id="94add-119">File mode (File systems permission octals and type, e.g: 0777)</span></span> |
| <span data-ttu-id="94add-120">$LXDEV</span><span class="sxs-lookup"><span data-stu-id="94add-120">$LXDEV</span></span> | <span data-ttu-id="94add-121">デバイス (デバイス ファイルの場合)</span><span class="sxs-lookup"><span data-stu-id="94add-121">Device, if it is a device file</span></span> |

<span data-ttu-id="94add-122">さらに、通常のファイルやディレクトリではないファイル (例: シンボリック リンク、FIFO、ブロック デバイス、UNIX ソケット、文字デバイス) には、NTFS [再解析ポイント](/windows/win32/fileio/reparse-points)もあります。</span><span class="sxs-lookup"><span data-stu-id="94add-122">Additionally, any file that is not a regular file or directory (e.g: symlinks, FIFOs, block devices, unix sockets, and character devices) also have an NTFS [reparse point](/windows/win32/fileio/reparse-points).</span></span> <span data-ttu-id="94add-123">これにより、特定のディレクトリ内のファイルの種類を、その拡張属性を照会しなくても、はるかにすばやく特定できます。</span><span class="sxs-lookup"><span data-stu-id="94add-123">This makes it much faster to determine the kind of file in a given directory without having to query its extended attributes.</span></span>

## <a name="file-access-scenarios"></a><span data-ttu-id="94add-124">ファイル アクセスのシナリオ</span><span class="sxs-lookup"><span data-stu-id="94add-124">File Access Scenarios</span></span>

<span data-ttu-id="94add-125">以下は、Linux 用 Windows サブシステムを使用してさまざまな方法でファイルにアクセスするときに、アクセス許可がどのように特定されるかを説明したものです。</span><span class="sxs-lookup"><span data-stu-id="94add-125">Below is a description of how permissions are determined when accessing files in different ways using the Windows Subsystem for Linux.</span></span>

### <a name="accessing-files-in-the-windows-drive-file-system-drvfs-from-linux"></a><span data-ttu-id="94add-126">Linux から Windows ドライブ ファイル システム (DrvFS) のファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="94add-126">Accessing Files in the Windows drive file system (DrvFS) from Linux</span></span>

<span data-ttu-id="94add-127">これらのシナリオは、WSL から (ほとんどの場合 `/mnt/c` 経由で) Windows ファイルにアクセスする場合に生じるものです。</span><span class="sxs-lookup"><span data-stu-id="94add-127">These scenarios occur when you are accessing your Windows files from WSL, most likely via `/mnt/c`.</span></span>

#### <a name="reading-file-permissions-from-an-existing-windows-file"></a><span data-ttu-id="94add-128">既存の Windows ファイルからファイルのアクセス許可を読み取る</span><span class="sxs-lookup"><span data-stu-id="94add-128">Reading file permissions from an existing Windows file</span></span>

<span data-ttu-id="94add-129">結果は、ファイルに既存のメタデータがあるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="94add-129">The result depends on if the file already has existing metadata.</span></span>

##### <a name="drvfs-file-does-not-have-metadata-default"></a><span data-ttu-id="94add-130">DrvFS ファイルにメタデータがない場合 (既定)</span><span class="sxs-lookup"><span data-stu-id="94add-130">DrvFS file does not have metadata (default)</span></span>

<span data-ttu-id="94add-131">ファイルにメタデータが関連付けられていない場合は、Windows ユーザーの有効なアクセス許可が読み取りビット、書き込みビット、または実行ビットに変換され、これらが "ユーザー"、"グループ"、および "その他" に対して同じ値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="94add-131">If the file has no metadata associated with it then we translate the effective permissions of the Windows user to read/write/execute bits and set them to the this as the same value for user, group, and other.</span></span> <span data-ttu-id="94add-132">たとえば、Windows ユーザー アカウントにファイルの読み取りおよび実行アクセス権がある一方で書き込みアクセス権がない場合、これは "ユーザー"、"グループ"、および "その他" に対して `r-x` と表示されます。</span><span class="sxs-lookup"><span data-stu-id="94add-132">For example, if your Windows user account has read and execute access but not write access to the file then this will be shown as `r-x` for user, group and other.</span></span> <span data-ttu-id="94add-133">Windows でファイルに "読み取り専用" 属性が設定されている場合、Linux で書き込みアクセス権は付与されません。</span><span class="sxs-lookup"><span data-stu-id="94add-133">If the file has the 'Read Only' attribute set in Windows then we do not grant write access in Linux.</span></span>

##### <a name="the-file-has-metadata"></a><span data-ttu-id="94add-134">ファイルにメタデータがある場合</span><span class="sxs-lookup"><span data-stu-id="94add-134">The file has metadata</span></span>

<span data-ttu-id="94add-135">ファイルにメタデータが存在する場合は、Windows ユーザーの有効なアクセス許可を変換する代わりに、これらのメタデータ値がそのまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="94add-135">If the file has metadata present, we simply use those metadata values instead of translating effective permissions of the Windows user.</span></span>

#### <a name="changing-file-permissions-on-an-existing-windows-file-using-chmod"></a><span data-ttu-id="94add-136">chmod を使用して既存の Windows ファイルのファイル アクセス許可を変更する</span><span class="sxs-lookup"><span data-stu-id="94add-136">Changing file permissions on an existing Windows file using chmod</span></span>

<span data-ttu-id="94add-137">結果は、ファイルに既存のメタデータがあるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="94add-137">The result depends on if the file already has existing metadata.</span></span>

##### <a name="chmod-file-does-not-have-metadata-default"></a><span data-ttu-id="94add-138">chmod ファイルにメタデータがない場合 (既定)</span><span class="sxs-lookup"><span data-stu-id="94add-138">chmod file does not have metadata (default)</span></span>

<span data-ttu-id="94add-139">chmod の効果は 1 つだけです。ファイルのすべての書き込み属性を削除すると、Windows ファイルに "読み取り専用" 属性が設定されます。これは、Linux の SMB (Server Message Block) クライアントである CIFS (Common Internet File System) と同じ動作であるためです。</span><span class="sxs-lookup"><span data-stu-id="94add-139">Chmod will only have one effect, if you remove all the write attributes of a file then the 'read only' attribute on the Windows file will be set, since this is the same behaviour as CIFS (Common Internet File System) which is the SMB (Server Message Block) client in Linux.</span></span>

##### <a name="chmod-file-has-metadata"></a><span data-ttu-id="94add-140">chmod ファイルにメタデータがある場合</span><span class="sxs-lookup"><span data-stu-id="94add-140">chmod file has metadata</span></span>

<span data-ttu-id="94add-141">chmod を使用すると、ファイルの既存のメタデータに応じて、メタデータを変更または追加できます。</span><span class="sxs-lookup"><span data-stu-id="94add-141">Chmod will change or add metadata depending on the file's already existing metadata.</span></span> 

<span data-ttu-id="94add-142">たとえメタデータに示されていても、Windows 上で与えられている以上のアクセス権を自分に与えることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="94add-142">Please keep in mind that you cannot give yourself more access than what you have on Windows, even if the metadata says that is the case.</span></span> <span data-ttu-id="94add-143">たとえば、`chmod 777` を使用してファイルに対する書き込みアクセス許可があることを示すメタデータを設定することはできますが、そのファイルへのアクセスを試みたときにそのファイルに書き込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="94add-143">For example, you could set the metadata to display that you have write permissions to a file using `chmod 777`, but if you tried to access that file you would still not be able to write to it.</span></span> <span data-ttu-id="94add-144">これは、相互運用性により、Windows ファイルに対するすべての読み取りまたは書き込みコマンドが Windows ユーザーのアクセス許可を介してルーティングされるためです。</span><span class="sxs-lookup"><span data-stu-id="94add-144">This is thanks to interopability, as any read or write commands to Windows files are routed through your Windows user permissions.</span></span>

#### <a name="creating-a-file-in-drivefs"></a><span data-ttu-id="94add-145">DriveFS にファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="94add-145">Creating a file in DriveFS</span></span>

<span data-ttu-id="94add-146">結果は、メタデータが有効になっているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="94add-146">The result depends on if metadata is enabled.</span></span>

##### <a name="metadata-is-not-enabled-default"></a><span data-ttu-id="94add-147">メタデータが有効になっていない場合 (既定)</span><span class="sxs-lookup"><span data-stu-id="94add-147">Metadata is not enabled (default)</span></span>

<span data-ttu-id="94add-148">新しく作成されたファイルの Windows アクセス許可は、特定のセキュリティ記述子なしで Windows でファイルを作成した場合と同じく、親のアクセス許可から継承されます。</span><span class="sxs-lookup"><span data-stu-id="94add-148">The Windows permissions of the newly created file will be the same as if you created the file in Windows without a specific security descriptor, it will inherit the parent's permissions.</span></span>

##### <a name="metadata-is-enabled"></a><span data-ttu-id="94add-149">メタデータが有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="94add-149">Metadata is enabled</span></span>

<span data-ttu-id="94add-150">ファイルのアクセス許可ビットは Linux umask に従うように設定され、ファイルと共にメタデータが保存されます。</span><span class="sxs-lookup"><span data-stu-id="94add-150">The file's permission bits are set to follow the Linux umask, and the file will be saved with metadata.</span></span>

#### <a name="which-linux-user-and-linux-group-owns-the-file"></a><span data-ttu-id="94add-151">どの Linux ユーザーおよび Linux グループがファイルを所有しているか</span><span class="sxs-lookup"><span data-stu-id="94add-151">Which Linux user and Linux group owns the file?</span></span> 

<span data-ttu-id="94add-152">結果は、ファイルに既存のメタデータがあるかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="94add-152">The result depends on if the file already has existing metadata.</span></span>

##### <a name="user-file-does-not-have-metadata-default"></a><span data-ttu-id="94add-153">ユーザー ファイルにメタデータがない場合 (既定)</span><span class="sxs-lookup"><span data-stu-id="94add-153">User file does not have metadata (default)</span></span>

<span data-ttu-id="94add-154">既定のシナリオでは、Windows ドライブを自動マウントするときに、任意のファイルのユーザー ID (UID) が WSL ユーザーのユーザー ID に設定され、グループ ID (GID) が WSL ユーザーのプリンシパル グループ ID に設定されるように指定します。</span><span class="sxs-lookup"><span data-stu-id="94add-154">In the default scenario, when automounting Windows drives, we specify that the user ID (UID) for any file is set to the user ID of your WSL user and the group ID (GID) is set to the principal group ID of your WSL user.</span></span>

##### <a name="user-file-has-metadata"></a><span data-ttu-id="94add-155">ユーザー ファイルにメタデータがある場合</span><span class="sxs-lookup"><span data-stu-id="94add-155">User file has metadata</span></span>

<span data-ttu-id="94add-156">メタデータに指定されている UID および GID は、ファイルのユーザー所有者およびグループ所有者として適用されます。</span><span class="sxs-lookup"><span data-stu-id="94add-156">The UID and GID specified in the metadata is applied as the user owner and group owner of the file.</span></span>

### <a name="accessing-linux-files-from-windows-using-wsl"></a><span data-ttu-id="94add-157">`\\wsl$` を使用して Windows から Linux ファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="94add-157">Accessing Linux files from Windows using `\\wsl$`</span></span>

<span data-ttu-id="94add-158">`\\wsl$` 経由で Linux ファイルにアクセスする場合は、WSL ディストリビューションの既定のユーザーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="94add-158">Accessing Linux files via `\\wsl$` will use the default user of your WSL distribution.</span></span> <span data-ttu-id="94add-159">したがって、Linux ファイルにアクセスするすべての Windows アプリに、既定のユーザーと同じアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="94add-159">Therefore any Windows app accessing Linux files will have the same permissions as the default user.</span></span>

#### <a name="creating-a-new-file"></a><span data-ttu-id="94add-160">新しいファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="94add-160">Creating a new file</span></span>

<span data-ttu-id="94add-161">Windows から WSL ディストリビューション内に新しいファイルを作成する場合は、既定の umask が適用されます。</span><span class="sxs-lookup"><span data-stu-id="94add-161">The default umask is applied when creating a new file inside of a WSL distribution from Windows.</span></span> <span data-ttu-id="94add-162">既定の umask は `022` です。つまり、"グループ" と "その他" に対する書き込みアクセス許可を除くすべてのアクセス許可が許可されます。</span><span class="sxs-lookup"><span data-stu-id="94add-162">The default umask is `022`, or in other words it allows all permissions except write permissions to groups and others.</span></span> 

### <a name="accessing-files-in-the-linux-root-file-system-from-linux"></a><span data-ttu-id="94add-163">Linux から Linux ルート ファイル システム内のファイルにアクセスする</span><span class="sxs-lookup"><span data-stu-id="94add-163">Accessing files in the Linux root file system from Linux</span></span>

<span data-ttu-id="94add-164">Linux ルート ファイル システム内で作成、変更、またはアクセスされるすべてのファイルには、新しく作成されたファイルに umask を適用するといった標準の Linux 規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="94add-164">Any files created, modified, or accessed in the Linux root file system follow standard Linux conventions, such as applying the umask to a newly created file.</span></span>

## <a name="configuring-file-permissions"></a><span data-ttu-id="94add-165">ファイルのアクセス許可を構成する</span><span class="sxs-lookup"><span data-stu-id="94add-165">Configuring file permissions</span></span>

<span data-ttu-id="94add-166">wsl.conf 内でマウント オプションを使用して、Windows ドライブ内のファイルのアクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="94add-166">You can configure your file permissions inside of your Windows drives using the mount options in wsl.conf.</span></span> <span data-ttu-id="94add-167">マウント オプションを使用すると、`umask`、`dmask`、および `fmask` のアクセス許可マスクを設定できます。</span><span class="sxs-lookup"><span data-stu-id="94add-167">The mount options allow you to set `umask`, `dmask` and `fmask` permissions masks.</span></span> <span data-ttu-id="94add-168">`umask` はすべてのファイルに適用され、`dmask` はディレクトリにのみ適用されます。`fmask` はファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="94add-168">The `umask` is applied to all files, the `dmask` is applied just to directories and the `fmask` is applied just to files.</span></span> <span data-ttu-id="94add-169">これらのアクセス許可のマスクは、ファイルに適用されるときに論理 OR 演算が適用されます。たとえば、`umask` の値が `023` で、`fmask` の値が `022` の場合、ファイルに対する結果のアクセス許可マスクは `023` になります。</span><span class="sxs-lookup"><span data-stu-id="94add-169">These permission masks are then put through a logical OR operation when being applied to files, e.g: If you have a `umask` value of `023` and an `fmask` value of `022` then the resulting permissions mask for files will be `023`.</span></span>

<span data-ttu-id="94add-170">これを行う方法については、「[ディストリビューションごとの起動設定を wslconf で構成する](./wsl-config.md#configure-per-distro-launch-settings-with-wslconf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94add-170">Please see the [Configure per distro launch settings with wslconf](./wsl-config.md#configure-per-distro-launch-settings-with-wslconf) article for instructions on how to do this.</span></span>