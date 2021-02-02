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


