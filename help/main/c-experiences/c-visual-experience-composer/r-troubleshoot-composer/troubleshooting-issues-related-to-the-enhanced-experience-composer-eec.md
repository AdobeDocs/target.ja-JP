---
keywords: ターゲット設定;eec;visual experience composer;拡張 experience composer のトラブルシューティング;トラブルシューティング
description: Adobeで発生することのある問題のトラブルシューティング方法を説明します [!DNL Target] 特定の条件下での Experience Composer(EEC) の拡張。
title: 拡張 Experience Composer に関連する問題のトラブルシューティング方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 38%

---

# [!UICONTROL Experience Composer の強化]に関連する問題のトラブルシューティング

表示の問題が [!DNL Adobe Target] [!UICONTROL 拡張 Experience Composer] (EEC) を使用します。

## EEC で、公開 IP ではアクセスできない内部 QA 用 URL が読み込まれません。 {#section_D29E96911D5C401889B5EACE267F13CF}

これは、次の IP アドレスを許可リストに加えるすることで解決できます。 これらの IP アドレスは、EEC プロキシで使用されるAdobeのサーバー用です。 これらは、アクティビティの編集にのみ必要です。サイトの訪問者は、これらの IP アドレスを許可リストに加えるする必要はありません。

次の IP アドレスを IT チームに許可リストするよう依頼します。

* 34.253.100.20
* 34.248.100.23
* 52.49.228.246
* 54.205.42.123
* 107.22.177.39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

次のエラーメッセージが [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error 画像](assets/EEC_error.png)

このエラーメッセージが表示される理由と、問題の解決方法は次のとおりです。

* **問題：** Web サイトドメイン (ISP) が [!UICONTROL 拡張 Experience Composer].

   **修正：** 許可リスト上記の IP アドレスをします。

* **問題：** IP アドレスは許可リストに加えるされましたが、お使いの Web サイトは TLS バージョン 1.2 をサポートしていません。 [!DNL Target] は現在、1.2 のデフォルト設定を使用しています。 [!DNL Target] 18.4.1（2018 年 4 月 26 日）では、デフォルトの設定で TLS 1.0 がサポートされていました。詳しくは、 [TLS(Transport Layer Security) 暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

   **解決策：**[!UICONTROL 次の質問（TLS 1.2 を使用しているサイトのセキュリティで保護されているページで、拡張 Visual Experience Composer が読み込まれません）を参照してください。]

## TLS 1.0 を使用しているサイトのセキュリティで保護されているページで、EEC が読み込まれません。（EEC のみ） {#section_C5B31E3D32A844F68E5A8153BD17551F}

上記の「 [!UICONTROL 拡張 Visual Experience Composer] 自分のサイトのセキュリティで保護されているページでは読み込まれません。」 上記の IP アドレスが許可リストに加えるされているにもかかわらず、お使いの web サイトが TLS バージョン 1.2 をサポートしていない場合。 [!DNL Target] は現在、1.2 のデフォルト設定を使用しています。 [!DNL Target] 18.4.1（2018 年 4 月 26 日）では、デフォルトの設定で TLS 1.0 がサポートされていました。詳しくは、 [TLS(Transport Layer Security) 暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Firefox を使用して、Web サイトの TLS バージョンをチェックする方法は次のとおりです（他のブラウザーでの手順も同様です）。

1. Firefox で対象の Web サイトを開きます。
1. ブラウザーのアドレスバーにある&#x200B;**[!UICONTROL サイトの情報を表示します]**&#x200B;アイコンをクリックします。

   ![firefox_more_info 画像](assets/firefox_more_info.png)

1. **[!UICONTROL 接続の詳細を表示]**／**[!UICONTROL 詳細を表示]**&#x200B;をクリックします。

   ![firefox_more_info_2 image](assets/firefox_more_info_2.png)

1. 「技術情報」の下にある TLS バージョンを確認します。

   ![firefox_more_info_3 image](assets/firefox_more_info_3.png)

1. Web サイトが TLS 1.0 を表示している場合は、 [TLS(Transport Layer Security) 暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} for information about Target's TLS support policy. To remedy the situation for now (valid until September 12, 2018){target=_blank}、に連絡して [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) を参照してください。

## プロキシが有効なサイトを読み込む際に、タイムアウトまたは「アクセスが拒否されました」というエラーが表示されます。（EEC のみ） {#section_60CBB9022DC449F593606C0E6252302D}

ご使用の環境でプロキシ IP がブロックされていないことを確認してください。
