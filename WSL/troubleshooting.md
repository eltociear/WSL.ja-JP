---
title: Windows Subsystem for Linux のトラブルシューティング
description: Windows Subsystem for Linux で Linux を実行しているときに発生する一般的なエラーと問題について詳しく説明します。
keywords: BashOnWindows, bash, wsl, windows, windowssubsystem, ubuntu
ms.date: 01/20/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 78d122ce22e3ab4d67339cc6f0d6038502e23dbb
ms.sourcegitcommit: b15b847b87d29a40de4a1517315949bce9c7a3d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413293"
---
# <a name="troubleshooting-windows-subsystem-for-linux"></a><span data-ttu-id="6ad00-104">Windows Subsystem for Linux のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6ad00-104">Troubleshooting Windows Subsystem for Linux</span></span>

<span data-ttu-id="6ad00-105">WSL に関連する問題のサポートについては、GitHub リポジトリを参照してください。 https://github.com/Microsoft/wsl/issues</span><span class="sxs-lookup"><span data-stu-id="6ad00-105">For support with issues related to WSL, please see our GitHub repo: https://github.com/Microsoft/wsl/issues</span></span>

## <a name="search-for-any-existing-issues-related-to-your-problem"></a><span data-ttu-id="6ad00-106">発生している問題に関連する既存の問題を検索します</span><span class="sxs-lookup"><span data-stu-id="6ad00-106">Search for any existing issues related to your problem</span></span>

<span data-ttu-id="6ad00-107">技術的な問題については、製品リポジトリを使用します: https://github.com/Microsoft/wsl/issues</span><span class="sxs-lookup"><span data-stu-id="6ad00-107">For technical issues, use the product repo: https://github.com/Microsoft/wsl/issues</span></span>

<span data-ttu-id="6ad00-108">このドキュメントの内容に関連する問題については、ドキュメント リポジトリを使用します: https://github.com/MicrosoftDocs/wsl/issues</span><span class="sxs-lookup"><span data-stu-id="6ad00-108">For issues related to the contents of this documentation, use the docs repo: https://github.com/MicrosoftDocs/wsl/issues</span></span>

## <a name="submit-a-bug-report"></a><span data-ttu-id="6ad00-109">バグ報告の送信</span><span class="sxs-lookup"><span data-stu-id="6ad00-109">Submit a bug report</span></span>

<span data-ttu-id="6ad00-110">WSL の関数または機能に関連するバグについては、製品リポジトリに問題を報告します: https://github.com/Microsoft/wsl/issues</span><span class="sxs-lookup"><span data-stu-id="6ad00-110">For bugs related to WSL functions or features, file an issue in the product repo: https://github.com/Microsoft/wsl/issues</span></span>

## <a name="submit-a-feature-request"></a><span data-ttu-id="6ad00-111">機能リクエストの送信</span><span class="sxs-lookup"><span data-stu-id="6ad00-111">Submit a feature request</span></span>

<span data-ttu-id="6ad00-112">WSL の機能または互換性に関連する新しい機能を要求する場合は、製品リポジトリに問題を報告します: https://github.com/Microsoft/wsl/issues</span><span class="sxs-lookup"><span data-stu-id="6ad00-112">To request a new feature related to WSL functionality or compatibility, file an issue in the product repo: https://github.com/Microsoft/wsl/issues</span></span>

## <a name="contribute-to-the-docs"></a><span data-ttu-id="6ad00-113">ドキュメントに投稿する</span><span class="sxs-lookup"><span data-stu-id="6ad00-113">Contribute to the docs</span></span>

<span data-ttu-id="6ad00-114">WSL ドキュメントに投稿するには、ドキュメント リポジトリに pull request を送信します: https://github.com/MicrosoftDocs/wsl/issues</span><span class="sxs-lookup"><span data-stu-id="6ad00-114">To contribute to the WSL documentation, submit a pull request in the docs repo: https://github.com/MicrosoftDocs/wsl/issues</span></span>

## <a name="terminal-or-command-line"></a><span data-ttu-id="6ad00-115">ターミナルまたはコマンド ライン</span><span class="sxs-lookup"><span data-stu-id="6ad00-115">Terminal or Command Line</span></span>

<span data-ttu-id="6ad00-116">最後に、問題が Windows ターミナル、Windows コンソール、またはコマンドライン UI に関連している場合は、Windows ターミナル リポジトリを使用します: https://github.com/microsoft/terminal</span><span class="sxs-lookup"><span data-stu-id="6ad00-116">Lastly, if your issue is related to the Windows Terminal, Windows Console, or the command-line UI, use the Windows terminal repo: https://github.com/microsoft/terminal</span></span>

## <a name="common-issues"></a><span data-ttu-id="6ad00-117">一般的な問題</span><span class="sxs-lookup"><span data-stu-id="6ad00-117">Common issues</span></span>

### <a name="im-on-windows-10-version-1903-and-i-still-do-not-see-options-for-wsl-2"></a><span data-ttu-id="6ad00-118">Windows 10 バージョン 1903 を使用しており、WSL 2 のオプションがまだ表示されません。</span><span class="sxs-lookup"><span data-stu-id="6ad00-118">I'm on Windows 10 version 1903 and I still do not see options for WSL 2.</span></span> 

<span data-ttu-id="6ad00-119">これはおそらく、お客様のマシンが WSL 2 のバックポートをまだ取得していないことが原因です。</span><span class="sxs-lookup"><span data-stu-id="6ad00-119">This is likely because your machine has not yet taken the backport for WSL 2.</span></span> <span data-ttu-id="6ad00-120">これの最も簡単な解決方法は、Windows 設定に移動し、[更新プログラムの確認] をクリックして最新の更新プログラムをお客様のシステムにインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="6ad00-120">The simplest way to resolve this is by going to Windows Settings and clicking 'Check for Updates' to install the latest updates on your system.</span></span> <span data-ttu-id="6ad00-121">バックポート取得の詳細な手順については、[こちら](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/#how-do-i-get-it)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-121">You can view the full instructions on taking the backport [here](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/#how-do-i-get-it).</span></span> 

<span data-ttu-id="6ad00-122">[更新プログラムの確認] を押しても更新プログラムが届かない場合は、[このリンクに従って](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4566116)手動で KB KB4566116 をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-122">If you hit 'Check for Updates' and still do not receive the update you can install KB KB4566116 manually by [following this link](https://www.catalog.update.microsoft.com/Search.aspx?q=KB4566116).</span></span>  

### <a name="error-0x1bc-when-wsl---set-default-version-2"></a><span data-ttu-id="6ad00-123">エラー: 0x1bc (`wsl --set-default-version 2` の場合)</span><span class="sxs-lookup"><span data-stu-id="6ad00-123">Error: 0x1bc when `wsl --set-default-version 2`</span></span>
<span data-ttu-id="6ad00-124">これは、[表示言語] または [システム ロケール] の設定が英語ではない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-124">This may happen when 'Display Language' or 'System Locale' setting is not English.</span></span>
```
wsl --set-default-version 2
Error: 0x1bc
For information on key differences with WSL 2 please visit https://aka.ms/wsl2
```

<span data-ttu-id="6ad00-125">`0x1bc` の実際のエラーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ad00-125">THe actual error for `0x1bc` is:</span></span>
```
WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel
```

<span data-ttu-id="6ad00-126">詳細については、問題 [5749](https://github.com/microsoft/WSL/issues/5749) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-126">For more information, please refer to issue [5749](https://github.com/microsoft/WSL/issues/5749)</span></span>


### <a name="cannot-access-wsl-files-from-windows"></a><span data-ttu-id="6ad00-127">Windows から WSL ファイルにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="6ad00-127">Cannot access WSL files from Windows</span></span>
<span data-ttu-id="6ad00-128">9P プロトコル ファイル サーバーは、Linux 側のサービスを提供して、Windows が Linux ファイル システムにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6ad00-128">A 9p protocol file server provides the service on the Linux side to allow Windows to access the Linux file system.</span></span> <span data-ttu-id="6ad00-129">Windows で `\\wsl$` を使用して WSL にアクセスできない場合は、9P が正常に開始されなかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-129">If you cannot access WSL using `\\wsl$` on Windows, it could be because 9P did not start correctly.</span></span>

<span data-ttu-id="6ad00-130">これを確認するには、`dmesg |grep 9p` によってスタートアップ ログをチェックして、エラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-130">To check this, you can check the start up logs using: `dmesg |grep 9p`, and this will show you any errors.</span></span> <span data-ttu-id="6ad00-131">正常な出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-131">A successfull output looks like the following:</span></span> 

```
[    0.363323] 9p: Installing v9fs 9p2000 file system support
[    0.363336] FS-Cache: Netfs '9p' registered for caching
[    0.398989] 9pnet: Installing 9P2000 support
```

<span data-ttu-id="6ad00-132">この問題の詳細については、[この Github スレッド](https://github.com/microsoft/wsl/issues/5307)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-132">Please see [this Github thread](https://github.com/microsoft/wsl/issues/5307) for further discussion on this issue.</span></span>

### <a name="cant-start-wsl-2-distro-and-only-see-wsl-2-in-output"></a><span data-ttu-id="6ad00-133">WSL 2 ディストリビューションを開始できず、出力で 'WSL 2' のみが表示される</span><span class="sxs-lookup"><span data-stu-id="6ad00-133">Can't start WSL 2 distro and only see 'WSL 2' in output</span></span>
<span data-ttu-id="6ad00-134">表示言語が英語でない場合は、切り捨てられたエラー テキストが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-134">If your display language is not English, then it is possible you are seeing a truncated version of an error text.</span></span>

```powershell
C:\Users\me>wsl
WSL 2
```

<span data-ttu-id="6ad00-135">この問題を解決するには、`https://aka.ms/wsl2kernel` にアクセスし、そのドキュメント ページの指示に従って手動でカーネルをインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-135">To resolve this issue, please visit `https://aka.ms/wsl2kernel` and install the kernel manually by following the directions on that doc page.</span></span> 

### <a name="please-enable-the-virtual-machine-platform-windows-feature-and-ensure-virtualization-is-enabled-in-the-bios"></a><span data-ttu-id="6ad00-136">仮想マシン プラットフォームの Windows 機能を有効にし、BIOS で仮想化が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-136">Please enable the Virtual Machine Platform Windows feature and ensure virtualization is enabled in the BIOS.</span></span>

1. <span data-ttu-id="6ad00-137">[Hyper-V のシステム要件](/windows-server/virtualization/hyper-v/system-requirements-for-hyper-v-on-windows#:~:text=on%20Windows%20Server.-,General%20requirements,the%20processor%20must%20have%20SLAT.)を確認</span><span class="sxs-lookup"><span data-stu-id="6ad00-137">Check the [Hyper-V system requirements](/windows-server/virtualization/hyper-v/system-requirements-for-hyper-v-on-windows#:~:text=on%20Windows%20Server.-,General%20requirements,the%20processor%20must%20have%20SLAT.)</span></span>
2. <span data-ttu-id="6ad00-138">マシンが VM の場合は、[入れ子になった仮想化](./wsl2-faq.md#can-i-run-wsl-2-in-a-virtual-machine)を手動で有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-138">If your machine is a VM, please enable [nested virtualization](./wsl2-faq.md#can-i-run-wsl-2-in-a-virtual-machine) manually.</span></span> <span data-ttu-id="6ad00-139">管理者で Powershell を起動し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-139">Launch powershell with admin, and run:</span></span> 

```powershell
Set-VMProcessor -VMName <VMName> -ExposeVirtualizationExtensions $true
```

3. <span data-ttu-id="6ad00-140">仮想化を有効にする方法については、お使いの PC の製造元のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-140">Please follow guidelines from your PC's manufacturer on how to enable virtualization.</span></span> <span data-ttu-id="6ad00-141">一般に、これらの機能が CPU で確実に有効になるようにするには、システム BIOS の使用が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-141">In general, this can involve using the system BIOS to ensure that these features are enabled on your CPU.</span></span> 
4. <span data-ttu-id="6ad00-142">`Virtual Machine Platform` のオプションのコンポーネントを有効にしたら、コンピューターを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-142">Restart your machine after enabling the `Virtual Machine Platform` optional component.</span></span> 

### <a name="bash-loses-network-connectivity-once-connected-to-a-vpn"></a><span data-ttu-id="6ad00-143">VPN に接続されると、bash のネットワーク接続が切断される</span><span class="sxs-lookup"><span data-stu-id="6ad00-143">Bash loses network connectivity once connected to a VPN</span></span>

<span data-ttu-id="6ad00-144">Windows で VPN に接続した後、bash のネットワーク接続が切断される場合は、bash 内からこの回避策を試してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-144">If after connecting to a VPN on Windows, bash loses network connectivity, try this workaround from within bash.</span></span> <span data-ttu-id="6ad00-145">この回避策により、`/etc/resolv.conf` を使用して DNS 解決を手動で上書きできます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-145">This workaround will allow you to manually override the DNS resolution through `/etc/resolv.conf`.</span></span>

1. <span data-ttu-id="6ad00-146">`ipconfig.exe /all` を実行して、VPN の DNS サーバーをメモします</span><span class="sxs-lookup"><span data-stu-id="6ad00-146">Take a note of the DNS server of the VPN from doing `ipconfig.exe /all`</span></span>
2. <span data-ttu-id="6ad00-147">`sudo cp /etc/resolv.conf /etc/resolv.conf.new` で、既存の resolv.conf のコピーを作成します</span><span class="sxs-lookup"><span data-stu-id="6ad00-147">Make a copy of the existing resolv.conf `sudo cp /etc/resolv.conf /etc/resolv.conf.new`</span></span>
3. <span data-ttu-id="6ad00-148">`sudo unlink /etc/resolv.conf` で、現在の resolv.conf のリンクを解除します</span><span class="sxs-lookup"><span data-stu-id="6ad00-148">Unlink the current resolv.conf `sudo unlink /etc/resolv.conf`</span></span>
4. `sudo mv /etc/resolv.conf.new /etc/resolv.conf`
5. <span data-ttu-id="6ad00-149">`/etc/resolv.conf` を開きます。そして、</span><span class="sxs-lookup"><span data-stu-id="6ad00-149">Open `/etc/resolv.conf` and</span></span> <br/>
   <span data-ttu-id="6ad00-150">a。</span><span class="sxs-lookup"><span data-stu-id="6ad00-150">a.</span></span> <span data-ttu-id="6ad00-151">ファイルから最初の行を削除します。この行の内容は "\# This file was automatically generated by WSL.</span><span class="sxs-lookup"><span data-stu-id="6ad00-151">Delete the first line from the file, which says "\# This file was automatically generated by WSL.</span></span> <span data-ttu-id="6ad00-152">To stop automatic generation of this file, remove this line." です。</span><span class="sxs-lookup"><span data-stu-id="6ad00-152">To stop automatic generation of this file, remove this line.".</span></span> <br/>
   <span data-ttu-id="6ad00-153">b.</span><span class="sxs-lookup"><span data-stu-id="6ad00-153">b.</span></span> <span data-ttu-id="6ad00-154">DNS サーバーの一覧の最初のエントリとして、上記 (1) の DNS エントリ を追加します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-154">Add the DNS entry from (1) above as the very first entry in the list of DNS servers.</span></span> <br/>
   <span data-ttu-id="6ad00-155">c.</span><span class="sxs-lookup"><span data-stu-id="6ad00-155">c.</span></span> <span data-ttu-id="6ad00-156">ファイを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-156">Close the file.</span></span> <br/>

<span data-ttu-id="6ad00-157">VPN を切断したら、変更を `/etc/resolv.conf` に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-157">Once you have disconnected the VPN, you will have to revert the changes to `/etc/resolv.conf`.</span></span> <span data-ttu-id="6ad00-158">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-158">To do this, do:</span></span>

1. `cd /etc`
2. `sudo mv resolv.conf resolv.conf.new`
3. `sudo ln -s ../run/resolvconf/resolv.conf resolv.conf`

### <a name="starting-wsl-or-installing-a-distribution-returns-an-error-code"></a><span data-ttu-id="6ad00-159">WSL の開始またはディストリビューションのインストールでエラー コードが返される</span><span class="sxs-lookup"><span data-stu-id="6ad00-159">Starting WSL or installing a distribution returns an error code</span></span>

<span data-ttu-id="6ad00-160">[こちらの手順](https://github.com/Microsoft/WSL/blob/master/CONTRIBUTING.md#8-detailed-logs)に従って、詳細なログを収集し、Microsoft の GitHub で問題を提出してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-160">Follow [these instructions](https://github.com/Microsoft/WSL/blob/master/CONTRIBUTING.md#8-detailed-logs) to collect detailed logs and file an issue on our GitHub.</span></span>

### <a name="updating-bash-on-ubuntu-on-windows"></a><span data-ttu-id="6ad00-161">Bash on Ubuntu on Windows の更新</span><span class="sxs-lookup"><span data-stu-id="6ad00-161">Updating Bash on Ubuntu on Windows</span></span>

<span data-ttu-id="6ad00-162">Bash on Ubuntu on Windows には、更新が必要になることがある 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-162">There are two components of Bash on Ubuntu on Windows that can require updating.</span></span>

1. <span data-ttu-id="6ad00-163">Windows Subsystem for Linux</span><span class="sxs-lookup"><span data-stu-id="6ad00-163">The Windows Subsystem for Linux</span></span>
  
   <span data-ttu-id="6ad00-164">Bash on Ubuntu on Windows のこの部分をアップグレードすると、[リリース ノート](./release-notes.md)で概説されている新しい修正が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-164">Upgrading this portion of Bash on Ubuntu on Windows will enable any new fixes outlines in the [release notes](./release-notes.md).</span></span> <span data-ttu-id="6ad00-165">Windows Insider Program をサブスクライブしていることと、ビルドが最新であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-165">Ensure that you are subscribed to the Windows Insider Program and that your build is up to date.</span></span> <span data-ttu-id="6ad00-166">Ubuntu インスタンスのリセットなど、より細かな制御を行うには、[コマンド リファレンスに関するページ](./reference.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-166">For finer grain control including resetting your Ubuntu instance check out the [command reference page](./reference.md).</span></span>

2. <span data-ttu-id="6ad00-167">Ubuntu ユーザー バイナリ</span><span class="sxs-lookup"><span data-stu-id="6ad00-167">The Ubuntu user binaries</span></span>

   <span data-ttu-id="6ad00-168">Bash on Ubuntu on Windows のこの部分をアップグレードすると、apt-get を使用してインストールしたアプリケーションを含む Ubuntu ユーザー バイナリにすべての更新プログラムがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-168">Upgrading this portion of Bash on Ubuntu on Windows will install any updates to the Ubuntu user binaries including applications that you have installed via apt-get.</span></span> <span data-ttu-id="6ad00-169">更新するには、Bash で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-169">To update run the following commands in Bash:</span></span>
  
   1. `apt-get update`
   2. `apt-get upgrade`
  
### <a name="apt-get-upgrade-errors"></a><span data-ttu-id="6ad00-170">apt-get アップグレードのエラー</span><span class="sxs-lookup"><span data-stu-id="6ad00-170">Apt-get upgrade errors</span></span>

<span data-ttu-id="6ad00-171">一部のパッケージでは、まだ Microsoft が実装していない機能が使用されています。</span><span class="sxs-lookup"><span data-stu-id="6ad00-171">Some packages use features that we haven't implemented yet.</span></span> <span data-ttu-id="6ad00-172">たとえば、`udev` はまだサポートされていないため、`apt-get upgrade` エラーがいくつか発生します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-172">`udev`, for example, isn't supported yet and causes several `apt-get upgrade` errors.</span></span>

<span data-ttu-id="6ad00-173">`udev` に関連する問題を修正するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6ad00-173">To fix issues related to `udev`, follow the following steps:</span></span>

1. <span data-ttu-id="6ad00-174">次の内容を `/usr/sbin/policy-rc.d` に記述して、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-174">Write the following to `/usr/sbin/policy-rc.d` and save your changes.</span></span>
  
   ```bash
   #!/bin/sh
   exit 101
   ```
  
2. <span data-ttu-id="6ad00-175">実行のアクセス許可を `/usr/sbin/policy-rc.d` に追加します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-175">Add execute permissions to `/usr/sbin/policy-rc.d`:</span></span>

   ```bash
   chmod +x /usr/sbin/policy-rc.d
   ```
  
3. <span data-ttu-id="6ad00-176">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-176">Run the following commands:</span></span>

   ```bash
   dpkg-divert --local --rename --add /sbin/initctl
   ln -s /bin/true /sbin/initctl
   ```
  
### <a name="error-0x80040306-on-installation"></a><span data-ttu-id="6ad00-177">"Error:0x80040306" がインストール時に発生</span><span class="sxs-lookup"><span data-stu-id="6ad00-177">"Error: 0x80040306" on installation</span></span>

<span data-ttu-id="6ad00-178">これは、従来のコンソールがサポートされていないということと関連があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-178">This has to do with the fact that we do not support legacy console.</span></span>
<span data-ttu-id="6ad00-179">従来のコンソールをオフにするには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-179">To turn off legacy console:</span></span>

1. <span data-ttu-id="6ad00-180">cmd.exe を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-180">Open cmd.exe</span></span>
1. <span data-ttu-id="6ad00-181">タイトル バーを右クリックして、[プロパティ] を選択し、[従来のコンソールを使う] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="6ad00-181">Right click title bar -> Properties -> Uncheck Use legacy console</span></span>
1. <span data-ttu-id="6ad00-182">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ad00-182">Click OK</span></span>

### <a name="error-0x80040154-after-windows-update"></a><span data-ttu-id="6ad00-183">"Error:0x80040154" が Windows Update 後に発生</span><span class="sxs-lookup"><span data-stu-id="6ad00-183">"Error: 0x80040154" after Windows update</span></span>

<span data-ttu-id="6ad00-184">Windows Update 時に Windows Subsystem for Linux 機能が無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-184">The Windows Subsystem for Linux feature may be disabled during a Windows update.</span></span> <span data-ttu-id="6ad00-185">その場合は、この Windows 機能を再度有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-185">If this happens the Windows feature must be re-enabled.</span></span> <span data-ttu-id="6ad00-186">Windows Subsystem for Linux を有効にする手順については、[インストール ガイド](./install-win10.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-186">Instructions for enabling the Windows Subsystem for Linux can be found in the [Installation Guide](./install-win10.md).</span></span>

### <a name="changing-the-display-language"></a><span data-ttu-id="6ad00-187">表示言語の変更</span><span class="sxs-lookup"><span data-stu-id="6ad00-187">Changing the display language</span></span>

<span data-ttu-id="6ad00-188">WSL インストールでは、Windows インストールのロケールに合わせて Ubuntu ロケールを自動的に変更しようとします。</span><span class="sxs-lookup"><span data-stu-id="6ad00-188">WSL install will try to automatically change the Ubuntu locale to match the locale of your Windows install.</span></span>  <span data-ttu-id="6ad00-189">この動作が不要な場合は、次のコマンドを実行して、インストールの完了後に Ubuntu ロケールを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-189">If you do not want this behavior you can run this command to change the Ubuntu locale after install completes.</span></span>  <span data-ttu-id="6ad00-190">この変更を有効にするには、bash.exe を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-190">You will have to relaunch bash.exe for this change to take effect.</span></span>

<span data-ttu-id="6ad00-191">次の例は、ロケールを en-US に変更します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-191">The below example changes to locale to en-US:</span></span>

```bash
sudo update-locale LANG=en_US.UTF8
```

### <a name="installation-issues-after-windows-system-restore"></a><span data-ttu-id="6ad00-192">Windows システムの復元後のインストールの問題</span><span class="sxs-lookup"><span data-stu-id="6ad00-192">Installation issues after Windows system restore</span></span>

1. <span data-ttu-id="6ad00-193">`%windir%\System32\Tasks\Microsoft\Windows\Windows Subsystem for Linux` フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-193">Delete the `%windir%\System32\Tasks\Microsoft\Windows\Windows Subsystem for Linux` folder.</span></span> <br/>
  <span data-ttu-id="6ad00-194">**注: オプションの機能が完全にインストールされて動作している場合は、この操作を行わないでください。**</span><span class="sxs-lookup"><span data-stu-id="6ad00-194">**Note: Do not do this if your optional feature is fully installed and working.**</span></span>
2. <span data-ttu-id="6ad00-195">WSL オプション機能を有効にします (まだ有効にされていない場合)</span><span class="sxs-lookup"><span data-stu-id="6ad00-195">Enable the WSL optional feature (if not already)</span></span>
3. <span data-ttu-id="6ad00-196">再起動します</span><span class="sxs-lookup"><span data-stu-id="6ad00-196">Reboot</span></span>
4. <span data-ttu-id="6ad00-197">lxrun /uninstall /full</span><span class="sxs-lookup"><span data-stu-id="6ad00-197">lxrun /uninstall /full</span></span>
5. <span data-ttu-id="6ad00-198">Bash をインストールします</span><span class="sxs-lookup"><span data-stu-id="6ad00-198">Install bash</span></span>

### <a name="no-internet-access-in-wsl"></a><span data-ttu-id="6ad00-199">WSL でインターネットにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="6ad00-199">No internet access in WSL</span></span>

<span data-ttu-id="6ad00-200">一部のユーザーにより、WSL でのインターネット アクセスをブロックする特定のファイアウォール アプリケーションに関する問題が報告されています。</span><span class="sxs-lookup"><span data-stu-id="6ad00-200">Some users have reported issues with specific firewall applications blocking internet access in WSL.</span></span>  <span data-ttu-id="6ad00-201">報告されているファイアウォールは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ad00-201">The firewalls reported are:</span></span>

1. <span data-ttu-id="6ad00-202">Kaspersky</span><span class="sxs-lookup"><span data-stu-id="6ad00-202">Kaspersky</span></span>
2. <span data-ttu-id="6ad00-203">AVG</span><span class="sxs-lookup"><span data-stu-id="6ad00-203">AVG</span></span>
3. <span data-ttu-id="6ad00-204">Avast</span><span class="sxs-lookup"><span data-stu-id="6ad00-204">Avast</span></span>

<span data-ttu-id="6ad00-205">ファイアウォールをオフにすると、アクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-205">In some cases turning off the firewall allows for access.</span></span>  <span data-ttu-id="6ad00-206">場合によっては、ファイアウォールをインストールするだけでアクセスがブロックされるようです。</span><span class="sxs-lookup"><span data-stu-id="6ad00-206">In some cases simply having the firewall installed looks to block access.</span></span>

### <a name="permission-denied-error-when-using-ping"></a><span data-ttu-id="6ad00-207">ping 使用時のアクセス拒否エラー</span><span class="sxs-lookup"><span data-stu-id="6ad00-207">Permission Denied error when using ping</span></span>

<span data-ttu-id="6ad00-208">[Windows Anniversary Update (バージョン 1607)](./release-notes.md#build-14388-to-windows-10-anniversary-update) では、WSL で ping を実行するには、Windows の **管理者特権** が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ad00-208">For [Windows Anniversary Update, version 1607](./release-notes.md#build-14388-to-windows-10-anniversary-update), **administrator privileges** in Windows are required to run ping in WSL.</span></span>  <span data-ttu-id="6ad00-209">ping を実行するには、管理者として Bash on Ubuntu on Windows を実行するか、管理者特権を使用して CMD/PowerShell プロンプトから bash.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-209">To run ping, run Bash on Ubuntu on Windows as an administrator, or run bash.exe from a CMD/PowerShell prompt with administrator privileges.</span></span>

<span data-ttu-id="6ad00-210">Windows の最新バージョン ([Build 14926 以降](./release-notes.md#build-14926)) では、管理者特権は不要になりました。</span><span class="sxs-lookup"><span data-stu-id="6ad00-210">For later versions of Windows, [Build 14926+](./release-notes.md#build-14926), administrator privileges are no longer required.</span></span>

### <a name="bash-is-hung"></a><span data-ttu-id="6ad00-211">Bash がハングしている</span><span class="sxs-lookup"><span data-stu-id="6ad00-211">Bash is hung</span></span>

<span data-ttu-id="6ad00-212">bash を使用しているときに bash がハングしている (またはデッドロックされている) か、入力に応答していないことに気付いた場合は、Microsoft が問題を診断できるようにメモリ ダンプを収集して報告してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-212">If while working with bash, you find that bash is hung (or deadlocked) and not responding to inputs, help us diagnose the issue by collecting and reporting a memory dump.</span></span> <span data-ttu-id="6ad00-213">次の手順によりシステムがクラッシュすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-213">Note that these steps will crash your system.</span></span> <span data-ttu-id="6ad00-214">それが問題である場合は、この操作を行わないでください。または、これを行う前に作業を保存してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-214">Do not do this if you are not comfortable with that or save your work prior to doing this.</span></span>

<span data-ttu-id="6ad00-215">メモリ ダンプを収集するには</span><span class="sxs-lookup"><span data-stu-id="6ad00-215">To collect a memory dump</span></span>

1. <span data-ttu-id="6ad00-216">メモリ ダンプの種類を "完全なメモリ ダンプ" に変更します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-216">Change the memory dump type to "complete memory dump".</span></span> <span data-ttu-id="6ad00-217">ダンプの種類を変更するときに、現在の種類をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-217">While changing the dump type, take a note of your current type.</span></span>

2. <span data-ttu-id="6ad00-218">[こちらの手順](https://techcommunity.microsoft.com/t5/Core-Infrastructure-and-Security/How-to-Force-a-Diagnostic-Memory-Dump-When-a-Computer-Hangs/ba-p/257809)を使用して、キーボード コントロールを使ってクラッシュを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-218">Use the [steps](https://techcommunity.microsoft.com/t5/Core-Infrastructure-and-Security/How-to-Force-a-Diagnostic-Memory-Dump-When-a-Computer-Hangs/ba-p/257809) to configure crash using keyboard control.</span></span>

3. <span data-ttu-id="6ad00-219">ハングまたはデッドロックを再現します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-219">Repro the hang or deadlock.</span></span>

4. <span data-ttu-id="6ad00-220">(2) のキー シーケンスを使用してシステムをクラッシュさせます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-220">Crash the system using the key sequence from (2).</span></span>

5. <span data-ttu-id="6ad00-221">システムはクラッシュし、メモリ ダンプを収集します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-221">The system will crash and collect the memory dump.</span></span>

6. <span data-ttu-id="6ad00-222">システムが再起動したら、memory.dmp を secure@microsoft.com に報告します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-222">Once the system reboots, report the memory.dmp to secure@microsoft.com.</span></span> <span data-ttu-id="6ad00-223">ダンプ ファイルの既定の場所は、%SystemRoot%\memory.dmp です。つまり、C: がシステム ドライブである場合は、C:\Windows\memory.dmp になります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-223">The default location of the dump file is %SystemRoot%\memory.dmp or C:\Windows\memory.dmp if C: is the system drive.</span></span> <span data-ttu-id="6ad00-224">メールには、ダンプは WSL or Bash on Windows チーム向けであることを記載します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-224">In the email, note that the dump is for the WSL or Bash on Windows team.</span></span>

7. <span data-ttu-id="6ad00-225">メモリ ダンプの種類を元の設定に戻します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-225">Restore the memory dump type to the original setting.</span></span>

### <a name="check-your-build-number"></a><span data-ttu-id="6ad00-226">ビルド番号を確認する</span><span class="sxs-lookup"><span data-stu-id="6ad00-226">Check your build number</span></span>

<span data-ttu-id="6ad00-227">PC のアーキテクチャと Windows ビルド番号を確認するには、次を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-227">To find your PC's architecture and Windows build number, open</span></span>  
<span data-ttu-id="6ad00-228">**[設定]**  >  **[システム]**  >  **[バージョン情報]**</span><span class="sxs-lookup"><span data-stu-id="6ad00-228">**Settings** > **System** > **About**</span></span>

<span data-ttu-id="6ad00-229">**[OS ビルド]** フィールドと **[システムの種類]** フィールドを探します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-229">Look for the **OS Build** and **System Type** fields.</span></span>  
    <span data-ttu-id="6ad00-230">![ビルドとシステムの種類のフィールドのスクリーンショット](media/system.png)</span><span class="sxs-lookup"><span data-stu-id="6ad00-230">![Screenshot of Build and System Type fields](media/system.png)</span></span>

<span data-ttu-id="6ad00-231">Windows Server のビルド番号を確認するには、PowerShell で次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-231">To find your Windows Server build number, run the following in PowerShell:</span></span>  

``` PowerShell
systeminfo | Select-String "^OS Name","^OS Version"
```

### <a name="confirm-wsl-is-enabled"></a><span data-ttu-id="6ad00-232">WSL が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="6ad00-232">Confirm WSL is enabled</span></span>

<span data-ttu-id="6ad00-233">Windows Subsystem for Linux が有効になっていることを確認するには、PowerShell で次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-233">You can confirm that the Windows Subsystem for Linux is enabled by running the following in PowerShell:</span></span>  

``` PowerShell
Get-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

### <a name="openssh-server-connection-issues"></a><span data-ttu-id="6ad00-234">OpenSSH サーバーの接続に関する問題</span><span class="sxs-lookup"><span data-stu-id="6ad00-234">OpenSSH-Server connection issues</span></span>

<span data-ttu-id="6ad00-235">SSH サーバーに接続しようとしましたが、次のエラーで失敗しました。"Connection closed by 127.0.0.1 port 22" (127.0.0.1 ポート 22 によって接続は閉じられました)。</span><span class="sxs-lookup"><span data-stu-id="6ad00-235">Trying to connect your SSH server is failed with the following error: "Connection closed by 127.0.0.1 port 22".</span></span>

1. <span data-ttu-id="6ad00-236">OpenSSH サーバーが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-236">Make sure your OpenSSH Server is running:</span></span>

   ```bash
   sudo service ssh status
   ```

   <span data-ttu-id="6ad00-237">次のチュートリアルに従っていることも確認します。 https://help.ubuntu.com/lts/serverguide/openssh-server.html.en</span><span class="sxs-lookup"><span data-stu-id="6ad00-237">and you've followed this tutorial: https://help.ubuntu.com/lts/serverguide/openssh-server.html.en</span></span>

2. <span data-ttu-id="6ad00-238">sshd サービスを停止し、デバッグ モードで sshd を開始します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-238">Stop the sshd service and start sshd in debug mode:</span></span>

   ```bash
   sudo service ssh stop
   sudo /usr/sbin/sshd -d
   ```

3. <span data-ttu-id="6ad00-239">スタートアップ ログを調べて、HostKey が使用可能であり、次のようなログ メッセージが表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-239">Check the startup logs and make sure HostKeys are available and you don't see log messages such as:</span></span>

   ```BASH
   debug1: sshd version OpenSSH_7.2, OpenSSL 1.0.2g  1 Mar 2016
   debug1: key_load_private: incorrect passphrase supplied to decrypt private key
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_rsa_key
   debug1: key_load_private: No such file or directory
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_dsa_key
   debug1: key_load_private: No such file or directory
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_ecdsa_key
   debug1: key_load_private: No such file or directory
   debug1: key_load_public: No such file or directory
   Could not load host key: /etc/ssh/ssh_host_ed25519_key
   ```

<span data-ttu-id="6ad00-240">このようなメッセージが表示されていて、`/etc/ssh/` の下にそれらのキーがない場合は、キーを再生成するか、単に purge openssh-server と install openssh-server を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-240">If you do see such messages and the keys are missing under `/etc/ssh/`, you will have to regenerate the keys or just purge&install openssh-server:</span></span>

```BASH
sudo apt-get purge openssh-server
sudo apt-get install openssh-server
```

### <a name="the-referenced-assembly-could-not-be-found-when-enabling-the-wsl-optional-feature"></a><span data-ttu-id="6ad00-241">"参照されているアセンブリが見つかりませんでした。"</span><span class="sxs-lookup"><span data-stu-id="6ad00-241">"The referenced assembly could not be found."</span></span> <span data-ttu-id="6ad00-242">WSL オプション機能を有効にする場合</span><span class="sxs-lookup"><span data-stu-id="6ad00-242">when enabling the WSL optional feature</span></span>

<span data-ttu-id="6ad00-243">このエラーは、インストール状態が正しくないことに関係があります。</span><span class="sxs-lookup"><span data-stu-id="6ad00-243">This error is related to being in a bad install state.</span></span> <span data-ttu-id="6ad00-244">この問題を解決するには、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-244">Please complete the following steps to try and fix this issue:</span></span>

- <span data-ttu-id="6ad00-245">PowerShell から WSL 機能を有効にするコマンドを実行している場合、代わりに GUI を使用してみてください。[スタート] メニューを開き、[Windows の機能の有効化または無効化] を検索して、一覧で [Windows Subsystem for Linux] を選択すると、オプションのコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-245">If you are running the enable WSL feature command from PowerShell, try using the GUI instead by opening the start menu, searching for 'Turn Windows features on or off' and then in the list select 'Windows Subsystem for Linux' which will install the optional component.</span></span>

- <span data-ttu-id="6ad00-246">[設定]、[更新] の順に移動し、[更新プログラムの確認] をクリックして、Windows のバージョンを更新します</span><span class="sxs-lookup"><span data-stu-id="6ad00-246">Update your version of Windows by going to Settings, Updates, and clicking 'Check for Updates'</span></span>

- <span data-ttu-id="6ad00-247">上記の両方が失敗し、WSL にアクセスする必要がある場合は、インプレース アップグレードを検討してください。インストール メディアを使用して Windows 10 を再インストールし、[すべて保持] を選択することにより、アプリとファイルが確実に保持されます。</span><span class="sxs-lookup"><span data-stu-id="6ad00-247">If both of those fail and you need to access WSL please consider upgrading in place by reinstalling Windows 10 using installation media and selecting 'Keep Everything' to ensure your apps and files are preserved.</span></span> <span data-ttu-id="6ad00-248">これを行うための手順については、[「Windows 10 を再インストールする」のページ](https://support.microsoft.com/help/4000735/windows-10-reinstall)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-248">You can find instructions on how to do so at the [Reinstall Windows 10 page](https://support.microsoft.com/help/4000735/windows-10-reinstall).</span></span>

### <a name="correct-ssh-related-permission-errors"></a><span data-ttu-id="6ad00-249">(SSH 関連の) アクセス許可のエラーを修正する</span><span class="sxs-lookup"><span data-stu-id="6ad00-249">Correct (SSH related) permission errors</span></span>

<span data-ttu-id="6ad00-250">以下のエラーが表示される場合:</span><span class="sxs-lookup"><span data-stu-id="6ad00-250">If you're seeing this error:</span></span>

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0777 for '/home/artur/.ssh/private-key.pem' are too open.
```

<span data-ttu-id="6ad00-251">これを修正するには、```/etc/wsl.conf``` ファイルに以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="6ad00-251">To fix this, append the following to the the ```/etc/wsl.conf``` file:</span></span>

```
[automount]
enabled = true
options = metadata,uid=1000,gid=1000,umask=0022
```

<span data-ttu-id="6ad00-252">このコマンドを追加すると、メタデータが組み込まれ、WSL から見た Windows ファイルに対するファイルのアクセス許可が変更されることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-252">Please note that adding this command will include metadata and modify the file permissions on the Windows files seen from WSL.</span></span> <span data-ttu-id="6ad00-253">詳細については、[ファイル システムのアクセス許可](./file-permissions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ad00-253">Please see the [File System Permissions](./file-permissions.md) for more information.</span></span>