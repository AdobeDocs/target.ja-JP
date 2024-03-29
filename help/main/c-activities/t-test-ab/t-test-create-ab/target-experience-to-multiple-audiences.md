---
keywords: 複数オーディエンス;エクスペリエンスバージョン;ターゲットエクスペリエンスバージョン
description: 同じエクスペリエンスのバージョンを、 [!DNL Adobe Target] A/B アクティビティ。
title: A/B アクティビティで複数のエクスペリエンスバージョンを使用できますか？
feature: A/B Tests
exl-id: 7afe36f0-ec46-4d63-bfff-45d2c8923a04
source-git-commit: 3adf1e763e6fabec28aacd63219b8e53e638c1b6
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 56%

---

# A/B テストの複数のエクスペリエンスオーディエンス

同じエクスペリエンスのバージョンを、 [!DNL Adobe Target] A/B アクティビティ。 1 つのエクスペリエンスに対して、複数のオーディエンスを [!UICONTROL Visual Experience Composer] (VEC) またはフォームベースの Experience Composer で使用できます。

訪問者は、プロファイルの変更に合わせてエクスペリエンスオーディエンスを切り替えることができます。 訪問者は、アクティビティの有効期間内は同じエクスペリエンスにとどまりません。

例えば、サイトがページや製品を通して一貫性のあるデザインを使用していて、同じエクスペリエンスを複数のオーディエンスに使用したい場合（ブラウザーの言語が異なる訪問者など）、エクスペリエンスのバージョンを複数設定することができます。例えば、英語と日本語の訪問者に同じエクスペリエンスを提示し、テキストだけを訪問者の言語に置き換えることがあります。エクスペリエンスのデータを言語に関係なく収集すれば、レポートは、バージョンのパフォーマンスではなくエクスペリエンスのパフォーマンスを示すことになります。

エクスペリエンスのバージョンを設定する機能がなければ、（この用例では）それぞれの言語に異なるテストを設定し、結果を手動で集計して、両言語で提供した単一のエクスペリエンスがどのようなパフォーマンスを示したかを推定しなければなりません。そのため、結果が不正確になります。テストによっては、訪問者がランダム化されるため、こういった計算が役に立たないこともあります。

1 つのエクスペリエンスから複数のバージョンを作成することで、手動の計算をしたり前提条件を立てたりしなくても、より正確な情報を入手できます。

## シナリオ

地域ターゲット設定のバナーと汎用のバナーの 2 つのエクスペリエンスをテストしています。 地域ごとにバナーを変える必要がありますが、テスト全体では、地域ターゲット設定が汎用コンテンツを表示するよりも適しているかどうかを判断する必要があります。 各場所に個別のエクスペリエンスを設定する場合、汎用バナーに対して測定する際に、地域ターゲット設定が成功目標の達成に役立つかどうかではなく、各地域のパフォーマンスを実際に測定する必要があります。

この場合、必要なのはエクスペリエンスの地域固有のバージョンなので、地域ターゲット設定されていないコントロールに対して地域ターゲット設定されたエクスペリエンスをテストできます。

1. [通常通りに A/B アクティビティを作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)します。

   複数のバージョンを持つエクスペリエンスを設定する際に、次の手順のようにして各バージョンのオーディエンスを選択します。

1. エクスペリエンスを選択し、**[!UICONTROL 設定]**／**[!UICONTROL オーディエンス]**／**[!UICONTROL 複数のオーディエンス]**&#x200B;をクリックします。

   ![「複数のオーディエンス」オプション](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/multiple-audiences-new.png)

1. 「**[!UICONTROL オーディエンスを追加]**」をクリックし、ターゲットにしたい最初のオーディエンスを選択します。各オーディエンスについて繰り返します。

   ![exp-versions 画像](assets/exp-versions.png)

   オーディエンスがまだ存在しない場合は、「[オーディエンスを作成](/help/main/c-target/c-audiences/create-audience.md#task_E18BD77A9A8F4ED0AC50569F94556558)」をクリックして設定します。

   訪問者が 2 つ以上のオーディエンスにあてはまる場合は、すべてのオーディエンスのコンテンツが戻され、そのリストの中で最後のものが実際にページにレンダリングされます。

1. 続けてアクティビティを設定します。

## ベストプラクティス

* 相互に排他的なオーディエンスを選択します。 VEC で作成されたアクティビティの場合、訪問者が複数のオーディエンスと一致する場合は、各オーディエンスのコンテンツが返され、リストに表示された最後のオーディエンスのコンテンツがページに表示されます。
* ダイアグラムで定義されたアクティビティエントリオーディエンスは、エクスペリエンスオーディエンスと AND の条件で組み合わされます。アクティビティに入るためには、訪問者はアクティビティのオーディエンスとエクスペリエンスオーディエンスのうちの 1 つにあてはまらなければなりません。
* レポートのセグメントとして、同じオーディエンスを追加します。これにより、単に「ブラウザー言語 ja_JP」のエクスペリエンス A 対 B の高レベルでテスト結果を確認し、エクスペリエンス A 対 B の低レベルでテスト結果を確認できます。 これは、 [!DNL Target] — ベースのレポート。 [!DNL Analytics] — ベースのレポート。
