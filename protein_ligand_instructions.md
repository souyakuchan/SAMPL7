<!-- # SAMPL7 Detailed Protein-Ligand (PHIP2) Instructions -->
# SAMPL7 タンパク質(PHIP2)-リガンド予測チャレンジ要項詳細

<!-- Details of the challenge itself, and what information you will submit at each stage, is available in [protein_ligand/README.md](protein_ligand/README.md). This document provides information on how submissions will be handled. -->
チャレンジ自体の詳細及び各ステージでの提出内容に関しては [protein_ligand/README.md](protein_ligand/README.md) に示す通り。ここでは、提出をどのように行うかについて述べる。

<!-- ## Due date -->
## 〆切

<!-- Due dates vary by challenge; refer to the main [README.md](README.md) for exact dates. -->
チャレンジごとに〆切は異なる。正確な日程については元の [README.md](README.md) で確認すること。

<!-- Your predictions must be uploaded via our [web form](http://sampl-submission.us-west-1.elasticbeanstalk.com/submit) before midnight US Pacific time on the due date. The experimental results will be available as soon as possible after SAMPL closes. Please refer to the below instructions for information on uploading. -->
各自の予測結果は、我々の [ウェブフォーム](http://sampl-submission.us-west-1.elasticbeanstalk.com/submit) 経由で〆切日の 24 時 (US Pacific time) までにアップロードされなければならない。実験結果は SAMPL のクローズののち可及的速やかに公開される。アップロードに関する細則は下記を参照すること。

<!-- You must use the provided templates to upload your predictions. Templates are:
- [protein_ligand/stage1_submission_template.txt](protein_ligand/stage1_submission_template.txt) for the virtual screening component
- (to be updated) -->
各自の予測結果をアップロードする際には必ず所定のテンプレートを用いること。テンプレートとは:
- [protein_ligand/stage1_submission_template.txt](protein_ligand/stage1_submission_template.txt) バーチャルスクリーニング結果提出用
- (随時更新予定)

<!-- File names must begin with the letters "PHIP2" and the additional details provided in the submission template. -->
ファイル名は `PHIP2` で始めること。その他の詳細については提出用テンプレート内に記載されている。

<!-- ## Multiple submissions -->
## 複数の提出エントリーについて

<!-- As per our [policy on multiple submissions](https://samplchallenges.github.io/roadmap/submissions/), each participant or organization is allowed only one ranked submission, which must be clearly indicated as such by filling the appropriate field in the submission form. We also accept non-ranked submissions, which we will not formally judge. These allow us to certify that your calculations were done without knowing the answers, but do not receive formal ranking, as discussed at the link above. -->
[複数提出の場合のポリシー](https://samplchallenges.github.io/roadmap/submissions/) に示す通り、順位が付く提出エントリーは各参加者もしくは各組織ごとに１つずつのみとなる。どれを順位付け対象とするかは提出フォームの該当欄で明示すること。順位付け対象外の提出エントリーも受け付けるが、公式の順位判定は成されない。こうすることによって、参加者が答えを知らない状態でブラインド計算したということを保証することができるが、公式順位は付かない。上記リンク先で議論されている通りである。

<!-- If multiple submissions are incorrectly provided as "ranked" by a single participant, we will judge only one of them; likely this will be the first submitted, but it may be a random submission. -->
１人の参加者が複数の提出エントリーを誤ってランキング対象として送信してしまった場合にも、公式順位を判定するのはそのうち１つのみである。恐らく１番目の提出エントリーを採用するが、違うかもしれない。

<!-- ## Anonymous participation -->
## 匿名参加について

<!-- Anonymous participation is not allowed. -->
匿名参加については許可していない。

<!-- ## Computational methods -->
## 計算手法

<!-- You may use any method(s) you like to generate your predictions; e.g. docking, shape-based methods, machine learning models, etc. We only ask that you clearly explain your method in your submission file. Null model submissions are also acceptable. -->
予測を生成するために各自あらゆる好きな手段を使ってよい。例えば、ドッキング、形状ベースの手法、機械学習モデルなど。我々が要求するのは、提出ファイル内で明確に手法を説明して頂くことのみである。ヌルモデルを提出してもらっても構わない。

<!-- ## Method descriptions -->
## 手法の記載について

<!-- Your method descriptions should give a detailed description of your approach, ideally with enough detail that someone could reproduce the work. These often serve to allow researchers to coordinate on why calculations which seem similar performed quite different in practice, so you should be sure to address how you generated poses, selected protonation states and tautomers if applicable, etc., as well as any method-specific details that, if varied, might result in different performance. Software versions should be provided. You will also need to assign a category to your method, as discussed below. -->
手法の記載においては各自がとったアプローチの詳細な説明をなすべきで、理想的には他人が作業を再現するのに充分な記載であること。これによって、同様な計算を実施したように見えるのに実際の振る舞いが極めて異なるような場合に、研究者間で原因究明にあたれる。なので、各参加者は、結合ポーズの生成法やプロトン化状態の選択、トートマーの選択などについて確実に記載すべきである。個別の手法において結果に影響を与えるような条件設定についても全て記載すること。ソフトウェアのバージョンも記載すること。用いた手法のカテゴリについても、下記の通り明示すること。

<!-- ## Method category -->
## 手法のカテゴリについて

<!-- In the Method Category section of your submission file please state which of the method category labels describe your prediction the best: `Docking`, `Ligand-based`, `MD`, `ML`, `Other`, `Null`. -->
提出ファイルの Method Category セクションでは、各自の予測手法が次のどのカテゴリに最も当てはまるかを選んで記載すること: `Docking`(ドッキング)、`Ligand-based`(リガンドベース)、`MD`（分子動力学法）、`ML`(機械学習)、`Other`（その他）、`Null`(ヌルモデル)。

<!-- If your method takes advantage of multiple approaches please report more than one category label, separated by comma.  
- `Docking` refers to structure-based virtual screening methods that model the structure of the receptor binding pocket and pose of the ligand followed by a scoring the goodness of the fit.
- `Ligand-based` methods are virtual screening methods that do not rely on protein structure such as pharmacophore modeling, ligand shape-based, 2D or 3D structural similarity based methods.
- `MD` methods utilize molecular dynamics simulations based on molecular mechanics including free energy calculations. Select this also if you used a docking or ligand-based approach combined with MD.
- `ML` category includes machine learning, QSPR approaches, and other predictive methods trained on empirical knowledge (however, docking approaches using empirical scoring functions belong in the `docking` category)
- `Null` predictions employ a model which is not expected to produce useful predictions (e.g., molecular weight). However, these can provide a simple comparison point for more sophisticated methods, as ideally, good methods should outperform the null model.
- `Other`: If these categories do not match your method, report as “Other”. If you choose the “Other” category, please explain your decision in the beginning of Method Description section. -->
もし手法が複数のカテゴリにわたるようであれば、コンマで区切って複数のカテゴリラベルを記載すること。
- `Docking` は構造に基づくバーチャルスクリーニング法を指す。受容体の結合ポケットの構造とリガンドの結合様式をモデリングし、当てはまりの良さがスコア化される。
- `Ligand-based` 法はタンパク質の構造情報を用いないバーチャルスクリーニング法である。ファーマコフォアモデリングやリガンド形状比較、2D/3D 構造類似性など。
- `MD` 法は分子力学に基づく分子動力学シミュレーションを用いる手法で、それによる自由エネルギー計算も含む。ドッキングやリガンドベースの手法と共に MD を併用した場合にも、このカテゴリラベルを選択すること。
- `Null` はまともな予測にはならないと考えられるモデル（例えば分子量をそのまま使うなど）である。ただし、他のより洗練された手法との比較には使えることがある。理想的には、良い手法はヌルモデルより性能が良いはずである。
- `Other`: これらの手法に当てはまらない場合、"Other" を選択すること。"Other" を選んだ場合、手法の記載セクションの冒頭に、なぜそう選んだかを説明すること。


<!-- ## Uploading your predictions -->
## 予測結果のアップロードについて

<!-- (This section will be updated with a URL once our submission site is ready to receive submissions.) -->
（このセクションは、提出用ウェブサイトが準備出来次第 URL を記載して更新される。）

<!-- If you want to upload more than one set of predictions, generated by different methods, each set must be uploaded as a separate file. Please use the template provided, as the predictions will be parsed and analyzed with automated scripts, and if you violate the file format, you will receive an error message and your submission will not be accepted. A complete set of predictions constitutes predicted binding free energies for all required host-guest pairs, with predicted numerical uncertainties. We also encourage predictions of the binding enthalpies. Incomplete submissions - such as for a subset of compounds - will also be accepted if desired (contact David Mobley if this is needed, as currently our submission system checks for completeness), but would be treated as "verified" submissions rather than "ranked" submissions. However, omission of enthalpies and/or bonus cases will not cause a submission to be regarded as incomplete. -->
*訳注: タンパク質-リガンド予測チャレンジではなくホスト-ゲスト予測チャレンジの内容のまま流用された記載となっているようです*  

異なる手法で生成した１セット以上の予測結果を提出したい場合は、各セットは別々のファイルとしてアップロードされなければならない。提出物は自動化スクリプトによってパースされて解析されるので、必ず所定のテンプレートを用いること。所定のファイル形式を守らなかった場合、エラーメッセージが返されて提出が拒絶される。全てのホスト-ゲストペアについての予測された結合自由エネルギー（と数値の不確実性）を以って完全な提出物となる。結合エンタルピーの予測の実施も奨励する。一部の化合物についてなど、不完全な提出エントリーとなっている場合にも、ご要望とあらば受付可能（提出システムは不完全なエントリーを弾いてしまうので、その場合は David Mobley に連絡すること）であるが、ランキング対象とはならず "verified" な提出エントリーとして取り扱われる。ただし、エンタルピー予測もしくはボーナスケースについては、提出省略しても不完全な提出エントリー扱いとはならない。

<!-- Names of the uploaded prediction files must begin with the name of the challenge component for which it contains predictions, as in the provided templates (i.e., PHIP2). -->
アップロードする予測結果ファイルのファイル名は、所定のテンプレート同様、予測対象のチャレンジ名で始めること。（例: PHIP2）

<!-- The file will be machine parsed, so correct formatting is essential. -->
ファイルは機械的にパースされるので、正しいフォーマットであることが必須である。

<!-- Lines beginning with a hash-tag (#) may be included as comments. These and blank lines will be ignored. -->
ハッシュタグ (#) で始まる行は、コメント行として扱われ、空行と共に無視される。

<!-- The file must contain the following five components in the following order: your predictions, a name for your computational protocol, a list of the major software packages used, a long-form methods description, and, finally, whether your submission is to be ranked or not. Each of these components must begin with a line containing only the corresponding keyword: Predictions:, Name:, Software:, Method:, and Ranked:, as illustrated in the example files. The last field should have a boolean value (True or False). See above information on "multiple submissions" for discussion of the role this plays. -->
ファイル内には、次の５つの内容がこの順で含まれていなければならない: 予測結果、用いた計算プロトコルの名称、予測に用いた主たるソフトウェアパッケージのリスト、手法の記載の長文バージョン、そして最後に、当該提出エントリーをランキング対象とするか否か。各項目は、対応するキーワード（Predictions:, Name:, Software:, Method:, and Ranked:）のみを含む行で始まらなければならない。最後のフィールドは boolean 値 (True or False) である。これが意図するところに関する議論については、上記の "複数の提出エントリーについて" を参照すること。
