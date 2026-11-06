---
source-git-commit: 87c0d2aa67d54dcbc2963be63d2d7ad9c02b6aa9
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 53%
---
# スニペット

## Target Premium の機能 {#premium-note}

>[!NOTE]
>
>この機能は、[Target Premium](/help/main/c-intro/intro.md#premium) ライセンスの一部として利用できます。 [!DNL Target Standard] では、この機能を利用できません。

## Target 権限の更新 {#permissions-update}

>[!IMPORTANT]
>
>[!UICONTROL 製品管理者]および[!UICONTROL システム管理者]の権限を持つ [!DNL Target] ユーザーは、[!DNL Target] での役割に関係なく、[!UICONTROL 管理]ページ上のすべての設定を編集できます。 これらの権限を持たないユーザーには、これらの設定に対して読み取り専用アクセス権があります。

## 更新された Target UI {#updated-ui}

>[!NOTE]
>
>2025年の新機能として、[!DNL Target] では、更新された UI と [!UICONTROL Visual Experience Composer]（VEC）が導入されました。 詳しくは、次のリンクをクリックしてください。
>
>* [[!DNL Target Standard/Premium]  25.2.1（2025年2月17日（PT））リリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2)：[!DNL Target] の[!UICONTROL アクティビティ]、[!UICONTROL レコメンデーション]、[!UICONTROL Visual Experience Composer]（VEC）に関する主な UI の変更の概要について説明します。
>
>* [[!DNL Target Standard/Premium]  25.1.1（2025年1月9日（PT））リリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1)：[!DNL Target] の[!UICONTROL オファーライブラリ] に関する主な UI の変更の概要について説明します。
>
>* [&#x200B; [!DNL Target]  UI &#x200B;](/help/main/c-intro/understand-the-target-ui.md)について：[!DNL Target] に慣れるための概要と、より詳細な情報と手順を説明するリンクを提供します。
>
>* [[!UICONTROL Visual Experience Composer] の変更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)：[!DNL Adobe Target Standard/Premium] 25.2.1 リリース（2015年2月17日（PT））では、更新された [!UICONTROL Visual Experience Composer]（VEC）が導入されています。 この記事では、VEC のレガシーバージョンと更新されたバージョンの違いについて説明します。
>
>* [[!UICONTROL Visual Experience Composer] オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)：この記事では、更新された VEC UI とそのオプションについて説明します。
>
>* [[!DNL Target] UI の更新に関する FAQ](/help/main/c-intro/updated-ui-faq.md)：この FAQ では、ナビゲーションの変更、機能の場所、一時的な UI バージョンの切替スイッチの非推奨（廃止予定）など、新しい [!DNL Target] UI と [!UICONTROL Visual Experience Composer]（VEC）に関するよくある質問について説明します。 マーケター、開発者、管理者のいずれであっても、このFAQは、スムーズに移行し、更新されたUIを最大限に活用するのに役立ちます。

## アクティビティ名ルール {#activity-name-rules}

アクティビティ名の先頭に`=`、`+`、`-`、または`@`を指定することはできません。 アクティビティ名に次の文字シーケンスを含めることはできません：`;=`、`;+`、`;-`、`;@`、`,=`、`,+`、`,-`、`,@`、`["`、または`"]`。

## ターゲティングステップでオーディエンスを選択します {#audience-selection-steps}

1. オーディエンスを変更するには、右側のフレームの&#x200B;**[!UICONTROL 置換]** アイコン（![置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。

1. **[!UICONTROL オーディエンスを追加]** ダイアログボックスで、[目的のオーディエンス &#x200B;](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)を選択し、**[!UICONTROL オーディエンスを割り当て]**&#x200B;をクリックします。

   複数のオーディエンスを組み合わせたオーディエンスを作成するには、**[!UICONTROL オーディエンスを組み合わせる]**&#x200B;をクリックします。 詳しくは、[複数のオーディエンスを組み合わせる](/help/main/c-target/combining-multiple-audiences.md)を参照してください。

   まだ[!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;]にない新しいオーディエンスを作成するには、**[!UICONTROL オーディエンスの作成]**&#x200B;をクリックします。 [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)で、次のいずれかのオプションを選択します。

   * **[!UICONTROL オーディエンスライブラリ]**: [!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;]に保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します。
   * **[!UICONTROL このアクティビティのみ]**: [!UICONTROL &#x200B; オーディエンスライブラリ &#x200B;]に保存されていない[&#x200B; アクティビティ固有のオーディエンス &#x200B;](/help/main/c-target/creating-activity-only-audience.md)を作成し、現在のアクティビティでのみ使用できます。

1. 右側のフレームで「**[!UICONTROL 訪問者の割合]**」をクリックし、アクティビティに参加する対象となる訪問者の割合を選択します。


