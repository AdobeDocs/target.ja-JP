---
description: Release notes that provide information about features, enhancements, and fixes for the latest or upcoming [!DNL Adobe Target] releases.
keywords: リリースノート
seo-description: '[!DNL Adobe Target]の最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。'
seo-title: Adobe Target リリースノート（プレリリース）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: d675c6875c8474ba490956ea395076eef5b9e58f

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 9 月 24 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## 発表

**2019年7月31日**

[!UICONTROL Enterprise権限では] 、顧客は [!DNL Target] 単一の組織を使用できますが、異なるチームやワークフローのワークスペースに分割できます。 エンタープラ [!UICONTROL イズ権限機能は] 、チーム間で最適化プログラムを効果的に拡大/縮小するのを容易にします。 この機能はUIで使用できましたが、2019年2月のリリ [!DNL Target] ースまで、管理APIには対応するサポートが [!DNL Target] ありませんでした。 アドビは管理APIを更新し、統合アカウントを使用して組織で作成されたすべてのワークスペースにアクセスできるようにしました。 以前は、管理APIはデフォルトのワークスペースに制限されていましたが、2019年2月の更新では、承認者アクセス権を持つすべてのワークスペースに対するアク [!UICONTROL セス権] が付与されました。

今後の2019年9月のリリ [!DNL Target] ースでは、 [!UICONTROL Enterprise権限によって] 、お客様に次のアクセス制御が提供されます。

* 統合を適用できるワークスペースを選択できます
* Adobe I/O統合に次の役割を適用できます。承認 [!UICONTROL 者]、編 [!UICONTROL 集者]、監視 [!UICONTROL 者]。

**必要なアクション**:現在、すべてのワークスペースでリソース（アクティビティ、オーディエンス、オファーおよびレポート）に対するCRUD操作のAPIを利用しているお客様は、目的の役割を持つすべてのワークスペースに対して、既存のAdobe I/O統合アクセス権を付与する必要があります。 9月のリリースより前は、「製品の役割」ドロップダウンリストで選択した役割に関係なく、すべての統合は [!UICONTROL 「承認者」アクセスを使用して] 実行されていました  。 今後のリリースで、目的のロールを選択できるようになりました。

この操作は2019年8月に実行する必要が **あります**。 2019年9月のリリ [!DNL Target] ース以降、アクセスコントロールがアクティブになり、デフォルトのワークスペースのみが現在の設定になっている場合は、そのアクセス権のみが確認されます。 事前に統合ロールを設定しても、悪影響はありません。

手順と詳細については、「Adobe I/O統合にワークスペースへのアク [セス権を付与し、ロールを割り当てる」を参照してください](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。

## Target Standard/Premium 19.9.2（2019 年 9 月 30 日）

このメンテナンスリリースには、次の機能強化が含まれています。

* Visual Experience Composer(VEC)のリッチテキストエディター(RTE)のセキュリティ更新を含む、いくつかのセキュリティ修正が行われました。 （TGT-35383）

## Target Standard/Premium 19.9.1（2019 年 9 月 10 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) Enterprise権限 | Target 2019年9月のリリースでは、Enterprise Permissionsで次のアクセス制御を利用できます。<UL><li>統合を適用できるワークスペースを選択できます。</li><li>Adobe I/O統合に次の役割を適用できます。承認者、編集者または監視者。</li></ul>手順と詳細については、「Adobe I/O統合にワークスペースへのアク [セス権を付与し、ロールを割り当てる」を参照してください](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
