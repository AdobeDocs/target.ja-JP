---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: CSV ファイルをアップロードしてレコメンデーションをカスタマイズします。
title: カスタム条件のアップロード
feature: criteria
uuid: e0b4d320-db00-43ad-b49e-ce36c8532320
translation-type: tm+mt
source-git-commit: 108bbe65732b7df20caf9df6b3e5b77e3c31c457
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 63%

---


# ![PREMIUM](/help/assets/premium.png) カスタム条件のアップロード{#upload-custom-criteria}

CSV ファイルをアップロードしてレコメンデーションをカスタマイズします。

[!UICONTROL 新しい条件を作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** ライブラリ画面で、条件を作成 **[!UICONTROL /条件を作成をクリックし]******&#x200B;ます。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* Visual Experience Composer [!DNL Recommendations] (VEC)を使用してアクティビティを作成する場合、ページ上の要素を選択し、「Recommendationsの置き換え、Recommendationsの置き換え、の挿入、Recommendationsの [!UICONTROL 挿入」をクリックした後、すぐに「基準の] 選択 」画面に移動します。 その後、使用可能な条件を選択するか、「条件を **[!UICONTROL 作成]**」をクリックします。 新しい条件を作成する場合は、他の [!DNL Recommendations] アクティビティで使用できるように条件を保存できます。 For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* [!DNL Recommendations] アクティビティを編集している場合、ページの「 [!UICONTROL レコメンデーションの場所]」ボックスをクリックして、「**[!UICONTROL 条件を変更]**」を選択します。On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. 他の [!DNL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順は、最初の方法で  新しい条件を作成画面にアクセスすることを前提としています。 **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** ライブラリ画面。

1. **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]**&#x200B;をクリックします。

1. 条件 **[!UICONTROL を]** 作成 **[!UICONTROL /カスタム条件を]**&#x200B;アップロードをクリックします。

1. Fill in the information in the [Basic Information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info) section.

1. 「 [データソース](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) 」セクションの情報を入力します。

1. Fill in the information in the [Content](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content) section.

1. （条件付き）「 [コンテンツの類似性](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity) 」セクションの情報を入力します。

1. （条件付き）「インクルー [ジョンルール](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 」セクションの情報を入力します。

1. （条件付き入力を参照） [](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting) 。

1. 「 **[!UICONTROL CSVを]** アップロード **[!UICONTROL 」セクションで、CSVファイルの]** 場所を選択します。

   ![「CSV」セクションのアップロード](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   アップロードを成功させるには、CSV ファイルが正しくフォーマットされている必要があります。「**[!UICONTROL CSV テンプレートのダウンロード]**」をクリックして、正しくフォーマットされた CSV ファイルをダウンロードします。

   次の 2 つの場所のオプションがあります。

   * **FTP：** FTP サーバーから CSV ファイルをアップロードするには、「**[!UICONTROL FTP]**」を選択し、必要な情報を入力します。CSV ファイルを安全に送信するために FTPS プロトコルを使用する、SSL の使用を選択することもできます。
   * **URL:** URLからCSVファイルをアップロードするには、「 **[!UICONTROL URL]**」を選択し、フィードURLを入力します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   >[!NOTE]
   >
   >カスタム条件エンティティ（行）は、最大 1,000 のレコメンデーション品目（列）を含むことができます。

カスタム条件の更新は、デフォルトでは「累積的」です。既存のキーと値のペアが、CSV アップロードファイルで指定した新しいキーと値のペアで上書きされます。CSV アップロードで指定されたキーを持たない既存のキーと値のペアは、依然として配信に使用でき、CSV ファイルの一部として最後にアップロードしたときから 31 日で期限が切れます。

クライアントケアに連絡して、次回の CSV アップロードに含まれていない既存の結果を破棄できるようにします。この設定を有効にすると、カスタム CSV フィードファイルに存在するキーだけが配信可能になります。この設定は、すべてのカスタム条件に適用されます。

カスタム条件フィードは 24 時間ごとに更新されます。

カスタム条件のアップロードと同期のステータスは、レコメンデーション／条件ページの各条件カードの下部に表示されます。また、カスタム条件の編集時に編集ダイアログボックスにも表示されます。

エラーが起こらなかった場合のアップロードの流れは、スケジュール設定／フィードファイルのダウンロード／読み込み／成功となります。

The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

| エラーメッセージ | 詳細 |
|--- |--- |
| 不明なエラー | 技術的な内部エラーを示します。 |
| 解析エラー | フィードファイルの形式に問題がある可能性があります。ファイルの形式を修正し、アルゴリズムを保存し直します。そうすると、ファイルのダウンロードプロセスが再度開始されます。 |
| サーバーが見つかりません | インターネット上で認識可能な IP またはホスト名を指定します。 |
| 資格情報エラー | サーバーでアクティブなアカウントの有効なユーザー名とパスワードを指定します。 |
| ディレクトリが見つかりません | サーバーに存在するディレクトリを指定します。 |
| ファイルが見つかりません | サーバー上の指定したディレクトリに存在するファイルの名前を指定します。 |

## トレーニングビデオ：Recommendations の条件の作成（12:33） ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオには次の情報が含まれています（カスタム条件のアップロードの詳細は、11:43から始まります）。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)