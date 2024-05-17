---
keywords: ターゲット設定;eec;visual experience composer;拡張 experience composer のトラブルシューティング;トラブルシューティング
description: Adobeで発生する場合がある問題のトラブルシューティング方法を説明します [!DNL Target] 特定の条件下での Experience Composer （EEC）の強化。
title: Experience Composer の強化に関連する問題をトラブルシューティングする方法
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 7562a1da201b570ee529db9763ef5f4b463f65a8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 23%

---

# に関連した問題のトラブルシューティング [!UICONTROL Enhanced Experience Composer]

で表示の問題が発生することがある [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] （EEC）一定の条件下で。

## EEC は、パブリック IP でアクセスできない内部 QA URL を読み込みません。 {#section_D29E96911D5C401889B5EACE267F13CF}

これは、次の IP アドレスを許可リストに加えるすることで解決できます。 これらの IP アドレスは、EEC プロキシに使用されるAdobeのサーバー用です。 これらは、アクティビティの編集にのみ必要です。サイトへの訪問者は、これらの IP アドレスの許可リストに加えるは必要ありません。

IT チームに次の IP アドレスを許可リストに加えるするように依頼してください。

* 34.254.77.200
* 54.73.207.147
* 54.229.152.123
* 3.224.194.242
* 54.90.51.39
* 34.228.136.112
* 54.150.116.11
* 18.178.142.8
* 54.199.107.77
* 99.80.139.221
* 54.78.56.224
* 54.247.179.246
* 54.80.219.243
* 34.201.235.54
* 54.196.224.236
* 35.75.212.45
* 52.199.184.130
* 18.180.161.176

次のエラーメッセージが [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![EEC_error 画像](assets/EEC_error.png)

このエラーメッセージが表示される理由と、問題の解決方法は次のとおりです。

* **問題：** Web サイトドメイン（ISP）によりブロックされている [!UICONTROL Enhanced Experience Composer].

  **救済策：** 上記の IP アドレスを許可リストに加えるします。

* **問題：** IP アドレスは許可リストに加えるされますが、お使いの web サイトは TLS バージョン 1.2 をサポートしていません。 [!DNL Target] は現在、デフォルトの設定である 1.2 を使用します。より前 [!DNL Target] 18.4.1 （2018 年 4 月 25 日（PT））。デフォルト設定では、TLS 1.0 がサポートされています。詳しくは、を参照してください [TLS （Transport Layer Security）暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **解決策：** 次の質問（ [!UICONTROL Enhanced Visual Experience Composer] tls 1.2 を使用するサイトのセキュリティで保護されたページに読み込まれません）。

## TLS 1.0 を使用しているサイトのセキュリティで保護されているページで、EEC が読み込まれません。（EEC のみ） {#section_C5B31E3D32A844F68E5A8153BD17551F}

上記のエラーメッセージが「The [!UICONTROL Enhanced Visual Experience Composer] サイトのセキュリティで保護されたページに読み込まれません。」 上記の IP アドレスを許可リストに加えるしたが、web サイトが TLS バージョン 1.2 をサポートしていない場合。 [!DNL Target] は現在、デフォルトの設定である 1.2 を使用します。より前 [!DNL Target] 18.4.1 （2018 年 4 月 25 日（PT））。デフォルト設定では、TLS 1.0 がサポートされています。詳しくは、を参照してください [TLS （Transport Layer Security）暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Firefox を使用して、Web サイトの TLS バージョンをチェックする方法は次のとおりです（他のブラウザーでの手順も同様です）。

1. Firefox で対象の Web サイトを開きます。
1. 「」をクリックします **[!UICONTROL Show Site Information]** アイコンをクリックします。

   ![firefox_more_info 画像](assets/firefox_more_info.png)

1. クリック **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![firefox_more_info_2 画像](assets/firefox_more_info_2.png)

1. 「技術情報」の下にある TLS バージョンを確認します。

   ![firefox_more_info_3 画像](assets/firefox_more_info_3.png)

1. Web サイトで TLS 1.0 が表示されている場合は、を参照してください。 [TLS （Transport Layer Security）暗号化の変更](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} target の TLS サポートポリシーに関する情報。 今のところ状況を修正するには（2018 年 9 月 12 日まで有効）{target=_blank}に連絡してください [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) （TLS バージョンとドメインを使用した設定）。

## プロキシが有効なサイトを読み込む際に、タイムアウトまたは「アクセスが拒否されました」というエラーが表示されます。（EEC のみ） {#section_60CBB9022DC449F593606C0E6252302D}

ご使用の環境でプロキシ IP がブロックされていないことを確認してください。
