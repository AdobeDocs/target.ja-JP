---
keywords: カスタム条件作成;アルゴリズム;条件;レコメンデーション条件;csv;ftp;csv のアップロード
description: CSV ファイルをアップロードして、Adobe [!DNL Target] Recommendationsでお勧めをカスタマイズする方法を説明します。
title: ' [!DNL Recommendations] にカスタム条件をアップロードするにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 35%

---

# カスタム条件のアップロード

CSV ファイルをアップロードして、[!DNL Adobe Target] でレコメンデーションをカスタマイズします。

[!UICONTROL Create New Criteria] 画面に到達する方法は複数あります。 一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** / **[!UICONTROL Criteria]** ライブラリ画面で、**[!UICONTROL Create Criteria]** / **[!UICONTROL Create Criteria]** をクリックします。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Visual Experience Composer] （VEC）を使用して [!DNL Recommendations] アクティビティを作成している場合は、ページで要素を選択して [!UICONTROL Replace w/ Recommendations]、[!UICONTROL Insert Recommendations Before] または [!UICONTROL Insert Recommendations After] をクリックすると、すぐに [!UICONTROL Select Criteria] の画面が表示されます。 使用可能な条件を選択するか、「**[!UICONTROL Create Criteria]**」をクリックします。 新しい条件を作成する場合は、他の [!DNL Recommendations] アクティビティで使用する条件を保存できます。 詳しくは、[Recommendations アクティビティの作成 ](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) を参照してください。
* [!DNL Recommendations] アクティビティを編集する場合は、ページの [!UICONTROL Recommendations Location] ボックスをクリックし、「**[!UICONTROL Change Criteria]**」を選択します。 [!UICONTROL Select Criteria] の画面で、「**[!UICONTROL Create Criteria]**」をクリックします。 他の [!DNL Recommendations] アクティビティで使用する新しい条件を保存できます。

以下の手順では、最初のメソッド（**[!UICONTROL Recommendations]** / **[!UICONTROL Criteria]** ライブラリ画面）を使用して [!UICONTROL Create New Criteria] ール画面にアクセスすることを想定しています。

1. **[!UICONTROL Recommendations]**／**[!UICONTROL Criteria]**&#x200B;をクリックします。

1. **[!UICONTROL Create Criteria]**／**[!UICONTROL Create Criteria]**&#x200B;をクリックします。

1. 「基本情報 [ セクションに情報を入力し ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) す。

1. 「**[!UICONTROL Select Algorithm Type]**」ドロップダウン・リストから「**[!UICONTROL Custom Criteria]**」を選択します。

1. 「**[!UICONTROL Algorithm]**」ドロップダウン・リストから「**[!UICONTROL Custom Algorithm]**」を選択します。

   >[!NOTE]
   >
   >上記の手順を実行すると、[!UICONTROL Upload CSV] のセクションが [!UICONTROL Create Criteria] のダイアログボックスの下部に表示されます。

1. （条件付き）「コンテンツのバックアップ [ セクションの情報を入力し ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) す。

1. （条件付き）「[ インクルージョンルール ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) セクションの情報を入力します。

1. **[!UICONTROL Upload CSV]** セクションで、CSV ファイルの **[!UICONTROL Location]** を選択します。

アップロードを成功させるには、CSV ファイルが正しくフォーマットされている必要があります。「**[!UICONTROL Download the CSV template]**」をクリックすると、正しい形式の CSV ファイルを取得できます。

次の 2 つの場所のオプションがあります。

    * **FTP:** FTP サーバーから CSV ファイルをアップロードするには、**[!UICONTROL FTP]**を選択してから、必要な情報を入力します。 FTPS プロトコルを使用する SSL を使用して、CSV ファイルを安全に転送できます。
    
    * **URL:**URL から CSV ファイルをアップロードするには、「**[!UICONTROL URL]**」を選択してから、フィード URL を入力します。

1. **[!UICONTROL Create]** をクリックします。

## 注意点

* カスタム条件エンティティ（行）は、最大 1,000 のレコメンデーション品目（列）を含むことができます。

* カスタム条件の更新は、デフォルトでは「累積的」です。既存のキーと値のペアが、CSV アップロードファイルで指定した新しいキーと値のペアで上書きされます。CSV アップロードで指定されたキーを持たない既存のキーと値のペアも引き続き配信でき、CSV ファイルの一部として最後にアップロードされた時点から 31 日以内に期限切れになります。

  クライアントケアに連絡して、次回の CSV アップロードに含まれていない既存の結果を破棄できるようにします。この設定が有効な場合、カスタム CSV フィードファイルに存在するキーのみが配信に使用できます。 この設定は、すべてのカスタム条件に適用されます。

* カスタム条件フィードは 24 時間ごとに更新されます。

  [!UICONTROL Recommendations] / [!UICONTROL Criteria] ページで、各条件に対するカスタム条件のアップロードのアップロードと同期のステータスを確認できます。 また、カスタム条件を編集するときに、[[!UICONTROL Edit]] ダイアログ ボックスにステータスを表示することもできます。

* エラーのないアップロードのフローは、[!UICONTROL Scheduled]/[!UICONTROL Downloading Feed File]/[!UICONTROL Importing]/[!UICONTROL Successful] にする必要があります。

* アップロードで問題が発生した場合に表示される可能性の [!DNL Target] るエラーメッセージを以下に示します。

  | エラーメッセージ | 詳細 |
  |--- |--- |
  | 不明なエラー | 技術的な内部エラーを示します。 |
  | 解析エラー | フィードファイルの形式に問題がある可能性があります。ファイル形式を修正し、アルゴリズムを再保存します。これにより、ファイルダウンロードプロセスが再開されます。 |
  | サーバーが見つかりません | インターネット上で認識可能な IP またはホスト名を指定します。 |
  | 資格情報エラー | サーバーでアクティブなアカウントの有効なユーザー名とパスワードを指定します。 |
  | ディレクトリが見つかりません | サーバーに存在するディレクトリを指定します。 |
  | ファイルが見つかりません | サーバー上の指定したディレクトリに存在するファイルの名前を指定します。 |
