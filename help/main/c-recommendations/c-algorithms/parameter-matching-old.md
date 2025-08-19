---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；動的；動的フィルタリング；動的；パラメーターのマッチング
description: 項目（エンティティ）をリクエスト（API または mbox）の値と比較して、Adobe [!DNL Target] Recommendations で動的にフィルタリングする方法を説明します。
title: Recommendations アクティビティでパラメーターの一致を使用してフィルタリングする方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 13%

---

# パラメーターのマッチング

リクエスト（API または mbox）の値に対して項目（エンティティ）を比較することで動的にフィルタリングします。

例えば、次の例に示すように、「業界」ページパラメーターまたは他のパラメーター（デバイスのサイズや位置情報など）に一致するコンテンツのみをレコメンデーションします。

* 画面の幅と高さの mbox パラメーターは、モバイル訪問者をターゲットにし、モバイルデバイスとアクセサリのみを推奨するために使用できます。
* 訪問者がページの表示を使用しているモバイルデバイスの画面の高さと一致するか、それを超える、トップセラーの携帯電話のみを返すレコメンデーションルールを作成します。
* 地域のジオロケーションパラメーターを使用して、冬期のツールに関するレコメンデーションを返すことができます。 雪が降る地域の利用者には除雪機などの除雪具を、雪が降らない地域の利用者には推奨しません。

>[!NOTE]
>
>アクティビティが 2016 年 10 月 31 日（PT）より前に作成された場合、「パラメーターのマッチング」フィルターを使用すると、その配信は失敗します。 この問題を回避する方法は次のとおりです。
>
>* 新しいアクティビティを作成し、条件を追加します。
>* 「パラメーターのマッチング」フィルターを含まない条件を使用します。
>* 条件から「パラメーターのマッチング」フィルターを削除します。

## パラメーターのマッチングの例

次の例に示すように、ページのパラメーターまたは訪問者のパラメーターに一致するコンテンツ（デバイスのサイズや位置情報など）をレコメンデーションで [!UICONTROL Parameter Matching] ます。

[!DNL Recommendations] 呼び出 [!DNL Target] で送信されたパラメーター値と一致させることができます。 この場合、[!DNL Target] は、[!DNL Target] 呼び出しで送信された画面の高さと幅のパラメーターに基づいて、訪問者がモバイルデバイスを使用していることを検出し、モバイルデバイスである項目のみをレコメンデーションします。

次の Target 呼び出し例について考えてみます。

![Target 呼び出し ](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪問者が表示しているページには、モバイルデバイス製品が表示されます。

![ モバイル機器製品 ](/help/main/c-recommendations/c-algorithms/assets/phones.png)
