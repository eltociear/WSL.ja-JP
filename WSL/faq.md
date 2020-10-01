---
title: よく寄せられる質問 (FAQ)
description: "\"WSL で何ができますか\" などの、Linux 用 Windows サブシステムについてよく寄せられる質問 (FAQ) への回答をご確認いただけます。"
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, faq
ms.date: 09/15/2020
ms.topic: article
ms.assetid: 129101ed-b88a-43c2-b6a2-cd2c4ff6fee1
ms.localizationpriority: high
ms.openlocfilehash: f769261bab35619b034e2a84e4f308eeb0a93cb4
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413242"
---
# <a name="frequently-asked-questions-about-windows-subsystem-for-linux"></a><span data-ttu-id="0d3b3-104">Windows Subsystem for Linux に関してよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="0d3b3-104">Frequently Asked Questions about Windows Subsystem for Linux</span></span>

## <a name="what-is-windows-subsystem-for-linux-wsl"></a><span data-ttu-id="0d3b3-105">Windows Subsystem for Linux (WSL) とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-105">What is Windows Subsystem for Linux (WSL)?</span></span>

<span data-ttu-id="0d3b3-106">Windows Subsystem for Linux (WSL) は、ネイティブ Linux コマンド ライン ツールを Windows で直接実行できる Windows 10 の新機能です。これは、従来の Windows デスクトップや最新のストア アプリと共存します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-106">The Windows Subsystem for Linux (WSL) is a new Windows 10 feature that enables you to run native Linux command-line tools directly on Windows, alongside your traditional Windows desktop and modern store apps.</span></span>

<span data-ttu-id="0d3b3-107">詳しくは、[詳細ページ](./about.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-107">See the [about page](./about.md) for more details.</span></span>

## <a name="who-is-wsl-for"></a><span data-ttu-id="0d3b3-108">WSL の対象ユーザーは誰ですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-108">Who is WSL for?</span></span>

<span data-ttu-id="0d3b3-109">これは、主に開発者向けのツールです。特に Web 開発者と、オープン ソース プロジェクトで作業している開発者が対象です。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-109">This is primarily a tool for developers -- especially web developers and those who work on or with open source projects.</span></span> <span data-ttu-id="0d3b3-110">これにより、Bash、一般的な Linux ツール (`sed`、 `awk` など)、および多くの Linux ファースト ツール (Ruby、Python など) を使用する必要があるユーザーは、Windows でそれらのツールチェーンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-110">This allows those who want/need to use Bash, common Linux tools (`sed`, `awk`, etc.) and many Linux-first tools (Ruby, Python, etc.) to use their toolchain on Windows.</span></span>

## <a name="what-can-i-do-with-wsl"></a><span data-ttu-id="0d3b3-111">WSL で何ができますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-111">What can I do with WSL?</span></span>

<span data-ttu-id="0d3b3-112">WSL が提供する Bash.exe というアプリケーションを開始すると、Bash シェルを実行している Windows コンソールが開きます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-112">WSL provides an application called Bash.exe that, when started, opens a Windows console running the Bash shell.</span></span> <span data-ttu-id="0d3b3-113">Bash を使用すると、コマンド ライン Linux ツールおよびアプリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-113">Using Bash, you can run command-line Linux tools and apps.</span></span> <span data-ttu-id="0d3b3-114">たとえば、「`lsb_release -a`」と入力して Enter キーを押すと、現在実行中の Linux ディストリビューションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-114">For example, type `lsb_release -a` and hit enter; you’ll see details of the Linux distro currently running:</span></span>

![ディストリビューションの詳細のスクリーンショット](media/distro.png)

<span data-ttu-id="0d3b3-116">Linux Bash シェル内からローカル コンピューターのファイル システムにアクセスすることもできます。ローカル ドライブは `/mnt` フォルダーの下にマウントされます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-116">You can also access your local machine’s filesystem from within the Linux Bash shell – you’ll find your local drives mounted under the `/mnt` folder.</span></span> <span data-ttu-id="0d3b3-117">たとえば、 `C:` ドライブは `/mnt/c` の下にマウントされます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-117">For example, your `C:` drive is mounted under `/mnt/c`:</span></span>  

![マウントされた C ドライブのスクリーンショット](media/ls.png)

## <a name="could-you-describe-a-typical-development-workflow-that-incorporates-wsl"></a><span data-ttu-id="0d3b3-119">WSL が組み込まれた一般的な開発ワークフローについて説明してください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-119">Could you describe a typical development workflow that incorporates WSL?</span></span>

<span data-ttu-id="0d3b3-120">WSL は開発者を対象としており、内部開発ループの一部としての使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-120">WSL targets a developer audience with the intent to be used as part of an inner development loop.</span></span> <span data-ttu-id="0d3b3-121">たとえば、Sam が CI/CD パイプライン (継続的インテグレーションおよび継続的デリバリー) を作成しており、クラウドにデプロイする前に、まずローカル コンピューター (ノート PC) でそれをテストしたいと思っているとします。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-121">Let's say that Sam is creating a CI/CD pipeline (Continuous Integration & Continuous Delivery) and wants to test it first on a local machine (laptop) before deploying it to the cloud.</span></span> <span data-ttu-id="0d3b3-122">Sam は WSL (速度とパフォーマンスを向上させるには WSL 2) を有効にして、ローカル (ノート PC) で本物の Linux Ubuntu インスタンスと、任意の Bash コマンドとツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-122">Sam can enable WSL (& WSL 2 to improve speed and performance), and then use a genuine Linux Ubuntu instance locally (on the laptop) with whatever Bash commands and tools they prefer.</span></span> <span data-ttu-id="0d3b3-123">開発パイプラインをローカルで検証したら、Sam はその CI/CD パイプラインをクラウド (Azure) にプッシュできます。そうするには、これを Docker コンテナーに格納し、そのコンテナーをクラウド インスタンスにプッシュします。こうして、運用に対応した Ubuntu VM 上でこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-123">Once the development pipeline is verified locally, Sam can then push that CI/CD pipeline up to the cloud (ie Azure) by making it into a Docker container and pushing the container to a cloud instance where it runs on a production-ready Ubuntu VM.</span></span>

## <a name="what-is-bash"></a><span data-ttu-id="0d3b3-124">Bash とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-124">What is Bash?</span></span>

<span data-ttu-id="0d3b3-125">[Bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) は、広く使われているテキスト ベースのシェルおよびコマンド言語です。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-125">[Bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) is a popular text-based shell and command-language.</span></span> <span data-ttu-id="0d3b3-126">これは、Ubuntu およびその他の Linux ディストリビューション内と macOS に含まれる既定のシェルです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-126">It is the default shell included within Ubuntu and other Linux distros, and in macOS.</span></span> <span data-ttu-id="0d3b3-127">ユーザーは、シェルにコマンドを入力して、スクリプトを実行したり、コマンドやツールを実行したりして多くのタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-127">Users type commands into a shell to execute scripts and/or run commands and tools to accomplish many tasks.</span></span>

## <a name="how-does-this-work"></a><span data-ttu-id="0d3b3-128">この処理のしくみ</span><span class="sxs-lookup"><span data-stu-id="0d3b3-128">How does this work?</span></span>

<span data-ttu-id="0d3b3-129">基礎となるテクノロジの詳細については、[ブログ](/archive/blogs/wsl/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-129">Check out our [blog](/archive/blogs/wsl/) where we go into detail about the underlying technology.</span></span>

## <a name="why-would-i-use-wsl-rather-than-linux-in-a-vm"></a><span data-ttu-id="0d3b3-130">VM で Linux ではなく WSL を使用するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-130">Why would I use WSL rather than Linux in a VM?</span></span>

<span data-ttu-id="0d3b3-131">WSL は、必要なリソース (CPU、メモリ、およびストレージ) が完全な仮想マシンよりも少なくて済みます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-131">WSL requires fewer resources (CPU, memory, and storage) than a full virtual machine.</span></span> <span data-ttu-id="0d3b3-132">また、WSL を使用すると、Linux コマンド ライン ツールおよびアプリを Windows コマンド ライン、デスクトップおよびストア アプリと共に実行したり、Linux 内から Windows ファイルにアクセスしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-132">WSL also allows you to run Linux command-line tools and apps alongside your Windows command-line, desktop and store apps, and to access your Windows files from within Linux.</span></span> <span data-ttu-id="0d3b3-133">これにより、必要に応じて、同じファイル セットに対して Windows アプリと Linux コマンド ライン ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-133">This enables you to use Windows apps and Linux command-line tools on the same set of files if you wish.</span></span>

## <a name="why-would-i-use-for-example-ruby-on-linux-instead-of-on-windows"></a><span data-ttu-id="0d3b3-134">たとえば、Windows ではなく Linux 上で Ruby を使用するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-134">Why would I use, for example, Ruby on Linux instead of on Windows?</span></span>

<span data-ttu-id="0d3b3-135">一部のクロスプラットフォーム ツールは、それらが実行される環境が Linux のように動作することを前提として構築されました。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-135">Some cross-platform tools were built assuming that the environment in which they run behaves like Linux.</span></span> <span data-ttu-id="0d3b3-136">たとえば、一部のツールでは、非常に長いファイル パスにアクセスできることや、特定のファイルまたはフォルダーが存在することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-136">For example, some tools assume that they are able to access very long file paths or that specific files/folders exist.</span></span> <span data-ttu-id="0d3b3-137">これにより、Linux とは動作が異なる事が多い Windows で問題が発生することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-137">This often causes problems on Windows which often behaves differently from Linux.</span></span>

<span data-ttu-id="0d3b3-138">Ruby や node のような多くの言語は、たいていの場合、Windows に移植され、非常にうまく動作します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-138">Many languages like Ruby and node are often ported to, and run great, on Windows.</span></span> <span data-ttu-id="0d3b3-139">ただし、すべての Ruby Gem または node/NPM ライブラリ所有者が、Windows をサポートするためにライブラリを移植するわけではなく、多くのものに Linux 固有の依存関係があります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-139">However, not all of the Ruby Gem or node/NPM library owners port their libraries to support Windows, and many have Linux-specific dependencies.</span></span> <span data-ttu-id="0d3b3-140">これにより、このようなツールやライブラリを使用して構築されたシステムはビルドから悪影響を受ける場合が多く、Windows で実行時エラーや望ましくない動作が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-140">This can often result in systems built using such tools and libraries suffering from build and sometimes runtime errors or unwanted behaviors on Windows.</span></span>

<span data-ttu-id="0d3b3-141">これらは、多くのユーザーが Windows のコマンド ライン ツールの向上を Microsoft に依頼する原因となった問題の一部に過ぎません。また、こうした要因から、Microsoft が Canonical と提携して、ネイティブ Bash と Linux コマンド ライン ツールを Windows で実行できるようにすることになりました。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-141">These are just some of issues that caused many people to ask Microsoft to improve Windows’ command-line tools and what drove us to partner with Canonical to enable native Bash and Linux command-line tools to run on Windows.</span></span>

## <a name="what-does-this-mean-for-powershell"></a><span data-ttu-id="0d3b3-142">PowerShell においてこれは何を意味しますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-142">What does this mean for PowerShell?</span></span>

<span data-ttu-id="0d3b3-143">OSS プロジェクトでの作業中、PowerShell プロンプトから Bash を実行すると非常に役立つシナリオが多数あります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-143">While working with OSS projects, there are numerous scenarios where it’s immensely useful to drop into Bash from a PowerShell prompt.</span></span> <span data-ttu-id="0d3b3-144">Bash のサポートは補完的なものであり、Windows でのそのコマンド ラインの価値を高め、PowerShell と PowerShell コミュニティでその他の一般的なテクノロジを利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-144">Bash support is complementary and strengthens the value of the command-line on Windows, allowing PowerShell and the PowerShell community to leverage other popular technologies.</span></span>

<span data-ttu-id="0d3b3-145">詳細については、PowerShell チームのブログ「[Windows の Bash:それがすばらしい理由と PowerShell における意味](https://blogs.msdn.microsoft.com/powershell/2016/04/01/bash-for-windows-why-its-awesome-and-what-it-means-for-powershell/)」をお読みください</span><span class="sxs-lookup"><span data-stu-id="0d3b3-145">Read more on the PowerShell team blog -- [Bash for Windows: Why it’s awesome and what it means for PowerShell](https://blogs.msdn.microsoft.com/powershell/2016/04/01/bash-for-windows-why-its-awesome-and-what-it-means-for-powershell/)</span></span>

## <a name="can-i-run-all-linux-apps-in-wsl"></a><span data-ttu-id="0d3b3-146">WSL ですべての Linux アプリを実行できますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-146">Can I run ALL Linux apps in WSL?</span></span>

<span data-ttu-id="0d3b3-147">いいえ。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-147">No!</span></span> <span data-ttu-id="0d3b3-148">WSL は、Bash およびコア Linux コマンド ライン ツールを必要とするユーザーが Windows 上でそれらを実行できるようにすることを目的としたツールです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-148">WSL is a tool aimed at enabling users who need them to run Bash and core Linux command-line tools on Windows.</span></span>

<span data-ttu-id="0d3b3-149">WSL は、GUI デスクトップやアプリケーション (例: Gnome、KDE など) をサポートすることを目的として**いません**。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-149">WSL does **not** aim to support GUI desktops or applications (e.g. Gnome, KDE, etc.)</span></span>  

<span data-ttu-id="0d3b3-150">また、多くの一般的なサーバー アプリケーション (Redis など) を実行できる場合でも、実稼働サービスをホストする目的には WSL をお勧めしません。Microsoft は、Azure、Hyper-V、Docker で実稼働 Linux ワークロードを実行するためのさまざまなソリューションを提供しています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-150">Also, even though you will be able to run many popular server applications (e.g. Redis), we do not recommend WSL for hosting production services – Microsoft offers a variety of solutions for running production Linux workloads in Azure, Hyper-V, and Docker.</span></span> 

## <a name="what-windows-skus-is-wsl-included-in"></a><span data-ttu-id="0d3b3-151">WSL はどの Windows SKU に含まれていますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-151">What Windows SKUs is WSL included in?</span></span>

<span data-ttu-id="0d3b3-152">Windows Subsystem for Linux は、Windows 10 Anniversary および Creators Update 以降の Windows デスクトップ バージョンで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-152">Windows Subsystem for Linux is available on the desktop version of Windows for Windows 10 Anniversary and Creators update or later.</span></span>

<span data-ttu-id="0d3b3-153">Fall Creators Update 以降では、WSL は Windows のデスクトップとサーバーの両方の SKU で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-153">Beginning in the Fall Creators update WSL will be available on both the desktop and server SKUs of Windows.</span></span>

## <a name="what-processors-does-wsl-support"></a><span data-ttu-id="0d3b3-154">WSL はどのようなプロセッサをサポートしていますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-154">What processors does WSL support?</span></span>

<span data-ttu-id="0d3b3-155">WSL は x64 および ARM の CPU をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-155">WSL supports x64 and ARM CPUs.</span></span>

## <a name="how-do-i-access-my-c-drive"></a><span data-ttu-id="0d3b3-156">C: ドライブにアクセスするにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-156">How do I access my C: drive?</span></span>

<span data-ttu-id="0d3b3-157">ローカル コンピューター上のハード ドライブのマウント ポイントが自動的に作成され、Windows ファイル システムに簡単にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-157">Mount points for hard drives on the local machine are automatically created and provide easy access to the Windows filesystem.</span></span>

<span data-ttu-id="0d3b3-158">**/mnt/\<drive letter>/**</span><span class="sxs-lookup"><span data-stu-id="0d3b3-158">**/mnt/\<drive letter>/**</span></span>

<span data-ttu-id="0d3b3-159">使用例は、c:\ にアクセスする `cd /mnt/c` です。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-159">Example usage would be `cd /mnt/c` to access c:\</span></span>

## <a name="how-do-i-set-up-git-credential-manager-how-do-i-use-my-windows-git-permissions-in-wsl"></a><span data-ttu-id="0d3b3-160">Git Credential Manager をセットアップするにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-160">How do I set up Git Credential Manager?</span></span> <span data-ttu-id="0d3b3-161">(WSL で Windows Git アクセス許可を使用するにはどうすればよいですか。)</span><span class="sxs-lookup"><span data-stu-id="0d3b3-161">(How do I use my Windows Git permissions in WSL?)</span></span> 

<span data-ttu-id="0d3b3-162">Git Credential Manager を使用すると、Azure Active Directory や 2 要素認証などの複雑な認証パターンがある場合でも、リモート Git サーバーを認証できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-162">Git Credential Manager enables you to authenticate a remote Git server, even if you have a complex authentication pattern like Azure Active Directory or two-factor authentication.</span></span> <span data-ttu-id="0d3b3-163">Git Credential Manager は、GitHub などのサービスの認証フローに統合されています。ユーザーがホスティング プロバイダーに対して認証されると、新しい認証トークンが要求されます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-163">Git Credential Manager integrates into the authentication flow for services like GitHub and, once you're authenticated to your hosting provider, requests a new authentication token.</span></span> <span data-ttu-id="0d3b3-164">その後、そのトークンは Windows 資格情報マネージャーに安全に格納されます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-164">It then stores the token securely in the Windows Credential Manager.</span></span> <span data-ttu-id="0d3b3-165">2 回目以降は、Git を使用してホスティング プロバイダーと通信することができ、再認証は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-165">After the first time, you can use git to talk to your hosting provider without needing to re-authenticate.</span></span> <span data-ttu-id="0d3b3-166">Windows 資格情報マネージャーにあるトークンへのアクセスだけが行われることになります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-166">It will just access the token in the Windows Credential Manager.</span></span>

<span data-ttu-id="0d3b3-167">WSL ディストリビューションで使用するように Git Credential Manager をセットアップするには、ディストリビューションを開き、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-167">To set up Git Credential Manager for use with a WSL distribution, open your distribution and enter this command:</span></span>

```Bash
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
```

<span data-ttu-id="0d3b3-168">これで、WSL ディストリビューション内で実行するすべての Git 操作で、資格情報マネージャーが使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-168">Now any git operation you perform within your WSL distribution will use the credential manager.</span></span> <span data-ttu-id="0d3b3-169">ホスト用に既にキャッシュされている資格情報がある場合は、それらへのアクセスが資格情報マネージャーから行われます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-169">If you already have credentials cached for a host, it will access them from the credential manager.</span></span> <span data-ttu-id="0d3b3-170">そうでない場合は、Linux コンソールを使用しているとしても、資格情報を要求するダイアログ応答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-170">If not, you'll receive a dialog response requesting your credentials, even if you're in a Linux console.</span></span>

<span data-ttu-id="0d3b3-171">このサポートは、[Linux 用 Windows サブシステムと Windows そのものとの相互運用性](./interop.md)に依存しています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-171">This support relies on the [interoperability between Windows Subsystem for Linux and Windows itself](./interop.md).</span></span>

## <a name="how-do-i-use-a-windows-file-with-a-linux-app"></a><span data-ttu-id="0d3b3-172">Linux アプリで Windows ファイルをどのように使用しますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-172">How do I use a Windows file with a Linux app?</span></span>

<span data-ttu-id="0d3b3-173">WSL の利点の 1 つは、Windows と Linux の両方のアプリまたはツールを経由してファイルにアクセスできることです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-173">One of the benefits of WSL is being able to access your files via both Windows and Linux apps or tools.</span></span> 

<span data-ttu-id="0d3b3-174">WSL では、コンピューターの固定ドライブを Linux ディストリビューションの `/mnt/<drive>` フォルダーの下にマウントします。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-174">WSL mounts your machine's fixed drives under the `/mnt/<drive>` folder in your Linux distros.</span></span> <span data-ttu-id="0d3b3-175">たとえば、 `C:` ドライブは `/mnt/c/` の下にマウントされます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-175">For example, your `C:` drive is mounted under `/mnt/c/`</span></span>

<span data-ttu-id="0d3b3-176">マウントされたドライブを使用すると、[Visual Studio](https://visualstudio.microsoft.com/vs/) または[VS Code](https://code.visualstudio.com/)を使用して、たとえば `C:\dev\myproj\` 内のコードを編集したり、`/mnt/c/dev/myproj` を介して同じファイルにアクセスして Linux でそのコードをビルド/テストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-176">Using your mounted drives, you can edit code in, for example, `C:\dev\myproj\` using [Visual Studio](https://visualstudio.microsoft.com/vs/) / or [VS Code](https://code.visualstudio.com/), and build/test that code in Linux by accessing the same files via `/mnt/c/dev/myproj`.</span></span>

> <span data-ttu-id="0d3b3-177">**重要な注意**:WSL を使用する際の主な制限事項の 1 つは、Windows アプリまたはツールを使用して Linux ディストリビューションのファイル システム内のファイルに直接アクセスしたり、変更したりすることがサポートされていないことです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-177">**IMPORTANT NOTE**: One of the key limitations of using WSL is that directly accessing/changing files in your Linux distros' filesystem using Windows apps or tools is not supported.</span></span> <span data-ttu-id="0d3b3-178">以下を参照してください。[Windows アプリやツールを使用して Linux ファイルを変更しない](https://blogs.msdn.microsoft.com/commandline/2016/11/17/do-not-change-linux-files-using-windows-apps-and-tools/)</span><span class="sxs-lookup"><span data-stu-id="0d3b3-178">See: [Do not change Linux files using Windows apps and tools](https://blogs.msdn.microsoft.com/commandline/2016/11/17/do-not-change-linux-files-using-windows-apps-and-tools/)</span></span>

## <a name="are-files-in-the-linux-drive-different-from-the-mounted-windows-drive"></a><span data-ttu-id="0d3b3-179">Linux ドライブのファイルはマウントされた Windows ドライブのものとは異なりますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-179">Are files in the Linux drive different from the mounted Windows drive?</span></span>

1. <span data-ttu-id="0d3b3-180">Linux ルート (つまり `/`) の下にあるファイルは、Linux 固有の性質を模倣する WSL によって制御されます。次のようなものが含まれますが、これらに限定されません。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-180">Files under the Linux root (i.e. `/`) are controlled by WSL which mimics Linux specific behavior, including but not limited to:</span></span>
   * <span data-ttu-id="0d3b3-181">無効な Windows ファイル名の文字を含むファイル</span><span class="sxs-lookup"><span data-stu-id="0d3b3-181">Files which contain invalid Windows filename characters</span></span>
   * <span data-ttu-id="0d3b3-182">管理者以外のユーザー用に作成されたシンボリック リンク</span><span class="sxs-lookup"><span data-stu-id="0d3b3-182">Symlinks created for non-admin users</span></span>
   * <span data-ttu-id="0d3b3-183">chmod および chown を使用したファイル属性の変更</span><span class="sxs-lookup"><span data-stu-id="0d3b3-183">Changing file attributes through chmod and chown</span></span>
   * <span data-ttu-id="0d3b3-184">ファイル/フォルダーの大文字と小文字の区別</span><span class="sxs-lookup"><span data-stu-id="0d3b3-184">File/folder case sensitivity</span></span>

2. <span data-ttu-id="0d3b3-185">マウントされたドライブのファイルは Windows によって制御され、次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-185">Files in mounted drives are controlled by Windows and have the following behaviors:</span></span>
   * <span data-ttu-id="0d3b3-186">大文字と小文字の区別をサポート</span><span class="sxs-lookup"><span data-stu-id="0d3b3-186">Support case sensitivity</span></span>
   * <span data-ttu-id="0d3b3-187">すべてのアクセス許可は、Windows アクセス許可を最適に反映するように設定</span><span class="sxs-lookup"><span data-stu-id="0d3b3-187">All permissions are set to best reflect the Windows permissions</span></span>

## <a name="why-are-there-so-many-errors-when-i-run-apt-get-upgrade"></a><span data-ttu-id="0d3b3-188">apt-get upgrade を実行すると、多くのエラーが発生するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-188">Why are there so many errors when I run apt-get upgrade?</span></span>

<span data-ttu-id="0d3b3-189">一部のパッケージでは、Microsoft がまだ実装していない機能が使用されています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-189">Some packages use features that we haven't implemented yet.</span></span> <span data-ttu-id="0d3b3-190">たとえば、`udev` はまだサポートされていないため、`apt-get upgrade` エラーがいくつか発生します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-190">`udev`, for example, isn't supported yet and causes several `apt-get upgrade` errors.</span></span>

<span data-ttu-id="0d3b3-191">`udev` に関連する問題を修正するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-191">To fix issues related to `udev`, follow the following steps:</span></span>

1. <span data-ttu-id="0d3b3-192">次の内容を `/usr/sbin/policy-rc.d` に記述して、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-192">Write the following to `/usr/sbin/policy-rc.d` and save your changes.</span></span>

    ```bash
    #!/bin/sh
    exit 101
    ```

2. <span data-ttu-id="0d3b3-193">実行のアクセス許可を `/usr/sbin/policy-rc.d` に追加します</span><span class="sxs-lookup"><span data-stu-id="0d3b3-193">Add execute permissions to `/usr/sbin/policy-rc.d`</span></span>

    ```bash
    chmod +x /usr/sbin/policy-rc.d
    ```
  
3. <span data-ttu-id="0d3b3-194">次のコマンドを実行します</span><span class="sxs-lookup"><span data-stu-id="0d3b3-194">Run the following commands</span></span>

    ```bash
    dpkg-divert --local --rename --add /sbin/initctl
    ln -s /bin/true /sbin/initctl
    ```

## <a name="how-do-i-uninstall-a-wsl-distribution"></a><span data-ttu-id="0d3b3-195">WSL ディストリビューションをアンインストールするにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-195">How do I uninstall a WSL Distribution?</span></span>

<span data-ttu-id="0d3b3-196">1709 (16299) より前のビルドでは、コマンド プロンプトを開き、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-196">On builds prior to 1709 (16299) open a command prompt and run:</span></span>

  ```batchfile
  lxrun /uninstall /full
  ```
  
<span data-ttu-id="0d3b3-197">ストアからインストールされた WSL ディストリビューションは、他の Windows アプリと同様に、アプリ タイルを右クリックして [アンインストール] をクリックするか、[`Remove-AppxPackage` コマンドレット](/previous-versions//hh856038(v=technet.10))を使用して PowerShell を介してアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-197">WSL distributions installed from the store can be uninstalled like any other Windows app, by right-clicking on the app tile and clicking Uninstall, or via PowerShell using the [`Remove-AppxPackage` cmdlet](/previous-versions//hh856038(v=technet.10)).</span></span>

## <a name="why-does-ping-generate-permission-denied-errors"></a><span data-ttu-id="0d3b3-198">ping によってアクセス拒否エラーが発生するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-198">Why does ping generate permission denied errors?</span></span>

<span data-ttu-id="0d3b3-199">14926 より前の WSL ビルドでは、WSL で管理者特権のコンソールを使用して ping を実行する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-199">In WSL builds < 14926, ping required WSL to run via an elevated Console.</span></span> <span data-ttu-id="0d3b3-200">この問題は、ビルド14926 以降で修正されました。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-200">This issue was fixed in Build 14926 and later.</span></span>

## <a name="how-do-i-run-an-openssh-server"></a><span data-ttu-id="0d3b3-201">OpenSSH サーバーを実行するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-201">How do I run an OpenSSH server?</span></span>

<span data-ttu-id="0d3b3-202">WSL で OpenSSH を実行するには、Windows の管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-202">Administrator privileges in Windows are required to run OpenSSH in WSL.</span></span> <span data-ttu-id="0d3b3-203">OpenSSH サーバーを実行するには、管理者として Bash on Ubuntu on Windows を実行するか、管理者特権を使用して CMD/PowerShell プロンプトから bash.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-203">To run an OpenSSH server, run Bash on Ubuntu on Windows as an administrator, or run bash.exe from a CMD/PowerShell prompt with administrator privileges.</span></span>

## <a name="why-do-i-get-error-0x80040306-when-i-try-to-install"></a><span data-ttu-id="0d3b3-204">インストールしようとすると、"エラー:0x80040306" が表示されるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-204">Why do I get "Error: 0x80040306" when I try to install?</span></span>

<span data-ttu-id="0d3b3-205">WSL は、従来のコンソールでの実行をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-205">WSL does not support running in a legacy console.</span></span> <span data-ttu-id="0d3b3-206">従来のコンソールをオフにするには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-206">To turn off legacy console:</span></span>

1. <span data-ttu-id="0d3b3-207">WSL、PowerShell、または Cmd を開きます</span><span class="sxs-lookup"><span data-stu-id="0d3b3-207">Open WSL, PowerShell, or Cmd</span></span>
1. <span data-ttu-id="0d3b3-208">タイトル バーを右クリックして、[プロパティ] を選択し、[従来のコンソールを使う] をオフにします</span><span class="sxs-lookup"><span data-stu-id="0d3b3-208">Right click title bar -> Properties -> Uncheck "Use legacy console"</span></span>
1. <span data-ttu-id="0d3b3-209">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-209">Click OK</span></span>

## <a name="why-do-i-get-error-0x80040154-when-i-run-bashexe-after-upgrading-windows"></a><span data-ttu-id="0d3b3-210">Windows のアップグレード後に bash.exe を実行すると、"エラー:0x80040154" が表示されるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-210">Why do I get "Error: 0x80040154" when I run bash.exe after upgrading Windows?</span></span>

<span data-ttu-id="0d3b3-211">Windows Update 時に "Windows Subsystem for Linux" 機能が無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-211">The "Windows Subsystem for Linux" feature may be disabled during a Windows update.</span></span> <span data-ttu-id="0d3b3-212">その場合は、この Windows 機能を再度有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-212">If this happens the Windows feature must be re-enabled.</span></span> <span data-ttu-id="0d3b3-213">"Windows Subsystem for Linux" 機能を有効にする手順については、[インストール ガイド](./install-win10.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-213">Instructions for enabling the "Windows Subsystem for Linux" feature can be found in the [Installation Guide](./install-win10.md).</span></span>

## <a name="how-do-i-change-the-display-language-of-wsl"></a><span data-ttu-id="0d3b3-214">WSL の表示言語を変更するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-214">How do I change the display language of WSL?</span></span>

<span data-ttu-id="0d3b3-215">WSL インストールでは、Windows インストールのロケールに合わせて Ubuntu ロケールを自動的に変更しようとします。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-215">WSL install will try to automatically change the Ubuntu locale to match the locale of your Windows install.</span></span> <span data-ttu-id="0d3b3-216">この動作が不要な場合は、次のコマンドを実行して、インストールの完了後に Ubuntu ロケールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-216">If you do not want this behavior you can run this command to change the Ubuntu locale after install completes.</span></span> <span data-ttu-id="0d3b3-217">この変更を有効にするには、bash.exe を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-217">You will have to relaunch bash.exe for this change to take effect.</span></span>

<span data-ttu-id="0d3b3-218">次の例は、ロケールを en-US に変更します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-218">The below example changes to locale to en-US:</span></span>

```bash
sudo update-locale LANG=en_US.UTF8
```

## <a name="why-do-i-not-have-internet-access-from-wsl"></a><span data-ttu-id="0d3b3-219">WSL からインターネットにアクセスできないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-219">Why do I not have internet access from WSL?</span></span>

<span data-ttu-id="0d3b3-220">一部のユーザーにより、WSL でのインターネット アクセスをブロックする特定のファイアウォール アプリケーションに関する問題が報告されています。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-220">Some users have reported issues with specific firewall applications blocking internet access in WSL.</span></span> <span data-ttu-id="0d3b3-221">報告されているファイアウォールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-221">The firewalls reported are:</span></span>

1. <span data-ttu-id="0d3b3-222">Kaspersky</span><span class="sxs-lookup"><span data-stu-id="0d3b3-222">Kaspersky</span></span>
1. <span data-ttu-id="0d3b3-223">AVG</span><span class="sxs-lookup"><span data-stu-id="0d3b3-223">AVG</span></span>
1. <span data-ttu-id="0d3b3-224">Avast</span><span class="sxs-lookup"><span data-stu-id="0d3b3-224">Avast</span></span>

<span data-ttu-id="0d3b3-225">ファイアウォールをオフにすると、アクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-225">In some cases turning off the firewall allows for access.</span></span> <span data-ttu-id="0d3b3-226">場合によっては、ファイアウォールをインストールするだけでアクセスがブロックされるようです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-226">In some cases simply having the firewall installed looks to block access.</span></span>

## <a name="how-do-i-access-a-port-from-wsl-in-windows"></a><span data-ttu-id="0d3b3-227">Windows の WSL からポートにアクセスするにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-227">How do I access a port from WSL in Windows?</span></span>
<span data-ttu-id="0d3b3-228">WSL は Windows で実行されているため、Windows の IP アドレスを共有します。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-228">WSL shares the IP address of Windows, as it is running on Windows.</span></span> <span data-ttu-id="0d3b3-229">そのため、localhost 上の任意のポートにアクセスできます。たとえば、ポート 1234 に Web コンテンツがあるとすると、 https://localhost:1234 を Windows ブラウザーに入力できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-229">As such you can access any ports on localhost e.g. if you had web content on port 1234 you could https://localhost:1234 into your Windows browser.</span></span>

## <a name="how-can-i-back-up-my-wsl-distros-or-move-them-from-one-drive-to-another"></a><span data-ttu-id="0d3b3-230">WSL ディストリビューションをバックアップしたり、別のドライブに移動したりするにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-230">How can I back up my WSL distros, or move them from one drive to another?</span></span>

<span data-ttu-id="0d3b3-231">ディストリビューションをバックアップまたは移動する最適な方法は、Windows バージョン 1809 以降で使用できるエクスポート/インポート コマンドを使用することです。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-231">The best way to backup or move your distros is via the export/import commands available in Windows Version 1809 and later.</span></span> <span data-ttu-id="0d3b3-232">`wsl --export` コマンドを使用して、ディストリビューション全体を tarball にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-232">You can export your entire distribution to a tarball using the `wsl --export` command.</span></span> <span data-ttu-id="0d3b3-233">その後、`wsl --import` コマンドを使用してこのディストリビューションを WSL にインポートし直すことができます。これにより、インポート用の新しいドライブの場所に名前を付けて、WSL ディストリビューションをバックアップして状態を保存 (または移動) できます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-233">You can then import this distro back into WSL using the `wsl --import` command, which can name a new drive location for the import, allowing you to backup and save states of (or move) your WSL distributions.</span></span> 

<span data-ttu-id="0d3b3-234">Appdata フォルダーのファイルをバックアップする従来のバックアップ サービス (Windows バックアップなど) によって Linux ファイルが破損することはありません。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-234">Please note that traditional backup services that backup files in your Appdata folders (like Windows Backup) will not corrupt your Linux files.</span></span>

## <a name="where-can-i-provide-feedback"></a><span data-ttu-id="0d3b3-235">フィードバックはどこで提供できますか。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-235">Where can I provide feedback?</span></span>

<span data-ttu-id="0d3b3-236">複数のチャネルを通じて、フィードバックを送ったり、質問したりできます。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-236">You can share feedback and ask questions through multiple channels.</span></span>

<span data-ttu-id="0d3b3-237">技術上の問題がある場合や、新機能のリクエストをしたい場合は、GitHub の問題の追跡ツールにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-237">If you have technical issues, or want to request new features please go to our Github issue tracker:</span></span>

* [<span data-ttu-id="0d3b3-238">GitHub の問題の追跡ツール</span><span class="sxs-lookup"><span data-stu-id="0d3b3-238">GitHub issue tracker</span></span>](https://github.com/Microsoft/BashOnWindows/issues)

<span data-ttu-id="0d3b3-239">WSL の最新ニュースを入手するには、以下をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-239">If you'd like to stay up to date with the latest WSL news you can do so with:</span></span>

* <span data-ttu-id="0d3b3-240">[Microsoft のコマンド ライン チームのブログ](https://blogs.msdn.microsoft.com/commandline/)</span><span class="sxs-lookup"><span data-stu-id="0d3b3-240">Our [command-line team blog](https://blogs.msdn.microsoft.com/commandline/)</span></span>
* <span data-ttu-id="0d3b3-241">Twitter。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-241">Twitter.</span></span> <span data-ttu-id="0d3b3-242">ニュース、更新などを確認するには、Twitter で [@craigaloewen](https://twitter.com/craigaloewen) をフォローしてください。</span><span class="sxs-lookup"><span data-stu-id="0d3b3-242">Please follow [@craigaloewen](https://twitter.com/craigaloewen) on Twitter to learn of news, updates, etc.</span></span>