---
keywords: ターゲティング;eec;visual experience composer;拡張 experience composer のトラブルシューティング;トラブルシューティング
description: 特定の条件で [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] （EEC）で発生することがある問題のトラブルシューティング方法について説明します。
title: '[!UICONTROL Enhanced Experience Composer]に関連する問題のトラブルシューティング方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
TQID: https://experienceleague.adobe.com/Yan2cKWjs-u9JHQzT-PiRAFdxUJa1JSHS-fT68yxIjg
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 479
ht-degree: 35%

---

# [!UICONTROL Enhanced Experience Composer]に関連する問題のトラブルシューティング

特定の条件で、[!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] （EEC）で表示の問題が発生することがあります。

## EEC で、公開 IP ではアクセスできない内部 QA 用 URL が読み込まれません。 {#section_D29E96911D5C401889B5EACE267F13CF}


+++詳細
この問題は、次のIP アドレスを許可リストに加えるすることで解決できます。 これらのIP アドレスは、EEC プロキシに使用される[!DNL Adobe] サーバー用です。 これらのIP アドレスは、アクティビティ編集にのみ必要です。 サイトへの訪問者は、これらのIP アドレスを許可リストに加えるする必要はありません。

IT部門に次のIP アドレスの許可リストに加えるを依頼します。

### 米国（va7）

40.70.154.136/29
52.254.106.240/28
52.254.106.160/28
52.254.107.16/28
20.186.185.181
20.22.83.112
20.186.185.227
52.254.106.192/28
52.254.106.0/28
52.254.107.128/28
52.254.107.80/28
52.254.106.176/28
52.254.107.32/28
52.254.105.192/28
52.254.107.64/28
52.254.106.208/28
52.254.107.0/28
52.254.106.224/28
20.14.241.153
20.186.185.239
4.152.211.251
52.254.107.144/28
52.254.106.144/28

### EMEA （nld2）

51.138.17.16/28
51.138.17.48/28
51.138.16.128/28
51.138.17.32/28
51.138.16.240/28
51.138.17.112/28
51.138.16.160/28
51.138.16.208/28
51.138.17.80/28
51.138.17.0/28
51.138.17.96/28
51.138.16.144/28
20.31.145.248
20.126.189.248
51.138.16.224/28
51.138.16.192/28
51.138.12.94
51.138.12.11
51.138.16.176/28
51.138.12.100
51.138.17.64/28
51.138.12.160/28

### APAC （aus）

20.43.104.160/28
20.227.35.177
20.40.188.227
20.43.104.112/28
20.43.104.128/28
20.43.104.144/28
20.40.188.166
20.53.206.128
20.43.104.80/28
20.43.104.16/28
20.43.105.48/28
20.43.104.96/28
20.43.104.48/28
20.40.188.194
20.43.104.32/28
20.40.191.224/28
20.43.105.16/28
20.40.191.96/28
20.43.104.176/28
20.40.191.240/28
20.43.104.64/28
20.43.105.32/28
20.43.104.192/28
20.43.105.0/28
20.43.104.0/28

### レガシーIP アドレス

以下のレガシーIP アドレスは、追って通知があるまで引き続き許可リストに加えるする必要があります。

34.254.77.200
54.73.207.147
54.229.152.123
3.224.194.242
54.90.51.39
34.228.136.112
54.150.116.11
18.178.142.8
54.199.107.77
99.80.139.221
54.78.56.224
54.247.179.246
54.80.219.243
34.201.235.54
54.196.224.236
35.75.212.45
52.199.184.130
18.180.161.176

[!DNL Target]に次のエラーメッセージが表示される場合があります。

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error イメージ &#x200B;](assets/EEC_error.png)

このエラーメッセージが表示される理由と、問題の解決方法は次のとおりです。

* **問題：**&#x200B;お使いのweb サイト ドメイン （ISP）が[!UICONTROL Enhanced Experience Composer]をブロックしています。

  **救済策：** – 上記のIP アドレスを許可リストに加えるします。

* **問題：** IP アドレスは許可リストに加えるされていますが、Web サイトではTLS バージョン 1.2はサポートされていません。 [!DNL Target]は現在、1.2のデフォルト設定を使用しています。 [!DNL Target] 18.4.1 （2018年4月25日）より前のデフォルト設定では、TLS 1.0がサポートされていました。 詳しくは、[TLS（トランスポートレイヤーセキュリティ）暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=ja){target=_blank}を参照してください。

  **解決策：**&#x200B;次の質問を参照してください（TLS 1.2を使用するサイトの安全なページで[!UICONTROL Enhanced Visual Experience Composer]が読み込まれません）。

+++

## TLS 1.0 を使用しているサイトのセキュリティで保護されているページで、EEC が読み込まれません。 （EEC のみ） {#section_C5B31E3D32A844F68E5A8153BD17551F}

+++詳細
上記のエラーメッセージが「サイトの安全なページで[!UICONTROL Enhanced Visual Experience Composer]が読み込まれない」に表示される場合があります。 上記のIP アドレスが許可リストに加えるされていても、web サイトでTLS バージョン 1.2がサポートされていない場合。 [!DNL Target]は現在、1.2のデフォルト設定を使用しています。 [!DNL Target] 18.4.1 （2018年4月25日）より前のデフォルト設定では、TLS 1.0がサポートされていました。 詳しくは、[TLS（トランスポートレイヤーセキュリティ）暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=ja){target=_blank}を参照してください。

Firefox を使用して、Web サイトの TLS バージョンをチェックする方法は次のとおりです（他のブラウザーでの手順も同様です）。

1. Firefox で対象の Web サイトを開きます。
1. ブラウザーのアドレスバーの&#x200B;**[!UICONTROL Show Site Information]** アイコンをクリックします。

   ![firefox_more_info image](assets/firefox_more_info.png)

1. **[!UICONTROL Show Connection Details]**／**[!UICONTROL More Information]**&#x200B;をクリックします。

   ![firefox_more_info_2 image](assets/firefox_more_info_2.png)

1. 「技術情報」の下にある TLS バージョンを確認します。

   ![firefox_more_info_3 image](assets/firefox_more_info_3.png)

1. Web サイトにTLS 1.0が表示されていることがわかったら、TargetのTLS サポートポリシーについて詳しくは、[TLS （Transport Layer Security）暗号化変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html?lang=ja){target=_blank}を参照してください。 現在の状況を解決するには（2018年9月12日まで有効） {target=_blank}、TLS バージョンとドメインを使用した設定については、[&#x200B; カスタマーケア &#x200B;](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

+++

## プロキシが有効なサイトを読み込む際に、タイムアウトまたは「アクセスが拒否されました」というエラーが表示されます。 （EEC のみ） {#section_60CBB9022DC449F593606C0E6252302D}

+++詳細
ご使用の環境でプロキシ IP がブロックされていないことを確認してください。

+++
