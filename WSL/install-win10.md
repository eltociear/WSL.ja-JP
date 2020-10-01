---
title: Windows Subsystem for Linux (WSL) を Windows 10 にインストールする
description: Ubuntu、Debian、SUSE、Kali、Fedora、Pengwin、Alpine などの Linux ディストリビューションを、Bash ターミナルを使用して、Windows 10 マシンにインストールする方法について説明します。
keywords: BashOnWindows, bash, wsl, windows, linux 用 windows サブシステム, windowssubsystem, ubuntu, debian, suse, windows 10, インストール, 有効にする, WSL2, バージョン 2
ms.date: 09/15/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 74a5960609e058b2f2da6160ecd04dc48f666a69
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413114"
---
# <a name="windows-subsystem-for-linux-installation-guide-for-windows-10"></a><span data-ttu-id="e71e3-104">Windows 10 用 Windows Subsystem for Linux のインストール ガイド</span><span class="sxs-lookup"><span data-stu-id="e71e3-104">Windows Subsystem for Linux Installation Guide for Windows 10</span></span>

## <a name="install-windows-subsystem-for-linux"></a><span data-ttu-id="e71e3-105">Linux 用 Windows サブシステムをインストールする</span><span class="sxs-lookup"><span data-stu-id="e71e3-105">Install Windows Subsystem for Linux</span></span>

<span data-ttu-id="e71e3-106">Linux 用 Windows サブシステムには 2 つの異なるバージョンがあり、インストール プロセス中にどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-106">Windows Subsystem for Linux has two different versions to choose between during the installation process.</span></span> <span data-ttu-id="e71e3-107">全体的なパフォーマンスは WSL 2 の方が優れているため、これを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e71e3-107">WSL 2 has better overall performance and we recommend using it.</span></span> <span data-ttu-id="e71e3-108">システムが WSL 2 をサポートしていない場合、またはクロスシステム ファイル ストレージを必要とする特定の状況がある場合は、WSL 1 を使い続けることができます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-108">If your system does not support WSL 2, or you have a specific situation that requires cross-system file storage, then you may want to stick with WSL 1.</span></span> <span data-ttu-id="e71e3-109">詳細については、「[WSL 2 と WSL 1 の比較](./compare-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-109">Read more about [Comparing WSL 2 and WSL 1](./compare-versions.md).</span></span>

## <a name="step-1---enable-the-windows-subsystem-for-linux"></a><span data-ttu-id="e71e3-110">手順 1 - Linux 用 Windows サブシステムを有効にする</span><span class="sxs-lookup"><span data-stu-id="e71e3-110">Step 1 - Enable the Windows Subsystem for Linux</span></span>

<span data-ttu-id="e71e3-111">Windows 上に Linux ディストリビューションをインストールする前に、まず "Linux 用 Windows サブシステム" オプション機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-111">You must first enable the "Windows Subsystem for Linux" optional feature before installing any Linux distributions on Windows.</span></span>

<span data-ttu-id="e71e3-112">管理者として PowerShell を開き、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-112">Open PowerShell as Administrator and run:</span></span>

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

<span data-ttu-id="e71e3-113">ここで、手順 2 に進み、WSL 2 に更新することをお勧めしますが、WSL 1 のみをインストールする場合は、マシンを再起動して、「[手順 6 - 選択した Linux ディストリビューションをインストールする](./install-win10.md#step-6---install-your-linux-distribution-of-choice)」に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-113">We recommend now moving on to step #2, updating to WSL 2, but if you wish to only install WSL 1, you can now restart your machine and move on to [Step 6 - Install your Linux distribution of choice](./install-win10.md#step-6---install-your-linux-distribution-of-choice).</span></span> <span data-ttu-id="e71e3-114">WSL 2 に更新するには、マシンの再起動を待ってから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-114">To update to WSL 2, wait to restart your machine and move on to the next step.</span></span>

## <a name="step-2---update-to-wsl-2"></a><span data-ttu-id="e71e3-115">手順 2 - WSL 2 に更新する</span><span class="sxs-lookup"><span data-stu-id="e71e3-115">Step 2 - Update to WSL 2</span></span>

<span data-ttu-id="e71e3-116">WSL 2 に更新するには、Windows 10 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-116">To update to WSL 2, you must be running Windows 10.</span></span>

### <a name="requirements"></a><span data-ttu-id="e71e3-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e71e3-117">Requirements</span></span>

- <span data-ttu-id="e71e3-118">x64 システムの場合:**バージョン 1903** 以降、**ビルド 18362** 以上。</span><span class="sxs-lookup"><span data-stu-id="e71e3-118">For x64 systems: **Version 1903** or higher, with **Build 18362** or higher.</span></span>
- <span data-ttu-id="e71e3-119">ARM64 システムの場合:**バージョン 2004** 以降、**ビルド 19041** 以上。</span><span class="sxs-lookup"><span data-stu-id="e71e3-119">For ARM64 systems: **Version 2004** or higher, with **Build 19041** or higher.</span></span>
- <span data-ttu-id="e71e3-120">18362 より前のビルドは WSL 2 をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e71e3-120">Builds lower than 18362 do not support WSL 2.</span></span> <span data-ttu-id="e71e3-121">[Windows 更新アシスタント](https://www.microsoft.com/software-download/windows10)を使用して、お使いのバージョンの Windows を更新します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-121">Use the [Windows Update Assistant](https://www.microsoft.com/software-download/windows10) to update your version of Windows.</span></span>

<span data-ttu-id="e71e3-122">バージョンとビルド番号を確認するには、**Windows ロゴ キー + R キー**を押して、「**winver**」と入力し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-122">To check your version and build number, select **Windows logo key + R**, type **winver**, select **OK**.</span></span> <span data-ttu-id="e71e3-123">(または、Windows コマンド プロンプトで `ver` コマンドを入力します)。</span><span class="sxs-lookup"><span data-stu-id="e71e3-123">(Or enter the `ver` command in Windows Command Prompt).</span></span> <span data-ttu-id="e71e3-124">[設定] メニューで、[最新の Windows バージョンに更新](ms-settings:windowsupdate)します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-124">[Update to the latest Windows version](ms-settings:windowsupdate) in the Settings menu.</span></span>

> [!NOTE]
> <span data-ttu-id="e71e3-125">Windows 10 バージョン 1903 または 1909 を実行している場合は、Windows メニューから [設定] を開き、[更新とセキュリティ] に移動して、[更新プログラムのチェック] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-125">If you are running Windows 10 version 1903 or 1909, open "Settings" from your Windows menu, navigate to "Update & Security" and select "Check for Updates".</span></span> <span data-ttu-id="e71e3-126">ビルド番号は、18362.1049+ または 18363.1049+ で、マイナー ビルド番号は .1049 より大きい必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-126">Your Build number must be 18362.1049+ or 18363.1049+, with the minor build # over .1049.</span></span> <span data-ttu-id="e71e3-127">詳細については、「[Windows 10 バージョン 1903 および 1909 で WSL 2 のサポート開始](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-127">Read more: [WSL 2 Support is coming to Windows 10 Versions 1903 and 1909](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/).</span></span> <span data-ttu-id="e71e3-128">また、[トラブルシューティング手順](./troubleshooting.md#im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-128">See the [troubleshooting instructions](./troubleshooting.md#im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2).</span></span>

## <a name="step-3---enable-virtual-machine-feature"></a><span data-ttu-id="e71e3-129">手順 3: 仮想マシンの機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="e71e3-129">Step 3 - Enable Virtual Machine feature</span></span>

<span data-ttu-id="e71e3-130">WSL 2 をインストールする前に、"**仮想マシン プラットフォーム**" オプション機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-130">Before installing WSL 2, you must enable the **Virtual Machine Platform** optional feature.</span></span>

<span data-ttu-id="e71e3-131">管理者として PowerShell を開き、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-131">Open PowerShell as Administrator and run:</span></span>

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

<span data-ttu-id="e71e3-132">お使いのマシンを**再起動**して WSL のインストールを完了し、WSL 2 に更新します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-132">**Restart** your machine to complete the WSL install and update to WSL 2.</span></span>

## <a name="step-4---download-the-linux-kernel-update-package"></a><span data-ttu-id="e71e3-133">手順 4 - Linux カーネル更新プログラム パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e71e3-133">Step 4 - Download the Linux kernel update package</span></span>

1. <span data-ttu-id="e71e3-134">最新のパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e71e3-134">Download the latest package:</span></span>
    - [<span data-ttu-id="e71e3-135">x64 マシン用 WSL2 Linux カーネル更新プログラム パッケージ</span><span class="sxs-lookup"><span data-stu-id="e71e3-135">WSL2 Linux kernel update package for x64 machines</span></span>](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

    > [!NOTE]
    > <span data-ttu-id="e71e3-136">ARM64 マシンを使用している場合は、代わりに [ARM64 パッケージ](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-136">If you're using an ARM64 machine, please download the [ARM64 package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi) instead.</span></span> <span data-ttu-id="e71e3-137">使用しているマシンの種類がわからない場合は、コマンド プロンプトまたは PowerShell を開き、「`systeminfo | find "System Type"`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-137">If you're not sure what kind of machine you have, open Command Prompt or PowerShell and enter: `systeminfo | find "System Type"`.</span></span>

2. <span data-ttu-id="e71e3-138">前の手順でダウンロードした更新プログラム パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-138">Run the update package downloaded in the previous step.</span></span> <span data-ttu-id="e71e3-139">(ダブルクリックして実行します。管理者特権のアクセス許可を求めるメッセージが表示されます。[はい] を選択して、このインストールを承認します。)</span><span class="sxs-lookup"><span data-stu-id="e71e3-139">(Double-click to run - you will be prompted for elevated permissions, select ‘yes’ to approve this installation.)</span></span>

<span data-ttu-id="e71e3-140">インストールが完了したら、次の手順に進み、新しい Linux ディストリビューションをインストールする際の既定のバージョンとして WSL 2 を設定します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-140">Once the installation is complete, move on to the next step - setting WSL 2 as your default version when installing new Linux distributions.</span></span> <span data-ttu-id="e71e3-141">(新しい Linux インストールを WSL 1 に設定する場合は、この手順をスキップしてください)。</span><span class="sxs-lookup"><span data-stu-id="e71e3-141">(Skip this step if you want your new Linux installs to be set to WSL 1).</span></span>

> [!NOTE]
> <span data-ttu-id="e71e3-142">詳細については、[Windows コマンドラインのブログ](https://aka.ms/cliblog)にある[WSL2 Linux カーネルの更新プログラムに対する変更](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-142">For more information, read the article [changes to updating the WSL2 Linux kernel](https://devblogs.microsoft.com/commandline/wsl2-will-be-generally-available-in-windows-10-version-2004), available on the [Windows Command Line Blog](https://aka.ms/cliblog).</span></span>

## <a name="step-5---set-wsl-2-as-your-default-version"></a><span data-ttu-id="e71e3-143">手順 5 - WSL 2 を既定のバージョンとして設定する</span><span class="sxs-lookup"><span data-stu-id="e71e3-143">Step 5 - Set WSL 2 as your default version</span></span>

<span data-ttu-id="e71e3-144">管理者として PowerShell を開いて次のコマンドを実行し、新しい Linux ディストリビューションをインストールする際の既定のバージョンとして WSL 2 を設定します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-144">Open PowerShell as Administrator and run this command to set WSL 2 as the default version when installing a new Linux distribution:</span></span>

```powershell
wsl --set-default-version 2
```

> [!NOTE]
> <span data-ttu-id="e71e3-145">対象のディストリビューションのサイズによっては、WSL 1 から WSL 2 への更新が完了するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-145">The update from WSL 1 to WSL 2 may take several minutes to complete depending on the size of your targeted distribution.</span></span> <span data-ttu-id="e71e3-146">Windows 10 Anniversary Update または Creators Update から WSL 1 の古い (レガシ) インストールを実行している場合は、更新エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-146">If you are running an older (legacy) installation of WSL 1 from Windows 10 Anniversary Update or Creators Update, you may encounter an update error.</span></span> <span data-ttu-id="e71e3-147">次の手順に従って、[レガシ ディストリビューションをアンインストールして削除](./install-legacy.md#uninstallingremoving-the-legacy-distro)します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-147">Follow these instructions to [uninstall and remove any legacy distributions](./install-legacy.md#uninstallingremoving-the-legacy-distro).</span></span>
>
> <span data-ttu-id="e71e3-148">`wsl --set-default-version` の結果が無効なコマンドである場合は、「`wsl --help`」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-148">If `wsl --set-default-version` results as an invalid command, enter `wsl --help`.</span></span> <span data-ttu-id="e71e3-149">`--set-default-version` が表示されない場合は、お使いの OS によってサポートされていないことを意味しているため、バージョン 1903、ビルド 18362 以上に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-149">If the `--set-default-version` is not listed, it means that your OS doesn't support it and you need to update to version 1903, Build 18362 or higher.</span></span>
>
> <span data-ttu-id="e71e3-150">コマンドの実行後に、次のメッセージが表示される場合: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`。</span><span class="sxs-lookup"><span data-stu-id="e71e3-150">If you see this message after running the command: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`.</span></span> <span data-ttu-id="e71e3-151">さらに MSI Linux カーネル更新パッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-151">You still need to install the MSI Linux kernel update package.</span></span>

## <a name="step-6---install-your-linux-distribution-of-choice"></a><span data-ttu-id="e71e3-152">手順 6 - 選択した Linux ディストリビューションをインストールする</span><span class="sxs-lookup"><span data-stu-id="e71e3-152">Step 6 - Install your Linux distribution of choice</span></span>

1. <span data-ttu-id="e71e3-153">[Microsoft Store](https://aka.ms/wslstore) を開き、希望する Linux ディストリビューションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-153">Open the [Microsoft Store](https://aka.ms/wslstore) and select your favorite Linux distribution.</span></span>

    ![Microsoft Store での Linux ディストリビューションの表示](media/store.png)

    <span data-ttu-id="e71e3-155">次のリンクを使用すると、各ディストリビューションの Microsoft Store ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-155">The following links will open the Microsoft store page for each distribution:</span></span>

    - [<span data-ttu-id="e71e3-156">Ubuntu 16.04 LTS</span><span class="sxs-lookup"><span data-stu-id="e71e3-156">Ubuntu 16.04 LTS</span></span>](https://www.microsoft.com/store/apps/9pjn388hp8c9)
    - [<span data-ttu-id="e71e3-157">Ubuntu 18.04 LTS</span><span class="sxs-lookup"><span data-stu-id="e71e3-157">Ubuntu 18.04 LTS</span></span>](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
    - [<span data-ttu-id="e71e3-158">Ubuntu 20.04 LTS</span><span class="sxs-lookup"><span data-stu-id="e71e3-158">Ubuntu 20.04 LTS</span></span>](https://www.microsoft.com/store/apps/9n6svws3rx71)
    - [<span data-ttu-id="e71e3-159">openSUSE Leap 15.1</span><span class="sxs-lookup"><span data-stu-id="e71e3-159">openSUSE Leap 15.1</span></span>](https://www.microsoft.com/store/apps/9NJFZK00FGKV)
    - [<span data-ttu-id="e71e3-160">SUSE Linux Enterprise Server 12 SP5</span><span class="sxs-lookup"><span data-stu-id="e71e3-160">SUSE Linux Enterprise Server 12 SP5</span></span>](https://www.microsoft.com/store/apps/9MZ3D1TRP8T1)
    - [<span data-ttu-id="e71e3-161">SUSE Linux Enterprise Server 15 SP1</span><span class="sxs-lookup"><span data-stu-id="e71e3-161">SUSE Linux Enterprise Server 15 SP1</span></span>](https://www.microsoft.com/store/apps/9PN498VPMF3Z)
    - [<span data-ttu-id="e71e3-162">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="e71e3-162">Kali Linux</span></span>](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [<span data-ttu-id="e71e3-163">Debian GNU/Linux</span><span class="sxs-lookup"><span data-stu-id="e71e3-163">Debian GNU/Linux</span></span>](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
    - [<span data-ttu-id="e71e3-164">WSL のための Fedora リミックス</span><span class="sxs-lookup"><span data-stu-id="e71e3-164">Fedora Remix for WSL</span></span>](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
    - [<span data-ttu-id="e71e3-165">Pengwin</span><span class="sxs-lookup"><span data-stu-id="e71e3-165">Pengwin</span></span>](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [<span data-ttu-id="e71e3-166">Pengwin Enterprise</span><span class="sxs-lookup"><span data-stu-id="e71e3-166">Pengwin Enterprise</span></span>](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
    - [<span data-ttu-id="e71e3-167">Alpine WSL</span><span class="sxs-lookup"><span data-stu-id="e71e3-167">Alpine WSL</span></span>](https://www.microsoft.com/store/apps/9p804crf0395)

2. <span data-ttu-id="e71e3-168">ディストリビューションのページで、[入手] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-168">From the distribution's page, select "Get".</span></span>

    ![Microsoft Store での Linux ディストリビューション](media/UbuntuStore.png)

## <a name="step-7---set-up-a-new-distribution"></a><span data-ttu-id="e71e3-170">手順 7 - 新しいディストリビューションを設定する</span><span class="sxs-lookup"><span data-stu-id="e71e3-170">Step 7 - Set up a new distribution</span></span>

<span data-ttu-id="e71e3-171">新しくインストールした Linux ディストリビューションを初めて起動すると、コンソール ウィンドウが開き、ファイルが圧縮解除されて PC に格納されるまで 1、2 分待つように求められます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-171">The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for a minute or two for files to de-compress and be stored on your PC.</span></span> <span data-ttu-id="e71e3-172">今後のすべての起動には、1 秒もかかりません。</span><span class="sxs-lookup"><span data-stu-id="e71e3-172">All future launches should take less than a second.</span></span>

<span data-ttu-id="e71e3-173">次に、[新しい Linux ディストリビューションのユーザー アカウントとパスワードを作成する](./user-support.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-173">You will then need to [create a user account and password for your new Linux distribution](./user-support.md).</span></span>

![Windows コンソールでの Ubuntu の展開](media/UbuntuInstall.png)

<span data-ttu-id="e71e3-175">**お疲れさまでした。これで、Windows オペレーティング システムと完全に統合された Linux ディストリビューションのインストールと設定が正常に完了しました。**</span><span class="sxs-lookup"><span data-stu-id="e71e3-175">**CONGRATULATIONS! You've successfully installed and set up a Linux distribution that is completely integrated with your Windows operating system!**</span></span>

## <a name="install-windows-terminal-optional"></a><span data-ttu-id="e71e3-176">Windows ターミナルをインストールする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e71e3-176">Install Windows Terminal (optional)</span></span>

<span data-ttu-id="e71e3-177">Windows ターミナルでは、複数のタブ (複数の Linux コマンド ライン、Windows コマンド プロンプト、PowerShell、Azure CLI などをすばやく切り替える) が有効になり、カスタム キー バインド (タブを開くまたは閉じる、コピーと貼り付けを行うなどのためのショートカット キー) を作成でき、検索機能、カスタム テーマ (配色、フォント スタイルとサイズ、背景画像、ぼかし、透明度) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-177">Windows Terminal enables multiple tabs (quickly switch between multiple Linux command lines, Windows Command Prompt, PowerShell, Azure CLI, etc), create custom key bindings (shortcut keys for opening or closing tabs, copy+paste, etc.), use the search feature, and custom themes (color schemes, font styles and sizes, background image/blur/transparency).</span></span> [<span data-ttu-id="e71e3-178">詳細情報。</span><span class="sxs-lookup"><span data-stu-id="e71e3-178">Learn more.</span></span>](/windows/terminal)

<span data-ttu-id="e71e3-179">[Windows ターミナルをインストール](/windows/terminal/get-started)します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-179">[Install Windows Terminal](/windows/terminal/get-started).</span></span>

  ![Windows ターミナル](media/terminal.png)

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a><span data-ttu-id="e71e3-181">ディストリビューションのバージョンを WSL 1 または WSL 2 に設定する</span><span class="sxs-lookup"><span data-stu-id="e71e3-181">Set your distribution version to WSL 1 or WSL 2</span></span>

<span data-ttu-id="e71e3-182">インストールされている各 Linux ディストリビューションに割り当てられている WSL バージョンを確認するには、PowerShell コマンド ラインを開き、次のコマンドを入力します ([Windows ビルド 18362 以上](ms-settings:windowsupdate)でのみ使用可能): `wsl -l -v`</span><span class="sxs-lookup"><span data-stu-id="e71e3-182">You can check the WSL version assigned to each of the Linux distributions you have installed by opening the PowerShell command line and entering the command (only available in [Windows Build 18362 or higher](ms-settings:windowsupdate)): `wsl -l -v`</span></span>

```powershell
wsl --list --verbose
```

<span data-ttu-id="e71e3-183">ディストリビューションで使用される WSL のバージョンを設定するには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-183">To set a distribution to be backed by either version of WSL please run:</span></span>

```powershell
wsl --set-version <distribution name> <versionNumber>
```

<span data-ttu-id="e71e3-184">`<distribution name>` は、お使いのディストリビューションの実際の名前に必ず置き換えてください。`<versionNumber>` は、数字の "1" または "2" に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-184">Make sure to replace `<distribution name>` with the actual name of your distribution and `<versionNumber>` with the number '1' or '2'.</span></span> <span data-ttu-id="e71e3-185">上記と同じコマンドで "2" を "1" に置き換えて実行することにより、いつでも WSL 1 に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-185">You can change back to WSL 1 at anytime by running the same command as above but replacing the '2' with a '1'.</span></span>

<span data-ttu-id="e71e3-186">また、WSL 2 を既定のアーキテクチャにする場合は、次のコマンドを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-186">Additionally, if you want to make WSL 2 your default architecture you can do so with this command:</span></span>

```powershell
wsl --set-default-version 2
```

<span data-ttu-id="e71e3-187">これにより、インストールされるすべての新しいディストリビューションのバージョンが WSL 2 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-187">This will set the version of any new distribution installed to WSL 2.</span></span>

## <a name="troubleshooting-installation"></a><span data-ttu-id="e71e3-188">インストールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e71e3-188">Troubleshooting installation</span></span>

<span data-ttu-id="e71e3-189">関連エラーと推奨される修正を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-189">Below are related errors and suggested fixes.</span></span> <span data-ttu-id="e71e3-190">その他の一般的なエラーとその解決策については、[WSL のトラブルシューティングのページ](troubleshooting.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-190">Refer to the [WSL troubleshooting page](troubleshooting.md) for other common errors and their solutions.</span></span>

- <span data-ttu-id="e71e3-191">**エラー 0x80070003 が発生してインストールに失敗しました**</span><span class="sxs-lookup"><span data-stu-id="e71e3-191">**Installation failed with error 0x80070003**</span></span>
  - <span data-ttu-id="e71e3-192">Windows Subsystem for Linux はシステム ドライブ (通常、これは `C:` ドライブ) でのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-192">The Windows Subsystem for Linux only runs on your system drive (usually this is your `C:` drive).</span></span> <span data-ttu-id="e71e3-193">ディストリビューションがシステム ドライブに格納されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-193">Make sure that distributions are stored on your system drive:</span></span>  
  - <span data-ttu-id="e71e3-194">**[設定]** -> **[ストレージ]** -> **[その他のストレージ設定: 新しいコンテンツの保存先を変更する]** 
    を開きます。![C: ドライブにアプリをインストールするためのシステム設定の画像](media/AppStorage.png)</span><span class="sxs-lookup"><span data-stu-id="e71e3-194">Open **Settings** -> **Storage** -> **More Storage Settings: Change where new content is saved**
![Picture of system settings to install apps on C: drive](media/AppStorage.png)</span></span>

- <span data-ttu-id="e71e3-195">**WslRegisterDistribution failed with error 0x8007019e (エラー0x8007019e で WslRegisterDistribution が失敗しました)**</span><span class="sxs-lookup"><span data-stu-id="e71e3-195">**WslRegisterDistribution failed with error 0x8007019e**</span></span>
  - <span data-ttu-id="e71e3-196">Windows Subsystem for Linux オプション コンポーネントが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e71e3-196">The Windows Subsystem for Linux optional component is not enabled:</span></span>
  - <span data-ttu-id="e71e3-197">**[コントロール パネル]**  ->  **[プログラムと機能]**  ->  **[Windows の機能の有効化または無効化]** を開いて、 **[Linux 用 Windows サブシステム]** をチェックするか、またはこの記事の冒頭に記載した PowerShell コマンドレットを使用してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-197">Open **Control Panel** -> **Programs and Features** -> **Turn Windows Feature on or off** -> Check **Windows Subsystem for Linux** or using the PowerShell cmdlet mentioned at the beginning of this article.</span></span>

- <span data-ttu-id="e71e3-198">**インストールがエラー 0x80070003 またはエラー 0x80370102 で失敗した**</span><span class="sxs-lookup"><span data-stu-id="e71e3-198">**Installation failed with error 0x80070003 or error 0x80370102**</span></span>
  - <span data-ttu-id="e71e3-199">コンピューターの BIOS 内部で仮想化が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-199">Please make sure that virtualization is enabled inside of your computer's BIOS.</span></span> <span data-ttu-id="e71e3-200">これを行う方法の手順は、コンピューターによって異なりますが、最も可能性が高いのは CPU 関連のオプションの下です。</span><span class="sxs-lookup"><span data-stu-id="e71e3-200">The instructions on how to do this will vary from computer to computer, and will most likely be under CPU related options.</span></span>

- <span data-ttu-id="e71e3-201">**アップグレードしようとしたときに次のエラーが発生する: `Invalid command line option: wsl --set-version Ubuntu 2`**</span><span class="sxs-lookup"><span data-stu-id="e71e3-201">**Error when trying to upgrade: `Invalid command line option: wsl --set-version Ubuntu 2`**</span></span>
  - <span data-ttu-id="e71e3-202">Linux 用 Windows サブシステムが有効になっていること、および Windows ビルド バージョン 18362 以上を使用していることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-202">Enure that you have the Windows Subsystem for Linux enabled, and that you're using Windows Build version 18362 or higher.</span></span> <span data-ttu-id="e71e3-203">WSL を有効にするには、PowerShell プロンプトで管理者特権を使用してこのコマンドを実行します: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`。</span><span class="sxs-lookup"><span data-stu-id="e71e3-203">To enable WSL run this command in a PowerShell prompt with admin privileges: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`.</span></span>

- <span data-ttu-id="e71e3-204">**仮想ディスク システムの制限があるため、要求された操作を完了できませんでした。仮想ハード ディスク ファイルは、圧縮と暗号化が解除されている必要があります。また、スパースにすることはできません。**</span><span class="sxs-lookup"><span data-stu-id="e71e3-204">**The requested operation could not be completed due to a virtual disk system limitation. Virtual hard disk files must be uncompressed and unencrypted and must not be sparse.**</span></span>
  - <span data-ttu-id="e71e3-205">[内容を圧縮] ([内容を暗号化] のチェックボックスがオンになっている場合はこれも) を選択解除するため、Linux ディストリビューションのプロファイル フォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-205">Deselect “Compress contents” (as well as “Encrypt contents” if that’s checked) by opening the profile folder for your Linux distribution.</span></span> <span data-ttu-id="e71e3-206">これは、Windows ファイル システムのフォルダーにあります (例: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`)。</span><span class="sxs-lookup"><span data-stu-id="e71e3-206">It should be located in a folder on your Windows file system, something like: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`</span></span>
  - <span data-ttu-id="e71e3-207">この Linux ディストリビューション プロファイル内に、LocalState フォルダーが存在します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-207">In this Linux distro profile, there should be a LocalState folder.</span></span> <span data-ttu-id="e71e3-208">このフォルダーを右クリックして、オプションのメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-208">Right-click this folder to display a menu of options.</span></span> <span data-ttu-id="e71e3-209">[プロパティ] > [詳細設定] の順に選択し、[内容を圧縮してディスク領域を節約する] および [内容を暗号化してデータをセキュリティで保護する] チェックボックスを確実にオフにします。</span><span class="sxs-lookup"><span data-stu-id="e71e3-209">Select Properties > Advanced and then ensure that the “Compress contents to save disk space” and “Encrypt contents to secure data” checkboxes are unselected (not checked).</span></span> <span data-ttu-id="e71e3-210">これを現在のフォルダーのみに適用するか、すべてのサブフォルダーとファイルに適用するかを確認するメッセージが表示された場合は、圧縮フラグをオフにしようとしているだけなので、[このフォルダーのみ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-210">If you are asked whether to apply this to just to the current folder or to all subfolders and files, select “just this folder” because you are only clearing the compress flag.</span></span> <span data-ttu-id="e71e3-211">この操作を実行すると、`wsl --set-version` コマンドが機能するようになります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-211">After this, the `wsl --set-version` command should work.</span></span>

![WSL ディストリビューションのプロパティ設定のスクリーンショット](media/troubleshooting-virtualdisk-compress.png)

> [!NOTE]
> <span data-ttu-id="e71e3-213">この例では、Ubuntu 18.04 ディストリビューションの LocalState フォルダーの場所は次のとおりです。C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc</span><span class="sxs-lookup"><span data-stu-id="e71e3-213">In my case, the LocalState folder for my Ubuntu 18.04 distribution was located at C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc</span></span>
>
> <span data-ttu-id="e71e3-214">この問題の最新情報が追跡されている [WSL ドキュメント GitHub スレッド #4103](https://github.com/microsoft/WSL/issues/4103) をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-214">Check [WSL Docs GitHub thread #4103](https://github.com/microsoft/WSL/issues/4103) where this issue is being tracked for updated information.</span></span>

- <span data-ttu-id="e71e3-215">**"wsl" という用語が、コマンドレット、関数、スクリプト ファイル、または操作可能なプログラムの名前として認識されません。**</span><span class="sxs-lookup"><span data-stu-id="e71e3-215">**The term 'wsl' is not recognized as the name of a cmdlet, function, script file, or operable program.**</span></span>
  - <span data-ttu-id="e71e3-216">[Linux 用 Windows サブシステムのオプション コンポーネントがインストールされている](./install-win10.md#step-3---enable-virtual-machine-feature)ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-216">Ensure that the [Windows Subsystem for Linux Optional Component is installed](./install-win10.md#step-3---enable-virtual-machine-feature).</span></span> <span data-ttu-id="e71e3-217">また、ARM64 デバイスを使用し、PowerShell からこのコマンドを実行している場合も、このエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-217">Additionally, if you are using an ARM64 device and running this command from PowerShell, you will receive this error.</span></span> <span data-ttu-id="e71e3-218">代わりに、`wsl.exe`PowerShell Core[ またはコマンド プロンプトから ](/powershell/scripting/install/installing-powershell-core-on-windows) を実行します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-218">Instead run `wsl.exe` from [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows), or Command Prompt.</span></span>

- <span data-ttu-id="e71e3-219">**Error:この更新プログラムは、Linux 用 Windows サブシステムを搭載したマシンにのみ適用されます。**</span><span class="sxs-lookup"><span data-stu-id="e71e3-219">**Error: This update only applies to machines with the Windows Subsystem for Linux.**</span></span>
  - <span data-ttu-id="e71e3-220">Linux カーネル更新プログラム MSI パッケージをインストールするには、WSL が必要であり、最初に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-220">To install the Linux kernel update MSI package, WSL is required and should be enabled first.</span></span> <span data-ttu-id="e71e3-221">失敗した場合は、"`This update only applies to machines with the Windows Subsystem for Linux`" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-221">If it fails, it you will see the message: `This update only applies to machines with the Windows Subsystem for Linux`.</span></span>
  - <span data-ttu-id="e71e3-222">このメッセージが表示される理由として、次の 3 つが考えられます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-222">There are three possible reason you see this message:</span></span>

  1. <span data-ttu-id="e71e3-223">WSL 2 をサポートしていない古いバージョンの Windows を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e71e3-223">You are still in old version of Windows which doesn't support WSL 2.</span></span> <span data-ttu-id="e71e3-224">バージョン要件と更新プログラムへのリンクについては、手順 2 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-224">See step #2 for version requirements and links to update.</span></span>

  2. <span data-ttu-id="e71e3-225">WSL が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="e71e3-225">WSL is not enabled.</span></span> <span data-ttu-id="e71e3-226">手順 1 に戻り、お使いのマシンでオプションの WSL 機能が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-226">You will need to return to step #1 and ensure that the optional WSL feature is enabled on your machine.</span></span>

  3. <span data-ttu-id="e71e3-227">WSL を有効にした後、再起動しないと、効力が発しません。マシンを再起動してから、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="e71e3-227">After you enabled WSL, a reboot is required for it to take effect, reboot your machine and try again.</span></span>

- <span data-ttu-id="e71e3-228">**Error:WSL 2 のカーネル コンポーネントを更新する必要があります。詳細については、 https://aka.ms/wsl2kernel をアクセスしてください。**</span><span class="sxs-lookup"><span data-stu-id="e71e3-228">**Error: WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel .**</span></span>
  - <span data-ttu-id="e71e3-229">Linux カーネル パッケージが %SystemRoot%\system32\lxss\tools フォルダーにない場合、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e71e3-229">If the Linux kernel package is missing in the %SystemRoot%\system32\lxss\tools folder, you will encounter this error.</span></span> <span data-ttu-id="e71e3-230">このインストール手順の手順 4 に従って Linux カーネル更新プログラム MSI パッケージをインストールすることにより、このエラーを解決できます。</span><span class="sxs-lookup"><span data-stu-id="e71e3-230">Resolve it by installing the Linux kernel update MSI package in step #4 of these installation instructions.</span></span> <span data-ttu-id="e71e3-231">[[プログラムの追加と削除]](ms-settings:appsfeatures-app) から MSI をアンインストールして、インストールし直すことが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e71e3-231">You may need to uninstall the MSI from ['Add or Remove Programs'](ms-settings:appsfeatures-app), and install it again.</span></span>