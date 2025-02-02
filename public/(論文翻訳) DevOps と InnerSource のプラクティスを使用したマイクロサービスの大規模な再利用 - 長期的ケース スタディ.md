# 原文  
  
https://arxiv.org/abs/2309.15175  
  
# 要約   
  
InnerSource や DevOps などの最新のプラクティスは、ソフトウェアの再利用を促進します。  
この調査では、最新のプラクティスの使用がソフトウェアの再利用に与える影響を調査します。特に、Ericsson での最新の再利用のコスト、利点、課題、および潜在的な改善を調査します。  
  
この調査は 2 つのフェーズで実施しました。a) データ収集方法 (インタビュー、ディスカッション、企業ポータルなど) の組み合わせに基づく初期データ収集、および b) 最初のフェーズで特定された課題と改善の状況を把握するための 1 年後のフォローアップ グループ ディスカッションです。  
  
結果によると、再利用可能な資産の開発には、コンプライアンスを確保するための追加作業などの初期コストが発生しました。さらに、再利用による開発には、再利用可能な資産の統合と理解などの追加作業も発生しました。Ericsson は、この追加作業を、品質、生産性、顧客体験、作業方法の改善などの長期的なメリットをもたらす投資と認識しました。   
  
Ericsson の主な課題は、再利用可能な資産のプロデューサーに対するプレッシャーが増すことでしたが、InnerSource の採用を拡大することで軽減されました。InnerSource の成功は、再利用可能な資産への貢献の増加から明らかです。さらに、Ericsson はコンプライアンス チェックの自動化などの対策を実施し、再利用可能な資産の成熟度を高めて再利用の増加をもたらしました。  
  
# 1. イントロダクション  
  
ソフトウェアの再利用とは、既存のソフトウェア資産を使用してシステムを構築することです。数十年にわたって、小さなサブルーチンから重要な機能を提供する大きなコンポーネントまで、さまざまな再利用資産が見られてきました。  
  
さらに、コード再利用資産の種類は継続的に進化しています。再利用可能なWebサービスを使用してシステムを構築することは1990年代から人気があり、最近ではマイクロサービスの再利用に進化しています。マイクロサービスは、「メッセージを介して対話するまとまりのある独立したプロセス」と定義されています。  
  
マイクロサービスアーキテクチャの重要な特徴は、アーキテクチャの侵食に対して耐性があり、開発とテストが容易なモジュール式でスケーラブルなソリューションを作成することです 。これにより、再利用の増加がさらに促進されます。  
  
dockerやKubernetesなどのソフトウェアプラットフォームは、マイクロサービスを使用して大規模なアプリケーションを構築するために使用されます。このようなプラットフォームは、より良い再利用率と簡単な展開を実現するために使用されます。さらに、継続的インテグレーションやデリバリーなどの DevOps プラクティスは、サービスの迅速な展開を促進します。これは、一般的なマイクロサービスを統合するときに有益です。  
  
InnerSource などの最新のプラクティスは、再利用を促進します。InnerSource は、利用可能な共通サービスの発見可能性の欠如など、再利用の障壁を排除するためのパターンを提供します。さらに、InnerSource パターンは、共通サービスの潜在的な消費者が分析、設計、開発、テストに参加する共同アプローチを促進し、消費者のニーズをより適切に調整します。企業は、再利用率を高めるために InnerSource プラクティスを採用しています。  
  
ソフトウェア プラクティスの進化は、今日のソフトウェア再利用の実践方法に影響を与えています。最も顕著な変化は、再利用資産 (マイクロサービスへのコンポーネント) と共同プラクティス (InnerSource) にあります。Docker、DevOps、InnerSource プラクティスなどのプラットフォームを使用したマイクロサービスの再利用を、現代的な再利用と呼びます。  
  
個々の現代的なプラクティスが再利用に及ぼす利点は調査されましたが、大規模な現代的な再利用の影響はよくわかっていません。前回の研究では、中規模企業における現代のソフトウェアエンジニアリングの実践におけるソフトウェアの再利用の影響を調査しました。  
  
この研究では、現代の再利用、つまりEricssonのクラウドネイティブ環境でDevOpsとInnerSourceの実践を使用したマイクロサービスの大規模な再利用の影響を調査します。より具体的には、現代の再利用のコスト、利点、課題、改善提案を特定します。また、課題と改善提案を特定してから1年後に課題を再検討し、どのような改善が実施され、どの課題が軽減されたかを理解します。私たちの研究の貢献は次のとおりです  
  
- 現代の再利用プロセスの詳細な説明を提供します  
- 現代の再利用のコストと利点を特定します  
- 現代の再利用の課題と改善提案を特定します  
- 特定された課題を軽減するためにEricssonが実施した改善の概要を示します  
  
論文の残りの部分は次のように構成されています。セクション2では、関連する概念と関連する作業について説明します。セクション3では、研究の質問に答えるために使用した方法論を示します。第 4 章では、エリクソンで現在行われている再利用プロセスについて詳しく説明します。第 5 章と第 6 章では、現在の再利用のコスト、利点、課題、改善提案の結果を示します。さらに、現在の再利用の課題と改善に関するフォローアップ調査の詳細を示します。第 7 章では、調査結果について説明します。第 8 章では、この論文を締めくくり、今後の作業を提案します。  
  
# 2 背景と関連研究  
  
このセクションでは、私たちの研究に関連する概念と、ソフトウェア再利用の影響に関する関連研究を紹介します。  
  
## 2.1 ソフトウェア再利用の影響を調査した研究  
  
研究者は 50 年以上にわたってソフトウェア再利用の実践を調査してきました。このセクションでは、ソフトウェア再利用の影響に関する関連研究について説明します。  
  
### 利点とコスト  
  
Barros Jutso らは、ソフトウェア再利用に関するマッピング研究を実施し、開発生産性の向上と製品品質の向上がソフトウェア再利用の最大のメリットであることを発見しました。  
  
Kruger と Berger  は、ソフトウェア再利用には再利用可能な資産の調整、設計、実装に追加のコストがかかることを発見しました。  
  
さらに、私たちの以前の研究 では、ソフトウェア再利用の利点として、学習の改善、使いやすさの向上、リソース割り当ての最適化が挙げられ、ソフトウェア再利用のコストとして、再利用可能な資産のドキュメント、追加の承認、サポート ツール、再利用可能な資産の学習にかかる余分な時間などが挙げられました。  
  
### 課題と改善  
  
Bauer と Vetro は、2 つの大規模企業におけるソフトウェア再利用の課題を調査しました。彼らは、再利用可能な資産の粒度が両方のケース企業にとって課題であることを発見しました。ケース企業の 1 つは、組織全体の再利用ポリシーと再利用可能な資産の透明性の欠如という課題を経験しました。さらに、両方の企業で、再利用可能な資産の制御の喪失、パフォーマンスの低下、再利用可能な資産を変更できないことに関連する問題が特定されました。  
  
BarrosJusto らは、中規模企業で Bauer と Vetro の研究を再現し、中規模企業での再利用の課題は、再利用可能な資産の発見可能性とプロジェクトのニーズへの適応に関連していると指摘しました。  
  
さらに、以前の研究によると、バージョン依存関係などの依存関係の問題や、再利用可能な資産の変更によって引き起こされる波及効果も課題です。既存の文献は、再利用可能な資産の理解可能性と発見可能性 と 開発者間の再利用関連タスクの分散 がソフトウェアの再利用を改善するために重要であることを示唆しています。さらに、再利用の測定を改善して上級管理職が再利用のメリットを理解できるようにすることも重要です。  
  
## 2.2 マイクロサービスを再利用可能なユニットとして調査する研究  
  
マイクロサービスは、小規模で自律的なサービスです。各マイクロサービスには、開発、展開、運用、バージョン管理、スケーリングの独立したユニットがあります。さらに、マイクロサービスは疎結合されている場合は独立しており、必要な場合を除きデータを共有しません。コンテナと DevOps は、アプリケーションの開発、テスト、展開を改善するためにマイクロサービスとともに使用されます。マイクロサービスにより、再利用性が向上し、配信が迅速化されるため、企業はモノリスからマイクロサービスに移行しています。  
  
Assuncao らは、レガシー システムからマイクロサービスに移行する可能性のある候補を特定するのに役立つ 5 つの基準を特定しました。特定された基準は、結合、凝集性、機能のモジュール化、ネットワーク オーバーヘッド、再利用です。マイクロサービスへの移行候補を特定するためにマルチ基準戦略を使用すると、再利用の機会を増やすことができます。   
  
Tizzei と Nery は、マイクロサービスと製品ライン アーキテクチャがマルチテナントの Software as a Service (SaaS) の再利用をサポートし、LOC の再利用が 60% 増加することを発見しました。  
  
Silva らは、マイクロサービスに移行して DevOps を使用すると、移植性、再利用、保守性が向上することを観察しました。Shadija らも同様の発見をしており、より「きめ細かい」マイクロサービスでは、マイクロサービスが同じコンテナーまたは異なるコンテナーだが同じホストにある場合に、再利用性が向上することを発見しました。  
  
2 つの研究において、マイクロサービスの再利用の利点と課題について明確に言及しています。Gouigoux と tamzalitは、マイクロサービスによってさまざまなビジネス コンテキストでの再利用が増加し、類似のアプリケーションの開発時間が短縮されて経済的利益が得られることを明らかにしました。独立したマイクロサービスにより、さまざまなチームがさまざまな言語を使用できます。ただし、Wang らは、複数の言語を使用する利点によって、異なる言語のマイクロサービスを理解するのに時間がかかるため、再利用の機会が制限されることを発見しました。さらに、著者らは、複数のマイクロサービスで共有される共通コードの管理が困難であることも発見しました。  
  
## 2.3 再利用の促進者としての InnerSource を調査する研究  
  
InnerSource は、社内ソフトウェア開発にオープンソース開発手法を採用しています。InnerSource は、機能の実装と不具合の修正速度を向上させるために、個人が他のチームに貢献することを奨励しています。  
  
企業が InnerSource を採用する主な理由の 1 つは、ソフトウェアの再利用を増やすことです。再利用可能な資産を共有するための共通スペースを構築するなどの InnerSource の手法は、透明性を高め、やり直しを回避するため、再利用を促進します。再利用時に共通スペースを使用する利点は、Lucent Technologies、Philips、Nokia 、Hewlett-Packard、Ericsson、IBMなどの企業で確認されています。同様の利点は、Morgan らによる Zalando、Philips Healthcare、PayPal の共通スペースを調査した研究でも確認されています。  
  
共通スペースは、さまざまな企業によってソフトウェアフォージ、マーケットプレイス、ポータル、またはプラットフォームと呼ばれています。共通スペースで共有される再利用可能な資産には、プロジェクト、スタンドアロン製品、フレームワーク、ドキュメントテンプレート、ソフトウェア製品、ソフトウェアモジュールとアイテム、ソフトウェアライブラリとコンポーネントなどがあります。  
  
透明性の向上に加えて、InnerSource の実践により、チーム間のコミュニケーションが改善され、消費者の観点から再利用可能な資産に対する理解が深まります。さらに、Lindenは、InnerSource によって、消費者自身も再利用可能な資産に貢献できるため、プロバイダーが消費者の要求の一部を軽減し、市場投入までの時間を短縮できることを発見しました。  
  
ただし、利用可能な容量が不足していることと、InnerSource 貢献を行う利点についての認識が低いことにより、開発者から InnerSource 貢献を引き出すのは簡単ではありません。さらに、生産者の観点から見ると、貢献を受け入れることは、貢献がすべての利害関係者のニーズを満たすことを確認する必要があるため、課題を伴う可能性があります。  
  
私たちの以前の研究では、中規模企業における現代の再利用の影響を調査しました。InnerSourceの採用を拡大することで、再利用可能な資産の発見可能性と所有権、知識の共有、再利用の測定に関連する主な課題に対処できることがわかりました。  
  
#### 研究のギャップ   
  
前回の研究では、ソフトウェア再利用の取り組みの初期段階にある中規模企業における最新の再利用プロセスを調査しました。この企業は、マイクロサービスへの移行とInnerSourceプラクティスの実装の初期段階にありました。さらに、再利用の規模は、この研究で調査したコンテキストほど大きくはありませんでした。  
  
この研究では、再利用の取り組みをさらに進め、大規模に再利用を実践している企業における最新の再利用を調査します。以前の研究では、マイクロサービスとInnerSourceがソフトウェアの再利用を促進することがわかりましたが、InnerSourceプラクティスを採用しながらクラウドネイティブ環境でマイクロサービスを再利用することの利点、コスト、課題はまだ調査されていません。この研究では、インタビュー、グループディスカッション、企業の再利用関連ポータル、企業ドキュメントを使用して詳細なケーススタディを実施し、大規模なマイクロサービスの再利用とInnerSourceプラクティスの組み合わせの影響を調査しました。  
  
# 3. 研究⽅法 - ケーススタディ設計  
  
省略  
  
# 4 ケースの説明  
  
ケース カンパニーである Ericsson は、世界中のサービス プロバイダー向けに ICT (情報通信技術) 関連製品を開発している大手多国籍企業です。  
  
Ericsson は、ソフトウェア アプリケーションとマイクロサービスの開発においてクラウド ネイティブ アプローチに移行しています。同社は、クラウド ネイティブ アプローチへの移行をサポートするエコシステムを開発しました。このアプローチでは、共通機能がマイクロサービスとして開発され、Ericsson 内のすべてのアプリケーションで広く再利用できます。このエコシステムは、アプリケーション開発プラットフォーム - ADP エコシステムと呼ばれています。  
  
ADP エコシステムは、クラウド ネイティブ コンテキストで Ericsson 全体で共通マイクロサービスの大規模な開発と再利用をサポートする (テクノロジ、ツール、プラクティス、原則を含む) 役割を担っています。ADP エコシステムが私たちの分析単位です。エコシステムの開発は 2017 年に始まり、それ以来進化を続けています。ADP エコシステムは、いくつかの側面で構成されており、最近、記事で説明されています。この調査では、一般的なマイクロサービスの大規模な再利用を実践した場合の効果を、観察されたコストと利点、直面している課題、およびそれらに対処するための潜在的な改善提案の観点から理解することに焦点を当てています。現在のケーススタディの結果と議論を理解するには、エリクソンでマイクロサービスの再利用が実践されている状況と背景を理解する必要があります。そのため、次のサブセクションでは、ADP エコシステムのさまざまな側面について説明します。  
  
## 4.1 アーキテクチャ フレームワーク  
  
ADP エコシステムは、マイクロサービスとコンテナの最新のクラウド ネイティブ アーキテクチャ スタイルを採用しています。Kubernetes1 はコンテナ オーケストレーターとして使用され、Helm2 はパッケージ マネージャーとして使用されます。Cloud Native Computing Foundation (CNCF)3 は、必要な API をサポートしなければならないさまざまなベンダー ソリューション間の適合性と相互運用性を確保するために、Kubernetes 認定プログラムを維持しています。マイクロサービスとアプリケーションは、CNCF 認定のどの K8S ディストリビューションにも展開できます。ADP アーキテクチャ フレームワーク全体を図 3 に示します。  
  
![image.png](/image/43b854db-f16c-522e-daac-af3c4dc9ccd4.png)  
  
共通のマイクロサービスは、セキュリティ、データ、ネットワーク、監視、管理機能など​​、さまざまな機能領域に対応しています。これらのマイクロサービスは、Ericsson 全体のすべてのクラウド ネイティブ アプリケーション (CNA) で統合および再利用できます。これらのマイクロサービスのほとんどは、オープン ソース プロジェクト (さまざまな CNCF プロジェクトなど) に基づいており、そのライフ サイクルと構成管理は、エコシステムのニーズと要件に合わせてカスタマイズされています。 Ericsson チームは、社内使用のためにオープンソースの CNCF プロジェクトを採用するだけでなく、Kubernetes プロジェクトを含むこれらのオープンソース プロジェクトにバグ修正や機能を提供してアップストリームに貢献しています。  
  
ADP エコシステムのマイクロサービスは、次の 2 つの基準に基づいて 4 つのタイプに分類されます。  
  
- 潜在的なユーザーは誰か? 一部のマイクロサービスは他のマイクロサービスよりも汎用的です。つまり、Ericsson 内のさまざまなドメインのユーザーがいます (図 4 の汎用サービスと再利用可能なサービスを参照)。このようなマイクロサービスを共通マイクロサービスと呼びます。一方、一部の ADP マイクロサービスは特定のドメイン、または特定のアプリケーションにのみ適しています (図 4 のドメインおよびアプリケーション固有のサービスを参照)。  
- それらの開発と保守の責任者は誰か? 一部の共通マイクロサービスは中央から資金提供されています (図 4 の汎用サービスを参照)。汎用サービスは、中央組織である ADP プログラムの一部である中央チームが所有しています (詳細についてはセクション 4.5 を参照)。汎用サービス以外の ADP マイクロサービスは、関連するアプリケーション組織によって開発および保守されます。  
  
![image.png](/image/24018878-235c-10dd-be49-afe8b02e3f22.png)  
  
Ericsson のような大規模な組織全体での共通マイクロサービスの大規模な再利用には、多数の利害関係者 (つまり、さまざまな組織単位の個人やチーム) の関与が伴います。これらの利害関係者は、共通マイクロサービスの開発、再利用、貢献を通じてエコシステムに参加します。エコシステムでは、一貫性のない動作や実装を回避するためのいくつかの基本原則とルールが確立されています。これらの設計ルール (DR) は、エコシステムへの参加を希望するすべてのマイクロサービスが従う必要があります。  
  
DR の例には、イメージの命名とバージョン管理を一貫して行う要件や、ログとメトリックを一貫して構造化する要件が含まれます。再利用を大規模に拡張するこのような取り組みには、高度な自動化が必要です。そのため、エコシステムでは、開発者とチームがマイクロサービスがこれらの DR に準拠しているかどうかを自動的にチェックできるようにサポートする DR チェッカー ファミリも確立しました。開発者は DR チェッカーを CI パイプラインに統合して、マイクロサービスのコンプライアンスをテストできます。  
  
## 4.2 マーケットプレイス  
  
ADP エコシステムは、ADP マーケットプレイスと呼ばれる内部ポータルを開発しました。このポータルでは、利用可能なマイクロサービスに関する必要な情報がすべて提供されています。  
  
マーケットプレイスには、再利用および提供が可能なすべてのマイクロサービスがリストされています。マーケットプレイスには、関連するマイクロサービスをすばやく見つけるための検索およびフィルタリング オプションが用意されています。たとえば、マイクロサービスをタイプ (汎用、再利用可能、ドメイン固有、アプリケーション固有のサービスなど) 別にグループ化するためのフィルタがあります。エコシステムでは、マイクロサービスを分類するための 2 つの追加メカニズムも導入されています (図 5 を参照)。  
  
![image.png](/image/25357903-85d6-f59b-6bee-3c03b9f9bfb3.png)  
  
**成熟度** : マイクロサービスの成熟度は、マイクロサービスがどの程度商業的に準備されているかを示します。最も基本的なレベルでは、マイクロサービスは単なるアイデアまたは概念実証です。最も成熟度が高いマイクロサービスは、商業的に準備が整ったマイクロサービスです。成熟したマイクロサービスと比較的未熟なマイクロサービスを区別する主な要因の 1 つは、設計ルールへの準拠です。エコシステムでは、成熟度レベルごとに異なる設計ルール セットを割り当てています。成熟度を上げるには、より多くの設計ルールに準拠する必要があります。成熟度を上げるにつれて設計ルールの数を増やすというこのような段階的な方法により、エコシステムは、マイクロサービスが成熟度を達成するためのマイルストーン主導の経路を明確に説明し、伝達できるようになりました。  
  
**再利用性** : 再利用性の階段は、マイクロサービスが Ericsson 全体のさまざまなアプリケーションでどの程度再利用されているかを示します。基本レベルでは、これまで再利用テストが行​​われていないマイクロサービスがあります。最高レベルでは、多くのアプリケーションで再利用に成功したサービスがあります。  
  
一方で、成熟度と再利用性の階段は、マイクロサービス チームがマイクロサービスをさらに改善したい場合に、自分たちに何が期待されているかを確認するためのメカニズムを提供します。他方、階段により、マイクロサービスの消費者は、さまざまなマイクロサービスに何が期待できるかを確認できます。  
  
マーケットプレイスでは、マイクロサービスの使用、開発、貢献に関するガイドとチュートリアルも提供しています。マーケットプレイスには 280 を超えるマイクロサービスがホストされており、そのうち 50 を超えるサービス成熟度が最も高いもの (図 5 の成熟度レベルを参照) があります。各マイクロサービスについて、マーケットプレイスには、マイクロサービスのインストールと貢献に重要な必要な情報 (所有者チーム、所有者チーム外の貢献者のリストなど) とリンク (関連するコード リポジトリへのリンクなど) が含まれています。  
  
## 4.4 InnerSource の実践  
  
共通のマイクロサービスは、新しい要件や機能強化を頻繁に要求するいくつかのアプリケーションで使用されています。多数のコンシューマー アプリケーションがさらに多くの機能を求め続けるような構成は、ボトルネックになる可能性があります。中央チームはすべての変更を時間内に実装できず、遅延やボトルネックが発生します。  
  
これらの遅延を克服するために、エコシステムは、サービスのコンシューマーがサービスを使用していないが、バグ修正や機能強化にも貢献する、共通サービスを維持するための共同作業方法として InnerSource を導入しました。InnerSource Commons からインスピレーションを得て、エコシステムはマイクロサービスの開発と保守を管理するために、いくつかの InnerSource の実践、役割、責任を導入しました。  
  
共通のマイクロサービスは InnerSource プロジェクトとして処理され、各サービスにはガーディアン、1 人以上の信頼できるコミッター、および製品所有者がいます。  
  
- **ガーディアン**とは、サービスの技術的所有者であり、貢献ガイドラインの開発、貢献のレビュー、サービスに関するディスカッション フォーラムの作成と参加を担当します。  
  
- **信頼できるコミッター**とは、しばらくサービスに貢献しており、サービスに関する優れた技術的理解を身に付けている人のことです。1 つのサービスに対して複数の信頼できるコミッターが存在する場合があります。サービスの信頼できるコミッターは、InnerSource プロジェクトの持続可能なコミュニティの開発において重要な役割を果たします。新しい貢献者を指導したり、ディスカッション フォーラムに参加したりできます。信頼できるコミッターは通常、サービスを開発したユニットの外部から参加しますが、ガーディアンは通常、サービスを最初に開発したチームから参加します。  
- 各サービスには**プロダクト オーナー**もいて、サービスのバックログとロードマップの管理を担当します。共通のマイクロサービスのソース コードとバックログは、InnerSource への貢献を促進するために Ericsson 社内の全員に公開されています。ただし、貢献は、関連するガーディアンまたは信頼できるコミッターによってレビューされた後にのみマージされます。  
  
## 4.5 ADP プログラム  
  
ADP プログラムは、ADP エコシステムの維持と管理を担当する中央組織です。ADP プログラムには、Ericsson 全体のさまざまなアプリケーションで広く再利用される、中央資金による 50 を超える汎用サービスの開発と保守を担当する中央チームが含まれます。  
  
エコシステムの技術的リーダーシップは、アーキテクチャ チームによって提供されます。アーキテクチャ チームは ADP プログラムの一部です。マイクロサービスとアプリケーションを開発するためのクラウド ネイティブ アプローチに関する原則、DR、ガイドラインの設計と保守を推進します。また、ADP アーキテクトが、一般的なマイクロサービスを利用するアプリケーションのアーキテクトと会い、ガイドラインと DR の将来の方向性と変更について話し合うアーキテクチャ カウンシルもあります。  
  
ADP プログラムには、エコシステムのポリシーとガイドラインの設計を担当する ADP アンカーと呼ばれるユニットも含まれます。ADP アンカー ユニットは、一般的なマイクロサービスの開発、再利用、貢献に対するサポートを継続的に更新します。 ADP アンカー ユニットには、ADP エコシステム内でさまざまなアンカー機能を実行する 100 人以上の実務者が含まれています。また、ADP アンカー ユニットは、貢献数、トップ貢献者、DR 実現の観点から見たさまざまなマイクロサービスの成熟度、どのマイクロサービスが消費者向けアプリケーションによってよりうまく統合されているかなど、さまざまな指標を収集して分析することにより、さまざまな取り組みの進捗状況を追跡しています。  
  
# 5 結果 RQ1: ソフトウェア再利用のコストとメリット  
  
このセクションでは、Ericsson のクラウドネイティブ環境で DevOps と InnerSource プラクティスを使用してマイクロサービスを大規模に再利用することのコストとメリットについて説明します。複数のユーザーによって複数のドメインで使用されるマイクロサービス (図 4 の汎用サービスと再利用可能なサービスを参照) を共通マイクロサービスと呼びます。  
  
ソフトウェア再利用の主な目的は、コストを削減し、品質を向上させることです。  
ただし、共通マイクロサービスを開発する際には、ある程度の初期コストが避けられませんが、消費者がアプリケーションでそのようなマイクロサービスを再利用すると、そのコストは回収されます。一方、共通マイクロサービスを使用すると、追加コストも発生します。インタビュー対象者はこれを「ただで得られるものはない」と要約しました。この調査では、共通マイクロサービスを開発して統合するために必要な追加の労力をコストと呼びます。特定されたコストを「再利用のための開発」と「再利用を伴う開発」に分類し、図 6 に示すように、該当する場合は利点をテーマごとにグループ化しました。このセクションでは、ソフトウェアの再利用に関連するさまざまなコストと利点について説明します。  
  
![image.png](/image/8b8e2b99-115e-76c1-7bd2-ea6765fb4680.png)  
  
## 5.1 ソフトウェア再利用コスト  
  
このサブセクションでは、特定されたソフトウェア再利用コストについて、再利用のための開発と再利用を伴う開発の 2 つの観点から説明します。  
  
### 5.1.1 再利用のための開発  
  
このサブセクションでは、再利用のための開発に費やしたと実践者が認識している追加の労力について説明します。  
  
#### 設計ルールの実装における追加の労力  
  
Ericsson は、構成、統合、下位互換性の確保などの問題の処理要件を記述する設計ルール (DR) を開発しました。Ericsson で開発されるすべてのマイクロサービスは、DR に準拠する必要があります。ただし、Ericsson 全体のさまざまなアプリケーションに統合される共通マイクロサービスの場合は、DR への準拠を確実にする必要性が高まります。セクション 4 で述べたように、共通マイクロサービスが準拠し、一貫して開発されていることを確認することが重要です。共通マイクロサービスの ADP 製品所有者によると、DR とセキュリティなどのコンプライアンス要件の実装にはかなりの時間がかかります。さらに、共通マイクロサービスの作成と使用に携わる技術リーダーは、DR の実装を「苦痛で制限の多いプロセス」と呼んでいました。技術リーダーは、このような追加コストはサービスを再利用可能にするために必要であると強調して議論を続けました。DR は、顧客にとって共通のルック アンド フィールを可能にする調整を行うためにも不可欠です。したがって、DR は将来のメリットを得るために必要な投資です (セクション 5.2 で説明)。さらに、設計ルールの実装における追加の労力は、共通マイクロサービスに固有のものではないことに注意することが重要です。ただし、開発者が設計ルールへの準拠のペースを決定できる再利用されないマイクロサービスと比較して、共通マイクロサービスの準拠を監視する必要性が高まっています。  
  
#### ドキュメント、展開、テストにおける追加の労力  
  
コード自体に加えて、関連するドキュメントやテスト ケースなどの他の成果物を再利用可能にするには、追加の労力が必要です。開発者の 1 人は、共通のマイクロサービスには追加のドキュメントが必要であると述べました。  
コードはユーザーが理解する必要があるためです。さまざまなチームが、さまざまなデプロイメント環境で共通のマイクロサービスを使用します。したがって、プラットフォーム アーキテクトによると、共通のマイクロサービスは「デプロイメントをサポートするように適応させる必要があります」。  
  
### 5.1.2 再利用による開発  
  
このサブセクションでは、再利用による開発において実践者が感じる追加の労力について説明します。  
  
#### 共通マイクロサービスの理解と統合  
  
戦略製品マネージャーは、共通マイクロサービスを再利用する前に、チームはサービスとその統合方法を理解する必要があると述べました。さらに、SPM は、共通マイクロサービスはクラウド環境向けに開発されていると述べました。  
すべてのアプリケーションがまだ完全にクラウドネイティブであるわけではありません。小さなマイクロサービスを使用するためにも、チームはインフラストラクチャをクラウド環境に更新し、コンテナと CI/CD パイプラインをセットアップする必要があります。戦略製品マネージャーによると、「顧客の展開に大きなフットプリントが追加されます」。ただし、これは 1 回限りのセットアップであり、一度確立すると、セクション 5.2 で述べたように、統合は簡単になります。各共通マイクロサービスを統合すると、いくつかの依存関係も追加され、追加の統合テストが必要になります。プラットフォーム マネージャーは、「再利用すると依存関係が追加され、それが速度を低下させる可能性があります。そのため、人々は自分で行う傾向があります」と述べました。追加の依存関係は、マイクロサービスベースのアーキテクチャの必然的な結果です。マイクロサービス ベースのアーキテクチャでは、単一のマイクロサービスが単一の責任を持つ必要があるため、複数のマイクロサービスとそれらの間の依存関係が生じます。  
  
#### 能力とプロセスの更新の必要性  
  
一般的なマイクロサービスは、変化するテクノロジに合わせて最新の状態になっていることが多いため、ユーザーは、一般的なマイクロサービスを使い続けるために、能力を常に更新する必要があります。同様に、初期費用はかかりますが、技術リーダーによると、得られた知識と能力は「ユーザー自身の開発やあらゆる種類の再利用能力に」使用できます。  
ご覧のとおり、一般的なマイクロサービスを開発および再利用する際のコストのほとんどは、長期的にはメリットにつながります。一般的なマイクロサービスを再利用することで特定されたメリットについては、セクション 5.2 で説明します。  
  
## 5.2 ソフトウェア再利用のメリット  
  
このサブセクションでは、調査で特定されたソフトウェア再利用のメリットについて説明します。  
  
### 5.2.1 品質の向上  
  
インタビュー対象者のほとんどが、共通マイクロサービスの品質は一般的に優れているという見解を共有しました。ADP プログラム チームに加えて、アプリケーション チームとプラットフォーム チームもこのメリットを強調しました。技術リーダーは、「他のすべてのアプリケーションがすでにこの製品 [共通マイクロサービス] を使用しているため、発見しなければならない問題の数は少なくなります。そこに到達する前に、ある程度の成熟度と品質に達しています。」と述べました。  
プログラム マネージャーは、品質の向上は、マイクロサービス ユーザーからのフィードバックを考慮した優れた品質保証プロセスの結果であると述べました。  
プログラム マネージャーは、「[共通マイクロサービス] にはチェックが多く、設計ルールとテスト カバレッジの観点からのプレッシャーが少し大きくなります。」と付け加えました。以下では、インタビューでインタビュー対象者が議論した品質の具体的な属性について説明します。  
  
#### コンプライアンスの向上  
  
マイクロサービスが組織内で再利用できるようになると、マイクロサービスは既に会社のコンプライアンス要件の一部、あるいはすべてに準拠しています。プラットフォーム アーキテクトの 1 人は、一般的なマイクロサービスのほとんどはオープン ソースから採用されており、会社の指示に準拠していると述べています。「[一般的なマイクロサービス] はより安全で、通信環境に適したものになり、Ericsson の指示、たとえば Ericsson のセキュリティ要件にさらに準拠するようになりました。」  
  
#### 製品との統合の向上  
  
Ericsson には複数の製品があり、一般的なマイクロサービスは他の製品と統合する必要があることがよくあります。製品によって異なるテクノロジやプログラミング言語が使用される場合があり、統合の問題が発生します。製品マネージャーは、一般的なマイクロサービスがそのような統合をサポートしていることを確認しました。「再利用可能なコンポーネントや標準インターフェイスを再利用している場合は、統合がはるかに簡単になります。」技術リーダーは、統合が容易な理由として、「ADP エコシステムのガイドラインと Cassandra を使用した経験の両方に基づいて、他の製品が [特定のマイクロサービスに言及] をすばやくピックアップして、それを自社の製品に展開する方がはるかに簡単だと思います」と述べました。  
  
#### 標準化された共通サービス  
  
ADP の製品オーナーは、さまざまなアプリケーションのすべての共通機能に同じサービスを使用することで、統一性が確保されることを強調しました。技術リーダーは、「その [再利用可能なマイクロサービス] は、汎用ソリューションで製品化できるものになりました」と付け加えました。  
  
### 5.2.2 生産性の向上  
  
インタビュー対象者は、サービスの再利用によっても生産性が向上することを共有しました。ADP プログラムのメンバーとアプリケーション チームの両方が、生産性が次のように向上することを認識しています。  
開発時間と労力の節約: 共通マイクロサービスは 1 回開発され、複数回再利用されます。プログラム マネージャーは、「その [共通マイクロサービス] を 1 回だけ開発し、それをすべての異なるアプリケーション [チーム] で再利用できれば、より効率的になります」と強調しました。  
  
#### 人員削減とメンテナンスの容易さ  
  
共通マイクロサービスにより、人員が削減され、メンテナンスが容易になります。組織全体で使用されている共通マイクロサービスの 1 つを担当する ADP 製品所有者は、「[特定のマイクロサービスについて言及] をメンテナンスしている開発者は 8 人だけです。そのため、コストは小さなチームに集約されます。脆弱性が報告された場合、このチームが対処します。多くの異なる担当者に連絡して、異なるバージョンのログ記録をメンテナンスする必要はありません」と述べています。  
  
#### 市場投入までの時間の短縮  
  
時間と労力の削減のメリットにより、市場投入までの時間が短縮されます。 ADP チーフ アーキテクトは、共通マイクロサービスについて次のように語っています。「顧客に迅速なソリューションを提供することもできます。」  
  
#### 運用と保守 (O&M) の促進  
  
プラットフォーム チームの観点からのもう 1 つの利点は、共通マイクロサービスがさまざまなアプリケーションにわたる運用と保守のアクティビティの実行に使用されることです。  
プラットフォーム マネージャーは次のように振り返ります。「独自に何かを構築する代わりに、共通マイクロサービスをベースとして取り入れることができるという事実。これは大きな利点です。」  
  
### 5.2.3 顧客エクスペリエンスの向上  
  
共通マイクロサービスのプロデューサーとコンシューマーの両方が、顧客の観点からのメリットについて言及しました。共通マイクロサービスは連携を改善し、顧客に同じ外観と操作感を提供します。プラットフォーム マネージャーによると、再利用は顧客のインストール プロセスにもメリットをもたらします。複数のアプリケーションが特定の機能に共有サービスを使用する場合、顧客はそれを 1 回インストールするだけで済み、すべての製品の時間と労力を節約できます。最後に、共通マイクロサービスの再利用により、顧客の学習が向上します。プラットフォーム アーキテクトの 1 人は、「顧客が複数の Ericsson 製品を持っている場合、3 つの異なる Ericsson 製品に同じサービスがある場合、そのサービスの仕組みを一度理解して学習すれば、すべての製品を理解することができます」と述べています。  
  
### 5.2.4 能力の向上  
  
サービスを再利用することで、能力は分散されるのではなく、1 つのチームに統合されます。ADP プロダクト オーナーの 1 人は、「能力は各チームに分散されるのではなく、1 つのチームで利用可能」であると述べています。共通のマイクロサービスを担当する社内の専門チームは、共有資産の所有権と管理に役立ちます。プラットフォーム マネージャーは、「ベンダーやオープン ソースによる実装を試みる代わりに、一緒に作業できるチームがあることは利点です」と述べています。さらに、ADP アンカーによると、チームが協力して他のチームに貢献すると、「チーム内および組織内の能力も向上します」。  
  
### 5.2.5 インフラストラクチャと作業方法の改善  
  
共通のマイクロサービスを再利用する場合、再利用はソフトウェアを超えて行われます。たとえば、作業方法やテスト フレームワークの再利用も含まれます。プログラム マネージャーは、「[コード] の再利用だけでなく、実践や作業方法、テスト フレームワーク、その他多くのものの再利用も含まれます」と述べています。  
  
## 5.3 現代の再利用におけるコストと利益のトレードオフ  
  
セクション 5.1 で説明したように、共通マイクロサービスの開発と使用には、いくらかの追加コストがかかります。ただし、調査参加者は、共通マイクロサービスを再利用すると、開発時間、労力、人員の削減など、追加コストによっていくつかのメリットがもたらされることを強調しました (セクション 5.2.2 を参照)。したがって、共通マイクロサービスの開発にかかる追加コストは、組織内のさまざまなユーザーが共通マイクロサービスを再利用するときに利益がもたらされる投資です。  
共通マイクロサービスのユーザーは、最初から開発する必要がないため、追加コストを回避できます。少数のユーザーがマイクロサービスを使用する場合、コストの回避はすでに達成されています。ただし、かなりの数のユーザー (たとえば、10 人以上) が共通マイクロサービスを使用する場合、コストの回避は大幅に増加します。さらに、ユーザーは、顧客に共通の外観と操作性を提供するなど、共通マイクロサービスが提供する利点の恩恵を受けます。したがって、共通のマイクロサービスを再利用することによるメリットは、それらの開発と再利用にかかるコストを上回ります。  
  
# 6 結果 RQ2: 現代の再利用の課題と改善提案  
  
このセクションでは、Ericsson 内で複数のユーザーと複数のドメインで使用される共通マイクロサービス (図 4 の汎用および再利用可能なサービスを参照) を再利用する際の実務者が認識している課題と改善提案について説明します。さらに、Ericsson が課題に対処するためにすでに実装した改善の詳細を示します。  
  
## 6.1 課題 1: 中央資金提供チームのボトルネック  
  
インタビューを実施した時点では、共通マイクロサービスの開発と保守をサポートするために中央資金提供チームに大きく依存しており、これがボトルネックを引き起こしていました。中央資金提供チームへのプレッシャーがボトルネックを引き起こす理由は、図 7 に示されており、このサブセクションで説明します。  
  
![image.png](/image/27e32dbb-15d6-63ea-7d55-e90fa3f4298c.png)  
  
### 6.1.1 長いターンアラウンド タイム  
  
このセクションでは、長いターンアラウンド タイムの原因について説明します。また、図 7 に示します。  
  
#### 大きなバックログ  
  
中央から資金提供を受けたチームに依存しているため、多くの異なるチームから要件を受け取ると、大きなバックログが発生します。  
新しい要件は、共通マイクロサービスの目的と範囲に合わせる必要があり、要求が受け入れられない可能性があります。ADP のチーフ アーキテクトによると、「要求に対応するかどうかを示すだけでも、場合によっては 1 か月以上かかる可能性があります」とのことです。待機時間が長すぎる場合、チームが独自に回避策を実装することがあります。プロデューサーが最終的に修正または新しい要件を実装したときに、チームは回避策を置き換えることを決定する場合があります。ただし、一部のアプリケーションは、回避策ソリューションで引き続き動作する場合があります。そのため、待機時間が長くなると、チームが共通マイクロサービスを再利用できなくなる可能性があります。要件の詳細の欠如: 共通マイクロサービスのユーザーからの要件が明確で詳細でないことにも、ターンアラウンド時間が長くなる理由が挙げられました。プログラム マネージャーは、「要件が適切に記述されていないことがあるため、ユーザーが何を求めているのかよくわからない」と述べています。  
  
#### 頻繁な問い合わせ  
  
中央資金提供チームは、共通マイクロサービスの使用方法やクラウド ネイティブ ソリューションへの移行方法に関する問い合わせを多数受けています。  
開発者によると、「すべての問い合わせに回答したり、エンドツーエンドでサポートしたりするだけの帯域幅がない」ことが課題です。  
  
#### トラブル レポート (TR) の遅延と矛盾  
  
プログラム マネージャーによると、消費者からの TR が土壇場で届くことがあり、プレッシャーがかかります。さらに、プログラム マネージャーは、「私たち [中央資金提供チーム] が時々受ける主な苦情は、彼ら [消費者] が TR と見なしているものとの一致が、私たちが新しい機能だと考えているものであることです」と付け加えました。不整合は、設計ルールと一般的な製品要件およびその適用性の誤解が原因である可能性もあります (セクション 6.4 で詳しく説明)。一般的なマイクロサービスの数が増えると、機能要求とクエリの数も必然的に増加します。インタビュー対象者から提供された、増加するバックログを管理する改善提案は、消費者に貢献を促すことでした (セクション 6.2 で説明)。ターンアラウンド タイムを改善するために実装された改善については、セクション 6.3.1 で説明します。  
  
### 6.1.2 貢献の不足  
  
Ericsson は、消費者がマイクロサービスを利用し、その開発に貢献する共同作業方法である InnerSource を推進することを決定しました。しかし、ADP チーフ アーキテクトは、「貢献が少なすぎる」と報告しました。貢献の不足は、マーケットプレイス ポータルから収集したデータから明らかです。図 8 は、2020 年から 2022 年までの貢献を視覚化したものです。図 8 に示すように、2020 年の貢献は 2022 年に比べて少なくなっています。アプリケーションには独自のリリース プランがあり、共通のマイクロサービスに貢献することで得られる潜在的なメリットに疑問を抱く場合があります。たとえば、ADP アンカーは、消費者は「他の人が再利用するものを構築しても、自分にどんなメリットがあるのだろう... これにお金を費やしているのに、なぜ他の人に利用できるようにする必要があるのだろう」と考える可能性があると述べています。  
InnerSource を推進するマネージャーは、アプリケーションがより共同作業的な作業方法を採用することを望んでいます。たとえば、「もし私が消費者なら、それを[再利用可能な共通マイクロサービス] として受け取り、自由に使用しています。ですから、私も貢献すべきです。そうでなければ、エコシステムは機能しません。」  
  
![image.png](/image/27ab6cc6-e9ff-89d7-84b3-716485747ed8.png)  
  
#### 資金不足  
  
ADP の責任者は、「私の作品を他のユーザーが再利用可能にし、何の報酬も受け取らないようにすることが、強引な売り込みでした。」と述べました。戦略製品マネージャーの 1 人は、顧客がお金を払っている顧客要件を優先する必要があると述べました。共通マイクロサービスへの貢献は、収益面ですぐに利益を生むとは限りません。したがって、すぐに収益の利益をもたらす要件よりも優先されない可能性があります。  
  
#### 急峻な学習曲線  
  
アプリケーションは異なるプログラミング言語、ツール、テスト フレームワークを使用する可能性があり、貢献を開始する前に共通マイクロサービスを理解する必要があります。プログラム マネージャー全体は、学習曲線が貢献の障壁であると述べました。「すべてのサービスが同じ言語で記述されているわけではありません。アプリケーションが使用している言語とは異なるかもしれませんが、それが貢献の障壁になる可能性があります。」 Ericsson の InnerSource イニシアチブは、組織がポリシーとプラクティスを採用して、特定された課題に対処し、作業方法をさらに改善する過程です。実践者は、上記の課題に対処するためにいくつかの改善を提案しました。詳細はセクション 6.2 に記載されています。さらに、Ericsson は InnerSource の貢献を増やすためのいくつかの手順も実装しました。詳細はセクション 6.3.2 に記載されています。  
  
## 6.2 改善提案 1: InnerSource の導入を拡大  
  
Ericsson は、中央から資金提供を受けたチームがボトルネックになるのを防ぐために、InnerSource の作業方法の使用を推進しました。しかし、前述のように、この取り組みの開始時には貢献はわずかでした。インタビュー対象者は、InnerSource の導入を拡大する必要があると認識しました。改善前のシナリオと InnerSource の導入を拡大した後の望ましいシナリオを図 9 に示します。図 9 に示すように、InnerSource の導入を拡大する前は貢献の数が少なかったです。さらに、共通のマイクロサービスの提供は、中央から資金提供を受けたチームのみが担当していました。特に、次の改善を実施して貢献の数を増やすことが目的でした。  
  
![image.png](/image/7ab043f9-c1ad-efc5-9445-4718c6206dee.png)  
  
### 6.2.1 InnerSource 貢献のガイドライン  
  
プロデューサーとコンシューマーの両方が、InnerSource の実践方法に関するガイドラインを改善することが重要であると認識しています。貢献のプロセスは、製品マネージャーが「[一般的なマイクロサービスに]貢献したい場合、何をする必要がありますか? 誰に連絡すればよいですか? どのようにレビューされますか? 設計ドキュメントを提示する必要がありますか?」と述べたように定義する必要があります。  
  
さらに、マイクロサービスの所有者はサービスのガイドラインを説明する必要があります。たとえば、ADP の責任者は、所有者は「マイクロサービスのルールを説明する必要があります。これがコードに期待される方法です...。これがテストケースとドキュメントを拡張する方法です」と述べています。プログラムマネージャーは、「[貢献] が適切に記述され、適切にドキュメント化され、コードの一部が後で壊れないようにするためのテストケースも取得する必要がある」と述べました。インタビュー対象者も、貢献をレビューするためのプロセスを定義する必要があることを認識しています。  
  
### 6.2.2 IS 貢献の可能性を拡大する  
  
セクション 6.1 で述べたように、ボトルネックの原因の 1 つは、トラブル レポートの遅延と矛盾です。InnerSource 貢献の種類を拡大する 1 つの方法は、トラブル レポートを送信して解決を待つだけでなく、バ​​グの解決に貢献するようユーザーに促すことです。  
  
この方法では、ユーザーはより小規模でより頻繁な貢献を行うことができます。ユーザーは問題に関する直接の情報を持っているため、マイクロサービスを所有するチームの開発者にトラブル レポート (TR) を割り当てて解決を待つよりも、問題解決にかかる時間が大幅に短縮されます。コンシューマーに TR を完全に解決するためのリソースがない場合でも、プロデューサーが TR を解決するのをサポートできます。  
  
たとえば、プラットフォーム マネージャーは次のように述べています。「所有者のところに行って、この問題、このコード行を見つけたので、この変更で修正できると伝える方がはるかに簡単かもしれません。」要約すると、TR のトラブルシューティングや解決をサポートするために、小規模ながらも重要な貢献を受け入れることで、より多くの貢献を受け取ることを促し、機能リクエストやバグ/問題報告に関して、中央資金提供チームの作業負荷を軽減できます。マイクロサービスへの貢献のさまざまな方法に加えて、Ericsson はマイクロサービスでの貢献も奨励しています。さまざまな種類の貢献について、以下に説明します。  
  
- コードの貢献 - これらの貢献は、機能リクエストまたはバグ修正の結果としてのマイクロサービスの変更です。  
- マイクロサービスの貢献 - 中央資金提供チーム以外のチームが、マイクロサービスを再利用できるように公開できます。マイクロサービスで貢献するチームは、マイクロサービスのメンテナンスも担当します。  
  
### 6.2.3 貢献を同期して計画する  
  
貢献は、共通マイクロサービスの目的とアーキテクチャに合わせる必要があります。貢献者は、まず、対応する保護者と貢献の計画について話し合う必要があります。たとえば、プログラム マネージャーが「あなた [貢献者] が製品に導入したい新しい機能は、製品の目的とアーキテクチャに合致しているので、貢献しても問題ありません」と述べたとします。オーナー チームは、貢献者が事前に通知せずに直接大きな貢献を行うのではなく、計画について話し合った方が、貢献をレビューして迅速に対応する準備が整います。  
  
### 6.2.4 インナーソースの貢献の可視性  
  
目標はより多くの貢献を促すことなので、貢献を促す方法の 1 つは、貢献の良い例を見えるようにすることです。ADP マーケットプレイスでは、すでにトップの貢献者が表示されています。しかし、ADP の責任者は、ADP ダッシュボードでさまざまなレベルの貢献を見えるようにする必要があると認識していました。彼は、「誰かがコミットや数行のコードを貢献した場合、それらもダッシュボードに表示したい」と付け加えました。  
  
### 6.2.5 管理と財務サポート  
  
インタビュー対象者は、他のプロジェクトへの貢献に対する中間管理職 (SPM) の奨励を改善したいと考えています。SPM の観点からは、マイクロサービスへの貢献のための追加予算があれば、それが容易になる可能性があります。「[マイクロサービス] のセキュリティとフットプリントを向上させたい場合、そのための資金を提供する必要があります。」さらに、ADP の責任者は、「すべてのトップレベルのリーダーに InnerSource に参加してもらう必要がある」と述べました。  
  
### 6.2.6 貢献と貢献の受け取りに対するオープン性の向上  
  
インタビュー対象者の中には、貢献の提供と受け取りに対するオープン性など、行動面を改善する必要があると言及した人もいました。ADP チーフ アーキテクトは、チームが自立することの重要性を指摘しました。また、チームは貢献の責任を持つべきだとも付け加えました。貢献者の視点から、プロダクト マネージャーは、共通マイクロサービスの所有者は「貢献できるようにオープンである必要がある」と述べました。また、貢献プロセスは、誰もが貢献できるオープン ソース プロジェクトのようなものにすべきだと付け加えました。  
  
## 6.3 中央資金提供チームのボトルネックに対処するために実装された改善  
  
セクション 6.1 で説明したように、中央資金提供チームのボトルネックの原因は、要件への対応に長い時間がかかり、貢献が不足していることです。このセクションでは、ボトルネックの課題を軽減するために Ericsson が採用したアプローチについて説明します。  
  
### 6.3.1 長いターンアラウンド時間の緩和  
  
フォローアップ調査では、バックログが依然として大きいことがわかりましたが、次の 2 つの理由により、もはや大きな課題ではありません。  
すべての要件がアクティブなバックログの一部ではありません。中央資金提供チームは、今後 12 か月間に作業しない要件を将来の候補としてマークします。このような要件はアクティブなバックログの一部ではありません。  
このようにして、消費者は自分の要件がいつ考慮されるかを予測し、待つか貢献するかを決定できます。このアプローチにより、消費者から重要な要件を受け取ることもでき、中央資金提供チームは優先順位の高い要件に集中できるようになりました。  
  
#### 責任の分散  
  
中央資金提供チームが優先的に要件に対処できない場合、消費者チームは貢献できます。そのため、中央資金提供チームにプレッシャーがかからず、管理エスカレーションが少なくなります。さらに、消費者チームは貢献することでタイムラインをより細かく制御できます。  
  
### 6.3.2 貢献の増加  
  
セクション 6.2 で述べたように、Ericsson はマイクロサービス (中央資金提供チームが所有) への貢献とマイクロサービス (アプリケーション組織が所有) への貢献を奨励しています。  
  
マイクロサービスへのコンシューマー貢献が不足すると、中央資金提供チームにプレッシャーがかかり、ボトルネックが発生します。インタビュー対象者が認識しているように、マイクロサービスへの貢献不足は主に資金不足が原因でした。貢献者は、マイクロサービスに貢献できるようにするために、管理と資金の支援を求めました。現在、経営陣は、チームに期待される貢献の数に目標を設定しています。チームは既存のリソースから貢献することが期待されており、この期待は InnerSource の原則と一致しています。  
  
マイクロサービスで貢献するチームも、中央資金提供チームと同じボトルネックの課題を抱えている可能性があります。たとえば、チームがマイクロサービスで貢献し、他の多くのチームがそれを再利用し始めると、マイクロサービスを使用しているチームからの多くのバグやユーザー機能リクエストに対処しなければならない場合があります。ADP アンカーはこれを「罰則条項」と呼んでいます。つまり、マイクロサービスで貢献したことで多くの追加作業で罰せられるということです。ADP アンカーは、貢献者が貢献したマイクロサービスを維持するためのサポートを受けられる資金提供プログラムを開始しました。チームが 3 つ以上の製品に統合されているマイクロサービスで貢献すると、コードを維持するための追加の帯域幅というメリットが得られます (機能リクエスト、クエリ、バグ修正の処理)。インタビュー対象者は、急峻な学習曲線が貢献のもう 1 つの障壁であると特定しました。セクション 6.1 で述べたように、一般的なマイクロサービスは、同じテクノロジーを使用して実装されていません。貢献ガイドは 2021 年以降改善されていますが、学習曲線は依然として困難です。一般的なマイクロサービスが異なるテスト フレームワークを使用している場合、テスト ケースを追加するのは困難です。回避策の 1 つは、すべてのマイクロサービスに同じテスト フレームワークを使用するようにすることです。  
  
全体的に、Ericsson が実施したいくつかの取り組みにより、(i) マイクロサービス (ADP 汎用サービス) への貢献と (ii) マイクロサービス (ADP 再利用可能サービス) への貢献という、さまざまな種類の貢献の数が年々増加しています (図 8 を参照)。  
  
## 6.4 課題 2: 設計ルールと一般的な製品要件の解釈  
  
一般的な製品要件 (GPR) は、セキュリティなどのコンプライアンス要件です。すべての Ericsson 製品とアプリケーションは、GPR に準拠する必要があります。  
インタビュー対象者は、GPR が最初に指定されたとき、マイクロサービス レベルではなく、製品レベルなど、高レベルで指定されたと報告しました。マイクロサービス レベルでの GPR の適用性は不明確で、プロデューサーとコンシューマーの間に誤解が生じました。  
  
同様に、開発者は、設計ルールが具体的で詳細でない場合、それを誤解する可能性があります (設計ルールの詳細については、セクション 4 を参照)。詳細が不足しているため、設計ルールが実装されているかどうかを確認することが困難でした。  
  
さらに、設計ルールまたは一般的な製品要件が十分に具体的でない場合、異なるチームがそれらを異なる方法で解釈する可能性があります。ADP ハブのリーダーは、「ADP [プログラム チーム] はこの一般的な製品要件または設計ルールを 1 つの方法で解釈し、そのように実装しています。そして、当社のセキュリティ担当者は別の解釈をしています。これはギャップだと思います。」消費者の観点から見ると、リリースの遅延につながるため、この課題は優先度が高いです。戦略的な製品マネージャーは、「一般的なマイクロサービスにいくつかのセキュリティギャップがあるため、ソフトウェアをリリースできないことは明らかでした」と述べています。中央から資金提供を受けたチームのターンアラウンドタイムが長いため、セキュリティ修正を取得するのに時間がかかり、リリースがさらに遅れます。  
  
## 6.5 改善提案 2: 設計ルールと一般的な製品要件の理解を深める  
  
設計ルールを実装する場合、開発者が設計ルールの重要性を理解することが重要です。ADP チーフ アーキテクトは、開発者は「これらの設計ルールに実際に準拠する価値は何か」を知る必要があると述べています。セクション 4 で説明したように、Ericsson は、一般的なマイクロサービスが設計ルールに準拠しているかどうかを自動的にチェックする設計ルール チェッカー ファミリを開発しました。  
ADP アンカーによると、インタビューの実施時点で、設計ルール チェッカーは設計ルールの約 50% をカバーしていました。ADP アンカーは、「目標は、すべての設計ルールをスキャンする CI/CD ビルドに設計ルール チェッカーを統合することです」と述べています。このような CI/CD ビルドでは、合格したテストと不合格のテストの即時レポートを提供できます。開発者は、どの設計ルールが満たされていないかを把握し、効率的に準拠するためのソリューションを見つけることができます。  
  
## 6.6 設計ルールと一般的な製品要件の解釈を改善するために実装された改善  
  
設計ルールの誤解という課題を軽減するために、Ericsson は次の変更を実装しました。  
  
**作業方法の変革** : 設計ルールは、可能な限り自動テストを容易にする方法で記述する必要があります。」  
**適合性の変革** :「コンプライアンスに準拠しているかどうかを確認する必要がある」から「コンプライアンスに準拠しているかどうかはパイプラインが教えてくれる」へ。  
**管理と調整の変革** :「文書としてのルールとコンプライアンス」から「データとしてのルールとコンプライアンス」へ。  
  
さらに、セクション 6.5 で説明したように、設計ルールを実装する価値は明確である必要があります。批判の 1 つは、設計ルールが多すぎるため、実装する価値がない可能性があるというものです。設計ルールの作成には本質的な価値があり、たとえば製品マネージャーによって設定された主な要件に対応している必要があります。Ericsson は、作成できる設計ルールの数に制約を設定しました。新しいマイクロサービス成熟度リリースでは、3 週間ごとに 4 つを超える新しい設計ルールを作成することはできません。  
Ericsson が行っているもう 1 つの継続的な改善策は、設計ルールの実装コストを削減することです。したがって、設計ルールのチェックを自動化することに加えて、一部の設計ルールの実装も自動化されています。  
  
  
## 6.7 課題 3: 共通マイクロサービスの再利用の難しさ  
  
消費者は、共通マイクロサービスの再利用を妨げる課題を挙げました。共通マイクロサービスの再利用を困難にする理由は、図 10 に示されており、このセクションで説明します。  
  
![image.png](/image/197dd527-a888-dd30-9936-713b71ddb0fb.png)  
  
### 6.7.1 マイクロサービスの目的、ユースケース、および制限に関するドキュメントの欠如  
  
インタビューの時点では、マーケットプレイスで利用可能な一般的なマイクロサービスに関するドキュメント (セクション 4.2 を参照) は、デプロイメントと統合に限定されていました。マイクロサービスが実装するユースケースとその制限に関する詳細が欠けていました。プラットフォーム アーキテクトとプラットフォーム マネージャーは、「ドキュメントには制限に関する詳細が記載されていません... [マイクロサービス] で何ができないのかを知る必要があります。」と述べています。  
  
### 6.7.2 サービスの成熟度  
  
製品マネージャーによると、新しい一般的なマイクロサービスは比較的成熟度が低く、セキュリティの脆弱性や機能の不足などの問題が多くありました。さらに、技術リーダーは、すでに成熟したサービスが変更された場合 (新しい機能が追加された場合など)、「そのサービスのチームが望ましい品質と成熟度レベルに到達するには、ある程度の余裕が必要です。しかし、それが続かなかったのは残念です。」と述べています。したがって、一般的なマイクロサービスが成熟するにはある程度の時間がかかり、新機能が追加されたときには、成熟度を維持するために継続的な努力を払う必要があります。  
  
### 6.7.3 下位互換性の破壊  
  
一般的なマイクロサービスは頻繁に更新およびリリースされます。消費者チームも新しいマイクロサービス バージョンにアップグレードする必要がありますが、最新バージョンでは下位互換性が失われる場合があります。下位互換性がないため、アプリケーションは、アップグレードの影響を受ける複数のマイクロサービスのアップグレード シーケンスを同期する必要があります。戦略的な製品マネージャーは、「現在、既存のソフトウェアでは、すべてのインストールをアップグレードすると、莫大なコストがかかる可能性があります」と付け加えました。  
  
## 6.8 改善提案 3: 共通マイクロサービスを消費者にとって魅力的なものにする  
  
インタビュー対象者は、共通マイクロサービスを使いやすく、消費者にとって魅力的なものにするための提案を挙げました。  
  
### 6.8.1 共通マイクロサービスの強化  
  
共通マイクロサービスには、セキュリティ コンプライアンスなどの設計ルールと一般的な製品要件 (GPR) の実装が含まれている必要があります。  
戦略的製品マネージャーによると、「GPR は、各チームが貢献するのではなく、一元的な観点から推進する必要があります。」さらに、消費者は、土壇場でのブロッキングの問題を回避するために、共通マイクロサービスを厳密にテストする必要があることを認識しています。  
戦略的製品マネージャーが「サービスのフットプリントは小さくする必要があります。」と述べたように、共通マイクロサービスは統合が容易である必要があります。  
  
### 6.8.2 アップグレード可能性の確保  
  
共通マイクロサービス チームの所有者は、サービスがどのように使用されるかの全体像を把握するために、消費者からのフィードバックを考慮する必要があります。たとえば、プロダクト マネージャーの 1 人は、共通マイクロサービスの所有者は「共通マイクロサービスがどのように使用されるか。顧客の観点からの要件は何ですか。アップグレード可能で管理可能であることを確認する必要があります。」と付け加えました。  
  
### 6.8.3 統合と構成のガイドラインを提供する  
  
消費者は、共通マイクロサービスを統合する方法に関するより具体的なガイドラインを求めています。セクション 5.1 で説明したように、共通マイクロサービスを統合するには追加の作業が必要です。ガイドラインがないと、統合の作業が増えます。  
戦略プロダクト マネージャーは、「サービスをどのように統合、構成するかなどについて、より明確なルールが必要になります。」と述べました。  
プロダクト マネージャーは、HELM チャートを変更して構成可能なパラメーターを公開することで、サービスを簡単に構成できる必要があると述べました。  
  
## 6.9 共通マイクロサービスを消費者にとって魅力的なものにするために実装された改善  
  
セクション 6.7 で述べたように、消費者は共通マイクロサービスの再利用を困難にする 3 つの主な理由として、ドキュメントの欠如、マイクロサービスの成熟度、および下位互換性の欠如を挙げました。  
  
共通マイクロサービスは高い成熟度レベルに達しているため、成熟度の不足はもはや大きな課題ではありません。ADP アンカー ユニットは、3 週間ごとにサービスに対する期待値を使用してサービス成熟度の階段 (図 5 を参照) をベースライン化し、マイクロサービス チームは最新の期待値に対応するためにこれを実装します。自動設計ルール チェッカー (6.6 で説明) は、最新の期待値に対応するのに役立ちます。共通マイクロサービスのドキュメント (つまり、ユーザー ガイド) は、より充実したものになり、統合と展開に関する詳細が含まれています。したがって、共通マイクロサービスのドキュメントと成熟度はもはや課題ではありません。ただし、新しいマイクロサービス、特に中央から資金提供を受けていないチームによって提供されるマイクロサービスは、中央から資金提供を受けたチームがかつて作成したものと同じ課題を抱えている可能性があります。  
  
下位互換性の問題に対処するために、Ericsson にはすでに廃止プロセスがありました。変更に互換性がない場合は、廃止が登録されます。廃止は、承認される前にアーキテクチャ レビューとビジネス レビューが行われ、消費者は廃止を承認しない機会があります。廃止期間は 3 か月でした。このプロセスはうまく機能しました。ただし、消費者は廃止期間が短すぎると不満を述べました。Ericsson は現在、廃止プロセスを更新し、廃止期間を 13 か月に延長しました。セキュリティ強化や、古いソリューションと新しいソリューションの両方をアクティブに維持するための高コストなど、強力なビジネス ケースがあれば、廃止期間を短縮することも可能です。廃止期間が長くなると、チームは共通のマイクロサービスを使用して顧客側に展開し、比較的長期間にわたって修正によるサポートを受け続けることができます。  
  
## 6.10 課題 4: プロデューサーとコンシューマーのコンテキストの違い:  
  
インタビュー対象者は、リリース サイクルの違いやプロデューサーとコンシューマー間のクラウド ネイティブ ジャーニーの違いに関連する課題について言及しました。このセクションでは、その違いについて詳しく説明しました。  
  
### 6.10.1 ライフサイクル管理  
  
中央資金提供チームのリリース サイクルは比較的短いため、新しいバージョンは対応するコンシューマー チームのリリース サイクルよりもはるかに早くリリースされます。  
コンシューマー チームのマネージャーは、中央資金提供チームのリリース頻度が高すぎると述べました。製品マネージャーの 1 人は、「彼ら [中央資金提供チーム] は毎月または 3 週間ごとにリリースしますが、私たちはたとえば年に 2 回リリースします」と述べました。頻繁なリリースは、リリースが大きすぎないようにし、中央資金提供チームが受け取るいくつかの機能要求やバグ レポートに迅速に対応するために必要です。セクション 6.1.1 で述べたように、コンシューマー チームは迅速な対応を期待しており、あまり長く待ちたくありません。したがって、頻繁なリリースが必要ですが、一部の消費者向けアプリケーションではこれが課題となる可能性もあります。  
  
### 6.10.2 デプロイメント  
  
Ericsson 内で共通マイクロサービスの消費者が増加するにつれて、インターフェースの技術的な整合性を確保することが課題になりつつあります。クラウドネイティブの成熟度が異なる複数のアプリケーションが 1 つの製品にパッケージ化されると、デプロイメントと構成の整合性を確保することが困難になります。ADP チーフ アーキテクトの 1 人は、「1 つのアプリケーションがかなり進歩していて、誰かが [クラウドネイティブの旅] を始めたばかりの場合、大きな問題が発生する」と述べています。さらに、戦略製品マネージャーは、異なるアプリケーションがマイクロサービスを異なる方法で統合し、共通マイクロサービスの外観と操作感を同じにするなどの再利用のメリットが減少する可能性があると述べています。プロデューサーと消費者のコンテキストの違いによる課題は、共通マイクロサービスがより成熟し、チームが完全にクラウドネイティブになるにつれて、長期的には緩和されます。  
  
### 6.10.3 マイクロサービスの目的と範囲への整合  
  
インタビュー対象者は、消費者と生産者の間の調整の課題を報告しました。消費者が要求する修正や新しい要件は、マイクロサービスの目的と範囲に一致している必要があります。消費者の要求が共通のマイクロサービスの目的と範囲と一致しない場合、競合が発生する可能性があります。  
  
さらに、一部のチームは、他のチームが要求する要件をマイクロサービスの一部にしたくない場合があります。目的と範囲の整合には多くの調整が必要であり、技術リーダーによると、「非常に時間がかかり、長い議論になることがあります」。機能要求が承認されると、優先順位が付けられ、ロードマップに追加されます。タイムラインとともに、追加が予定されている機能が示されます。複数のチームが要件を要求する場合、ビジネスニーズを正当化することで、要求の優先順位付けが容易になる場合があります。ただし、プロダクト マネージャーによると、小規模なチームも影響を受ける可能性があります。「アプリケーションによって重みは異なります。小規模な製品である当社は、プロデューサーのロードマップやバックログに対する影響力や重みは小さくなります。」  
  
## 6.11 プロデューサーとコンシューマーのコンテキストの違いに対処するために実装された改善  
  
コンテキストの違いの 1 つは、共通マイクロサービスとコンシューマー チームのライフサイクルの違いです。機能要求とバグ レポートに対応するには、共通マイクロサービスのサイクルを短くする必要があります。  
さらに、廃止期間を延長すると (セクション 6.9 で説明)、頻繁な更新の課題を軽減するのに役立ちます。  
さらに、インタビュー対象者は、デプロイメントの調整が困難であると認識していました。Ericsson は現在、柔軟なデプロイメントのさまざまなフェーズを定義しています。デプロイメント フェーズの定義により、実行時に複数のチームがインスタンス化して、共通マイクロサービスのインスタンスを共有できます。チームは、共通マイクロサービスを整合した方法で使用する必要があり、統合と構成のガイドラインはより規範的です。  
  
# 7 考察  
  
Ericsson における一般的なマイクロサービスの大規模な再利用は、InnerSource プラクティス、クラウドネイティブのマイクロサービス アーキテクチャ、DevOps プラクティスなどのさまざまな側面の組み合わせによって可能になりました。次のサブセクションでは、これらの側面からの研究結果についてさらに説明します。さらに、これらの結果を既存の関連研究と関連させて説明します。  
  
## 7.1 インナーソースと再利用  
  
エリクソンは大規模な組織であるため、共通マイクロサービスの潜在的な消費者が多数存在します。つまり、共通マイクロサービスを再利用してアプリケーションに統合すると、バグ修正を報告するだけでなく、変更や新機能の要求も発生します。ADP プログラムの実践者が言うように、「このようなマイクロサービスの成功は失敗になる可能性がある」のです。つまり、このような共通マイクロサービスのチームが、これらのサービスの消費者からの多数の変更要求や新しい要件を処理できなくなる可能性があります。  
  
このようなシナリオにより、共通マイクロサービスを所有するチームがバックログの処理に苦労するというボトルネック現象が発生しました。このボトルネック現象は、組織がプラットフォームベースの開発を開発および維持しようとした際にも以前に報告されています。  
  
このような開発アプローチでは、中央から資金提供を受けたプラットフォームユニットが、プラットフォームを使用する他の組織ユニットからの多くの貢献なしにプラットフォームの保守を担当し、サイロ構造になります。ADPプログラムは、このようなアプローチ、つまりADPエコシステムをプラットフォーム的に見て操作する方法の潜在的な落とし穴を認識していました。彼らは、次のセクションで強調されているさまざまなイニシアチブの助けを借りて、このボトルネック現象を回避し、対処するために積極的に取り組みました。  
  
### 7.1.1 InnerSource の役割、実践、ガイドライン  
  
ADP プログラムとそのアンカー ユニットは、エコシステムを維持するためのポリシー、メカニズム、ガイダンスの開発を担当しています。ADP アンカー ユニットは、InnerSource 貢献のガイドラインとポリシーの開発と更新を主導するだけでなく、理事会に参加し、新しい貢献者を指導します。このようなユニットは、組織内で InnerSource イニシアチブを維持するために必要です。  
  
私たちの調査の参加者は、InnerSource に関するガイダンスを継続的に更新する上で ADP アンカー ユニットが果たしている役割を認識し、高く評価しました。  
InnerSource Commonsからの推奨事項に基づく「ガーディアン」や「信頼できるコミッター」などの役割の導入と定義は、役割と責任を明確にするのに役立ちました。  
開発者は自分の作業割り当てに集中しているため、共通資産に貢献する余裕がない場合があります。これが、InnerSource 貢献を引き付けるのが難しい主な理由の 1 つです。調査したケースでも、共通マイクロサービスへの貢献が増加し始めるまでにはしばらく時間がかかりました。ADP プログラムとそのアンカー ユニットによる継続的な取り組みと管理サポートにより、InnerSource への貢献の増加という点で良い結果が出始めています。  
  
#### 実践への影響 - InnerSource と再利用  
  
a) Ericsson のような大規模な組織では、ADP Anchor のような中央ユニットが InnerSource イニシアチブを前進させる上で重要です。利害関係者 (一般的なマイクロサービスの潜在的な消費者や貢献者など) には、ガイダンス、トレーニング、および責任の明確な説明 (サービスに貢献した後の対応など) が必要です。  
  
b) InnerSource のポリシーとガイダンスは、さまざまな利害関係者が直面している現在の課題に応じて継続的に更新する必要があります。  
c) 資金と利用可能な時間の不足は、消費者が InnerSource 貢献を優先するのを妨げる主な課題の 1 つです。中間管理職の資金関連の懸念を解決するには、トップマネジメントの継続的なサポートを確保することが不可欠です。  
  
### 7.1.2 マーケットプレイスと再利用  
  
再利用を実践する際の課題の 1 つは、再利用可能な資産が見つけにくいことです。多くの場合、企業は再利用可能な資産を共有リポジトリで公開します。しかし、そのようなリポジトリには最適な検索機能やフィルターがない場合があります。さらに、大規模な組織では、すべてのチームやユニットがアクセスしたり表示したりできない場合があります。  
  
Ericsson のマーケットプレイスは、共通マイクロサービスの潜在的なすべての消費者が、必要なサービスを効率的に検索およびフィルターできるだけでなく、InnerSource への貢献も促進します。これは、消費者と貢献者が関連するマイクロサービスを調べることができるだけでなく、サービスへの統合や貢献のための対応するドキュメントやリンクを見つけることができるワンストップの場所です。  
  
調査参加者は、共通マイクロサービスの開発、発見、統合、および InnerSource への貢献においてマーケットプレイスが果たす役割を高く評価しました。同様の共有スペースは、ルーセント テクノロジーズ 、フィリップス、ノキア、ヒューレット パッカード、IBM 、ザランド、フィリップス ヘルスケア、ペイパル などの他の企業でも確立されています。  
  
マーケットプレイスと同様に、これらの共有スペースは通常、組織内のすべてのユーザーが利用できる Web ベースのポータルであり、共通アセットを検索したり、ドキュメントやコード リポジトリへのリンクにアクセスしたりできます。エリクソンのマーケットプレイスで使用されている成熟度と再利用性の階段の概念は、共通のマイクロサービスを分類する独自の方法を提供しますが、同様の共有スペースに関する報告されたケースでは見つかりませんでした。  
  
サービスの成熟度は、マイクロサービスのプロデューサーと消費者の両方に役立ちます。成熟度レベルは、マイクロサービスのチーム (プロデューサー) にロードマップを提供し、より高いレベルに移動するために実装する必要がある設計ルールを明確にします。同様に、消費者は成熟したマイクロサービスを検索してフィルタリングできるだけでなく、成熟度に基づいてマイクロサービスに期待できることを知ることもできます。一方、再利用性の階段は、1 つ以上のアプリケーションによって正常に再利用された (または再利用されていない) マイクロサービスを識別するのに役立ちます。調査参加者は、これら 2 つの階段が作業計画に役立つことを認識しました。つまり、プロデューサーはマイクロサービスのロードマップを計画し、消費者は再利用する適切なマイクロサービスを特定します。  
  
  
#### 実践への影響 - マーケットプレイスと再利用  
  
a) 再利用を伴う大規模な開発は、再利用可能な資産を簡単に見つけてフィルタリングできるマーケットプレイスのような効果的なポータルを導入しなければ不可能です。  
  
b) 再利用可能な資産の消費者も、統合と構成のサポートを必要とします。したがって、このような共有スペースは、消費者に再利用可能な資産をアプリケーションに統合する方法に関するサポートと指示も提供する必要があります。  
c) このような共有スペースは、潜在的な貢献者にガイダンス (貢献ガイドラインなど)、リンク (コード リポジトリなど)、その他のサポート (チュートリアルなど) を提供することにより、InnerSource イニシアチブにとっても重要です。  
  
  
## 7.2 マイクロサービス アーキテクチャ、DevOps、再利用  
  
ADP エコシステムは、コンテナを使用したクラウド ネイティブのマイクロサービス ベースのアーキテクチャを使用します。報告されたケースでは、再利用可能な資産は、Ericsson 全体のさまざまなアプリケーションに必要な共通機能を実装するマイクロサービスです。  
  
ソフトウェアの再利用は何十年も前から存在していますが、マイクロサービスは比較的最近の現象です。いくつかの大企業 (Netflix、Microsoft など) は、マイクロサービスを使用してサービスや製品を提供しています。調査されたケースでは、ADP プログラムと関係する実務家は、そのサイズと独立した展開により、マイクロサービスが再利用に適した単位であると判断しました。これは、他の企業のいくつかの報告された経験と一致しています。たとえば、Tizzei ら 、Assun¸c˜ao 、Gouigoux と Tamzalit も、マイクロサービスの使用がソフトウェアの再利用の改善に役立ったと述べています。しかし、これらの研究では、私たちの研究の焦点である、このような大規模なマイクロサービスの再利用については報告されていません。私たちの研究は、このような大規模なマイクロサービスの再利用を実践するという独自の視点を提供し、しかも、クラウドネイティブのコンテキストでの InnerSource および DevOps の実践など、現代のソフトウェア エンジニアリングの実践と組み合わせたものです。このような現代の再利用、つまり、新しい実践 (InnerSource や DevOps など) とテクノロジー (Docker、Kubernetes など) の助けを借りて、最新の再利用可能な資産 (つまり、マイクロサービス) の再利用を実践することの特徴をさらに明らかにし、理解するために、より多くの産業ケース スタディを実施する必要があります。   
  
Ericsson におけるマイクロサービスの大規模な再利用には、2 つの側面があります。1) 多数の共通マイクロサービス (調査時点で 280 を超える) は、どのアプリケーションでも再利用できる可能性があります。2) Ericsson では、共通マイクロサービスを再利用するアプリケーションが多数あります (たとえば、一部の共通マイクロサービスは 40 を超えるアプリケーションで使用されています)。この 2 つの側面の組み合わせは、共通マイクロサービスの新しいバージョンを、これらのサービスを利用するアプリケーションによる統合に利用できるようにするメカニズムを開発することが重要になることを意味します。  
  
Ericsson の CI/CD 戦略では、マイクロサービス独自の CI パイプラインが Spinnaker パイプラインの助けを借りてコンシューマー アプリケーションのアセンブリ パイプラインに接続されるメカニズムを提供しています。このメカニズムにより、共通マイクロサービスの新しいバージョンがリリースされると、コンシューマー アプリケーションのステージング環境でテスト プロセスに利用できるようになります。調査参加者によると、このメカニズムは Ericsson 全体でのマイクロサービスの大規模な開発と再利用を維持するための鍵となります。  
  
調査結果から、DevOps (CI/CD プラクティス) とマイクロサービスの大規模な再利用との関係が明らかになりました。ただし、DevOps と再利用の潜在的な関係を調査した調査は多くありません。さらに、設計ルールの概念とその自動チェックは、マイクロサービスの自動テストと継続的デリバリーにおいて重要な役割を果たしています。DR チェッカーは、マイクロサービスが基本原則、制約、要件に準拠しているかどうかを自動的にチェックできるため、マイクロサービス チームに高く評価されています。  
  
# 8 結論  
  
Ericsson では、InnerSource や DevOps などの最新の再利用プラクティスを採用したことにより、マイクロサービスの広範な再利用が可能になりました。  
最新の再利用の採用には、最新のプラクティスを習得するための能力の更新などのコストが必然的に発生します。ただし、コストは、品質、生産性、顧客エクスペリエンス、作業方法の改善などの長期的なメリットをもたらします。さらに、これらのプラクティスの採用には課題​​が伴います。むしろ、複数の関係者が新しい作業方法を採用しながら直面する課題に対処するために、作業方法を継続的に適応させなければならない道のりです。  
  
この道のりの初めには、再利用可能な資産のプロデューサー (例: 作業負荷の増加によりボトルネックが発生) とコンシューマー (例: 再利用可能な資産の成熟度が低い) の両方が課題に直面しました。Ericsson は、InnerSource の採用、設計ルールと一般的な要件の実装とチェックの自動化、一般的なマイクロサービスの成熟度の強化により、課題を軽減しました。   
  
Ericsson は、共通マイクロサービスに対する InnerSource の貢献が、マイクロサービス再利用の成長と持続性を促進する重要な要素であることを発見しました。今後の作業の一環として、InnerSource の貢献を詳細に調査し、InnerSource の貢献を成功に導く要因を特定する予定です。  
