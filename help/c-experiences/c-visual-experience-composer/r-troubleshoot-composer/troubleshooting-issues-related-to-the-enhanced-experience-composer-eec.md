---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: 拡張 Experience Composer（EEC）では、特定の状況で表示の問題が起きることがあります。
title: 拡張 Experience Composer に関連する問題のトラブルシューティング
feature: null
uuid: 2ea9a91f-08ca-4a06-ad5d-35ced140db14
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 71%

---


# 拡張 Experience Composer に関連する問題のトラブルシューティング{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

拡張 Experience Composer（EEC）では、特定の状況で表示の問題が起きることがあります。

## EEC で、公開 IP ではアクセスできない内部 QA 用 URL が読み込まれません。（EEC のみ）{#section_D29E96911D5C401889B5EACE267F13CF}

この問題は、次のIPアドレスを許可することで解決できます。 これらの IP アドレスは、拡張 Experience Composer プロキシで使用されるアドビのサーバーのものです。これらは、アクティビティの編集にのみ必要です。サイトへの訪問者には、これらのIPアドレスを許可しておく必要はありません

ITチームに次のIPアドレスを許可リストするよう依頼します。

| 地域 | IP アドレス | ホスト名 |
|--- |--- |--- |
| 米国 | 52.55.99.45 | `us1-proxy.adobemc.com` |
| ヨーロッパ、中東、アフリカ（EMEA） | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| アジア太平洋（APAC） | 52.193.67.35 | `apac1-proxy.adobemc.com` |

Target では次のエラーメッセージが表示される場合があります。

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

このエラーメッセージが表示される理由と、問題の解決方法は次のとおりです。

* **問題：** Web サイトのドメイン（ISP）によって拡張 Experience Composer がブロックされています。

   **Remedy:** 上記のIPアドレスの許可リスト。

* **問題：** IPアドレスは許可されていますが、WebサイトではTLSバージョン1.2がサポートされていません。ターゲットは、デフォルトの設定である1.2を使用しています。ターゲット18.4.1（2018年4月25日）より前は、デフォルトの設定であるTLS 1.0を参照してください [](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)。.

   **解決策：**&#x200B;次の質問（TLS 1.2 を使用しているサイトのセキュリティで保護されているページで、拡張 Visual Experience Composer が読み込まれません）を参照してください。

## TLS 1.0 を使用しているサイトのセキュリティで保護されているページで、EEC が読み込まれません。（EEC のみ）{#section_C5B31E3D32A844F68E5A8153BD17551F}

上述の IP アドレスがホワイトリストに登録されていても、Web サイトが TLS バージョン 1.0 に対応していない場合は、上述のエラーメッセージが表示される場合があります（サイトのセキュリティで保護されているページで、拡張 Visual Experience Composer が読み込まれません）。if the above IP addresses are allowlisted but your website does not support TLS version 1.2. Target currently uses the default configuration of 1.2. Prior to the Target 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Firefox を使用して、Web サイトの TLS バージョンをチェックする方法は次のとおりです（他のブラウザーでの手順も同様です）。

1. Firefox で対象の Web サイトを開きます。
1. ブラウザーのアドレスバーにある&#x200B;**[!UICONTROL サイトの情報を表示します]**&#x200B;アイコンをクリックします。

   ![](assets/firefox_more_info.png)

1. **[!UICONTROL 接続の詳細を表示]**／**[!UICONTROL 詳細を表示]**&#x200B;をクリックします。

   ![](assets/firefox_more_info_2.png)

1. 「技術情報」の下にある TLS バージョンを確認します。

   ![](assets/firefox_more_info_3.png)

1. Web サイトが TLS 1.0 を示している場合、Target の TLS サポートポリシーの詳細については、[Target の TLS サポートポリシーについては、TLS (Transport Layer Security) 暗号化の変更](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)を参照してください。現在までの状況（2018 年 9 月 12 日まで有効）を解決するには、TLS バージョンとドメインの設定について[カスタマーケア](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## プロキシが有効なサイトを読み込む際に、タイムアウトまたは「アクセスが拒否されました」というエラーが表示されます。（EEC のみ）{#section_60CBB9022DC449F593606C0E6252302D}

ご使用の環境でプロキシ IP がブロックされていないことを確認してください。
