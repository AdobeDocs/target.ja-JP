---
keywords: 実装;実装;実装;adobe launch;launch;競合;リダイレクト;experience platform launch;platform launch;タグ;adobe platform
description: の実装方法を学ぶ [!DNL Adobe Target] at.js ライブラリの使用 [!DNL Adobe Experience Platform]を使用する場合、 [!DNL Target].
title: ' [!DNL Adobe Experience Platform] を使用して  [!DNL Target]  を実装する方法'
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 96%

---

# [!DNL Target] を使用した [!DNL Adobe Experience Platform] の実装

[!DNL Adobe Experience Platform] のタグは、[!DNL Adobe] の次世代タグ管理機能です。タグは、適切な顧客体験の実現に必要な分析、マーケティングおよび広告タグをデプロイおよび管理するためのシンプルな手段を提供します。

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] は、[!DNL Adobe Experience Platform] のデータ収集テクノロジーのスイートとしてリブランドされました。その結果、製品ドキュメント全体でいくつかの用語の変更がロールアウトされました。用語の変更に関する参照の一覧については、次の[ドキュメント ](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=ja)を参照してください。

詳細な情報を取得できる様々なソースを次の表に示します。

| リソース | 詳細 |
|--- |--- |
| [ [!UICONTROL Adobe Target] の追加](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html?lang=ja#implement-solutions) | このチュートリアルでは、[!DNL Adobe Experience Platform] のタグを使用して web サイトに [!DNL Target] を実装する手順を詳しく説明します。at.js JavaScript ライブラリの追加、グローバル mbox の発行、パラメーターの追加、他のソリューションとの統合といったトピックが含まれます。この記事は、[!DNL Adobe Experience Platform] や他の [!DNL Adobe Experience Cloud] ソリューションの実装方法を示す、より大きなチュートリアルの一部です。 |
| [クイックスタートガイド](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=ja) | 適切な顧客体験の実現に必要な分析、マーケティングおよび広告タグのデプロイおよび管理に関する情報。 |
| [Adobe  [!DNL Target]  拡張機能の概要](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=ja) | [!DNL Adobe Experience Platform] を使用した [!DNL Target] の実装に関する情報 |

## [!DNL Target] 拡張機能を使用して at.js を実装するメリット {#section_48B3F938B6F8491DAF798E0DB54EF304}

次のメリットは、[!DNL Adobe Experience Platform] のタグを使用して at.js を実装する場合にのみ当てはまります。したがって、[!DNL Adobe] では、at.js の手動実装ではなく、[!DNL Adobe Experience Platform] でタグを使用することを強くお勧めします。

* **[!DNL Adobe Analytics] と [!DNL Target] の競合状態の解消：**[!DNL Analytics] 呼び出しは [!DNL Target] 呼び出しより先に実行される可能性があるので、[!DNL Target] 呼び出しは [!DNL Analytics] 呼び出しには結合されません。これにより、データが正しくなくなるおそれがあります。[!DNL Target] 拡張機能では、[!DNL Target] 呼び出しが成否に関わらず完了するまで [!DNL Analytics] ビーコン呼び出しが待機します。[!DNL Adobe Experience Platform] でタグを使用すると、手動で実装する場合に発生する可能性のあるデータ不整合の問題を解決できます。

   >[!NOTE]
   >
   >[!DNL Analytics] 呼び出しが [!DNL Target] 呼び出しを待つように、[!DNL Adobe Analytics] 拡張機能で「[!UICONTROL ビーコンを送信]」アクションを使用します。 カスタムコードを使用して `s.t()` または `s.tl()` を直接呼び出す場合、[!DNL Analytics] 呼び出しは [!DNL Target] 呼び出しが完了するまで待機することはありません。

* **不正なリダイレクトオファー処理の防止：**&#x200B;ページに [!DNL Target] と [!DNL Analytics] があり、[!DNL Target] によってリダイレクトオファーが実行される場合、（ユーザーが別の URL にリダイレクトされようとしているにもかかわらず）[!DNL Analytics] トラッカーが誤ってリクエストをトリガーする状況が発生する可能性があります。[!DNL Adobe Experience Platform] のタグを使用して [!DNL Target] および [!DNL Analytics] を実装する場合、この問題は発生しません。[!DNL Adobe Experience Platform] でタグを使用すると、[!DNL Target] は、[!DNL Analytics] ビーコンリクエストを中止するように [!DNL Analytics] に指示します。
