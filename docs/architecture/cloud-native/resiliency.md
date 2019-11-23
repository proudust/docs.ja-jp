---
title: クラウドネイティブの回復性
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |クラウドネイティブの回復性
ms.date: 06/30/2019
ms.openlocfilehash: 680542abc5d8c43c577321d5ae834f0a13290da3
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841043"
---
# <a name="cloud-native-resiliency"></a>クラウドネイティブの回復性

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

回復性とは、障害に対処するシステムの能力であり、引き続き機能します。 エラーを回避することではありません。 しかし、クラウドベースのシステムではこのような障害に対処する必要があり、それに対応するアプリケーションを構築することは避けられません。 回復性の目標は、障害発生後にアプリケーションを完全に機能する状態に戻すことです。

すべてが1つのプロセスで一緒に実行される従来のモノリシックアプリケーションとは異なり、クラウドネイティブシステムは、図6-1 に示すように分散アーキテクチャを採用しています。

![分散型クラウド-ネイティブ環境](./media/distributed-cloud-native-environment.png)

**図 6-1.** 分散型クラウド-ネイティブ環境

前の図では、各クライアント、マイクロサービス、およびクラウドベースの[バッキングサービス](https://12factor.net/backing-services)が個別のプロセスとして実行され、さまざまなサーバーで実行されており、ネットワークベースの呼び出しを介して通信していることがわかります。

では、どのような問題が発生する可能性がありますか。

- 予期しない[ネットワーク待機時間](https://www.techopedia.com/definition/8553/network-latency)。
- [一時的な障害](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults)(一時的なネットワーク接続エラー)。
- 実行時間の長い同期操作によるブロック。
- クラッシュし、再起動または移動されているホストプロセス。
- 短時間応答できないオーバーロードされたマイクロサービス。
- 更新またはスケーリング操作などのインフライト DevOps 操作。
- 1つのノードから別のノードへのサービスの移動などの Orchestrator 操作。
- 汎用ハードウェアからのハードウェア障害。

クラウドベースのインフラストラクチャに分散サービスを展開すると、前の一覧の要因が非常に大きくなり、それらを処理するための防御を設計および開発する必要があります。

小規模な分散システムでは、障害の発生頻度は低くなりますが、システムのスケールアップとスケールアウトの際に、部分的な障害が通常の動作になる点に対して、これらの問題の多くを経験することができます。

そのため、アプリケーションとインフラストラクチャは回復性を備えている必要があります。 以下のセクションでは、アプリケーションに追加できる防御手法と、ユーザーのエクスペリエンスを箇条書きにするために利用できる組み込みのクラウド機能について説明します。

>[!div class="step-by-step"]
>[前へ](azure-data-storage.md)
>[次へ](application-resiliency-patterns.md)