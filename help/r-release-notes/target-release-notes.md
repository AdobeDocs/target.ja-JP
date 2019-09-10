---
description: 最新または今後の[!DNL Adobe Target]リリースを参照してください。
keywords: リリースノート
seo-description: 最新または今後の[!DNL Adobe Target]リリースを参照してください。
seo-title: Adobe Target リリースノート（プレリリース）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 9 月 6 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## 発表

**2019年7月1日**

[!UICONTROL エンタープライズ権限] を使用すると [!DNL Target] 、顧客は単一の組織を使用できますが、異なるチームやワークフローのワークスペースに分割することができます。[!UICONTROL エンタープライズ権限] 機能により、チーム間で最適化プログラムを効率的に拡大・縮小できます。この機能は [!DNL Target] UIで使用できましたが、管理APIは2019 [!DNL Target] 年2月リリースまで対応しています。アドビは管理者APIを更新して、統合アカウントを使用して組織で作成されたすべてのワークスペースにアクセスできるようにしました。これにより、管理者APIはデフォルトのワークスペースに制限されていましたが、2019年2月アップデートで [!UICONTROL は承認者] アクセスを持つすべてのワークスペースへのアクセス権が付与されました。

2019 [!DNL Target] 年9月にリリースされたリリースで [!UICONTROL は、次] のアクセス制御をお客様に提供します。

* 統合を適用できるワークスペースを選択できます
* Adobe I/O統合にロールを適用できます。 [!UICONTROL 承認者]、 [!UICONTROL エディター]または [!UICONTROL 監視者]。

**Action Required**:現在、すべてのワークスペースのリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するAPIを利用している顧客は、目的のロールを持つすべてのワークスペースへの既存のAdobe I/O統合アクセス権を付与する必要があります。9月のリリースより前は、製品の役割ドロップダウンリストから選択したロールに関係なく [!UICONTROL 、承認者] アクセスを使用して操作され [!UICONTROL たすべての統合] があります。今後のリリースで、目的の役割を選択できるようになりました。

このアクションは2019年8月 **の間に実行**&#x200B;されます。2019 [!DNL Target] 年9月リリース以降は、アクセス制御がアクティブになり、現在設定されている場合にのみデフォルトのワークスペースへのアクセス権を確認できます。統合の役割を事前に設定することに悪影響はありません。

手順について詳しくは、Adobe I/O統合のワークスペースへ [のアクセス権限の付与およびロールの割り当てを参照](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)してください。

## Target Standard/Premium 19.9.1（2019 年 9 月 10 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) Enterprise権限 | Targetの2019年9月リリースでは、次のアクセス制御をお客様に提供しています。<UL><li>統合を適用するワークスペースを選択できます。</li><li>Adobe I/O統合にロールを適用できます。承認者、エディターまたは監視者。</li></ul>手順について詳しくは、Adobe I/O統合のワークスペースへ [のアクセス権限の付与およびロールの割り当てを参照](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)してください。 |

## Target Standard/Premium 19.9.2（2019 年 9 月 24 日）

このメンテナンスリリースには、次の機能強化が含まれています。

* Visual Experience Composer（VEC）のリッチテキストエディター（RTE）へのセキュリティを含む、いくつかのセキュリティ修正が行われています。（TGT-35383）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
