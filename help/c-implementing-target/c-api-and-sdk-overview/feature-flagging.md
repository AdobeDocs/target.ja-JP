---
description: Contemporary technology product teams are adopting continuous delivery principles for product launches. Target helps developers and product teams roll out new product capabilities quickly and efficiently.
keywords: rollout;roll out;continuous delivery;product launch;phased rollout
seo-description: Contemporary technology product teams are adopting continuous delivery principles for product launches. Adobe Target helps developers and product teams roll out new product capabilities quickly and efficiently in a phased rollout.
seo-title: Contemporary technology product teams are adopting continuous delivery principles for product launches. Adobe targetは、開発者や製品チームが新しい製品機能を迅速かつ効率的に展開するのに役立ちます。
solution: Target
title: 機能のフラグ付け
topic: Standard
translation-type: tm+mt
source-git-commit: 08debab3ec3d2f6e6bfd3c42476dc1a021185ab7

---


# 機能のフラグ付け

現代のテクノロジー製品チームは、製品発表に向けて継続的な提供原則を採用しています。 Adobe targetは、開発者や製品チームが新しい製品機能を段階的に効率的に展開できるよう支援します。

次のリンクは、継続的な配信を有効にするために理解する必要がある主要な概念に関する情報を提供します。

* [A/Bテストアクティビティ](/help/c-activities/t-test-ab/test-ab.md)
* [JSONオファー](/help/c-experiences/c-manage-content/create-json-offer.md)
* [オーディエンスの調整](/help/c-target/c-audiences/creating-a-profile-attribute-comparison-audience.md)

## 連続配信

1. デフォルトでは、リリース時に機能を「オフ」にします。

   これを制御するには、サーバー側またはアプリ内変数を使用します。

1. この変数を「on」に設定するTarget JSONオファーを作成します。

1. 2つのエクスペリエンスを含む [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC)でA/Bテストアクティビティを作成し、前の手順で作成したJSONオファーを1つのエクスペリエンスで使用します。

   または

   単一のエクスペリエンスを使用して [Form-Based Experience ComposerでA/Bテストアクティビティを作成し](/help/c-experiences/form-experience-composer.md) 、前の手順で作成したJSONオファーを使用します。

   >[!NOTE]
   >
   >フォームベースのExperience Composerでは、単一のエクスペリエンスでA/Bテストアクティビティを作成できます。 VECを使用して、単一のエクスペリエンスでアクティビティを作成することはできません。

1. アクティビティに対して必要なトラフィック配分を指定します。

   この機能を訪問者の5%にロールアウトして開始する場合は、3つの部分から成るガイド付きワークフローのターゲット設定手順で5を指定し、資格を持つ訪問者の100%をJSONオファー（エクスペリエンスA）を使用したエクスペリエンスに送信します。

   次の図に、2つのエクスペリエンスを持つVECを示します。

   ![VECでの機能フラグ付けのトラフィック配分](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging.png)

   次の図に、単一のエクスペリエンスを含むフォームベースのExperience Composerを示します。

   ![フォームベースのExperience Composerでの機能フラグのトラフィック配分](/help/c-implementing-target/c-api-and-sdk-overview/assets/feature-flagging-form.png)

1. Target UIまたはAPIを使用して5 %ずつ徐々に増やし、100 %のトラフィック配分に到達するまで、このアクティビティへのトラフィック配分を増やすことができます。

   >[!NOTE]
   >
   >A/Bテストアクティビティは、訪問者にとってセッション全体で共通です。 トラフィックの配分を減らすと、この機能を表示し始めた訪問者は、セッションがリセットされるまでこの機能を引き続き表示します。

## A/Bテスト機能

A/B/.Nテスト機能では、上述のアプローチを使用し、以下の改善を行います。

* 各機能のバリアントは、Targetエクスペリエンスを作成する適切なJSONオファーを使用して表す必要があります。
* You can manage traffic allocation for this test in the manner described above.

## パラメータ化されたロールアウト

The method described above helps you manage a controlled rollout.

You can roll out a feature for your beta participants only and then later roll out the feature to all other customers. This can be easily achieved by leveraging Target Location (mbox) parameters or profile parameters. [](/help/c-target/c-audiences/c-target-rules/custom-parameters.md)[](/help/c-target/c-audiences/c-target-rules/visitor-profile.md)These parameters can be used in conjunction with phased traffic allocation.

## Server-side vs. client-side

Feature rollouts and testing can be delivered via Target APIs (and server-side SDKs) as well as the client side SDKs (JS, Mobile SDK). [](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)Webサイト、モバイルアプリ、キオスクのアーキテクチャに応じて、Targetの様々な統合オプションを活用できます。
