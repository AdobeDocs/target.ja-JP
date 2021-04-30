---
keywords: ターゲット設定;eec;visual experience composer;拡張 experience composer のトラブルシューティング;トラブルシューティング
description: 特定の条件下でAdobe [!DNL Target] 拡張Experience Composer(EEC)で発生することがある問題のトラブルシューティング方法を説明します。
title: 拡張Experience Composerに関連する問題のトラブルシューティング方法を教えてください。
feature: Visual Experience Composer（VEC）
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
translation-type: tm+mt
source-git-commit: 28e21ea0b0e2306a54c9353ae57de7de5d94f564
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 61%

---

# 拡張Experience Composerに関する問題のトラブルシューティング

[!DNL Adobe Target] [!UICONTROL 拡張Experience Composer](EEC)では、特定の状況で表示の問題が発生する場合があります。

## EEC で、公開 IP ではアクセスできない内部 QA 用 URL が読み込まれません。（EEC のみ）{#section_D29E96911D5C401889B5EACE267F13CF}

この問題は、次のIPアドレス許可リストに加えるで解決できます。 これらの IP アドレスは、拡張 Experience Composer プロキシで使用されるアドビのサーバーのものです。これらは、アクティビティの編集にのみ必要です。サイトへの訪問者には、これらのIPアドレスは必要ありま許可リストに加えるせん

次のIPアドレスをITチーム許可リストにするように依頼します。

* 52.16.72.74
* 52.5.174.79
* 54.246.238.65
* 54.249.183.154
* 54.65.105.214
* 54.82.142.68

Target では次のエラーメッセージが表示される場合があります。

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

このエラーメッセージが表示される理由と、問題の解決方法は次のとおりです。

* **問題：** Web サイトのドメイン（ISP）によって拡張 Experience Composer がブロックされています。

   **Remedy：上記のIPアドレスを** 許可リストします。

* **問題：IPアドレス許可リストに加えるはサポートされていますが、WebサイトではTLSバージョン1.2がサポートされていません。ターゲットは現在、デフォルトの設定である1.2を使用しています。ターゲット18.4.1（2018年4月25日）より前は、デフォルトの設定でTLS 1.0がサポートされています。詳細は、暗号化の変更**  [](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。

   **解決策：**&#x200B;次の質問（TLS 1.2 を使用しているサイトのセキュリティで保護されているページで、拡張 Visual Experience Composer が読み込まれません）を参照してください。

## TLS 1.0 を使用しているサイトのセキュリティで保護されているページで、EEC が読み込まれません。（EEC のみ）{#section_C5B31E3D32A844F68E5A8153BD17551F}

上述の IP アドレスがホワイトリストに登録されていても、Web サイトが TLS バージョン 1.0 に対応していない場合は、上述のエラーメッセージが表示される場合があります（サイトのセキュリティで保護されているページで、拡張 Visual Experience Composer が読み込まれません）。上記のIPアドレスが許可リストに加えるTLSバージョン1.2をサポートしていない場合、お使いのWebサイトでは、現在、デフォルトの設定である1.2がターゲットで使用されています。ターゲット18.4.1（2018年4月25日）より前は、デフォルトの設定でサポートされていたTLS 1.0を参照してください。](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)を変更。[

Firefox を使用して、Web サイトの TLS バージョンをチェックする方法は次のとおりです（他のブラウザーでの手順も同様です）。

1. Firefox で対象の Web サイトを開きます。
1. ブラウザーのアドレスバーにある&#x200B;**[!UICONTROL サイトの情報を表示します]**&#x200B;アイコンをクリックします。

   ![](assets/firefox_more_info.png)

1. **[!UICONTROL 接続の詳細を表示]**／**[!UICONTROL 詳細を表示]**&#x200B;をクリックします。

   ![](assets/firefox_more_info_2.png)

1. 「技術情報」の下にある TLS バージョンを確認します。

   ![](assets/firefox_more_info_3.png)

1. Web サイトが TLS 1.0 を示している場合、Target の TLS サポートポリシーの詳細については、[Target の TLS サポートポリシーについては、TLS (Transport Layer Security) 暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)を参照してください。現在までの状況（2018 年 9 月 12 日まで有効）を解決するには、TLS バージョンとドメインの設定について[カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## プロキシが有効なサイトを読み込む際に、タイムアウトまたは「アクセスが拒否されました」というエラーが表示されます。（EEC のみ）{#section_60CBB9022DC449F593606C0E6252302D}

ご使用の環境でプロキシ IP がブロックされていないことを確認してください。
