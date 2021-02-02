# Docker Desktop を Windows 10 Home の WSL 2 環境に導入する

## 概要

Windows 10 Home の場合、Ver. 1909 以前の場合は、Docker コンテナを動かすのに、
Docker Toolbox しか使えない。

Docker Toolbox は、VirtualBox が必要になる。
VirtualBox の Default という VM の上で Docker コンテナを動かす形になる。

ただし、VirtualBox の VM は、プロビジョニングが必要なため、起動に時間が掛かる。

ところが、OS が Ver. 2004 以降になると、Docker Desktop という
別の Docker GUI ツールが利用可能になる。

Docker Desktop は、WSL 2 の Linux 上で Docker コンテナを動かす形になる。

## 環境

- Windows Home 10
- Ver. 2004 以降

## WSL 2 のインストール

まず最初に WSL 2 をインストールする。

### Enable Virtualization  

WSL 2 を起動するためには CPU の Virtualization が有効化されている必要がある。

タスクマネージャーを開いて パフォーマンス > CPU 画面から、 **仮想化: 有効**（Virtualization: Enabled）になっていることを確認する。

もし有効（Enabled）になっていない場合は Bios を開いて CPU Configuration > Intel (AMD) Virtualization Technology: Enabled にする。

![](./task_manager.png)

## Enable Windows Feature

管理者モードで PowerShell を起動して次の 2 つのコマンドを実行します。再起動しないと機能が有効にならないため、コマンドを実行後に再起動する。

```console
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform
```


