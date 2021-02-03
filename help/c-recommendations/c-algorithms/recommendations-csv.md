---
keywords: カスタム条件作成;アルゴリズム;条件;レコメンデーション条件;csv;ftp;csv のアップロード
description: CSV ファイルをアップロードしてレコメンデーションをカスタマイズします。
title: カスタム条件をアップロード
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 64%

---


# ![PREMIUM](/help/assets/premium.png) カスタム条件のアップロード{#upload-custom-criteria}

CSV ファイルをアップロードしてレコメンデーションをカスタマイズします。

[!UICONTROL 新しい条件を作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]**/**[!UICONTROL 条件]**&#x200B;ライブラリ画面で、**[!UICONTROL 条件を作成]**/**[!UICONTROL 条件を作成]**&#x200B;をクリックします。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Visual Experience Composer](VEC)を使用して[!DNL Recommendations]アクティビティを作成する場合、ページ上の要素を選択し、[!UICONTROL Recommendationsを置き換え]、[!UICONTROL Recommendationsを]の前に挿入、または[!UICONTROL Recommendationsを]の後に挿入します。 次に、使用可能な条件を選択するか、「**[!UICONTROL 条件を作成]**」をクリックします。 新しい条件を作成する場合は、他の[!DNL Recommendations]アクティビティで使用するために条件を保存するオプションがあります。 詳しくは、[Recommendationsアクティビティを作成する](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md)を参照してください。
* [!DNL Recommendations] アクティビティを編集している場合、ページの「 [!UICONTROL レコメンデーションの場所]」ボックスをクリックして、「**[!UICONTROL 条件を変更]**」を選択します。[!UICONTROL 条件を選択]画面で、「**[!UICONTROL 条件を作成]**」をクリックします。 他の [!DNL Recommendations] アクティビティで使用するために新しい条件を保存するオプションがあります。

次の手順は、最初の方法を使用して[!UICONTROL 新しい条件を作成]画面にアクセスすることを前提としています。**[!UICONTROL Recommendations]** > **[!UICONTROL 条件]**&#x200B;ライブラリ画面。

1. **[!UICONTROL Recommendations]**/**[!UICONTROL 条件]**&#x200B;をクリックします。

1. **[!UICONTROL 条件を作成]**/**[!UICONTROL カスタム条件をアップロード]**&#x200B;をクリックします。

1. 「[基本情報](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info)」セクションの情報を入力します。

1. 「[データソース](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source)」セクションに情報を入力します。

1. 「[コンテンツ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)」セクションに情報を入力します。

1. （条件付き）「[コンテンツの類似性](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity)」セクションの情報を入力します。

1. （条件付き）「[インクルージョンルール](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion)」セクションの情報を入力します。

1. （条件付き）「[属性の重み付け](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting)」セクションの情報を入力します。

1. 「**[!UICONTROL CSV]**&#x200B;をアップロード」セクションで、CSVファイルの&#x200B;**[!UICONTROL 場所]**&#x200B;を選択します。

   ![「CSV」セクションのアップロード](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   アップロードを成功させるには、CSV ファイルが正しくフォーマットされている必要があります。「**[!UICONTROL CSV テンプレートのダウンロード]**」をクリックして、正しくフォーマットされた CSV ファイルをダウンロードします。

   次の 2 つの場所のオプションがあります。

   * **FTP：** FTP サーバーから CSV ファイルをアップロードするには、「**[!UICONTROL FTP]**」を選択し、必要な情報を入力します。CSV ファイルを安全に送信するために FTPS プロトコルを使用する、SSL の使用を選択することもできます。
   * **URL:URL** からCSVファイルをアップロードするには、「 **[!UICONTROL URL]**」を選択し、フィードURLを入力します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   >[!NOTE]
   >
   >カスタム条件エンティティ（行）は、最大 1,000 のレコメンデーション品目（列）を含むことができます。

カスタム条件の更新は、デフォルトでは「累積的」です。既存のキーと値のペアが、CSV アップロードファイルで指定した新しいキーと値のペアで上書きされます。CSV アップロードで指定されたキーを持たない既存のキーと値のペアは、依然として配信に使用でき、CSV ファイルの一部として最後にアップロードしたときから 31 日で期限が切れます。

クライアントケアに連絡して、次回の CSV アップロードに含まれていない既存の結果を破棄できるようにします。この設定を有効にすると、カスタム CSV フィードファイルに存在するキーだけが配信可能になります。この設定は、すべてのカスタム条件に適用されます。

カスタム条件フィードは 24 時間ごとに更新されます。

カスタム条件のアップロードと同期のステータスは、レコメンデーション／条件ページの各条件カードの下部に表示されます。また、カスタム条件の編集時に編集ダイアログボックスにも表示されます。

エラーが起こらなかった場合のアップロードの流れは、スケジュール設定／フィードファイルのダウンロード／読み込み／成功となります。

[!DNL Target]がアップロードで問題が発生した場合に発生する可能性があるエラーメッセージは、次のとおりです。

| エラーメッセージ | 詳細 |
|--- |--- |
| 不明なエラー | 技術的な内部エラーを示します。 |
| 解析エラー | フィードファイルの形式に問題がある可能性があります。ファイルの形式を修正し、アルゴリズムを保存し直します。そうすると、ファイルのダウンロードプロセスが再度開始されます。 |
| サーバーが見つかりません | インターネット上で認識可能な IP またはホスト名を指定します。 |
| 資格情報エラー | サーバーでアクティブなアカウントの有効なユーザー名とパスワードを指定します。 |
| ディレクトリが見つかりません | サーバーに存在するディレクトリを指定します。 |
| ファイルが見つかりません | サーバー上の指定したディレクトリに存在するファイルの名前を指定します。 |

## トレーニングビデオ：Recommendations の条件の作成（12:33）  ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオには次の情報が含まれています（カスタム条件のアップロードの詳細は、11:43から始まります）。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)