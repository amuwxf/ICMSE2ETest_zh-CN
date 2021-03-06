---
title: "会社の電子メールおよびドキュメントを保護する"
description: "会社の電子メールへのアクセスと、電子メールおよび電子メールの添付ファイルのコンテンツの保護を、準拠デバイスのみに許可します。"
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 78d8368e-1bfe-4ac4-991d-467321a76ed7
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: ca54682e87570d558db95c3d66c064c29d791d24
ms.sourcegitcommit: 45ffbe57b8a2ff1ba6d26efde7f4e2fee8495593
translationtype: MT
---
# <a name=""></a>会社の電子メールとドキュメントの保護
会社の電子メールを保護する主な目的は次の 2 つです。

-   準拠デバイスのみに会社の電子メールへのアクセスを許可する

-   電子メールのコンテンツと添付ファイルを保護する

## <a name=""></a>準拠デバイスのみに会社の電子メールへのアクセスを許可する
会社のデータを保護する重要な手順は、強力なパスワードを使用していないデバイス、脱獄されていないデバイス、および暗号化されていないデバイスへのアクセス制限です。Microsoft Intune では、会社のリソースにアクセスするためにユーザーが満たす必要がある条件を設定する機能を提供しています。これは、条件付きアクセスと呼ばれています。

条件付きアクセスは、Intune で設定できる次の 2 つの種類のポリシーによって決定されます。


            **コンプライアンス ポリシー:** デバイスのコンプライアンス対応状態を判断します。 このポリシーは、次のような設定と条件を評価します。

-   
            **PIN とパスワード**︰ IT 部門は、デバイスのロックを解除する前にパスワードを要求するルール、パスワードの複雑さ、パスワードの有効期限、その他のパスワードの設定を作成できます。

-   
            **暗号化**︰ IT 部門は、暗号化されているデバイスへのアクセスを制限できます。

-   
            **デバイスが脱獄またはルート化されていない**︰ Intune は、登録済みのデバイスが脱獄されているかどうかを検出できます。さらに、IT 部門はそのようなデバイスからのアクセスをブロックするポリシーを設定できます。


            **条件付きアクセス ポリシー:** Exchange Online や SharePoint Online などの特定のサービス向けに構成します。 各サービスに、これらのポリシーが適用されるユーザーのグループを定義することができます。 たとえば、財務部門のすべてのユーザーに、登録済みの準拠デバイスから会社の電子メールへのアクセスのみを許可することができます。

## <a name="-"></a>エンド ユーザー エクスペリエンスの概要
ソリューションの実装後、エンドユーザーは、管理されていて、かつ準拠しているデバイスでなければ会社の電子メールにアクセスできなくなります。デバイス上でメールにアクセスできるようになると、社内のデータは保護され、アプリのエコシステムに組み込まれ、特定のユーザー以外は使用できなくなります。デバイスが準拠しなくなった場合は、いつでもアクセス権を取り消すことができます。

具体的には、設定したコンプライアンス ポリシーに準拠しているデバイスに限り、Intune に設定された条件付きアクセス ポリシーによってメールへのアクセスを許可されます。コピーと貼り付け、または個人のクラウド ストレージ サービスへの保存などの操作は、モバイル アプリケーション管理ポリシーによって制限できます。Azure 权限管理 サービスでは、機密性の高いメール データや転送された添付ファイルを、特定の受信者だけに表示できます。エンドユーザー エクスペリエンスについては、「[条件付きアクセスのエンドユーザー エクスペリエンス](end-user-experience-conditional-access.md)」で詳しく説明しています。



            [この](https://www.youtube.com/watch?feature=player_embedded&v=lYx3YIezccg) 4 分のビデオを視聴して、条件付きアクセスがエンド ユーザーに与える影響を確認できます。

## <a name=""></a>アーキテクチャが重要な理由
EMS と Office 365 のさまざまなコンポーネントは、クラウド向けに構築され、クラウドで実行する目的で設計されています。これにより、クラウドが提供するすべての利点、つまり、スケーラビリティ、柔軟性、管理の容易さがもたらされます。

業務によって要件が異なるため、EMS は、Active Directory、Exchange Server、System 中心配置管理器 などの既存のオンプレミスのインフラストラクチャと統合できるように設計されています。これにより、オンプレミスとクラウドの両方のリソースに、ネットワークで既に確立されている資格情報を使用することができます。

次のセクションでは、クラウドで実行するために設計されたアーキテクチャについて説明し、オンプレミスのオプションを簡単に紹介します。

### <a name="-"></a>電子メール アクセス フロー
Exchange 的联机 へのアクセスに使用する電子メール アプリケーションの種類によっては、セキュリティで保護された状態での電子メールへのアクセスを確立する方法が若干異なる場合があります。ただし、主要なコンポーネントである Azure 的活动目录 (AD Azure)、Office 365/Exchange Online、および Microsoft Intune は同じです。IT 管理者の操作とエンド ユーザーの操作も似ています。EMS は現在、ネイティブの電子メール アプリと iOS および Android 用の Microsoft Outlook アプリをサポートしています。

### <a name="-"></a>ネイティブの電子メール アプリケーションのアクセス制御フロー
交换在线 の電子メールにアクセスする Exchange ActiveSync (EAS) クライアントは、次のプロパティが評価されます。

-   デバイスが Intune で管理されているか。

-   デバイスが Azure Active Directory に登録されているか。

-   デバイスは準拠デバイスか。

-   登録済みのデバイスにクライアント EAS ID がマップされているか。

準拠状態になるには、EAS クライアントが実行されているデバイスが次の条件を満たす必要があります。

-   Intune に登録する。

-   
            [Azure 的 Active Directory](https://msdn.microsoft.com/6a14cb1f-a058-4453-8ede-d9f4a66a7073.aspx)に登録する。

-   IT 管理者によって設定されたデバイス ポリシーに準拠する。

ほとんどのプラットフォームでは、Azure 活动目录 のデバイスの登録は、登録時に自動的に行われます。Intune によって Azure Active Directory に書き込まれたデバイスの状態は、EAS クライアントが次に電子メールを取得するときに、Exchange 在线 によって読み取られます。デバイスが登録されていない場合、ユーザーの受信トレイに登録方法について記載されたメッセージが届きます。デバイスが準拠していない場合、ユーザーを Intune Web ポータルにリダイレクトする別の電子メールが届きます。ポータルで準拠の問題とその修復方法の詳細を知ることができます。


            **Azure AD**がユーザーとデバイスを認証し、Microsoft Intune がコンプライアンス ポリシーと条件付きアクセス ポリシーを管理して、 **Exchange Online** がデバイスの状態に基づいて電子メールへのアクセスを管理します。

![iOS Android デバイスのネイティブ電子メール アプリのアクセス制御フローを示すグラフィック デバイスおよび](./media/ProtectEmail/Access-Control-Flow-For-Native-Email-Apps.png)

### <a name="outlook-"></a>Outlook アプリケーションのアクセス制御フロー
EAS クライアントと同様に、Exchange 在线 の電子メールにアクセスする Outlook 電子メール アプリは、次のプロパティが評価されます。

-   デバイスが Intune で管理されているか。

-   デバイスが Azure Active Directory に登録されているか。

-   デバイスは準拠デバイスか。

デバイスのコンプライアンス対応は、EAS クライアントのアクセス制御フローの説明とほとんど同じ方法で確立されます。ただし、Outlook アプリの場合、コンポーネント間のフローが若干異なります。Outlook アプリが電子メールを取得しようとすると、Azure AD にリダイレクトされます。Azure AD は、そのデバイスが登録済みで準拠していると評価された場合に、セキュリティ トークンを発行します。このセキュリティ トークンは、Exchange 在线 から会社の電子メールを取得するために使用されます。電子メールの同期は、実際には Outlook のクラウド サービスによって仲介されます。このクラウド サービスが、ユーザーの代わりに EAS サービス アクセス トークンを取得して、認証と電子メールの配信を実行します。

![Outlook アプリのアクセス制御フローを示すグラフィック](./media/ProtectEmail/Access-Control-Flow-For-Outlook-App.png)

## <a name="it-"></a>IT 管理者の操作︰
上記を実現するにあたって、Azure 广告 や 交换 では、複雑なインフラストラクチャのセットアップは不要です。IT 管理者は次の手順を実行します。

-   デバイスのコンプライアンス対応状態を評価するときに使用されるコンプライアンス ポリシーを構成し、展開する。

-   Exchange 在线 の条件付きアクセス ポリシーを構成し、どの Azure AD セキュリティ グループが影響を受け、どれがこれらのポリシーから除外されるかを指定する。

-   Intune への登録がサポートされていないデバイスを許可するか禁止するかを選択する。モバイル デバイスでサポートされるオペレーティング システムの一覧については、後ほど紹介します。

オプションのセットアップ段階の実行が必要になる場合があります。デバイスのアクセスと状態の管理および監視に使用されるレポートのために、Microsoft Intune 服务到服务连接器 をセットアップする必要があります。

## <a name="-"></a>エンド ユーザーの操作︰
ユーザーがデバイスで最初に電子メールにアクセスするとき、またはその後同期を試みるとき、デバイスの登録状態とコンプライアンス対応状態がチェックされます。登録やコンプライアンス対応の問題の修正は、画面の指示に従って処理します。エンド ユーザーは、ヘルプ デスクに連絡する必要なく、デバイスの登録とコンプライアンス対応に必要な手順を確認できます。

-   
            **デバイスが登録されていない場合**、アクセスが拒否されたことがサインイン ページに表示され、登録が求められます。登録時、デバイスは Azure Active Directory に自動的に登録されます。Intune は、デバイスのコンプライアンス対応を確認し、非対応の問題を解決する修復の手順を提供します。活动目录的 デバイスが対応すると、Intune は、Azure にデバイスのコンプライアンス対応状態を設定します。

-   
            **デバイスは登録されているがポリシーに準拠していない場合**、問題を修復する手順のリンクがデバイスに送信されます。エンド ユーザーが問題 （パスワードの設定、暗号化など） を修正すると、コンプライアンス ポリシーを管理する Intune で、Azure AD のデバイスのコンプライアンス対応状態が更新されます。

デバイスが登録済みで対応していると評価されると、電子メールの同期が数分内に始まります。

## <a name=""></a>この後の対応
会社の電子メールとドキュメントを保護する方法はわかりました。次は、[電子メールの添付ファイルを保護する](protect-email-attachments.md)方法を確認します。また、準備ができている場合は、[会社の電子メール保護ソリューションの実装](implement-solution.md)について詳しく見ていきます。
