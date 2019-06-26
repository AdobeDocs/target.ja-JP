---
description: Target の従来の API から Adobe I/O の新しい API への移行について説明します。
keywords: api;adobe i/o
seo-description: Target の従来の API から Adobe I/O の新しい API への移行について説明します。
seo-title: Target の従来の API から Adobe I/O への移行
solution: 'Target '
title: Target の従来の API から Adobe I/O への移行
topic: Standard
uuid: f8a0ab54-5840-4430-b9be-19e689b1c09a
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Target の従来の API から Adobe I/O への移行{#transition-from-target-legacy-apis-to-adobe-i-o}

Target の従来の API から Adobe I/O の新しい API への移行について説明します。

Adobe Target Classic の廃止に伴い、Target Classic アカウントに関連付けられている API も利用できなくなりました。ここでは、従来の API ベースの統合を、Adobe I/O ベースの Target API に移行する方法について説明します。

Target API ドキュメントについて詳しくは、[Target API と NodeJS SDK](../../c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md#concept_5718EC1FF2ED4436935D0BCCD7AA29A6).

## 用語 {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| 用語 | 説明 |
|--- |--- |
| 従来の API | Target Classic アカウントに関連付けられている API。これらの API の呼び出しは、ユーザー名とパスワードによる認証に基づいており、ホスト名は `testandtarget.omniture.com` を使用します。API 呼び出しでリクエスト URL にユーザー名とパスワードが含まれている場合は、Adobe I/O API に移行する必要があります。 |
| Adobe I/O | Adobe I/O は Target API 用の新しいゲートウェイです。この API は Target Standard/Premium アカウントに関連付けられています。Adobe I/O の Target API では、安全な企業 API の業界標準である JWT ベースの認証を使用します。 |

## 今後の予定 {#section_A478EBF637554A2DB5A31661955121ED}

Target Classic の廃止に伴い、次の段階を踏んで従来の API が廃止されます。

| 日付 | 詳細 |
|--- |--- |
| 2017 年 10 月 18 日 | 書き込み操作（`saveCampaign`、`copyCampaign`、`saveHTMLOfferContent`、`setCampaignState`）を実行する API メソッドがすべて廃止されました。<br>同日にすべての Target Classic ユーザーアカウントのステータスが読み取り専用に設定されました。 |
| 2017 年 11 月 15 日 | 残りの API が廃止されました。同日に Target Classic のユーザーインターフェイスも廃止されました。 |

Recommendations Classic の API については、この予定の影響はありません。

## 対応するメソッド {#section_DDB42CCC172545B09CB728D794CC466B}

次の表には、従来の API メソッドに対応する新しい Target API メソッドがまとめられています。従来の API による XML 応答とは異なり、新しい API では JSON が返されます。

新しい API の各メソッドをクリックすると、API ドキュメントサイト内のそのメソッドに関する節に移動します。それぞれの API メソッドのサンプルを確認できます。Admin Postman Collection でも、Adobe I/O の新しい Adobe API の各メソッドについて、API 呼び出しのサンプルを確認できます。

| グループ | 従来の API メソッド | 新しい API メソッド | メモ |
|--- |--- |--- |--- |
| キャンペーン／アクティビティ | キャンペーンの作成 | [AB アクティビティの作成](http://developers.adobetarget.com/api/#create-ab-activity)<br>[XT アクティビティの作成](http://developers.adobetarget.com/api/#create-xt-activity) | 新しい API では、AB と XT で別々の作成メソッドを使用します。 |
|  | キャンペーンの更新 | [AB アクティビティの更新](http://developers.adobetarget.com/api/#update-ab-activity)<br>[XT アクティビティの更新](http://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | キャンペーンのコピー | 該当なし | アクティビティの作成 API を使用します。 |
|  | キャンペーンリスト | [アクティビティのリスト](http://developers.adobetarget.com/api/#list-activities) |  |
|  | キャンペーン状態 | [アクティビティ状態の更新](http://developers.adobetarget.com/api/#update-activity-state) |  |
|  | キャンペーン表示 | [ID での AB アクティビティの取得](http://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[ID での XT アクティビティの取得](http://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | サードパーティキャンペーン ID | 該当なし | thirdpartyID を使用する場合は、該当のアクティビティメソッドを使用できます。 |
| オファー | オファー作成 | [オファーの作成](http://developers.adobetarget.com/api/#create-offer) |  |
|  | オファー取得 | [ID でのオファーの取得](http://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | オファーリスト | [オファーのリスト](http://developers.adobetarget.com/api/#list-offers) |  |
|  | フォルダーリスト | 該当なし | Target Standard/Premium ではフォルダーはサポートされていません。 |
| レポート | キャンペーンのパフォーマンスレポート | [AB パフォーマンスレポートの取得](http://developers.adobetarget.com/api/#get-ab-performance-report)<br>[XT パフォーマンスレポートの取得](http://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | 監査レポート | [監査レポートの取得](http://developers.adobetarget.com/api/#get-audit-report) |  |
|  | 1:1 コンテンツレポート | [AP パフォーマンスレポートの取得](http://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| アカウントの設定 | ホストグループの取得 | [環境のリスト](http://developers.adobetarget.com/api/#list-environments) |  |

## 例外 {#section_09CF9A0E289149279783B4801D1B6D4C}

例外の適用が必要な場合は、担当のカスタマーサクセスマネージャーまでお問い合わせください。

## ヘルプ {#section_591F850E2B7A4342B1C233693425415C}

Adobe I/O の新しい Target API への移行について、ご質問がある場合やサポートが必要な場合は、Adobe Target の ClientCare（tt-support@adobe.com）までお問い合わせください。
