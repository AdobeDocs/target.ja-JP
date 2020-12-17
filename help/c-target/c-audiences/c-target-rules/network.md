---
keywords: Targeting;network;target network;isp;domain name;connection speed;target isp;target domain name;target connection speed
description: Adobe Target でネットワークの詳細に基づいたオーディエンスを作成できます。
title: Adobe Targetオーディエンスのネットワークオプション
feature: audiences
translation-type: tm+mt
source-git-commit: fe6826e25b2d7c66ab245492f610585d0f5b3d69
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 98%

---


# ネットワーク{#network}

ネットワークの詳細に基づいたオーディエンスを作成できます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付けます。
1. **[!UICONTROL ルールを追加]**／**[!UICONTROL ネットワーク]**&#x200B;をクリックします。
1. 「**[!UICONTROL 選択]**」をクリックし、次のいずれかのオプションを選択します。

   * **ISP：** ISP は、加入者に対して、通常月額または年額の料金でインターネットアクセスを提供する企業です。多くの ISP は、Web ホスティングや電子メールなどの追加のサービスを提供しています。ISP フィールドには、商用 ISP（Comcast や TimeWarner など）または企業や教育機関などの法人を指定します。

      次に、米国で一般的な ISP の例を示します。

      | 一般名 | ISP 名 | ドメイン名 | サンプルの IP アドレス |
      |---|---|---|---|
      | Cablevision | Cablevision Systems Corp. | *.optonline.net | 68.196.130.239 |
      | CenturyLink | Qwest Communications Company, LLC | *.centurylink.net | 64.40.65.0 |
      | Charter Communications | Charter Communications | *.charter.com | 71.85.225.124 |
      | Comcast | Comcast Cable Communications, Inc. | *.comcast.net | 76.27.24.28 |
      | Cox | Cox Communications Inc. | *cox.net | 68.224.174.22 |
      | Speakeasy | MegaPath Corporation | *.speakeasy.net | 66.93.240.0 |
      | Time Warner | Time Warner Cable Internet LLC | *.res.rr.com | 72.229.28.185 |
      | Verizon FiOS | MCI Communications Services, Inc.（商号：Verizon Business） | *.fios.verizon.net | 173.68.112.34 |
      | Vivint | Smartrove Inc. | *.vivintwireless.net | 170.72.26.105 |
      | AT&amp;T Wireless | AT | *.mycingular.net |  |
      | Sprint mobile | Sprint Personal Communications Systems | IP アドレス |  |
      | T-Mobile | T-Mobile USA, Inc. | IP アドレス | 208.54.86.0 |
      | Verizon Wireless | Cellco Partnership DBA Verizon Wireless | *.myvzw.com | 70.195.74.199 |

      >[!NOTE]
      >
      >ISPに基づいてターゲット設定する場合は、一般名ではなくISP名を使用してください。大文字と小文字を区別するか、すべて小文字の形式を常に使用するようにルールを作成してください。

      ISP およびドメイン名の値をテストできます。ターゲット設定については、[](https://www.whoismyisp.org)https://www.whoismyisp.orgを参照してください。上記の表のサンプルの IP アドレスを使用することも、独自の IP アドレスを入力することもできます。その後、`mboxOverride.browserIp= URL` パラメーターを使用して、その IP アドレスを模倣できます。

   * **ドメイン名：**&#x200B;これは、訪問者の IP アドレスのドメイン名です。[!DNL Target] で使用している Web サイトのドメイン名ではありません。このドメイン名は、訪問者の IP アドレスに関連しており、ホスト名とも呼ばれます。通常、この値は ISP 名とよく似ています。ホスト名には、リブランドする前の、会社の古い ISP 名が設定されていることもありますが、ドメイン名ではそのようなことはありません。
   * **接続速度：**&#x200B;これは、訪問者のインターネットへの接続速度です。ブロードバンド、ケーブル、ダイアルアップ、モバイル、oc3、oc12、サテライト、t1、t2、ワイヤレス、xdsl などがあります。

      このフィールドは、実際の速度自体ではなく、接続の種類に基づいています。[!DNL Target] では、接続の正確な速度は判断できません。ブロードバンド接続タイプは、他の接続タイプであると判定できず、特定のタイプを選択できない場合に使用されます。

1. （オプション）「**[!UICONTROL ルールを追加]**」をクリックして、オーディエンス用の追加のルールを設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

以下の図に、[!UICONTROL モバイル]の接続速度の AT&amp;T を使用する訪問者をターゲットにするオーディエンスを示します。

![ネットワークターゲット](assets/target_network.png)

## トレーニングビデオ：オーディエンスの作成

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)