---
keywords: cookie;cookie;cookie の削除；target cookie の削除；google chrome;chrome;mozilla firefox;firefox;microsoft edge;safari
description: を削除する方法を説明します。 [!DNL Target] ブラウザーの Cookie を使用してエクスペリエンスを検証できます。
title: 以下を削除する方法 [!DNL Target] cookie?
feature: Privacy & Security
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 4%

---

# を削除します。 [!DNL Target] cookie

次の項目を削除できます： [!DNL Adobe Target] ブラウザーの Cookie(mbox) を使用してテストをおこないます。

次がない場合： [!DNL Target] Cookie(mbox) の場合、新しい訪問者と見なされ、新しいエクスペリエンスが表示されます。 ブラウザーの をすべて削除しないで、mbox Cookie を削除する方法はいくつかあります。

>[!NOTE]
>
>以下の手順は、一覧に表示されているブラウザーとバージョンに対して正しく行われます。 インターネットで特定のブラウザーまたはバージョンの手順を検索します。

## を削除します。 [!DNL Target] Google Chrome からの cookie

バージョン 84.0.4147.105

1. 次をクリック： **クロム** メニュー/ **環境設定**.
1. 次をクリック： **プライバシーとセキュリティ** タブをクリックします。
1. クリック **Cookie およびその他のサイトデータ**.
1. クリック **すべての cookie とサイトデータを見る**.
1. を展開します。 `adobe.com` セクションで、 **mbox** Cookie の上にマウスポインターを置いて、削除アイコン (X) をクリックします。

## を削除します。 [!DNL Target] Mozilla Firefox の cookie

バージョン 79.0

### に関連付けられているすべての cookie を削除します。 `adobe.com`

1. 次をクリック： **Firefox** メニュー/ **環境設定**.
1. 次をクリック： **プライバシーとセキュリティ** タブをクリックします。
1. の下 **cookie とサイトデータ**&#x200B;をクリックし、 **データを管理**.
1. を選択します。 `adobe.com` サイトを選択し、 **選択項目を削除**.

   >[!NOTE]
   >
   >これにより、 `adobe.com` サイト。 サイトの個々の cookie を削除する場合は、次の手順に従います。

### 個々の Cookie(mbox) の削除

1. Firefox で、 **ツール** > **Web 開発者** > **ストレージインスペクタ**.
1. 次をクリック： **詳細** タブをクリックします。
1. 削除する Cookie が保持されている Web ページに移動します。
1. を展開します。 **Cookie** 「 」セクションで、「 `https://experience.adobe.com`.
1. を右クリックします。 **mbox** cookie を設定し、「 **削除**.

## を削除します。 [!DNL Target] Microsoft Edge からの Cookie

バージョン 84.0.522.52

1. 次をクリック： **Microsoft Edge** メニュー/ **環境設定**.
1. 次をクリック： **サイトの権限** タブをクリックします。
1. クリック **cookie とサイトデータ**.
1. クリック **すべての cookie とサイトデータを見る**.
1. を展開します。 `adobe.com` セクションで、 **mbox** Cookie の上にマウスポインターを置いて、削除アイコン (X) をクリックします。

## を削除します。 [!DNL Target] Apple Safari からの Cookie

バージョン 13.1.2

### に関連付けられているすべての cookie を削除します。 `adobe.com`

1. 次をクリック： **Safari** メニュー/ **環境設定**.
1. 次をクリック： **プライバシー** タブをクリックします。
1. クリック **Web サイトデータの管理**.
1. 削除する cookie のサイトを選択し、 **削除**.

   >[!NOTE]
   >
   >これにより、 `adobe.com` サイト。 サイトの個々の cookie を削除する場合は、次の手順に従います。

### 個々の Cookie(mbox) の削除

1. 次をクリック： **Safari** メニュー/ **環境設定**.
1. 次をクリック： **詳細** タブをクリックします。
1. を選択します。 **メニューバーに開発メニューを表示** オプション。
1. 削除する Cookie が保持されている Web ページに移動します。
1. 次をクリック： **開発** メニュー/ **Web インスペクタを表示**.
1. 次をクリック： **ストレージ** タブをクリックします。
1. を展開します。 **Cookie** 「 」セクションで、「 `www.adobe.com`.
1. を右クリックします。 **mbox** cookie を設定し、「 **削除**.
