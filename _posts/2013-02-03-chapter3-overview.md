---
layout: post
title: "Chapter3. Overview"
description: ""
category: 
tags: []
---
{% include JB/setup %}

# 第三章 アーキテクチャ概要

本章ではInfinibandアーキテクチャにおける機能、能力、要素等の概要について述べ、また主な操作について説明をします。
全体像を簡潔に述べるため、詳細は意図的に割愛をしています。

IBAは複数の独立したプロセッサプラットフォーム(例えばホストプロセッサノード)I/O基盤、I/Oデバイス(図6参照)を接続
するために、システムエリアネットワーク(System Area Network)を定義しました。
IBA SANは単一または複数のコンピュータシステムのためのI/Oとプロセッサ内通信(IPC)の両方をサポートする
通信・管理のための基盤です。IBAシステムは単一のプロセッサといくつかのI/Oデバイスを持った小さなサーバから、
数百のプロセッサと数千のI/Oデバイスを持った並列コンピュータシステムで利用することができます。

*原文はcan rangeとなっていますが、うまく訳せないので「利用できます」としました。*

> Furthermore, the internet protocol(IP) friendly nature of IBA allows bridging to an internet, intranet,
> or connection to remote computer systems.

*うまく訳せないので原文のままです*

IBAは多くのデバイスが保護され遠隔操作環境で広帯域かつ低レイテンシな複合コミュニケーションを多くのデバイス
にもたらすスイッチコミュニケーションファブリックを定義します。

* ファブリックは網がいいんですかね？*

終端のノードは、複数のIBAポートを介して通信をすることができIBAファブリックを通じて複数の経路を活用することができます。
複数のポートとネットワーク接続は耐障害性と広帯域のそれぞれに活用されます。

IBAのハードウェアはCPUからI/O通信作業の負荷を軽減します。これは通信プロトコルが伝統的に持っているオーバヘッド無しに
通信を行うことを可能にします。(訳注: つまりCPUオフロードするということ)。IBA SANはI/OとIPCクライアントに、カーネルの
介在なしに信頼性の高い、耐障害性を持った、ゼロプロセッサコピー機能を提供します。

IBAシステムエリアネットワークーは、スイッチやルータが相互に接続されたファブリック内に、プロセッサノード、I/O装置の集合です。

> An IBA System Area Network consists of processor nodes and I/O units
> connected through an IBA fabric made up of cascaded switches and routers.

*うまく訳せないので原文のままです*

IO装置は、SCSIやLANアダプタと言った単一のASICから、複雑に構成された大規模メモリを搭載した巨大なRAID装置まで利用することができます。

*イメージの貼付け方がわからないので、図6はひとまず省略*