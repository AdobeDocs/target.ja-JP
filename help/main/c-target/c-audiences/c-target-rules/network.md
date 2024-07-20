---
keywords: ターゲット設定、network、ターゲットネットワーク、isp、domain name、接続速度、target isp、targetドメイン名、ターゲット接続速度
description: ネットワークの詳細に基づいてオーディエ  [!DNL Adobe Target]  スを作成する方法を説明します。
title: ネットワークオプションに基づいて訪問者をターゲットにできますか？
feature: Audiences
exl-id: 0a479d6d-ca17-43b8-9a42-8e68f31d4d54
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 65%

---

# ネットワーク

ISP、ドメイン名、接続速度などのネットワークの詳細に基づいて、[!DNL Adobe Target] でオーディエンスを作成できます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Network]** をオーディエンスビルダーペインにドラッグ&amp;ドロップします。
1. 「**[!UICONTROL Select]**」をクリックして、次のいずれかのオプションを選択します。

   * **ISP：** ISP は、加入者に対して、通常月額または年額の料金でインターネットアクセスを提供する企業です。多くの ISP は、Web ホスティングや電子メールなどの追加のサービスを提供しています。ISP フィールドには、商用 ISP（Comcast や TimeWarner など）または企業や教育機関などの法人を指定します。

     次に、米国で一般的な ISP の例を示します。

     | 一般名 | ISP 名 | ドメイン名 | サンプルの IP アドレス |
     |---|---|---|---|
     | Cablevision | Cablevision Systems Corp. | &#42;.optonline.net | 68.196.130.239 |
     | CenturyLink | Qwest Communications Company, LLC | &#42;.centurylink.net | 64.40.65.0 |
     | Charter Communications | Charter Communications | &#42;.charter.com | 71.85.225.124 |
     | Comcast | Comcast Cable Communications, Inc. | &#42;.comcast.net | 76.27.24.28 |
     | Cox | Cox Communications Inc. | &#42;cox.net | 68.224.174.22 |
     | Speakeasy | MegaPath Corporation | &#42;.speakeasy.net | 66.93.240.0 |
     | Time Warner | Time Warner Cable Internet LLC | &#42;.res.rr.com | 72.229.28.185 |
     | Verizon FiOS | MCI Communications Services, Inc.（商号：Verizon Business） | &#42;.fios.verizon.net | 173.68.112.34 |
     | Vivint | Smartrove Inc. | &#42;.vivintwireless.net | 170.72.26.105 |
     | AT&amp;T Wireless | AT | &#42;.mycingular.net |  |
     | Sprint mobile | Sprint Personal Communications Systems | IP アドレス |  |
     | T-Mobile | T-Mobile USA, Inc. | IP アドレス | 208.54.86.0 |
     | Verizon Wireless | Cellco Partnership DBA Verizon Wireless | &#42;.myvzw.com | 70.195.74.199 |

     >[!NOTE]
     >
     >ISPに基づいてターゲット設定する場合は、一般名ではなくISP名を使用してください。大文字と小文字を区別するか、すべて小文字の形式を常に使用するようにルールを作成してください。

     ISP およびドメイン名の値をテストできます。[https://www.whoismyisp.org](https://www.whoismyisp.org) は、ターゲット設定に適したリソースです。 上記の表のサンプルの IP アドレスを使用することも、独自の IP アドレスを入力することもできます。その後、`mboxOverride.browserIp= URL` パラメーターを使用して、その IP アドレスを模倣できます。

   * **ドメイン名：** 訪問者の IP アドレスのドメイン名です。 この名前は、[!DNL Target] で使用している web サイトのドメイン名ではありません。 このドメイン名は、訪問者の IP アドレスに関連しており、ホスト名とも呼ばれます。これは ISP 名に似ています。 ホスト名が、ドメイン名ではなく ISP 名をリブランドした会社の古い名前を参照する場合があります。
   * **接続速度：** この速度は、訪問者のインターネットへの接続速度です。 ブロードバンド、ケーブル、ダイアルアップ、モバイル、oc3、oc12、サテライト、t1、t2、ワイヤレス、xdsl などがあります。

     このフィールドは、実際の速度自体ではなく、接続の種類に基づいています。[!DNL Target] では、接続の正確な速度は判断できません。ブロードバンド接続タイプは、他の接続タイプであると判定できず、特定のタイプを選択できない場合に使用されます。

1. （任意）オーディエンスの追加ルールを設定します。
1. **[!UICONTROL Done]** をクリックします。

次の図は、接続速度が [!UICONTROL Mobile] の AT&amp;T を使用する訪問者をターゲットにするオーディエンスを示しています。

![ネットワークターゲット](assets/target_network.png)

## トレーニングビデオ: オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
