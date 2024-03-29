---
keywords: インクルージョンルール；インクルージョン条件；レコメンデーション；プロモーション；プロモーション；動的フィルタリング；動的；パラメーターの一致
description: Adobeで動的にフィルタリングする方法を説明します [!DNL Target] Recommendationsを使用するように設定します。
title: Recommendationsアクティビティでパラメーターの一致でフィルタリングする方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 10%

---

# パラメーターのマッチング

品目（エンティティ）とリクエスト（API または mbox）の値を比較することで、動的にフィルタリングします。

例えば、次の例に示すように、「業種」ページパラメーターまたはデバイスのサイズや位置情報などの他のパラメーターに一致するコンテンツのみをレコメンデーションできます。

* 画面の幅と高さの mbox パラメーターは、モバイル訪問者をターゲットにするのに使用でき、モバイルデバイスとアクセサリのみをレコメンデーションできます。
* 訪問者がページを使用しているモバイルデバイスの画面の高さに一致するか、それを超えるトップセルの携帯電話のみを返すレコメンデーションルールを作成します。
* 地域の位置情報パラメーターを使用して、冬のツールのレコメンデーションを返すことができます。 雪が降る地域の訪問者には、雪が降らない地域の訪問者には、雪吹き機や他の雪除け具を推奨できます。

>[!NOTE]
>
>2016 年 11 月 1 日以前に作成されたアクティビティの場合、「パラメーターのマッチング」フィルターを使用すると配信に失敗します。 この問題を回避する方法は次のとおりです。
>
>* 新しいアクティビティを作成し、条件を追加します。
>* 「パラメーターのマッチング」フィルターを含まない条件を使用します。
>* 条件から「パラメーターのマッチング」フィルターを削除します。


## パラメーターのマッチングの例

[!UICONTROL パラメーターのマッチング] では、次の例に示すように、ページパラメーターまたは訪問者のパラメーター（デバイスディメンションや地域など）に一致するコンテンツをレコメンデーションできます。

[!DNL Recommendations] は、 [!DNL Target] 呼び出し。 この場合、 [!DNL Target] は、 [!DNL Target] を呼び出し、がモバイルデバイスの品目のみをレコメンデーションします。

次に示す Target 呼び出しの例を考えてみましょう。

![Target 呼び出し](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

訪問者が表示しているページに、モバイルデバイス製品が表示されます。

![モバイルデバイス製品](/help/main/c-recommendations/c-algorithms/assets/phones.png)
