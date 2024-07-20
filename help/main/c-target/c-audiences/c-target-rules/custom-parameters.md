---
keywords: カスタムパラメーター、targetカスタムパラメーター、targetpageparams、ターゲットmboxパラメーター
description: オーディエンスで使用するために、カスタムパラメーターを  [!DNL Adobe Target]  に渡す方法を説明します。
title: カスタムパラメーターに基づいて訪問者をターゲットにできますか？
feature: Audiences
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 38%

---

# カスタムパラメーター

カスタムパラメーターは、[!DNL Adobe Target] の mbox パラメーターです。 mbox に任意の mbox パラメーターを渡すか、`targetPageParams` 関数を使用すると、オーディエンスで使用するためにこれらのパラメーターがここに表示されます。

詳しくは、[ グローバル mbox にパラメーターを渡す ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/global-mbox/pass-parameters-to-global-mbox.html?lang=ja){target=_blank} を参照してください。

mbox パラメーターに基づいてカスタムオーディエンスを作成しているときに、`mboxParameter` で `mboxName` の入力が求められなくなりました。mbox 名はオプションになりました。この変更により、複数の mbox のパラメーターを使用することや、まだエッジで記録されていないパラメーターを参照することができます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. オーディエンスビルダーにドラッグ&amp;ドロップ **[!UICONTROL Custom]** ます。

   目的のパラメーターを選択するには：

   * オーディエンスの作成時に、リストからパラメーター名を選択し、目的のパラメーター名の最初の文字の入力を開始するか、目的のパラメーター名のフルネームを入力します。
   * パラメーター名ではなく mbox 名を覚えている場合は、「[!UICONTROL Filter by]」ドロップダウンリストを使用して、目的のパラメーターを渡す既知の mbox でフィルタリングします。

   いずれの方法でも、mbox とパラメーターの間にリンクはありません。オーディエンスは、そのパラメーターを渡すすべての mbox で、パラメーターに基づいて機能します。

   >[!NOTE]
   >
   >「[!UICONTROL Filter By]」ドロップダウンリストから選択した mbox は、アクティビティの作成時には保存されません。 このオプションを使用すると、選択した mbox に基づいてパラメーターをフィルター処理できます。

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
   * パラメーターが存在する
   * パラメーターがありません
   * パラメーター値が存在する
   * パラメーター値がありません
   * パラメーターまたは値がありません
   * 最初に、
   * 次の語句で終わる

   ![カスタムパラメーターオーディエンス](assets/custom.png)

1. 新しい行に各値を入力します。
1. （任意）オーディエンスの追加ルールを設定します。
1. **[!UICONTROL Done]** をクリックします。

オーディエンスの [ 定義の詳細ポップアップカード ](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) の「**[!UICONTROL Rules]**」セクションにパラメーター名が表示されます。 フィルタリングに使用する mbox への参照はありません。

>[!NOTE]
>
>[!DNL Target] 18.5.1 リリース（2018 年 5 月 22 日（PT））より前に作成されたカスタムオーディエンスの場合、mbox 名はオーディエンスの定義ポップアップカードに表示されません。 カスタムオーディエンスを再度保存して、カードに表示される mbox 名を取得します。

## 注意点 {#considerations}

* オーディエンスおよびアクティビティは、特定の mbox 用に評価されます。例えば、グローバル mbox が特定のパラメーターを渡しても、地域の mbox が渡さない場合、そのパラメーターをターゲットにするアクティビティ/オーディエンスは、地域の mbox では認定されません。
* ターゲティングは、内部 mbox パラメーター（mboxPC、mboxSession、mbox3rdPartyId、mboxMCSDID、mboxMCAVID、mboxMCGVID、mboxCount、mboxId、mboxVersion など）では評価されません。

## トレーニングビデオ：オーディエンスの作成 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
