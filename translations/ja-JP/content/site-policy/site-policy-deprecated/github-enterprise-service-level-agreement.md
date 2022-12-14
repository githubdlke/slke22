---
title: GitHub Enterprise サービス レベル アグリーメント
hidden: true
redirect_from:
  - /github-enterprise-cloud-addendum
  - /github-business-cloud-addendum
  - /articles/github-enterprise-cloud-addendum
  - /github/site-policy/github-enterprise-service-level-agreement
  - /github/site-policy-deprecated/github-enterprise-cloud-addendum
versions:
  fpt: '*'
ms.openlocfilehash: e21816ada1c6b6d3062cecb5d4f0144702ea0f8e
ms.sourcegitcommit: 93b306112b5cd5ce482d468a25c9961ad02f87ac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2022
ms.locfileid: '147099283'
---
_これらの契約条件は、2021 年 1 月 4 日より前に製品のライセンスを取得したお客様に適用されます。その日以降に GitHub 製品を購入したお客様は、最新の契約条件として https://www.github.com/enterprise-legal をご覧ください。_

**ショートバージョン:** GitHub は、該当する GitHub サービスに対して、四半期ごとに 99.9% のアップタイムを保証します (「**サービス レベル**」または「**SLA**」)。 GitHub が SLA を満たさない場合、お客様はアカウントに対してサービス クレジットを受け取ることができます (「**サービス クレジット**」)。

各サービスの機能 (「**サービス機能**」) の定義、および過去と現在のアップタイムの確認は、[GitHub Status ページ](https://www.githubstatus.com/)をご覧ください。 本 SLA で使用されている用語のうち定義のないものについては、お客様に適用される契約に定義された意味を持つものとします。

## アップタイム保証

「**アップタイム**」とは、特定の歴四半期において該当する GitHub サービスが利用可能であった分数合計のパーセンテージを指します。 GitHub は、該当する GitHub サービスにおいて 99.9% 以上のアップタイムを維持することをコミットしています。 該当する GitHub サービスに含まれる可能性がある各「サービス機能」に対するアップタイムの計算方法については、以下に記載されています (「**アップタイム計算**」)。 GitHub が SLA を満たしていない場合、お客様は以下の計算 (「**サービス クレジット計算**」) に基づいてサービス クレジットを受け取ることができます。 ダウンタイムは、すべてのお客様に同時に、または同じ方法で影響するわけではないことに留意してください。

| **サービス機能** | **アップタイム計算** | **定義** | **サービス クレジット計算** |
|---|---|---|---|
| **イシュー**、<br>**プル&nbsp;要求**、<br>**Git&nbsp;操作**、<br>**API&nbsp;要求 (サービス機能の場合のみ)** 、<br>**Webhook**、<br>**ページ** | (歴四半期における分数合計 - ダウンタイム)/歴四半期における分数合計 | 「**ダウンタイム**」とは、(a) サービス機能のいずれかにおいてエラーレートが 5% を超えた特定の分数、または (b) GitHub の内部モニタリングシステムと外部モニタリングシステムの組み合わせによってサービスが利用不可能であると判断された分数のいずれかの期間のことです。 | サービス クレジットの権利は、以下のいずれか (両方ではない) の計算に基づきます。 <ul><li>サービス機能のアップタイムが 99.9% 以下、99.0% 超である場合、歴四半期においてサービス機能にお客様が支払った額の 10%。 <BR><BR>OR <BR><BR></li><li>サービス機能のアップタイムが 99.0% 未満である場合、歴四半期においてサービス機能にお客様が支払った額の 25%。</li></ul> | |
| **アクション** | (トリガーされた実行総数 – 実行不能数) / (トリガーされた実行総数) x 100 | 「**トリガーされた実行総数**」とは、歴四半期においてお客様によりトリガーされた全アクションの総数のことです。 <br><br> 「**実行不能数**」とは、トリガーされた実行総数のうち、歴四半期に実行できなかった総数のことです。  トリガーの発生が成功した 5 分後に、アクション履歴ログにおいて出力が捕捉されなかった場合、実行は失敗となります。 | 同上 |
| **パッケージ** | 転送アップタイム = アクションと同じ <br> <br> ストレージアップタイム = 100% - 平均エラー率* <br> <br> *パブリックな用途および総ストレージトランザクションまたはストレージトランザクション失敗として計算されないストレージトランザクション (事前認証の失敗、認証の失敗、ストレージアカウントに対する所定の容量を超えたトランザクションの試行を含む) は、アップタイム計算から除外されます。 | 「**エラー率**」とは、一定の時間 (現在は 1 時間に設定されています) において失敗したストレージ トランザクションの総数を、ストレージ トランザクション総数で割った値です。 所定の 1 時間におけるストレージ トランザクション総数が 0 である場合、その期間のエラー率は 0% となります。 <br><br> 「**平均エラー率**」とは、歴四半期における各時間のエラー率の合計を、歴四半期における総時間数で割ったものです。 | 同上 |

## 除外
(i) 本契約への違反を含む、お客様の作為、不作為、または該当する GitHub サービスの悪用、(ii) お客様のインターネット接続不良、(iii) 不可抗力の事象など、GitHubの合理的な管理を超える要因、および (iv) お客様の側の設備、サービス、その他の技術により生じたサービス機能の障害は、アップタイム計算から除外されます。

## サービス クレジットの償還
GitHub が本 SLA を満たさない場合、お客様は歴四半期末から 30 日以内に GitHub に対して書面で請求することで、サービス クレジットの償還を受けることができます。 サービス クレジットの償還請求ならびに月間または四半期間の GitHub Enterprise Cloud カスタム レポートは、[GitHub Support](https://support.github.com/contact?tags=docs-policy) までお送りください。

サービス クレジットは、お客様のアカウントに返金または付与され、現金に交換することはできず、歴四半期ごとに有料サービスの最大 90 日間に限定され、お客様に未払いの請求書がないことが求められ、GitHub とお客様との契約が終了した時点で無効となります。 サービス クレジットは、本 SLA の義務を GitHub が果たさなかった場合における唯一の救済措置です。
