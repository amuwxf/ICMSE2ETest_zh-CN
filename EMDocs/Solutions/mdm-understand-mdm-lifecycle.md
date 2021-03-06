---
title: "MDM ライフサイクルの理解"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 8/1/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 901b52bf-2340-4847-aaff-c94fec9ee925
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: a9fc2f3487fccce491d65d241c51da798e560804
ms.sourcegitcommit: 45ffbe57b8a2ff1ba6d26efde7f4e2fee8495593
translationtype: MT
---
# <a name="mdm-"></a>MDM ライフサイクルの理解

>[!NOTE]
>このトピックは、大規模な設計の考慮事項ガイドの一部です。ガイドの先頭から開始する場合は、[メイン トピック](mdm-design-considerations-guide.md)を参照してください。このガイド全体のダウンロード可能なコピーを入手する場合は、[TechNet ギャラリー](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582)にアクセスしてください。

モバイル デバイス管理ソリューションを設計するときは、モバイル デバイスの管理のさまざまな領域を理解することが重要です。次の図は、モバイル デバイス管理ライフサイクルの全段階を示しています。各ステージには、ソリューションを計画するときに考慮する必要がある固有の要件と確認事項があります。まず始めにこのセクションでは登録ステージについて説明し、このガイドを通して他のステージについても詳しく説明します。

![モバイル デバイス管理ライフサイクルの段階](./media/MDM_Figure_03.png)

**モバイル デバイス管理ライフサイクルの段階**

## <a name=""></a>デバイスの登録と構成
モバイル デバイスの管理は、モバイル デバイス管理ソリューションへのデバイスの初期登録と構成で開始します。単純さ、登録の簡単さ、および登録が、モバイル デバイス管理ライフサイクルが成功するための主な要因です。デバイスの初期登録が難しかったり複雑すぎたりすると、管理者もユーザーもモバイル デバイス管理ソリューションを使い続けるのが面倒になり、モバイル デバイス管理ソリューションの機能、利点、保護を活用できません。

モバイル デバイス管理ソリューションにおけるモバイル デバイスの登録は、通常、2 つの方法で開始されます。

- 管理者が管理する登録
- ユーザー/所有者の自己登録
 
管理者が管理する登録は、集中管理された登録エクスペリエンスを提供し、通常は単一ディレクトリ アカウントを使用する複数のデバイスの一括登録にまとめられます。これは、会社が所有する多数のデバイスをモバイル デバイス管理ソリューションに登録する必要がある場合に便利です。

自己登録では、デバイスのユーザー/所有者が自分でデバイスをモバイル デバイス管理ソリューションに登録します。"携带您自己的设备"通常これは (BYOD) シナリオにおいて使用されますが、会社がデバイスを所有するシナリオでも使用できます。この種の登録では通常、"プッシュ ベース"の登録モデルが使用されます。このモデルでは、ユーザーがデバイスから会社のネットワークまたはネットワーク リソースに接続しようとすると、モバイル デバイス管理ソリューションへのデバイスの登録が自動的に開始されます。ユーザーは、組織のネットワークやリソースに接続する前にデバイスを登録することもできます。

モバイル デバイスの登録と構成には次のことが含まれます。

- 内部および外部のアプリケーションとサービスの展開、アクセス、および管理
- デバイスのセキュリティとアクセスの構成の適用
- セキュリティの脅威からのデバイスの保護

通常、モバイル デバイスをモバイル デバイス管理ソリューションに登録すると、デバイスには、デバイスのユーザーのディレクトリ アカウントおよびデバイス自体がディレクトリ サービスで関連付けられているグループに関連付けられているポリシーとアクセス許可が自動的に割り当てられています。モバイル デバイス管理ソリューションによっては、デバイスのポリシーとアクセス許可のほとんどの構成およびプロビジョニングが、デバイスを登録する前に実行されます。その後、デバイスを登録するとすぐにポリシーとコンプライアンスが有効になり、登録とコンプライアンスの間にギャップが発生しません。

## <a name=""></a>デバイスの登録と構成の計画に関する確認項目

MDM ライフサイクル管理を計画するときは、デバイスの登録と構成の計画について、次の点を確認します。

- モバイル デバイスの登録を行うのは、管理者、ユーザー、両方のいずれですか。
- モバイル デバイスを一括登録する機能が必要ですか。
- 最大で何個のデバイスを一括登録する必要がありますか。
- 組織内のモバイル オペレーティング システム プラットフォームごとに、異なる一括登録要件およびリソースが必要ですか。
- 通常、1 人のユーザーが登録する必要のあるデバイスは何個ですか。
- モバイル デバイス管理ソリューションには、ユーザーごとにデバイス登録の制限がありますか。
- ユーザーによるデバイスの自己登録にはどのような要件がありますか （接続、アプリケーション、管理エージェント、会社ポータル、サポート）。
-  それは管理者が管理する登録の要件と異なりますか。
-  サポートする必要がある各デバイス オペレーティング システムにはどのような登録要件がありますか。
-  組織内のモバイル デバイス オペレーティング システムには、特別な登録要件または固有の登録要件が必要ですか。
-  モバイル デバイス管理ソリューションは有線接続登録と無線接続登録の両方をサポートしますか。
-  デバイス登録のサポートに関してハードウェアにはどのような要件がありますか （ある場合）。
-  デバイス登録のサポートに関してネットワーク接続およびネットワーク セキュリティにはどのような要件がありますか。
-  初期登録時にデバイスに特定のデバイス コンプライアンス ポリシーを適用する必要がありますか。
-  初期登録時にデバイスに特定のデバイス セキュリティ ポリシーを適用する必要がありますか。
-  初期登録からデバイス ポリシーのプロビジョニングまでの時間の最大値または最小値を構成または設定できる必要がありますか。
-  登録が失敗した場合に特別なプロビジョニング ポリシーを自動的に発動する必要がありますか。

##<a name=""></a>デバイス管理
管理者の観点およびデバイスのユーザーの観点からのモバイル デバイスの管理方法は、モバイル デバイス管理ソリューションの重要なコンポーネントです。

たとえば、モバイル デバイスを管理する方法と、モバイル以外のデバイス （サーバー、デスクトップ、他のネットワーク デバイス） の管理方法を、統合することが必要な場合があります。組織によっては、モバイル以外のデバイスの管理ソリューションが、組織へのモバイル デバイスの導入よりかなり前に実施されていることがあります。これにはかなりのコストがかかり、管理ソリューションに長期的な投資が行われているかもしれません。

モバイル デバイス管理ソリューションと既存のモバイル以外のデバイスの管理ソリューションの可能な統合方法をよく理解することは、おそらく、組織のニーズを満たすモバイル デバイス管理ソリューションを設計するときに行う最も重要な作業の 1 つです。

通常、モバイル デバイス管理には複数の管理領域が含まれます。

- 
            **デバイスのセキュリティと構成︰**モバイル デバイスのセキュリティには、組織内の管理対象デバイスに展開できるさまざまな設定が含まれます。設定には、タイミング、有効期限、およびデバイスのパスコード アクセス、デバイスの暗号化、紛失または盗難されたデバイスからのデータの消去に対する必要な特性などの指定が含まれることがあります。セキュリティと構成の詳細については、「[3-モバイル デバイスの保護を計画する 手順](mdm-step-3-plan-enhancing-mobile-devices-protection.md)」をご覧ください。
- 
            **アプリケーションの管理︰**この領域には、アプリケーションの展開の管理、インストール、状態の更新と管理、アプリケーションの削除が含まれます。特定の非対応アプリケーションに関する制限も管理できます。これは、全体的なコンプライアンスおよびセキュリティ戦略の中心になることがあります。モバイル デバイス上のアプリケーションは管理する必要があっても、デバイスをモバイル デバイス管理プラットフォームに登録する必要はないアプリケーション管理シナリオもあります。
- 
            **会社のリソースへのアクセス︰**MDM では、電子メール サーバー、Wi Fi ネットワーク、VPN 対応リソースなど、オンプレミス ネットワーク リソースへのアクセスも管理できます。これには、セキュリティ コンプライアンスの保証と、モバイル デバイス ユーザーが会社のポリシーに従って会社のリソースに簡単にアクセスできるようにすることの、2 つの目的があります。組織のリソースへのアクセスがモバイル デバイス ユーザーにとって複雑すぎたり難しすぎたりすると、その方が簡単だからという理由で、承認されていない会社のリソースを使用して会社のデータを保存するようになる可能性があります。
- 
            **インベントリとレポート︰**モバイル デバイスを管理するときは、モバイル デバイスとプラットフォームのイベントを記録して分析し、組織内の管理ポリシーへのコンプライアンスを追跡する必要があります。また、詳細なレポートはリアルタイムの統計とデータを提供でき、管理者はモバイル デバイスおよびモバイル デバイス ユーザーの状態に基づいてより速く、適切な決断を下すことができます。インベントリとレポートの詳細については、後のセクションで説明します。

### <a name=""></a>デバイス管理の計画に関する確認項目
現在はまだ要件を定義している段階なので、管理の重要な側面にのみ注目します。計画を繰り返しながら要件を調整し、組織の全体的なニーズに関する理解を深めることができます。</para><para>デバイスの管理の計画について以下のことを確認します。

- ユーザーのグループ、デバイスのグループ、デバイスのオペレーティング システムのグループに、特定の管理ポリシーを適用する必要がありますか。
- 異なる種類のデバイスに対して特定の管理ポリシーが必要ですか。たとえば、ユーザー所有デバイスと会社所有デバイス、またはモバイル デバイスと非モバイル デバイスに、異なるポリシーが必要ですか。
- デバイス管理の権限およびアクセス許可を、複数の IT の役割または地位に分離する必要がありますか。その場合︰
 - 権限レベルにはどのような分離が必要ですか。
 - ソリューションによってサポートされるアクセス許可レベルはカスタマイズできる必要がありますか。
 - アクセス許可を既存のアカウント ディレクトリ サービスに統合する必要がありますか。
- モバイル デバイス管理ソリューションのエージェントまたはソフトウェアを、手動と自動の両方で展開できる必要がありますか。
- モバイル デバイス上のアプリケーションを管理できる必要がありますか （ただし、デバイスを （新規または既存の） モバイル デバイス管理プラットフォームに登録する必要はない）。
- モバイル デバイスの管理を、既存のモバイル以外のデバイスの管理ソリューションと統合する必要がありますか。その場合︰
 - 統合管理コンソールまたはポータルからすべてのデバイスを管理する必要がありますか。
 - 既存の非モバイル デバイス管理ソリューションにはどのような統合要件がありますか。
 - 既存の非モバイル デバイス管理ソリューションは、必要な管理の役割およびアクセス許可をどのようにサポートしていますか。
 - モバイル デバイス管理ソリューションと非モバイル デバイス管理ソリューションの間で管理サービスを接続するために、ハードウェアまたはネットワークに関する要件はありますか。
 - 両方のソリューションのインベントリおよびレポート システムは、分離しますか、または統合しますか。
- モバイル デバイス管理ソリューションには、ユーザーがアプリをインストールするための会社ポータルがありますか。
- モバイル デバイス管理ソリューションは、会社のスケーラビリティ要件を満たしていますか。
- モバイル デバイス管理ソリューションは、リモート管理をサポートしますか。
- モバイル デバイス管理ソリューションは、自動化をサポートしますか。

## <a name=""></a>アプリ管理

モバイル デバイスをデバイス管理システムに登録する必要はなくても、会社のデータがデバイス上のコンシューマー アプリやサービスに漏洩するのを防ぐために、デバイス上のアプリケーションは管理する必要がある、という場合があります。これが当てはまるのは、BYOD シナリオや、モバイル デバイスとアプリケーションをそれぞれ別のデバイス管理プラットフォームで管理する必要があるシナリオで、従業員が個人所有のデバイスを使用して会社のリソースにアクセスする場合です。

### <a name=""></a>アプリ管理の計画に関する確認項目

アプリ管理に関する考慮事項を計画するときは、計画について次の点を確認します。

- モバイル デバイス上のアプリ内で会社のデータをコンシューマー データから分離する必要はありますか。
- モバイル デバイス上の会社のアプリと個人のアプリの間で、切り取り/コピー/貼り付け操作によるデータの共有を防ぐ必要はありますか。
- アプリが他のアプリやサービスにデータをバックアップしたり保存したりするのを防ぐ必要はありますか。
- アプリごとのデータ損失防止ポリシーを有効にする必要はありますか。
- 管理対象ブラウザーで表示される Web コンテンツを制限する必要はありますか。

##<a name=""></a>デバイスの廃棄/登録削除

ユーザーが組織を去るとき、またはモバイル デバイスを廃棄または交換するときは、企業のデータが失われたり侵害されたりしないことを確認する必要があります。通常、モバイル デバイス管理ソリューションは、IT 管理とユーザー管理の両方のデバイス リセットおよび登録削除をサポートします。ほとんどのモバイル デバイスでは、登録削除は、デバイスの工場出荷時の既定値へのリセット、またはすべての企業データおよびアプリケーションの選択的消去の実行によって開始します。その後、管理ソリューションへのデバイス登録の接続が削除されます。ただし、このプロセスは、モバイル デバイスの製造元およびデバイスのオペレーティング システム プラットフォームによって異なります。

### <a name=""></a>デバイスの廃棄/登録削除の計画に関する確認項目

デバイスの廃棄および登録削除の計画について、次の点を確認します。

- IT 部門とユーザーの両方がモバイル デバイスの登録を削除できる必要がありますか。
- デバイスを選択的に消去する場合、デバイスをモバイル デバイス管理ソリューションから自動的に登録削除する必要がありますか。
- モバイル デバイス ユーザーが自分のモバイル デバイスを登録削除できる場合、企業のデータやアプリケーションの削除はどのようにして確認しますか。
 - それは、選択的に消去されるデバイスと、工場出荷時の既定の設定にリセットされるデバイスでは異なりますか。

>[!TIP]
>各回答をメモし、答えの裏側にある論理的根拠を理解します。後の作業で、利用可能なオプションと各オプションの長所と短所を確認します。 これらのことを確認しておくと、ビジネス ニーズに最適なオプションを選択できます。
