---
keywords: カスタム条件作成;アルゴリズム;条件;レコメンデーション条件;csv;ftp;csv のアップロード
description: CSV ファイルをアップロードしてレコメンデーションをカスタマイズする方法をAdobe [!DNL Target] Recommendations。
title: Recommendationsでカスタム条件をアップロードする方法を教えてください。
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 39%

---

# ![PREMIUM](/help/main/assets/premium.png) カスタム条件のアップロード

CSV ファイルをアップロードしてでレコメンデーションをカスタマイズ [!DNL Adobe Target].

[!UICONTROL 新しい条件を作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* の **[!UICONTROL Recommendations]** > **[!UICONTROL 条件]** ライブラリ画面、「 **[!UICONTROL 条件の作成]** > **[!UICONTROL 条件の作成]**. ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* を作成する際に、 [!DNL Recommendations] アクティビティ [!UICONTROL Visual Experience Composer] (VEC)、すぐに [!UICONTROL 条件を選択] 画面を表示し、「 [!UICONTROL Recommendationsと置き換える], [!UICONTROL 前にRecommendationsを挿入]または [!UICONTROL 後ろにRecommendationsを挿入]. 次に、使用可能な条件を選択するか、 **[!UICONTROL 条件の作成]**. 新しい条件を作成する場合は、他の条件と共に使用するために条件を保存できます [!DNL Recommendations] アクティビティ。 詳しくは、 [Recommendationsアクティビティの作成](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* [!DNL Recommendations] アクティビティを編集している場合、ページの「 [!UICONTROL レコメンデーションの場所]」ボックスをクリックして、「**[!UICONTROL 条件を変更]**」を選択します。の [!UICONTROL 条件を選択] 画面、クリック **[!UICONTROL 条件の作成]**. 新しい条件を保存して、他のユーザーと共に使用できます [!DNL Recommendations] アクティビティ。

次の手順では、 [!UICONTROL 新しい条件の作成] 画面を次の最初の方法で表示します。の **[!UICONTROL Recommendations]** > **[!UICONTROL 条件]** ライブラリ画面

1. クリック **[!UICONTROL Recommendations]** > **[!UICONTROL 条件]**.

1. 「**[!UICONTROL 条件を作成]**」をクリックします。

1. 次の項目に情報を入力します。 [基本情報](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) 」セクションに入力します。

   1. 次の **[!UICONTROL アルゴリズムを選択]** 「タイプ」ドロップダウンリストで、「 **[!UICONTROL カスタム条件]**.

   1. 次の **[!UICONTROL アルゴリズム]** ドロップダウンリストで、「 **[!UICONTROL カスタムアルゴリズム]**.

      >[!NOTE]
      >
      >上記の手順により、 [!UICONTROL CSV をアップロード] セクションの下部に表示 [!UICONTROL 新しい条件の作成] ダイアログボックス

1. （条件付き） [コンテンツをバックアップ](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) 」セクションに入力します。

1. （条件付き） [インクルージョンルール](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) 」セクションに入力します。

1. 内 **[!UICONTROL CSV をアップロード]** セクションで、 **[!UICONTROL 場所]** を CSV ファイルに追加します。

   ![「CSV のアップロード」セクション](assets/upload-csv.png)

   アップロードを成功させるには、CSV ファイルが正しくフォーマットされている必要があります。「**[!UICONTROL CSV テンプレートのダウンロード]**」をクリックして、正しくフォーマットされた CSV ファイルをダウンロードします。

   次の 2 つの場所のオプションがあります。

   * **FTP：** FTP サーバーから CSV ファイルをアップロードするには、「**[!UICONTROL FTP]**」を選択し、必要な情報を入力します。CSV ファイルを安全に転送するために FTPS プロトコルを使用する SSL を使用できます。
   * **URL:** URL から CSV ファイルをアップロードするには、 **[!UICONTROL URL]**&#x200B;をクリックし、フィード URL を入力します。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 注意点

* カスタム条件エンティティ（行）は、最大 1,000 のレコメンデーション品目（列）を含むことができます。

* カスタム条件の更新は、デフォルトでは「累積的」です。既存のキーと値のペアが、CSV アップロードファイルで指定した新しいキーと値のペアで上書きされます。CSV アップロードで指定されたキーを持たない既存のキーと値のペアは、引き続き配信に使用でき、CSV ファイルの一部として最後にアップロードされた時点から 31 日で期限が切れます。

   クライアントケアに連絡して、次回の CSV アップロードに含まれていない既存の結果を破棄できるようにします。この設定を有効にした場合、カスタム CSV フィードファイルに存在するキーのみを配信に使用できます。 この設定は、すべてのカスタム条件に適用されます。

* カスタム条件フィードは 24 時間ごとに更新されます。

   カスタム条件のアップロードと同期のステータスは、 [!UICONTROL Recommendations] > [!UICONTROL 条件] ページ。 また、「 [!UICONTROL 編集] ダイアログボックスを開きます。

* エラーのないアップロードのフローは、次のようにする必要があります。 [!UICONTROL 予定] > [!UICONTROL フィードファイルのダウンロード] > [!UICONTROL インポート] > [!UICONTROL 成功].

* 次に、 [!DNL Target] アップロードで問題が発生しました：

   | エラーメッセージ | 詳細 |
   |--- |--- |
   | 不明なエラー | 技術的な内部エラーを示します。 |
   | 解析エラー | フィードファイルの形式に問題がある可能性があります。ファイル形式を修正し、アルゴリズムを保存し直すと、ファイルのダウンロードプロセスが再開します。 |
   | サーバーが見つかりません | インターネット上で認識可能な IP またはホスト名を指定します。 |
   | 資格情報エラー | サーバーでアクティブなアカウントの有効なユーザー名とパスワードを指定します。 |
   | ディレクトリが見つかりません | サーバーに存在するディレクトリを指定します。 |
   | ファイルが見つかりません | サーバー上の指定したディレクトリに存在するファイルの名前を指定します。 |

## トレーニングビデオ：Recommendations の条件の作成（12:33）![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています（カスタム条件のアップロードについて詳しくは、11:43 から始まります）。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
