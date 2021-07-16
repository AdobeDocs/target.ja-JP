---
keywords: ターゲット設定;eec;visual experience composer;拡張 experience composer のトラブルシューティング;トラブルシューティング
description: 特定の条件下でAdobe [!DNL Target] 拡張Experience Composer(EEC)で発生することのある問題のトラブルシューティング方法について説明します。
title: 拡張Experience Composerに関連する問題のトラブルシューティング方法を教えてください。
feature: Visual Experience Composer（VEC）
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b623b7ac3793aa340f0d3072e7453bd988b733ac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL Experience Composer の強化r]に関連する問題のトラブルシューティング

[!DNL Adobe Target] [!UICONTROL 拡張Experience Composer](EEC)では、特定の条件下で表示の問題が発生する場合があります。

## EEC で、公開 IP ではアクセスできない内部 QA 用 URL が読み込まれません。 {#section_D29E96911D5C401889B5EACE267F13CF}

これは、次のIPアドレスを許可リストに加えるすることで解決できます。 これらのIPアドレスは、EECプロキシで使用されるAdobeのサーバー用です。 これらは、アクティビティの編集にのみ必要です。サイトの訪問者は、これらのIPアドレスを許可リストに加えるする必要はありません。

次のIPアドレスをITチームに許可リストするよう依頼します。

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

[!DNL Target]には次のエラーメッセージが表示されます。

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

このエラーメッセージが表示される理由と、問題の解決方法は次のとおりです。

* **問題：** Webサイトドメイン(ISP)が拡張Experience Composerをブ [!UICONTROL ロックしています]。

   **解決方法：** 上許可リスト記のIPアドレスをします。

* **問題：** IPアドレスは許可リストに加えるされますが、お使いのWebサイトではTLSバージョン1.2がサポートされていません。現在 [!DNL Target] は、1.2のデフォルト設定を使用しています。18.4.1（2018年4月26日）以前は、デフォルト設定でTLS 1.0がサポートされていました。詳しくは、 [!DNL Target] TLS(TransportLayer Security)暗号化の変更 [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)を参照してください。

   **解決策：**[!UICONTROL 次の質問（TLS 1.2 を使用しているサイトのセキュリティで保護されているページで、拡張 Visual Experience Composer が読み込まれません）を参照してください。]

## TLS 1.0 を使用しているサイトのセキュリティで保護されているページで、EEC が読み込まれません。（EEC のみ） {#section_C5B31E3D32A844F68E5A8153BD17551F}

「サイトのセキュリティで保護されているページに[!UICONTROL 拡張Visual Experience Composer]が読み込まれません」で説明したエラーメッセージが表示される場合があります。 上記のIPアドレスが許可リストに加えるされていても、お使いのWebサイトでTLSバージョン1.2がサポートされていない場合。[!DNL Target]は現在、デフォルト設定の1.2を使用しています。[!DNL Target] 18.4.1（2018年4月25日）より前は、デフォルト設定のTLS 1.0をサポート。詳細レイヤセキュリティ)暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。[

Firefox を使用して、Web サイトの TLS バージョンをチェックする方法は次のとおりです（他のブラウザーでの手順も同様です）。

1. Firefox で対象の Web サイトを開きます。
1. ブラウザーのアドレスバーにある&#x200B;**[!UICONTROL サイトの情報を表示します]**&#x200B;アイコンをクリックします。

   ![](assets/firefox_more_info.png)

1. **[!UICONTROL 接続の詳細を表示]**／**[!UICONTROL 詳細を表示]**&#x200B;をクリックします。

   ![](assets/firefox_more_info_2.png)

1. 「技術情報」の下にある TLS バージョンを確認します。

   ![](assets/firefox_more_info_3.png)

1. Web サイトが TLS 1.0 を示している場合、Target の TLS サポートポリシーの詳細については、[Target の TLS サポートポリシーについては、TLS (Transport Layer Security) 暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)を参照してください。現在までの状況（2018 年 9 月 12 日まで有効）を解決するには、TLS バージョンとドメインの設定について[カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## プロキシが有効なサイトを読み込む際に、タイムアウトまたは「アクセスが拒否されました」というエラーが表示されます。（EEC のみ） {#section_60CBB9022DC449F593606C0E6252302D}

ご使用の環境でプロキシ IP がブロックされていないことを確認してください。
