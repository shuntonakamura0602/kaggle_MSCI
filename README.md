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
* NNで次元削減(非線形変換)
* testのdonor4で擬似ラベリング
* 逆変換して生データにもどしてNNに流す
* ノイズが多い(batch　effectによる)ならdartを試す

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
## 20221007
* kaggleに質問を投稿した(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/358209)

## 20221005
* メタデータの分布

<img width="862" alt="スクリーンショット 2022-10-05 16 58 40" src="https://user-images.githubusercontent.com/63344524/194189598-d9e0f85d-1d35-4d71-8746-8c8646a1aa99.png">

* 細胞の分布

<img width="862" alt="スクリーンショット 2022-10-05 16 59 17" src="https://user-images.githubusercontent.com/63344524/194189760-97d7e560-d3cc-46c7-934e-ac7a8430b6cd.png">

* cite inputsの0を除いた全体の遺伝子発現レベルの分布

<img width="862" alt="スクリーンショット 2022-10-05 17 00 29" src="https://user-images.githubusercontent.com/63344524/194189941-b1f4e27b-4df1-434d-af6d-1f348cc853eb.png">

* cite inputsの0を除いた一部の遺伝子idごとの遺伝子発現レベルの分布

<img width="862" alt="スクリーンショット 2022-10-05 17 01 00" src="https://user-images.githubusercontent.com/63344524/194190189-ba6ee3ed-0299-4c79-9699-2d1ebf4243e4.png">

* cite inputsをdonor/dayごとに二次元に射影したもの(黄色の点がある9つの図は学習データ、下のオレンジの点がある3つの図は公開テストセット、右側の濃い赤の4つの図はプライベートセット、灰色の部分は全学習データを指す、黒い部分はテストデータ全体を指す)

<img width="641" alt="スクリーンショット 2022-10-05 17 05 37" src="https://user-images.githubusercontent.com/63344524/194191561-eb696b52-3b72-40f7-acdb-7c8ea1e6473c.png">

* cite targetsの一部のタンパク質発現レベルの分布:分布が様々でターゲットの種類が140種類もあるため一律的なアプローチは避けた方がよさそう」

<img width="641" alt="スクリーンショット 2022-10-05 17 06 24" src="https://user-images.githubusercontent.com/63344524/194192114-4739d88e-b95c-4f02-a826-9c8a17cdf79c.png">

* cite targetsの全体のタンパク質発現レベルの分布

<img width="839" alt="スクリーンショット 2022-10-05 12 26 01" src="https://user-images.githubusercontent.com/63344524/193975652-88d13f45-a373-4e9b-8ba7-691c74524736.png">

* multi inputsの0を除いた全体のオープンクロマチン領域の分布

<img width="641" alt="スクリーンショット 2022-10-05 17 07 24" src="https://user-images.githubusercontent.com/63344524/194192555-e5ea1293-b4fc-44e9-a708-d52c94446f66.png">

* Y染色体の分布(学習データの一人が女性である)

<img width="641" alt="スクリーンショット 2022-10-05 17 07 49" src="https://user-images.githubusercontent.com/63344524/194192784-412ac864-6f05-4d3b-b408-2e9615bb8f9f.png">

* multi targetsの0を除いた一部の遺伝子発現レベルの分布

<img width="641" alt="スクリーンショット 2022-10-05 17 08 05" src="https://user-images.githubusercontent.com/63344524/194193017-c0caf899-6005-4836-96e9-7fb6359040b4.png">




* cite targetはドナーごと・dayごとでそれぞれ分布が異なっている(グレー：全体の分布,オレンジ：指定した分布)
* cite private:day2・3・4のdonor1・2・3を学習して、day7のdonor1・2・3・4を予測
* cite cv:day2のdonor1・2を学習して、day3のdonor1・2・3を予測(これをdayやdonorをずらした回数おこなう)しかし、計算量を節約するためday2・3のdonor1・2を学習してday4のdonor1・2・3を予測(donorをずらす)こともできる(https://aizine.ai/cross-validation0910/)
* batch effect:異なる実験環境（バッチ）で計測されたデータの場合、同じ臓器・細胞であっても、バッチ間でデータに大きく差が生じる
* 特にsingle-cell RNA-Seqの場合、低発現の遺伝子は検出限界により、計測されづらくなる"ドロップアウト"現象があり、実験プロトコルにより、ドロップアウトの程度が全く異なる。そのため、異なるsingle-cell RNA-Seq実験同士、またはsingle-cell RNA-Seqとbulk-cell RNA-Seq同士では、そのままでは正当な比較が行えないと考えられる。現在は、ドロップアウトするような低発現な遺伝子には着目せず、細胞型特異的に変動する遺伝子にのみ着目し、細胞型を同定するためのアルゴリズムを開発している。
* adversal validation:testデータに似たvalidationデータを作成する手法(https://www.acceluniverse.com/blog/developers/2020/01/kaggleadversarial-validation.html#:~:text=Adversarial%20Validation%E3%81%AFTrain%E3%83%87%E3%83%BC%E3%82%BF,%E3%81%AB%E4%BD%BF%E3%82%8F%E3%82%8C%E3%82%8B%E6%89%8B%E6%B3%95%E3%81%A7%E3%81%99%E3%80%82)

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
