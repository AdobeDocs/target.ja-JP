---
keywords: カスタムパラメーター、ターゲットカスタムパラメーター、targetpageparams、ターゲットmboxパラメーター
description: オーディエンスで使用するカスタムパラメーターを [!DNL Adobe Target] に渡す方法について説明します。
title: カスタムパラメーターに基づいて訪問者をターゲティングできますか？
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
TQID: https://experienceleague.adobe.com/IiMsTLXIYWfd8vXInIfyQtFZ4RDNTe28bPfvqFgi77U
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 507
ht-degree: 39%

---

# カスタムパラメーター

カスタムパラメーターは、[!DNL Adobe Target]のmbox パラメーターです。 mbox パラメーターをmboxに渡すか、`targetPageParams`関数を使用すると、これらのパラメーターがオーディエンスで使用するためにここに表示されます。

詳しくは、[ パラメーターをグローバル mboxに渡す](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=ja){target=_blank}を参照してください。

mbox パラメーターに基づいてカスタムオーディエンスを作成しているときに、`mboxParameter` で `mboxName` の入力が求められなくなりました。 mbox 名はオプションになりました。 この変更により、複数の mbox のパラメーターを使用することや、まだエッジで記録されていないパラメーターを参照することができます。

1. [!DNL Target] インターフェイスで、「**[!UICONTROL オーディエンス]**」 > 「**[!UICONTROL オーディエンスを作成]**」をクリックします。
1. オーディエンスに名前を付け、オプションの説明を追加します。
1. **[!UICONTROL カスタム]**&#x200B;をオーディエンスビルダーにドラッグ&amp;ドロップします。

   目的のパラメーターを選択するには：

   * オーディエンスの作成時に、リストからパラメーター名を選択するか、目的のパラメーター名の最初の文字を入力するか、目的のパラメーター名のフルネームを入力します。
   * mbox名を覚えていても、パラメーター名を覚えていない場合は、[!UICONTROL Filter by] ドロップダウンリストを使用して、目的のパラメーターを渡す既知のmboxでフィルタリングします。

   いずれの方法でも、mbox とパラメーターの間にリンクはありません。 オーディエンスは、そのパラメーターを渡すすべてのmboxのパラメーターに基づいて機能します。

   >[!NOTE]
   >
   >[!UICONTROL  フィルター条件] ドロップダウンリストから選択したmboxは、アクティビティの作成時に保存されません。 このオプションを使用すると、選択した mbox に基づいてパラメーターをフィルター処理できます。

   既存のオーディエンスを編集すると、作成時に指定された mbox 名と共にフィルタリング条件が表示されます。

1. 評価基準を選択します。

   * 次を含む（大文字と小文字を区別しない）
   * 次を含まない（大文字と小文字を区別しない）
   * 次と等しい
   * 次と等しくない
   * 次より大きい
   * 次よりも大きいか等しい
   * 次より小さい
   * 次よりも小さいか等しい
   * パラメーターが存在します
   * パラメーターが存在しません
   * パラメーター値が存在します
   * パラメーター値がありません
   * パラメーターまたは値が存在しません
   * 最初に、
   * 次の語句で終わる

   ![カスタムパラメーターオーディエンス](assets/custom.png)

1. 新しい行に各値を入力します。
1. （オプション）オーディエンスの追加ルールを設定します。
1. 「**[!UICONTROL Done]**」をクリックします。

オーディエンスの[定義の詳細ポップアップカード ](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)には、**[!UICONTROL ルール]** セクションにパラメーター名が表示されます。 フィルタリングに使用する mbox への参照はありません。

>[!NOTE]
>
>[!DNL Target] 18.5.1 リリース（2018年5月22日（PT））より前に作成されたカスタムオーディエンスの場合、mbox名はオーディエンスの定義ポップアップカードに表示されません。 カスタムオーディエンスをもう一度保存して、カードに表示されるmbox名を取得します。

## 注意点 {#considerations}

* オーディエンスおよびアクティビティは、特定の mbox 用に評価されます。 例えば、グローバル mboxが特定のパラメーターを渡したが、リージョン mboxが渡さない場合、そのパラメーターのアクティビティ/オーディエンスのターゲットはリージョン mboxで適格ではありません。
* ターゲティングは、mboxPC、mboxSession、mbox3rdPartyId、mboxMCSDID、mboxMCAVID、mboxMCGVID、mboxCount、mboxId、mboxVersionなどの内部mbox パラメーターでは評価されません。

## トレーニングビデオ：オーディエンスの作成![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
