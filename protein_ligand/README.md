Japanese translation of the SAMPL7 protein-ligand challenge  
日本語訳フォーク
<!-- # The SAMPL7 protein-ligand challenge -->
# SAMPL7 タンパク質-リガンド結合予測チャレンジ

<!-- We are excited to announce a new set of SAMPL7 challenges focusing on the binding of small fragment-like molecules to a relatively simple target protein. -->
新たな SAMPL7 チャレンジのお知らせ。比較的シンプルな標的タンパク質に対する、フラグメントライクな低分子の結合予測問題を提供する。  

<!-- The second bromodomain of PHIP (PHIP2)---a small protein for which little small molecule binding data is available---was targeted in an extensive X-ray crystallographic fragment screening experiment, leading to 3D structures of multiple screening hits. -->
PHIP というタンパク質の2番目のブロモドメイン、PHIP2 は低分子の結合に関するデータがほとんど無い小さなタンパク質だが、今回、X線結晶解析による徹底的なフラグメント化合物スクリーニング実験が行われ、複数のスクリーニングヒットの3次元構造が得られた。
<!-- This SAMPL7 challenge will take advantage of this dataset, assessing the accuracy of computational methods for the discrimination of binders from non-binders, binding pose prediction, and the unique opportunity to select new candidate ligands to be screened from a provided set of purchasable compounds that will be assessed experimentally by X-ray crystallography. -->
本 SAMPL7 チャレンジではこのデータセットを活用して、各計算手法の予測精度を評価する。すなわち、結合分子と非結合分子の識別タスク、結合様式予測タスク、さらには、購入可能な化合物セットからリガンド候補を選別してX線結晶解析で実験的に結合を評価する機会を提供する。

<!-- This challenge breaks out into at least three stages on a tight timeline:
1) Identification of binders from fragment screening
2) Prediction of fragment binding modes
3) Selection of new compounds for screening from an experimental database -->
本チャレンジは、タイトスケジュールだが少なくとも３段階から成る:  
1) フラグメントスクリーニングで見出された結合分子の予測  
2) 結合フラグメントの結合様式の予測  
3) ライブラリ化合物からの新規結合化合物選別

<!-- Stage 1 is now open and focuses on identification of binders. Unfortunately, the timeline for components 1 and 2 has to be tight given the timeframe for experimental compound screening (Stage 3). -->
現在ステージ１が開催中で、結合分子の同定にフォーカスしている。生憎、ステージ３の化合物スクリーニング実験のスケジュールの都合上、ステージ１と２は〆切がタイトとならざるを得ない。

<!-- If you plan to participate, please [join our SAMPL7 e-mail list](http://eepurl.com/gpBBun) so we can keep you updated.-->
参加したい場合は、[SAMPL7 メーリングリストに登録](http://eepurl.com/gpBBun) して頂ければアップデート情報が随時提供される。

<!-- ## System background -->
## 背景

<!-- The [Pleckstrin homology domain interacting protein (PHIP)](https://www.uniprot.org/uniprot/Q8WWQ0) is a multidomain protein that is involved in important cellular processes such as cytoskeletal organization, cell division and its deregulation was found to be involved in melanoma. -->
プレクストリン相同ドメイン相互作用タンパク質 ([Pleckstrin homology domain interacting protein; PHIP](https://www.uniprot.org/uniprot/Q8WWQ0)) は複数のドメインから成るタンパク質で、細胞骨格の構築や細胞分裂など重要な細胞現象に関わり、その機能異常はメラノーマの発生機序に寄与することが報告されている。

<!-- Two of PHIP’s domains are [bromodomains](https://en.wikipedia.org/wiki/Bromodomain), which are known to bind acetylated lysines.
These post-translationally modified protein residues can be found on the N-terminal tails of histones and mediate the regulation of gene expression. -->
PHIP の複数のドメインのうち、２つは [ブロモドメイン (bromodomains)](https://en.wikipedia.org/wiki/Bromodomain) であり、アセチル化リシンと結合することが知られている。このような翻訳語修飾が成されるアミノ酸残基はヒストン分子の N 末端テール領域に存在し、遺伝子発現制御を仲介する。
<!-- Bromodomains are attractive targets and several drugs are currently in clinical trials. -->
ブロモドメインは魅力的な創薬標的であり、既にいくつかの薬剤の臨床治験が実施されている。

<!-- X-ray crystallographic fragment screening experiments involve the [soaking of protein crystals with small fragment molecules](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Methods-for-Fragment-Screening.html) (<250 Da) into an apo crystal, followed by high-throughput automated X-ray crystallography and structure solution. -->
X線結晶解析によるフラグメントスクリーニング実験では、[低分子フラグメント（分子量250未満）を apo タンパク質結晶に浸潤させるソーキング法 (soaking)](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Methods-for-Fragment-Screening.html) で調製した試料をハイスループット自動化X線結晶解析に供し、構造を決定している。

<!-- This enables the identification of binders while providing high resolution structural information. -->
この実験によって、結合分子を同定すると同時に高解像度の構造情報が得られる。

<!-- Such experiments are now feasible in a high-throughput fashion thanks to infrastructures such as [XChem](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) where hundreds of crystals can be soaked and shot within a day. -->
[XChem](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) のようなインフラのおかげで１日で数百ものソーキング結晶を作製･測定することが可能となっており、上記のようなハイスループット実験が現実的なものとなっている。

<!-- The [second bromodomain of PHIP (PHIP2)](https://www.uniprot.org/uniprot/Q8WWQ0#family_and_domains) was utilized as target at [XChem](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) and a number of fragment hits were identified. -->
[XChem](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) において [PHIP の２番目のブロモドメイン (PHIP2)](https://www.uniprot.org/uniprot/Q8WWQ0#family_and_domains) を標的としてスクリーニングが実施され、複数のフラグメントヒット分子が同定された。

<!-- This unpublished dataset offers an opportunity to computational chemists and biochemists to test their predictive methods in a blind trial focused on protein-fragment complexes. -->
この未発表のデータセットを用いて、タンパク質-フラグメント複合体ブラインド予測の機会を提供するので、計算化学者･生化学者の皆は各自の予測手法を試すとよいだろう。

<!-- This edition of the SAMPL challenge will be divided into at least three stages. -->
本 SAMPL チャレンジは少なくとも３つのステージから成る。

<!-- ## Fragment screening at XChem -->
## XChem におけるフラグメントスクリーニング

<!-- This challenge is made possible through an exciting new collaboration with the [XChem fragment screening facility / Macromolecular Crystallography (MX) program](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) at the [Diamond Light Source](https://www.diamond.ac.uk/Home.html), with special thanks to [Harold Grosjean (Oxford)](https://www.linkedin.com/in/harold-grosjean-992741a8?originalSubdomain=uk), [Rachel Skyner (Diamond)](https://scholar.google.com/citations?user=qC2iEdMAAAAJ&hl=en), [Tobias Krojer (SGC Oxford)](https://thesgc.org/groupprofile/9489), and [Frank von Delft (SGC Oxford / Diamond)](https://www.thesgc.org/node/9489). -->
本チャレンジは [Diamond Light Source](https://www.diamond.ac.uk/Home.html) の [XChem fragment screening facility / Macromolecular Crystallography (MX) program](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) との新たなコラボレーションによって実現された。特に [Harold Grosjean (Oxford)](https://www.linkedin.com/in/harold-grosjean-992741a8?originalSubdomain=uk)、[Rachel Skyner (Diamond)](https://scholar.google.com/citations?user=qC2iEdMAAAAJ&hl=en)、[Tobias Krojer (SGC Oxford)](https://thesgc.org/groupprofile/9489)、[Frank von Delft (SGC Oxford / Diamond)](https://www.thesgc.org/node/9489) に感謝の意を表する。

<!-- The XChem fragment screening facility and Macromolecular Crystallography (MX) program at Diamond offer the ability to perform [high-throughput crystal soaking experiments](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) of several [fragment libraries](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html), and allow [both academic and industry groups](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Applying-for-XChem.html) to utilize their resources to advance drug discovery and the design of new chemical probes. -->
[フラグメント化合物ライブラリ群](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) を対象とした [ハイスループット結晶ソーキング実験](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) の実施機会を XChem fragment screening facility and Macromolecular Crystallography (MX) program at Diamond は提供しており、[アカデミアも企業のグループも](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Applying-for-XChem.html) 各自のリソースを用いて創薬や化学プローブのデザインのために利用することができる。

<!-- Academic groups can apply for access via a simple [two-page proposal](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Applying-for-XChem/Standard-access.html). -->
アカデミアのグループであれば簡単な [２ページのプロポーザル](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Applying-for-XChem/Standard-access.html) を提出することで応募して頂ける。

<!-- To get an idea for what existing XChem fragment screening datasets look like, you can use the [XChem Fragalysis browser](https://fragalysis.diamond.ac.uk) to interactively view fragment hits, or browse [all datasets available on Zenodo](https://zenodo.org/search?page=1&size=20&q=keywords:%22PanDDA%22) (example [here](https://zenodo.org/record/1244111#.XbiAzJNKiL4)). -->
既存の XChem フラグメントスクリーニングのデータセットの様態については、[XChem Fragalysis browser](https://fragalysis.diamond.ac.uk) でインタラクティブにフラグメントヒットを閲覧できるのでご覧頂けると良いだろう。もしくは、[全データセットを Zenodo 上で提供している](https://zenodo.org/search?page=1&size=20&q=keywords:%22PanDDA%22) （[例](https://zenodo.org/record/1244111#.XbiAzJNKiL4)）のでブラウジング可能となっている。

<!-- XChem also provides a [detailed overview of their fragment screening methods](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Methods-for-Fragment-Screening.html) and [available fragment libraries](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html). -->
また、XChem は [フラグメントスクリーニング法の詳細な概観](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Methods-for-Fragment-Screening.html) と [利用可能なフラグメントライブラリ群](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) についても開示しているので適宜参照されたい。

<!-- This project used both the [DSI-Poised fragment library](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Fragment-Libraries/DSI-poised-library.html) an the [Fraglites fragment library](https://pubs.acs.org/doi/abs/10.1021/acs.jmedchem.9b00304), but challenge participants are encouraged to use the provided `fragments_screened.csv` file for the exact chemical identities of compounds screened. -->
なお、本プロジェクトでは [DSI-Poised fragment library](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening/Fragment-Libraries/DSI-poised-library.html) 及び [Fraglites fragment library](https://pubs.acs.org/doi/abs/10.1021/acs.jmedchem.9b00304) を用いているが、チャレンジ参加者は所定の `fragments_screened.csv` に則って化合物 ID を取り扱うよう奨励する。

<!-- ## Overall participation instructions -->
## 参加要項

<!-- Instructions on overall participation in this challenge/challenge rules are given in [../protein_ligand_instructions.md](../protein_ligand_instrucitons.md). This document provides challenge details as well as specifics for each stage. -->
このチャレンジへの参加要項及びルールは [../protein_ligand_instructions.md](../protein_ligand_instructions.md) に示す通りである。この文書がチャレンジ詳細及び各ステージの細則を規定する。

<!-- ## Stage 1: Discrimination of binders from non-binders at specific sites -->
## ステージ１: 個々の結合部位における結合分子と非結合分子の識別

<!-- ### Setup and description of Stage 1 -->
### ステージ１の仕様

<!-- **Aim**: The objective of this first stage is to discriminate fragment binders from non-binders at each of the four sites identified by [PanDDA](https://pandda.bitbucket.io/) (pan-density data analysis), which facilitates the analysis of multiple crystallographic datasets to identify ligand binding sites and structural events. -->
**狙い**: このステージ１の目的は、[PanDDA](https://pandda.bitbucket.io/) (pan-density data analysis: リガンド結合部位と構造変化を同定するための結晶データセット解析ソフトウェア) で同定された４つの結合サイトそれぞれに関して、結合フラグメント分子と非結合フラグメント分子を識別することである。

<!-- A total of 799 unique fragments were screened at the [XChem facility](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html). -->
合計 799 種類のフラグメント分子が [XChem facility](https://www.diamond.ac.uk/Instruments/Mx/Fragment-Screening.html) でスクリーニングされた。

<!-- This will be validated by both positive hit data for PHIPA, and negative data where crystals were soaked and screened, but no readout identified binding. -->
この結果は、PHIPA に結合するポジティブヒット及び結合の見出されないネガティブデータとしてバリデートされる。

<!-- Fragment binding predictions here are important because accurate predictions could improve library design, including the ability to design bespoke libraries for specific targets. -->
特定の標的に対する特注ライブラリのデザイン含め、正確な結合予測によってフラグメントライブラリのデザインを改善できる可能性があり、フラグメント結合予測は重要な課題である。

<!-- PHIP2 was crystallized in space group C2 at 4C by vapour diffusion in ~230 nL sitting drops, by mixing 100 nL protein (in 10 mM HEPES, 5% glycerol, 500 mM NaCl and 0.5 mM TCEP pH 7.5) with 100 nL reservoir buffer (20% PEG8000 and 0.4 M potassium phosphate) and 30 nL seeds of the same composition. -->
PHIP2 は4℃にてシッティングドロップ蒸気拡散法で結晶化され、空間群 C2 に属していた。タンパク質溶液 100 nL (10 mM HEPES, 5% glycerol, 500 mM NaCl and 0.5 mM TCEP pH 7.5) とリザーバー緩衝液 100 nL (20% PEG8000 and 0.4 M potassium phosphate) を混合、そして同組成の 30 nL 種結晶を加えて ～230 nL の sitting drop を調製、最終溶液の pH は約 5.6 であった。
<!-- The final pH was measured to be about 5.6. -->

<!-- The resulting crystals were soaked with 20 mM final concentration of each fragment and 20%(v/v) ethylene glycol, plunged into liquid nitrogen and shot at the i04-1 beamline located at the Diamond Light Source (Harwell, UK). -->
生成した結晶には最終濃度 20 mM の各フラグメント化合物溶液 (20%(v/v) エチレングリコール) でソーキングを行い、液体窒素に注入し Diamond Light Source (Harwell, UK) の i04-1 beamline にて照射が実施された。

<!-- The diffraction data were analyzed with [PanDDA](https://pandda.bitbucket.io/) ([Pearce et al., 2017](https://www.nature.com/articles/ncomms15123)) which revealed a number of fragments located across four distinct sites. -->
回折データは [PanDDA](https://pandda.bitbucket.io/) ([Pearce et al., 2017](https://www.nature.com/articles/ncomms15123)) で解析され、４ヶ所の結合部位各々に結合フラグメントが見出された。

<!-- The first site (denoted by a helium atom `S1` in the provided structure (`PHIPA_C2_apo_sites.pdb`), see Manifest below) is the acetylated lysine binding site which is the most voluminous cavity. -->
１番目の結合部位（所定の構造 (`PHIPA_C2_apo_sites.pdb`) にてヘリウム原子 `S1` として表示; 後述の所定ファイルリスト参照）はアセチル化リシン結合部位であり、最も体積の大きいくぼみを形成している。位置は４ヘリックスバンドルの末端の非構造ループの間である。
<!-- It is located in between the disordered loops at the extremity  of the 4-helix bundle. -->

<!-- The second site (denoted by a neon atom `S2`) is a small pocket located near cysteine 1335. -->
２番目の結合部位（ネオン原子 `S2` として表示）は Cys1335 残基近傍にある小さなポケットである。

<!-- The third site (denoted by an argon atom `S3`) is solvent exposed and located near Aspartic acid 1384. -->
３番目の結合部位（アルゴン原子 `S3` として表示）は溶媒に露出しており、Asp1384 残基近傍にある。

<!-- The fourth and last site (denoted by a krypton atom `S4`) is also exposed to solvent and located behind a flexible loop near lysine 1399. -->
最後の４番目の結合部位（クリプトン原子 `S4`  として表示）も溶媒に露出しており、Lys1399 残基近傍の可動ループの後方に位置している。

<!-- An *apo* structure of PHIP2 has been provided (`PHIPA_C2_Apo.pdb`) along with the [isomeric SMILES strings](https://www.daylight.com/dayhtml/doc/theory/theory.smiles.html) (`fragments_screened.csv`) of the fragments screened. -->
PHIP2 の *アポ* 構造ファイル (`PHIPA_C2_Apo.pdb`) と、スクリーニング対象フラグメント化合物群の [isomeric SMILES strings](https://www.daylight.com/dayhtml/doc/theory/theory.smiles.html) (`fragments_screened.csv`) が提供される。

<!-- For the purposes of predicting whether a compound binds or not, consider the 20 mM concentration used for soaking fragments; compounds which bind observably at this concentration (after factoring in any applicable solubility issues) will be judged binders, and those which do not will be judged as nonbinders. -->
なお、化合物が結合するか否かを予測するにあたっては、フラグメント化合物のソーキング時の濃度である 20 mM での結合可否と考えてよい。（個別の溶解度の限界は踏まえた上で）当該濃度で結合が観測された化合物は結合化合物と判定し、そうでないものは非結合化合物と判定する。

<!-- We are asking you to submit both site-specific binding predictions (whether each compound binds at each specific site) as well as overall binding predictions (whether each compound binds at all), as detailed in the [submission format](stage1_submission_template.txt). -->
参加者の皆さんには、結合部位ごとの結合予測結果（各フラグメント化合物が各結合部位に結合するか否か）と結合予測全体（各化合物が結合するか否か）の両方を提出して頂く。詳細は [提出フォーマット](stage1_submission_template.txt) に記載の通りである。

<!-- You may elect to assess only binding to one specific site, or to all sites; we plan to analyze predictions for each site separately, as well as overall predictions. -->
各自は１ヶ所だけの結合部位に取り組んでもよいし、４つ全部やってくれてもよい。結果の分析は、個別の結合部位についても全体の結合可否についても行う予定である。


<!-- ### Provided data for Stage 1
- Apo structure of the protein: See Manifest below
- isomeric SMILES strings for the 799 fragments: See Manifest below
- Descriptions of the candidate binding sites are provided in the description above
- Coordinates of atoms marking the candidate binding sites are provided in the `PHIPA_C2_apo_sites.pdb` file, as described above
- Rules: See below
- Submission format: `stage1_submission_template.txt` -->
### ステージ１のための所定データ
- タンパク質のアポ構造: 下記ファイルリスト参照
- 799 フラグメント化合物を記載した isomeric SMILES strings: 下記ファイルリスト参照
- 各結合部位候補に関する説明（上記）
- 各結合部位候補を示すマーカー原子の座標（上記の通り `PHIPA_C2_apo_sites.pdb` 内に記載）
- 提出フォーマット: `stage1_submission_template.txt`

<!-- ### Rules for Stage 1 -->
### ステージ１のルール

<!-- **Start date**: Tuesday, October 29, 2019 -->
**開始日**: 2019 年 10 月 29 日 (火)

<!-- **Submissions due**: Thursday, Nov. 28, 2019, at midnight US Pacific Time -->
**提出〆切**: 2019 年 11 月 28 日 24 時 (US Pacific Time)

<!-- Your predictions must be uploaded via our web form (to be linked from here as soon as it is available) before midnight US Pacific time on the due date. The experimental results will be available as soon as possible after SAMPL closes. Please refer to the [../protein_ligand_instructions.md](../protein_ligand_instructions.md) for information on uploading. -->
各自の予測結果は、ウェブフォーム（準備出来次第ここにリンクする）を通じて〆切前にアップロードされなければならない。実験結果は SAMPL チャレンジがクローズし次第公開される予定である。アップロードの際には [../protein_ligand_instructions.md](../protein_ligand_instructions.md) を確認すること。

<!-- You must use the [provided template](stage1_submission_template.txt) to upload your predictions, and the file must have a filename beginning with `PHIP2`. We will be asking you to submit the compound identifier for each compound you predict to bind, along with a designation of which specific sites you predict it to bind to, if you are able to assess binding to specific subsites. Details as to how to submit this information are given in the [format file](stage1_submission_template.txt). Note that each submission must also be accompanied by a variety of methodological details, etc., as given in the submission format. Please refer to the [submission instructions](../protein_ligand_instructions.md) for details on what your method description should contain and how to upload. -->
予測結果をアップロードする際には、[所定のテンプレート](stage1_submission_template.txt) を用いること。ファイル名は `PHIP2` で始まるようにすること。結合分子であると予測した化合物の ID と、可能であればそれがどの結合部位に結合すると予測されたかを記載すること。これらの情報をどのように提出するかについては、[所定のフォーマットファイル](stage1_submission_template.txt) に記載されている。また、提出の際には、提出フォーマットに示されているように手法の詳細を付すこと。手法の記載に含めるべき内容の詳細及びアップロード方法については [提出要項](../protein_ligand_instructions.md) を参照すること。

<!-- While you are welcome to submit multiple entries in order to test diverse methods, as per our [policy on multiple submissions](https://samplchallenges.github.io/roadmap/submissions/), each participant or organization is allowed only one ranked submission, which must be clearly indicated as such by filling the appropriate field in the submission form. -->
様々な手法を試すために各自が複数のエントリーを提出することは歓迎だが、[複数提出の場合のポリシー](https://samplchallenges.github.io/roadmap/submissions/) に示す通り、順位が付く提出エントリーは各参加者もしくは各組織ごとに１つずつのみとなる。どれを順位付け対象とするかは提出フォームの該当欄で明示すること。

<!-- We also accept non-ranked submissions, which we will not formally judge. These allow us to certify that your calculations were done without knowing the answers, but do not receive formal ranking, as discussed at the link above. -->
順位付け対象外の提出エントリーも受け付けるが、公式の順位判定は成されない。こうすることによって、参加者が答えを知らない状態でブラインド計算したということを保証することができるが、公式順位は付かない。上記リンク先で議論されている通りである。

<!-- If multiple submissions are incorrectly provided as "ranked" by a single participant, we will judge only one of them; likely this will be the first submitted, but it may be a random submission. -->
１人の参加者が複数の提出エントリーを誤ってランキング対象として送信してしまった場合にも、公式順位を判定するのはそのうち１つのみである。恐らく１番目の提出エントリーを採用するが、違うかもしれない。

<!-- ### Manifest for Stage 1
- `fragments_screened.csv`: CSV file containing isomeric SMILES of compounds screened, along with identifiers
- `PHIPA_C2_Apo.pdb`: Structure for use in screening, as provided by XChem
- `PHIPA_C2_apo_sites.pdb`: *Apo* structure with manual addition of noble gas atoms to designate different potential binding sites, as described above (as provided by XChem)
- `stage1_submission_template.txt`: Sample submission format for submitting PHIP2 virtual screening results. -->

### ステージ１の所定ファイルリスト
- `fragments_screened.csv`: スクリーニング対象化合物群の isomeric SMILES と 化合物 ID が記載された CSV ファイル
- `PHIPA_C2_Apo.pdb`: XChem から提供されたスクリーニング用タンパク質構造
- `PHIPA_C2_apo_sites.pdb`: *アポ* 構造に希ガス原子で結合部位のマーカーを付けたもの（上述、XChem 提供）
- `stage1_submission_template.txt`: PHIP2 に対するバーチャルスクリーニング結果の提出フォーマットのサンプル

<!-- ## Stage 2: Prediction of binding poses for binding fragment -->
## ステージ２: 結合フラグメントの結合様式予測

<!-- Plans for stage 2 are still being finalized, but this is planned to involve predicting the bound structures of the compounds which bind, the identity of which will be released at the end of the first stage. -->
ステージ２の仕様は策定中。ただし、結合分子の結合様式の予測を含む予定である。結合分子の情報はステージ１終了時に公開される。

<!-- **Start date:** Friday the 29th of November 2019 -->
**開始日**: 2019 年 11 月 29 日 (金)

<!-- **End date:**  Thursday the 12th of December 2019 -->
**終了日**: 2019 年 12 月 12 日 (木)

<!-- ## Stage 3: Selection of novel binders from a database -->
## ステージ３: データベース化合物からの新規結合分子選別

<!-- Plans for Stage 3 are still being finalized. However, a brief summary follows below, which will be updated as plans are solidified. -->
ステージ３の仕様は策定中。ただし、簡潔な要旨は下記の通り。仕様が固まり次第アップデートされる。

<!-- **Aim**: The third stage of the SAMPL7 challenge will offer the unique opportunity to select new candidate ligands from a database of purchasable compounds. Cocrystal structures will have been released at the end of Stage 2, allowing participants to exploit that information to predict which new compounds bind to the target as well as their associated binding modes. Selected proposed ligands will be validated experimentally by X-ray crystallography at the Diamond Light Source using the C2 crystal form described in stage 1, but the number of ligands from each submission which are tested will depend on participation numbers. -->
**狙い**: SAMPL7 チャレンジのステージ３では、購入可能な化合物データベースから、新規リガンド候補を選別する機会を提供する。ステージ２の終了時に共結晶構造を公開するので、参加者はその情報を活用して新規結合分子をその結合様式と共に予測することとなる。提案されたリガンド群の中からX線結晶構造解析（ステージ１に記載の通りの C2 結晶を用いて Diamond Light Source にて実施する）に供するものを選び、実験的に結合を検証する。ただし、各提出エントリーから実験に供されるリガンドの数は、参加者数次第である。

<!-- Crystallography will be used to assay compounds for activity. Follow-up compounds should aim to improve biding and/or (predicted) potency from the hit they originated from. -->
化合物の活性をアッセイするために結晶解析を用いる。フラグメントヒットからのフォローアップ化合物で結合及び活性を更に改善することを目指す。

<!-- **Provided data**: Cocrystal structures, list of candidate compounds, possibly directing participants to predict binders to the main binding site of interest, rules for stage 3 of the challenge, and submission instructions. -->
**所定のデータ**: 共結晶構造、候補化合物リスト、主たる結合部位の指定、ステージ３のルール、提出要項。

<!-- **Start date:** Friday the 13th of December 2019 -->
**開始日**: 2019 年 12 月 13 日 (金)

<!-- **End date:**  Monday the 13th of January 2020 -->
**終了日**: 2020 年 1 月 13 日 (月)

<!-- ## Later stages -->
## 更なるステージ

<!-- Depending on the outcome of potential affinity measurements and other details, we may further extend this challenge by adding more stages. This remains to be determined. -->
アフィニティ測定の結果次第では、更なるステージを追加して本チャレンジを拡大する可能性がある。未定。
