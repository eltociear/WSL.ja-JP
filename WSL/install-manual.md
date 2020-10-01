---
title: Linux 用 Windows サブシステム (WSL) ディストリビューションを手動でダウンロードする
description: Linux 用 Windows サブシステム ディストリビューションを手動でダウンロードする方法について説明します。
keywords: wsl, linux 用 windows subsystem, 手動インストール, 手動でインストール, microsoft ストア, windows 10, curl, Add-AppxPackage, 長期的なサービス, LTSC
ms.date: 09/15/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1894f0bfcb9ede7b05870c99912f30f6d0b7286e
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413252"
---
# <a name="manually-download-windows-subsystem-for-linux-distro-packages"></a><span data-ttu-id="e7f91-104">Linux 用 Windows サブシステム ディストリビューション パッケージを手動でダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e7f91-104">Manually download Windows Subsystem for Linux distro packages</span></span>

<span data-ttu-id="e7f91-105">Microsoft Store 経由で WSL Linux ディストリビューションをインストールすることができない (または必要ない) シナリオがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e7f91-105">There are several scenarios in which you may not be able (or want) to, install WSL Linux distros via the Microsoft Store.</span></span> <span data-ttu-id="e7f91-106">具体的には、Microsoft Store をサポートしていない Windows サーバーまたは長期的なサービス (LTSC) デスクトップ OS SKU を実行している場合や、企業ネットワーク ポリシーや管理者が環境で Microsoft Store の使用を許可していない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7f91-106">Specifically, you may be running a Windows Server or Long-Term Servicing (LTSC) desktop OS SKU that doesn't support Microsoft Store, or your corporate network policies and/or admins to not permit Microsoft Store usage in your environment.</span></span>

<span data-ttu-id="e7f91-107">このような場合、WSL 自体は使用できても、ストアにアクセスできない場合に、WSL に Linux ディストリビューションをダウンロードしてインストールするにはどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e7f91-107">In these cases, while WSL itself is available, how do you download and install Linux distros in WSL if you can't access the store?</span></span>

> <span data-ttu-id="e7f91-108">注: **Cmd、PowerShell、Linux および WSL ディストリビューションなどのコマンドライン シェル環境は、Windows 10 S モード上の実行が許可されていません**。</span><span class="sxs-lookup"><span data-stu-id="e7f91-108">Note: **Command-line shell environments including Cmd, PowerShell, and Linux/WSL distros are not permitted to run on Windows 10 S Mode**.</span></span> <span data-ttu-id="e7f91-109">この制限は、S モードで提供される整合性と安全性の目標を確保するために存在します。詳細については、[この投稿](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f91-109">This restriction exists in order to ensure the integrity and safety goals that S Mode delivers: Read [this post](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/) for more information.</span></span>

## <a name="downloading-distros"></a><span data-ttu-id="e7f91-110">ディストリビューションのダウンロード</span><span class="sxs-lookup"><span data-stu-id="e7f91-110">Downloading distros</span></span>

<span data-ttu-id="e7f91-111">Microsoft Store アプリを使用できない場合は、以下のリンクをクリックして Linux ディストリビューションをダウンロードして手動でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e7f91-111">If the Microsoft Store app is not available, you can download and manually install Linux distros by clicking these links:</span></span>
* [<span data-ttu-id="e7f91-112">Ubuntu 20.04</span><span class="sxs-lookup"><span data-stu-id="e7f91-112">Ubuntu 20.04</span></span>](https://aka.ms/wslubuntu2004)
* [<span data-ttu-id="e7f91-113">Ubuntu 20.04 ARM</span><span class="sxs-lookup"><span data-stu-id="e7f91-113">Ubuntu 20.04 ARM</span></span>](https://aka.ms/wslubuntu2004arm)
* [<span data-ttu-id="e7f91-114">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e7f91-114">Ubuntu 18.04</span></span>](https://aka.ms/wsl-ubuntu-1804)
* [<span data-ttu-id="e7f91-115">Ubuntu 18.04 ARM</span><span class="sxs-lookup"><span data-stu-id="e7f91-115">Ubuntu 18.04 ARM</span></span>](https://aka.ms/wsl-ubuntu-1804-arm)
* [<span data-ttu-id="e7f91-116">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="e7f91-116">Ubuntu 16.04</span></span>](https://aka.ms/wsl-ubuntu-1604)
* [<span data-ttu-id="e7f91-117">Debian GNU/Linux</span><span class="sxs-lookup"><span data-stu-id="e7f91-117">Debian GNU/Linux</span></span>](https://aka.ms/wsl-debian-gnulinux)
* [<span data-ttu-id="e7f91-118">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="e7f91-118">Kali Linux</span></span>](https://aka.ms/wsl-kali-linux-new)
* [<span data-ttu-id="e7f91-119">OpenSUSE Leap 42</span><span class="sxs-lookup"><span data-stu-id="e7f91-119">OpenSUSE Leap 42</span></span>](https://aka.ms/wsl-opensuse-42)
* [<span data-ttu-id="e7f91-120">SUSE Linux Enterprise Server 12</span><span class="sxs-lookup"><span data-stu-id="e7f91-120">SUSE Linux Enterprise Server 12</span></span>](https://aka.ms/wsl-sles-12)
* [<span data-ttu-id="e7f91-121">WSL のための Fedora リミックス</span><span class="sxs-lookup"><span data-stu-id="e7f91-121">Fedora Remix for WSL</span></span>](https://github.com/WhitewaterFoundry/WSLFedoraRemix/releases/)

<span data-ttu-id="e7f91-122">これにより、選択したフォルダーに `<distro>.appx` パッケージがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="e7f91-122">This will cause the `<distro>.appx` packages to download to a folder of your choosing.</span></span> <span data-ttu-id="e7f91-123">[インストール手順](#installing-your-distro)に従って、ダウンロードしたディストリビューションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e7f91-123">Follow the [installation instructions](#installing-your-distro) to install your downloaded distro(s).</span></span>

## <a name="downloading-distros-via-the-command-line"></a><span data-ttu-id="e7f91-124">コマンド ラインからのディストリビューションのダウンロード</span><span class="sxs-lookup"><span data-stu-id="e7f91-124">Downloading distros via the command line</span></span>
<span data-ttu-id="e7f91-125">必要に応じて、コマンド ラインから好みのディストリビューションをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7f91-125">If you prefer, you can also download your preferred distro(s) via the command line:</span></span>

 ### <a name="download-using-powershell"></a><span data-ttu-id="e7f91-126">PowerShell を使用してダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e7f91-126">Download using PowerShell</span></span>
 <span data-ttu-id="e7f91-127">PowerShell を使用してディストリビューションをダウンロードするには、[Invoke-WebRequest](/powershell/module/microsoft.powershell.utility/invoke-webrequest) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e7f91-127">To download distros using PowerShell, use the [Invoke-WebRequest](/powershell/module/microsoft.powershell.utility/invoke-webrequest) cmdlet.</span></span> <span data-ttu-id="e7f91-128">Ubuntu 16.04 をダウンロードする手順の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7f91-128">Here's a sample instruction to download Ubuntu 16.04.</span></span>

```powershell
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1604 -OutFile Ubuntu.appx -UseBasicParsing
```

> [!TIP]
> <span data-ttu-id="e7f91-129">ダウンロードに時間がかかる場合は、`$ProgressPreference = 'SilentlyContinue'` を設定して進行状況バーをオフにします</span><span class="sxs-lookup"><span data-stu-id="e7f91-129">If the download is taking a long time, turn off the progress bar by setting `$ProgressPreference = 'SilentlyContinue'`</span></span>

### <a name="download-using-curl"></a><span data-ttu-id="e7f91-130">curl を使用してダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e7f91-130">Download using curl</span></span>
<span data-ttu-id="e7f91-131">Windows 10 Spring 2018 Update (またはそれ以降) には、コマンド ラインから Web 要求 (HTTP GET、POST、PUT などのコマンド) を呼び出すことができる一般的な [curl コマンドライン ユーティリティ](https://curl.haxx.se/)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7f91-131">Windows 10 Spring 2018 Update (or later) includes the popular [curl command-line utility](https://curl.haxx.se/) with which you can invoke web requests (i.e. HTTP GET, POST, PUT, etc. commands) from the command line.</span></span> <span data-ttu-id="e7f91-132">`curl.exe` を使用して、上記のディストリビューションをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e7f91-132">You can use `curl.exe` to download the above distros:</span></span>

```console
curl.exe -L -o ubuntu-1604.appx https://aka.ms/wsl-ubuntu-1604
```

<span data-ttu-id="e7f91-133">上記の例では、(`curl` だけでなく) `curl.exe` が実行され、PowerShell では、[Invoke-WebRequest](/powershell/module/microsoft.powershell.utility/invoke-webrequest) の PowerShell curl エイリアスではなく、実際の curl 実行可能ファイルが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e7f91-133">In the above example, `curl.exe` is executed (not just `curl`) to ensure that, in PowerShell, the real curl executable is invoked, not the PowerShell curl alias for [Invoke-WebRequest](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span></span>

> <span data-ttu-id="e7f91-134">注: Cmd シェルや `.bat` / `.cmd` スクリプトを使用してダウンロード手順を呼び出したりスクリプトで実行したりする必要がある場合は、`curl` を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7f91-134">Note: Using `curl` might be preferable if you have to invoke/script download steps using Cmd shell and/or `.bat` / `.cmd` scripts.</span></span>

## <a name="installing-your-distro"></a><span data-ttu-id="e7f91-135">ディストリビューションのインストール</span><span class="sxs-lookup"><span data-stu-id="e7f91-135">Installing your distro</span></span>
<span data-ttu-id="e7f91-136">Windows 10 を使用している場合、PowerShell を使用してディストリビューションをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e7f91-136">If you're using Windows 10 you can install your distro with PowerShell.</span></span> <span data-ttu-id="e7f91-137">上記の手順でダウンロードしたディストリビューションを含むフォルダーに移動して、そのディレクトリで次のコマンドを実行します。この `app_name` は、ディストリビューションの .appx ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="e7f91-137">Simply navigate to folder containing the distro downloaded from above, and in that directory run the following command where `app_name` is the name of your distro .appx file.</span></span>  
```Powershell
Add-AppxPackage .\app_name.appx
```

<span data-ttu-id="e7f91-138">Windows サーバーを使用している場合、インストール手順については、[Windows Server](install-on-server.md) のドキュメント ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f91-138">If you are using Windows server you can find the install instructions on the [Windows Server](install-on-server.md) documentation page.</span></span>

<span data-ttu-id="e7f91-139">ディストリビューションがインストールされたら、通常の手順に従って [WSL 2 に更新](./install-win10.md#step-2---update-to-wsl-2)するか、[新しいユーザー アカウントとパスワードを作成](./user-support.md)します。</span><span class="sxs-lookup"><span data-stu-id="e7f91-139">Once your distribution is installed, follow the normal instructions to [update to WSL 2](./install-win10.md#step-2---update-to-wsl-2) or [create a new user account and password](./user-support.md).</span></span>