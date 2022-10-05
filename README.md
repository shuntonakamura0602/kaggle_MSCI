# kaggle_MSCI
MSCIに参加したときのkaggle日記

# 最終結果

# timeline
* ~11/15

# 方針
* notebookで行った内容はすべてREADME.mdに記録する
* 思いついたアイデアをREAD.mdに書き込む

# アイデア

# do
* NNで次元削減
* testのdonor4で擬似ラベリング
* 逆変換して生データにもどしてNNに流す

# done

# paper
* 参考にした論文の一覧

# design


* 分析設計

問題の理解:cite;遺伝子発現レベル>タンパク質発現レベル,multi;オープンクロマチン領域>遺伝子発現レベル

分析の設計:ローカルで実装

* バリデーション設計

* EDA

* クレンジング/クリーニング

* データ前処理

* 特徴量エンジニアリング

* データセット作成/特徴量選択

* バリデーション設計

* モデル学習

* アンサンブル

* 後処理


# Log

## 20221005
<img width="839" alt="スクリーンショット 2022-10-05 12 26 01" src="https://user-images.githubusercontent.com/63344524/193975652-88d13f45-a373-4e9b-8ba7-691c74524736.png">
* cite targetはドナーごと・dayごとでそれぞれ分布が異なっている(グレー：全体の分布,オレンジ：指定した分布)
* cite private:day2・3・4のdonor1~3を学習して、day7のdonor1~4を予測
* cite cv:day2のdonor1~2を学習して、day3のdonor1~3を予測(これをdayやdonorをずらした回数おこなう)しかし、計算量を節約するためday2・3のdonor1~2を学習してday4のdonor1~3を予測(donorをずらす)こともできる(https://aizine.ai/cross-validation0910/)

## 20221003
* {gene_names}_{gene_ensemble-ids}に関して、どちらもgeneの名前である(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/346761)
* cite_inputs:遺伝子発現レベル(行：細胞id,列：遺伝子id)
* cite_targets:タンパク質発現レベル(行：細胞id,列：遺伝子id(タンパク質))
* multi_inputs:オープンクロマチン領域(行：細胞id,列：遺伝子id)
* multi_targets:遺伝子発現レベル(行：細胞id,列：遺伝子id)


## 20221002
* privateとpublicはかなり違う、ドメインシフトに対してロバストである必要がある(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/347202)
* 決定木モデルはcv↑lb↓になりやすい(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/352567)
* privateに対して妥当なcvを作成し、trust cv
* 4人のドナーの細胞は別々のプレートに置かれ、各細胞は一つの時点のみで測定されその後破棄される。つまり一つの細胞についての時系列データを得ることはできない。細胞はプレートからランダムサンプリングされる。(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/348524) (https://www.kaggle.com/competitions/open-problems-multimodal/discussion/347813)
* meta.dayでgkfした

## 20221001
* discussion読んだ

## 20220930
* lb・cv理解
* cv実装

|filename|cite_cv|multi_cv|all_cv|lb|
|--------|-------|--------|------|--|
|lgbm2ridge1.csv|0.88207|0.660|0.81811384|0.803|

## 20220929
* データ圧縮
* multi/citeでbaseline
* 初sub

|filename|cv|lb|
|--------|--|--|
|first.csv||0.802|

## 20220928
* join!
* 題材が難しい
* EDA確認した
