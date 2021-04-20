# About UNMET

UNMET stands for UNified METrics for unmappable, undetectable and unreliable genomic loci with short-read NGS.

UNMETスコアは、ショートリードNGSを用いたゲノム配列解析において、各塩基についてのバリアント検出における分析的妥当性をスコア化したものです。スコアは、[0, 1]の範囲の値をとり、値が1に近いほどNGSでの分析が難しいことを表しています。


## IGVを用いたスコアの可視化

IGVを用いて、UNMETスコアを表示させることができます。
IGVを起動し、ファイルメニューから、セッションファイルを開きます。


#### 使い方

1. 上記"Code"からこのリポジトリのZIPファイルをダウンロードします。
2. [IGV](https://software.broadinstitute.org/software/igv/download)をダウンロードします。
3. IGVを起動します。
4. Fileメニューから、Open Session...を選択し、ダウンロードしたリポジトリから、セッションファイル(UNMET_igv_session.xml)を選択します。

#### 表示例
<img width="1467" alt="UNMET-igv-snapshot" src="https://user-images.githubusercontent.com/2074467/115367252-02c40580-a201-11eb-9133-4eab9bdbe22e.png">


#### 各トラックの見方

* UNMET score
	* 各塩基の難読性（ショートリードNGSを用いた時の信頼性の高いバリアントの得られ難さ）をスコア化した値（[0, 1]の範囲）。値が大きいほど難読性が高いことを示す。

* gnomADカバレッジ
	* [gnomAD v3.1](https://gnomad.broadinstitute.org/downloads) の、ゲノムカバレッジ中央値をZスコア化して絶対値化した値。値が大きいほど、平均的な値から外れていることを示す。

* gnomADエクソームカバレッジ
	* [gnomAD v2.1.1](https://gnomad.broadinstitute.org/downloads) の、エクソームカバレッジの中央値。>100以上は100に固定。

* マッパビリティ
	* ゲノム上で、リードの配列がユニークにマッピングされる可能性を表す指標（(0, 1]の範囲をとる。マッパビリティ=1は、リードがユニークにマップされることを表す）。
	* [GenMap](https://academic.oup.com/bioinformatics/article/36/12/3687/5815974)ソフトウェアを用いて算出（パラメータ：リード長=150bp、許容ミスマッチ=2）。

* タンデムリピート
	* [TandemRepeat Finder(TRF)](https://academic.oup.com/nar/article/27/2/573/1061099)ソフトウェアを用いて算出

* ホモポリマー
	* 連続７塩基以上の領域を算出

* 低複雑度領域（Low complexity region, LCR)
	* [Symmetric DUST](https://www.liebertpub.com/doi/10.1089/cmb.2006.13.1028?url_ver=Z39.88-2003&rfr_id=ori:rid:crossref.org&rfr_dat=cr_pub%20%200pubmed)ソフトウェアを用いて算出

* 遺伝子発現量
	* [GTEx v8](https://gtexportal.org/home/)のデータに基づく。エクソン単位の遺伝子発現量（TPM値）。数値は、全組織間の発現量のうち最大値を示す。

* ALT loci
	* UCSC Genome browserに登録されている、ヒトゲノムのAlternate lociの情報。

* 構造多型情報
	* [DGV (Database of Genomic Variants)](http://dgv.tcag.ca/dgv/app/home)データベースに登録されている構造多型の情報を示す。

* Segmental duplication
	* UCSC Genome browserに登録されている、Segmental Dupsの情報。

　



