---
keywords: カスタム条件作成;アルゴリズム;条件;レコメンデーション条件;csv;ftp;csv のアップロード
description: Adobe [!DNL Target] RecommendationsでレコメンデーションをカスタマイズするためにCSV ファイルをアップロードする方法について説明します。
title: ' [!DNL Recommendations]でカスタム条件をアップロードするにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
TQID: https://experienceleague.adobe.com/8gSKOQxHGB5TPe6vdhjgy5sAFxN8O7dodITo7wgrR50
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 696
ht-degree: 35%

---

# カスタム条件のアップロード

CSV ファイルをアップロードして、[!DNL Adobe Target]でレコメンデーションをカスタマイズします。

[!UICONTROL 新しい条件を作成]画面を表示するには、複数の方法があります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** ライブラリ画面で、**[!UICONTROL 条件の作成]** > **[!UICONTROL 条件の作成]**&#x200B;をクリックします。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Visual Experience Composer] （VEC）を使用して[!DNL Recommendations] アクティビティを作成する場合、ページ上の要素を選択し、[!UICONTROL 推奨事項と置換]、[!UICONTROL 推奨事項の挿入]または[!UICONTROL 推奨事項の挿入]をクリックすると、すぐに[!UICONTROL 条件の選択画面]に移動します。 次に、使用可能な条件を選択するか、**[!UICONTROL 条件を作成]**&#x200B;をクリックします。 新しい条件を作成した場合は、他の[!DNL Recommendations] アクティビティで使用するために条件を保存できます。 詳しくは、[Recommendations アクティビティの作成](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md)を参照してください。
* [!DNL Recommendations] アクティビティを編集する場合は、ページの[!UICONTROL おすすめの場所] ボックスをクリックし、**[!UICONTROL 条件の変更]**&#x200B;を選択します。 [!UICONTROL 条件を選択]画面で、**[!UICONTROL 条件を作成]**&#x200B;をクリックします。 新しい条件を保存して、他の[!DNL Recommendations] アクティビティで使用できます。

次の手順では、最初の方法（**[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** ライブラリ画面）を使用して、[!UICONTROL 新規条件を作成]画面にアクセスすることを前提としています。

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL 条件を作成]** > **[!UICONTROL 条件を作成]**&#x200B;をクリックします。

1. 「[基本情報](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info)」セクションに情報を入力します。

1. 「**[!UICONTROL アルゴリズムの種類]**」ドロップダウンリストから、**[!UICONTROL カスタム条件]**&#x200B;を選択します。

1. 「**[!UICONTROL アルゴリズム]**」ドロップダウンリストから、「**[!UICONTROL カスタムアルゴリズム]**」を選択します。

   >[!NOTE]
   >
   >上記の手順により、[!UICONTROL 条件を作成] ダイアログボックスの下部に「[!UICONTROL CSV]をアップロード」セクションが表示されます。

1. （条件付き）「[&#x200B; コンテンツをバックアップ &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)」セクションに情報を入力します。

1. （条件付き）「[包含ルール &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)」セクションに情報を入力します。

1. 「**[!UICONTROL CSVをアップロード]**」セクションで、CSV ファイルの&#x200B;**[!UICONTROL 場所]**&#x200B;を選択します。

   アップロードを成功させるには、CSV ファイルが正しくフォーマットされている必要があります。 「**[!UICONTROL CSV テンプレートのダウンロード]**」をクリックして、正しくフォーマットされた CSV ファイルをダウンロードします。

   次の 2 つの場所のオプションがあります。

   * **FTP:** FTP サーバーからCSV ファイルをアップロードするには、**[!UICONTROL FTP]**&#x200B;を選択し、必要な情報を入力します。 FTPS プロトコルを使用してCSV ファイルを安全に転送するSSLを使用できます。

   * **URL:** CSV ファイルをURLからアップロードするには、**[!UICONTROL URL]**&#x200B;を選択し、フィード URLを入力します。

1. 「**[!UICONTROL 作成]**」をクリックします。

## 注意点

* カスタム条件エンティティ（行）は、最大 1,000 のレコメンデーション品目（列）を含むことができます。

* カスタム条件の更新は、デフォルトでは「累積的」です。 既存のキーと値のペアが、CSV アップロードファイルで指定した新しいキーと値のペアで上書きされます。 CSV アップロードで指定されたキーを持たない既存のキーと値のペアは、引き続き配信でき、CSV ファイルの一部として最後にアップロードされてから31日以内に期限切れになります。

  クライアントケアに連絡して、次回の CSV アップロードに含まれていない既存の結果を破棄できるようにします。 この設定が有効になっている場合、カスタム CSV フィード ファイルに存在するキーのみが配信できます。 この設定は、すべてのカスタム条件に適用されます。

* カスタム条件フィードは 24 時間ごとに更新されます。

  カスタム条件のアップロードと同期のステータスは、[!UICONTROL Recommendations] > [!UICONTROL Criteria] ページで各条件について確認できます。 カスタム条件を編集する際に、[!UICONTROL 編集] ダイアログボックスにステータスを表示することもできます。

* エラーのないアップロードのフローは、[!UICONTROL &#x200B; スケジュール済み] > [!UICONTROL &#x200B; フィードファイルのダウンロード &#x200B;] > [!UICONTROL &#x200B; インポート &#x200B;] > [!UICONTROL 成功]である必要があります。

* [!DNL Target]がアップロードに問題が発生した場合に表示される可能性のあるエラーメッセージは次のとおりです。

  | エラーメッセージ | 詳細 |
  |--- |--- |
  | 不明なエラー | 技術的な内部エラーを示します。 |
  | 解析エラー | フィードファイルの形式に問題がある可能性があります。 ファイル形式を修正し、アルゴリズムを再保存して、ファイルのダウンロードプロセスを再開します。 |
  | サーバーが見つかりません | インターネット上で認識可能な IP またはホスト名を指定します。 |
  | 資格情報エラー | サーバーでアクティブなアカウントの有効なユーザー名とパスワードを指定します。 |
  | ディレクトリが見つかりません | サーバーに存在するディレクトリを指定します。 |
  | ファイルが見つかりません | サーバー上の指定したディレクトリに存在するファイルの名前を指定します。 |
