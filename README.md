# kaggle_MSCI

# 最終結果
<img width="602" alt="スクリーンショット 2023-01-25 11 11 08" src="https://user-images.githubusercontent.com/63344524/214465069-827e1741-7572-4489-91af-41cf1ad9ab88.png">

銀メダルが61位のためあと少しだった

public LB

<img width="1088" alt="スクリーンショット 2023-02-21 15 39 31" src="https://user-images.githubusercontent.com/63344524/220266836-5704b889-8089-4681-8c67-4476b17e1e9c.png">

若干shake downしている
他の人と異なるvalidationが大きな原因だと思われる
![image](https://user-images.githubusercontent.com/63344524/220280995-742fce61-61b6-49ee-bd5c-882f49d8c3fc.png)
![image](https://user-images.githubusercontent.com/63344524/220281011-1b386f7d-df37-4efe-aff1-5da720010122.png)
![image](https://user-images.githubusercontent.com/63344524/220281029-4f928d7c-2eba-483c-927e-62374df1452b.png)
![image](https://user-images.githubusercontent.com/63344524/220281049-31b05fed-b699-42cb-978d-3f2645cf036c.png)
![image](https://user-images.githubusercontent.com/63344524/220281064-ce80ee04-3373-43e3-82f9-2ab38a1785a5.png)
![image](https://user-images.githubusercontent.com/63344524/220281078-b3b94e39-f695-4065-a202-93b36505cc67.png)
![image](https://user-images.githubusercontent.com/63344524/220281097-4b2ba565-3d0b-435c-9c72-8be7e3094efb.png)
![image](https://user-images.githubusercontent.com/63344524/220281114-b934d59a-e11f-41c8-9669-659762444d45.png)
![image](https://user-images.githubusercontent.com/63344524/220281134-b3ea5404-361a-4ca9-be25-98abacd29d55.png)
![image](https://user-images.githubusercontent.com/63344524/220281151-77433f50-1fb9-4e87-93f8-0584f8dc6375.png)

# 使用したモデル
<img width="605" alt="スクリーンショット 2023-03-23 14 01 02" src="https://user-images.githubusercontent.com/63344524/227107902-5bc8d897-2187-449f-9d26-4362c386a732.png">

# timeline
* ~11/15

# 方針
* notebookで行った内容はすべてREADME.mdに記録する
* 思いついたアイデアをREAD.mdに書き込む

# Leader board
|filename|cv|lb|
|--------|--|--|
|first.csv||0.802|

|filename|cite_cv|multi_cv|all_cv|lb|
|--------|-------|--------|------|--|
|lgbm2ridge1.csv|0.88207|0.660|0.81811384|0.803|

* cv変更後

multi adv=(10592,180000),adv2=(10592,210000),adv3=(10592,200000),adv4=(10592,190000)

|filename|multi_pri_cv|multi_pub_cv|comment|
|--------|------------|------------|-------|
|ridge2.csv|-|-|dataset:original|
|keras2.csv|-|-|dataset:svd512[:,:40]|
|keras3.csv|-|-|dataset:archive|
|keras4.csv|-|-|dataset:archive|
|keras5.csv|0.60613|0.66821|dataset:original-svd512[:,:40]|
|keras6.csv|0.60499|0.66800|dataset:original-svd512[:,:100]|
|keras7.csv|0.60441|0.66781|dataset:original-svd512[:,:200]|
|keras8.csv|0.60404|0.66769|dataset:original-svd512[:,:300]|
|keras9.csv|0.60313|0.66757|dataset:original-svd512[:,:400]|
|keras10.csv|0.60208|0.66734|dataset:original-svd512[:,:512]|
|keras11.csv|0.60361|0.66763|dataset:original-svd256[:,:256]|
|keras12.csv|0.60413|0.66782|dataset:original-svd256[:,:200]|
|keras13.csv|0.60476|0.66801|dataset:original-svd256[:,:100]|
|keras14.csv|0.60540|0.66807|dataset:original-svd256[:,:50]|
|keras15.csv|0.60471|0.66789|dataset:original-svd256[:,:25]|
|keras16.csv|0.60463|0.66791|dataset:original-svd128[:,:128]|
|keras17.csv|0.60495|0.66800|dataset:original-svd128[:,:64]|
|keras18.csv|0.60554|0.66801|dataset:original-svd128[:,:32]|
|keras19.csv|0.60533|0.66713|dataset:original-svd128[:,:16]|
|keras20.csv|0.60404|0.66771|dataset:original-svd64[:,:64]|
|keras21.csv|0.60461|0.66778|dataset:original-svd64[:,:32]|
|keras22.csv|0.60613|0.66821|svd_original_varianced512[:,:40]|
|keras23.csv|0.60440|0.66665|svd_minmax_varianced512[:,:40]|
|keras24.csv|0.60606|0.66847|svd_sqrt_varianced512[:,:40]|
|keras25.csv|0.60625|0.66800|svd_standard_varianced512[:,:40]|
|keras26.csv|0.60527|0.66845|svd_log_varianced512[:,:40]|
|keras27.csv|0.60500|0.66812|svd_original_varianced512[:,:40],std|
|keras28.csv|0.60395|0.66665|svd_minmax_varianced512[:,:40],std|
|keras29.csv|0.60551|0.66848|svd_sqrt_varianced512[:,:40],std|
|keras30.csv|0.60527|0.66819|svd_standard_varianced512[:,:40],std|
|keras31.csv|0.60530|0.66838|svd_log_varianced512[:,:40],std|
|keras32.csv|0.60561|0.66831|svd_sqrt_varianced512[:,:40],std,x0batch normalization|
|keras33.csv|0.60537|0.66853|svd_sqrt_varianced512[:,:40],std,x0x1batch normalization|
|keras34.csv|0.60533|0.66874|svd_sqrt_varianced512[:,:40],std,x0x1x2batch normalization|
|keras35.csv|0.60440|0.66880|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization|
|keras36.csv|0.26110|0.53178|svd_sqrt_varianced512[:,:40],std,x0x1x2x3xbatch normalization|
|keras37.csv|0.28706|0.66756|svd_sqrt_varianced512[:,:40],std,xbatch normalization|
|keras38.csv|0.60461|0.66834|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,mish|
|keras39.csv|0.60334|0.66839|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,swish|
|keras40.csv|0.60440|0.66880|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=256,oof|
|keras41.csv|0.60288|0.66877|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras42.csv|0.60068|0.66877|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=1024|
|keras43.csv|0.60456|0.66877|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=128|
|keras44.csv|0.60581|0.66853|svd_standard_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras45.csv|0.60509|0.66877|svd_log_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras46.csv|0.60288|___0.66879___|svd_sqrt_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512,以下pri-oof実装|
|keras47.csv|0.60421|0.66850|svd_sqrt_varianced512[:,:40],行std,x0x1x2x3batch normalization,bs=512|
|keras48.csv|0.60269|0.66876|svd_sqrt_varianced512[:,:50],std,x0x1x2x3batch normalization,bs=512|
|keras49.csv|0.60267|0.66870|svd_sqrt_varianced512[:,:60],std,x0x1x2x3batch normalization,bs=512|
|keras50.csv|0.60279|0.66849|svd_original_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras51.csv|0.60471|0.66820|svd_original_varianced512[:,:40],行std,x0x1x2x3batch normalization,bs=512|
|keras52.csv|0.60015|___0.66878___|svd_log_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras53.csv|0.60579|0.66847|svd_log_varianced512[:,:40],行std,x0x1x2x3batch normalization,bs=512|
|keras54.csv|0.60298|0.66845|svd_standard_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras55.csv|0.60569|0.66807|svd_standard_varianced512[:,:40],行std,x0x1x2x3batch normalization,bs=512|
|keras56.csv|0.60090|0.66705|svd_minmax_varianced512[:,:40],std,x0x1x2x3batch normalization,bs=512|
|keras57.csv|0.60196|0.66647|svd_minmax_varianced512[:,:40],行std,x0x1x2x3batch normalization,bs=512|
|keras58.csv|0.60524|0.66857|svd_sqrt_varianced512[:,:40],std,bs=512|
|keras59.csv|0.60494|0.66829|svd_sqrt_varianced512[:,:40],行std,bs=512|
|keras60.csv|0.60484|0.66827|svd_original_varianced512[:,:40],std,bs=512|
|keras61.csv|0.60547|0.66798|svd_original_varianced512[:,:40],行std,bs=512|
|keras62.csv|0.60522|0.66857|svd_log_varianced512[:,:40],std,bs=512|
|keras63.csv|___0.60664___|0.66820|svd_log_varianced512[:,:40],行std,bs=512|
|keras64.csv|0.60539|0.66822|svd_standard_varianced512[:,:40],std,bs=512|
|keras65.csv|___0.60641___|0.66780|svd_standard_varianced512[:,:40],行std,bs=512|
|keras66.csv|0.60325|0.66665|svd_minmax_varianced512[:,:40],std,bs=512|
|keras67.csv|0.60432|0.66628|svd_minmax_varianced512[:,:40],行std,bs=512|
|||||
|||||
|||||





cite adv2=(70988, 11699),adv3=(70988, 22050),adv4=(70988, 17050),adv5=(70988, 14550),adv6=(70988, 12050)

|filename|cite_pri_cv|cite_pub_cv|comment|
|--------|-----------|-----------|-------|
|lgbm4.csv|0.87536|-|dataset:original|
|lgbm5.csv|0.87529|-|dataset:adv|
|keras1.csv|0.88511|-|dataset:original N_COMPONENT=64|
|keras2.csv|0.85800|-|dataset:adv|
|keras3.csv|0.87134|-|dataset:adv2|
|keras4.csv|0.88221|-|dataset:adv3[:2500]|
|keras5.csv|0.88006|-|dataset:adv4[:5000]|
|keras6.csv|0.87623|-|dataset:adv5[:7500]|
|keras7.csv|0.87235|-|dataset:adv6[:10000]|
|keras8.csv|0.88354|-|dataset:adv7[:1000]|
|keras9.csv|0.88476|-|dataset:original N_COMPONENT=128|
|keras10.csv|0.88447|-|dataset:original N_COMPONENT=256|
|keras11.csv|0.88354|-|dataset:original N_COMPONENT=512|
|keras12.csv|0.88684|-|dataset:original-svd512[:,:75]|
|keras13.csv|0.88688|0.89409|dataset:original-svd512[:,:75]|
|keras14.csv|0.88187|0.89152|dataset:original-svd512|
|keras15.csv|0.88586|0.89410|dataset:original-svd512[:,:150]|
|keras16.csv|0.88454|0.89327|dataset:original-svd512[:,:250]|
|keras17.csv|0.88361|0.89241|dataset:original-svd512[:,:350]|
|keras18.csv|0.88251|0.89192|dataset:original-svd512[:,:450]|
|keras19.csv|0.88440|0.89307|dataset:original-svd256|
|keras20.csv|0.88674|0.89419|dataset:original-svd256[:,:80]|
|keras21.csv|0.88577|0.89373|dataset:original-svd256[:,:160]|
|keras22.csv|0.88598|0.89380|dataset:original-svd128|
|keras23.csv|0.88668|0.89408|dataset:original-svd128[:,:84]|
|keras24.csv|0.88690|0.89388|dataset:original-svd128[:,:42]|
|keras25.csv|0.88688|0.89395|dataset:original-svd64|
|keras26.csv|0.88677|0.89335|dataset:original-svd64[:,:32]|
|keras27.csv|0.87568|0.88539|dataset:adval2-svd512[:,:512]|
|keras28.csv|0.87790|0.88690|dataset:adval2-svd512[:,:256]|
|keras29.csv|0.87983|0.88805|dataset:adval2-svd512[:,:128]|
|keras30.csv|0.88085|0.88857|dataset:adval2-svd512[:,:64]|
|keras31.csv|0.88129|0.88871|dataset:adval2-svd512[:,:32]|
|keras32.csv|0.88523|0.89176|dataset:adval3-svd512[:,:32]|
|keras33.csv|0.88383|0.89092|dataset:adval4-svd512[:,:32]|
|keras34.csv|0.88240|0.88997|dataset:adval5-svd512[:,:32]|
|keras35.csv|0.88118|0.88832|dataset:svdtoadv462[:,:32]|
|keras36.csv|0.88669|0.89420|dataset:pca_original_varianced512[:,:75]|
|keras37.csv|0.88548|0.89311|dataset:pca_log_varianced512[:,:75]|
|keras38.csv|0.88643|0.89373|dataset:pca_minmax_varianced512[:,:75]|
|keras39.csv|0.88558|0.89319|dataset:pca_sqrt_varianced512[:,:75]|
|keras40.csv|0.88733|0.89429|dataset:pca_standard_varianced512[:,:75]|
|keras41.csv|0.88755|0.89468|dataset:pca_standard_varianced512[:,:75],X0&X0tを追加|
|keras42.csv|0.88692|0.89411|dataset:svd_original_varianced512[:,:75]|
|keras43.csv|0.88557|0.89302|dataset:svd_log_varianced512[:,:75]|
|keras44.csv|0.88630|0.89357|dataset:svd_minmax_varianced512[:,:75]|
|keras45.csv|0.88569|0.89329|dataset:svd_sqrt_varianced512[:,:75]|
|keras46.csv|0.88745|0.89460|dataset:svd_standard_varianced512[:,:75]|
|keras47.csv|0.87839|0.88124|dataset:umap_original_varianced512[:,:75]|
|keras48.csv|0.87982|0.88420|dataset:umap_standard_varianced512[:,:75]|
|keras49.csv|0.87865|0.88604|dataset:pca_standard_varianced512[:,75:150]|
|keras50.csv|0.87067|0.87909|dataset:pca_standard_varianced512[:,75:150],X0[:,:42]|
|keras51.csv|0.87662|0.88416|dataset:pca_standard_varianced512[:,75:150],X0[:,:63]|
|keras52.csv|0.87791|0.88518|dataset:pca_standard_varianced512[:,150:225]|
|keras53.csv|0.87794|0.88511|dataset:pca_standard_varianced512[:,225:300]|
|keras54.csv|0.87790|0.88524|dataset:pca_standard_varianced512[:,300:375]|
|keras55.csv|0.87775|0.88517|dataset:pca_standard_varianced512[:,375:450]|
|keras56.csv|0.88755|0.89468|dataset:pca_standard_varianced512[:,:75],bs=512|
|keras57.csv|0.88736|0.89460|dataset:svd_standard_varianced512[:,:75],bs=256|
|keras58.csv|0.88691|0.89461|dataset:svd_standard_varianced512[:,:75],bs=1024|
|keras59.csv|0.88654|0.89452|dataset:svd_standard_varianced512[:,:75],bs=2048|
|keras60.csv|0.88758|0.89437|dataset:svd_standard_varianced512[:,:75],bs=128|
|keras61.csv|0.88658|0.89398|dataset:pca_standard_varianced512[:,:75],bs=512,lgbm important cols|
|keras62.csv|-|-|dataset:pca_standard_varianced512[:,:75],bs=512|
|keras63.csv|___0.88791___|0.89427|dataset:pca_standard_varianced512[:,:75],行std|
|keras64.csv|0.88705|0.89372|dataset:pca_original_varianced512[:,:75],行std|
|keras65.csv|0.88669|0.89348|dataset:pca_standard_varianced512,次元削減後X0+Xとターゲット全体の平均で160特徴量選択|
|keras66.csv|0.88611|0.89331|dataset:pca_standard_varianced512,次元削減後Xとターゲット全体の平均で243特徴量選択|
|keras67.csv|0.88690|0.89379|dataset:pca_standard_varianced512,次元削減後Xとターゲット全体の平均で160特徴量選択|
|keras68.csv|0.88632|0.89399|Mish関数|
|keras69.csv|0.88643|0.89392|Swish関数|
|keras70.csv|0.88706|0.89439|x0batch normalization|
|keras71.csv|0.88695|0.89391|x0x1batch normalization|
|keras72.csv|0.88686|0.89402|x0x1x2batch normalization|
|keras73.csv|0.88679|0.89404|x0x1x2x3batch normalization|
|keras74.csv|0.88655|0.89392|x0x1x2x3xbatch normalization|
|keras75.csv|0.88721|0.89472|xbatch normalization|
|keras76.csv|||xbatch normalization,oof|
|keras77.csv|0.88563|0.89368|dataset:pca_original_varianced512[:,:75],std,以下pri-oof実装|
|keras78.csv|0.88652|0.89326|dataset:pca_original_varianced512[:,:75],行std|
|keras79.csv|0.88666|0.89414|dataset:pca_log_varianced512[:,:75],std|
|keras80.csv|0.88625|0.89355|dataset:pca_log_varianced512[:,:75],行std|
|keras81.csv|0.88664|0.89403|dataset:pca_minmax_varianced512[:,:75],std|
|keras82.csv|0.88629|0.89386|dataset:pca_minmax_varianced512[:,:75],行std|
|keras85.csv|___0.88755___|___0.89464___|dataset:pca_standard_varianced512[:,:75],std|
|keras86.csv|___0.88791___|0.89417|dataset:pca_standard_varianced512[:,:75],行std|
|keras87.csv|0.88666|0.89388|dataset:svd_original_varianced512[:,:75],std|
|keras88.csv|0.88657|0.89285|dataset:svd_original_varianced512[:,:75],行std|
|keras89.csv|0.88705|0.89418|dataset:svd_log_varianced512[:,:75],std|
|keras90.csv|0.88650|0.89325|dataset:svd_log_varianced512[:,:75],行std|
|keras91.csv|0.88698|0.89406|dataset:svd_minmax_varianced512[:,:75],std|
|keras92.csv|0.88656|0.89353|dataset:svd_minmax_varianced512[:,:75],行std|
|keras93.csv|___0.88745___|___0.89456___|dataset:svd_standard_varianced512[:,:75],std|
|keras94.csv|___0.88769___|0.89422|dataset:svd_standard_varianced512[:,:75],行std|
|keras95.csv|0.88547|0.89376|dataset:pca_original_varianced512[:,:75],std,xbatch|
|keras96.csv|0.88588|0.89323|dataset:pca_original_varianced512[:,:75],行std,xbatch|
|keras97.csv|0.88624|0.89397|dataset:pca_log_varianced512[:,:75],std,xbatch|
|keras98.csv|0.88596|0.89349|dataset:pca_log_varianced512[:,:75],行std,xbatch|
|keras99.csv|0.88636|0.89393|dataset:pca_minmax_varianced512[:,:75],std,xbatch|
|keras100.csv|0.88592|0.89378|dataset:pca_minmax_varianced512[:,:75],行std,xbatch|
|keras101.csv|0.88721|___0.89471___|dataset:pca_standard_varianced512[:,:75],std,xbatch|
|keras102.csv|0.88720|0.89411|dataset:pca_standard_varianced512[:,:75],行std,xbatch|
|keras103.csv|0.88671|0.89402|dataset:svd_log_varianced512[:,:75],std,xbatch|
|keras104.csv|0.88627|0.89293|dataset:svd_log_varianced512[:,:75],行std,xbatch|
|keras105.csv|0.88684|0.89401|dataset:svd_minmax_varianced512[:,:75],std,xbatch|
|keras106.csv|0.88615|0.89329|dataset:svd_minmax_varianced512[:,:75],行std,xbatch|
|keras107.csv|0.88723|___0.89480___|dataset:svd_standard_varianced512[:,:75],std,xbatch|
|keras108.csv|0.88713|0.89413|dataset:svd_standard_varianced512[:,:75],行std,xbatch|
|||||
|blending1.csv|-|0.89510|keras41,keras42|
|blending2.csv|-|0.89530|keras41,keras42,keras75|
|blending3.csv|-|0.89627|pri85,86,93,94|
|blending4.csv|-|0.89808|pri85,93,94,pub101|
|blending5.csv|-|0.89828|pub85,101,107,pri-86|
|blending6.csv|-|0.89511|pub85,93,107,101|
|||||
|ensemble_mlp1.csv|-|0.88814|keras41,keras42|
|ensemble_mlp2.csv|-|0.88930|keras41,keras42,st|
|ensemble_mlp3.csv|-|0.88771|keras41,keras44,keras45|
|ensemble_mlp4.csv|-|0.88873|keras41,keras44,keras45,st|
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||






|filename|all_pri_cv|all_pub_cv|lb|
|--------|----------|----------|--|
|lgbm4+ridge2.csv|-|-|0.803|
|lgbm5+ridge2.csv|-|-|0.803|
|keras1+ridge2.csv|-|-|0.805|
|keras2+ridge2.csv|-|-|0.790|
|keras3+ridge2.csv|-|-|0.798|
|keras4+ridge2.csv|-|-|0.805|
|keras5+ridge2.csv|-|-|0.803|
|keras6+ridge2.csv|-|-|0.801|
|keras7+ridge2.csv|-|-|0.798|
|keras8+ridge2.csv|-|-|0.805|
|all-in-one2.csv|-|-|0.812|
|keras12+keras2.csv|-|-|0.807|
|keras12+keras3.csv|-|-|0.807|
|keras13+keras4.csv|-|-|0.813|
|keras13+keras5.csv|0.80570|0.82904|0.812|
|keras13+keras13.csv|0.80563|0.82898|0.812|
|keras20+keras5.csv|0.80592|0.82911|0.812|
|keras20+keras4.csv|-|-|0.813|
|keras24+keras4.csv|-|-|0.812|
|keras35+keras4.csv|-|-|0.809|
|keras40+keras5.csv|0.80634|0.82918|0.813|
|keras41+keras5.csv|0.80650|___0.82946___|___0.813___|
|ensemble_mlp1+keras5.csv|0.80641|0.82480|0.810|
|ensemble_mlp2+keras5.csv|___0.80703___|0.82563|0.807|
|ensemble_mlp3+keras5.csv|0.80607|0.82449|0.811|
|ensemble_mlp4+keras5.csv|0.80642|0.82522|0.807|
|blending1+keras5.csv|-|0.81818|0.813|
|blending2+keras5.csv|-|0.81832||
|keras75+keras5.csv|0.79192|0.81793|0.813|
|keras75+keras24.csv|-|-|0.813|
|keras75+keras26.csv|-|-|0.813|
|blending2+keras24.csv|-|-|0.814|
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||
|||||

# 得られた事実
* svdデータセットは一定の分散を超えるとノイズが大きくなるため一部の列のみ使用
* MLPにおいてadv⇨svdの処理をした時cv↓lb↓
* MLPにおいてsvd⇨advの処理をした時cv↓lb↓
* lgbm4<lgbm5 なのでgbdtにおいてadversal validationは成功している

# 考察
* MLPにおいては特徴量選択がかなり重要になる
* MLPにおいてsvdは不要

# dataset detail
* adval~ :adversal validationをしたもの
* Citeseq_adval_truncated_~ :citeをsvdしたもの
* log~ :originalにlog変換をしたもの
* minmax~ :originalにminmax変換をしたもの
* sqrt~ :originalにsquare root変換したもの
* standard~ :originalにstandard変換したもの
* Y_~ :multiomeのtargetをsvdしたもの
* train_~ :multiomeのtrainをsvdしたもの
* pca_target:multiomeのsvd自体
* pca_train:multiomeのsvd自体
* Varianced_~_cite_inputs.h5 :originalをvarianced thresholdしたもの


# アイデア

# do
* NNで次元削減(非線形変換)
* testのdonor4で擬似ラベリング
* 逆変換して生データにもどしてNNに流す
* ノイズが多い(batch　effectによる)ならdartを試す
* adversal validationの応用:dayごとにtargetを設定して説明能力の低い特徴量を選択する。なぜなら日付にロバストな特徴量だから(https://blog.amedama.jp/entry/adversarial-validation)
* ノイズの処理:統計的処理or異常検知
* データを多くの次元に圧縮して,Attentionを適応.Attentionが特徴量抽出の役割を持つのではないか？
* LSTMでの実装
* テーブルデータを画像化してCNNを扱う(https://qiita.com/hirune924/items/82fccd08865f7467339d)
* 特徴量エンジニアリング(差分特徴量について)(https://blog.recruit.co.jp/rtc/2020/12/23/kaggle_moa/)
* 位置情報が関係ある
* Mish(活性化関数)使ってみる
* 1D-CNN
* BN
* skip connection
* GNN


# done
* adversal validation:testデータに似たvalidationデータを作成する手法
* 次元削減した特徴量は分散があるレベルに達すると情報よりもノイズをもたらす
* 多重共線性を避けるため最適な特徴量を選択する

# paper(参考にした論文の一覧)
* skip connectionについて(https://www.slideshare.net/yamatookamoto5/skip-connection-neural-network)

# discussion
* privateLBとpublicLBに適したcross validationは異なる(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/347202)
* PCAは疎行列を扱うことができない,TruncatedSVDは疎行列を扱うことができる.(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/348377)
* fold間の標準偏差を最小化することはモデルをロバストさせ,汎化能力を高める.(https://www.kaggle.com/competitions/feedback-prize-english-language-learning/discussion/352800)
* 決定木モデルはcv↑lb↓になりやすい(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/352567)
* シングルセルデータ解析に使われるpythonパッケージ(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/344816)
* 特徴重要度の高いカラム(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/349242)
* 4人のドナーの細胞は別々のプレートに置かれ、各細胞は一つの時点のみで測定されその後破棄される。つまり一つの細胞についての時系列データを得ることはできない。細胞はプレートからランダムサンプリングされる。(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/348524) (https://www.kaggle.com/competitions/open-problems-multimodal/discussion/347813)
* privateとpublicはかなり違う、ドメインシフトに対してロバストである必要がある(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/347202)
* {gene_names}_{gene_ensemble-ids}に関して、どちらもgeneの名前である(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/346761)
* citeデータの負の値は0に変換したほうがよさそう(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/346210)
* 損失関数は何をつかうべきか(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/346518)
* 後処理について(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/349132)
* カスタム損失関数(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/347595)
* 次元削減法一覧(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/348233)
* 検体は1人の女性(Donor 13176)と3人の男性である

<img width="749" alt="スクリーンショット 2022-10-17 13 31 37" src="https://user-images.githubusercontent.com/63344524/196090323-1adfc066-fe18-4199-8558-0e8679a31b8f.png">

<img width="749" alt="スクリーンショット 2022-10-17 13 32 05" src="https://user-images.githubusercontent.com/63344524/196090343-d5418b87-4e12-469a-86cf-359cedce300c.png">

# domain knowledge
* CDとはなにか(https://en.wikipedia.org/wiki/Cluster_of_differentiation)
* bioinformaticiansがsingle-cell dataを解析する場合4つの前処理をおこなう 1.低品質の細胞のフィルタリング 2.データの正規化(ホストによってすでに行われている) 3.次元削減・特徴量選択 4.特徴量のスケーリング
* batch effect:異なる実験環境（バッチ）で計測されたデータの場合、同じ臓器・細胞であっても、バッチ間でデータに大きく差が生じる
* 特にsingle-cell RNA-Seqの場合、低発現の遺伝子は検出限界により、計測されづらくなる"ドロップアウト"現象があり、実験プロトコルにより、ドロップアウトの程度が全く異なる。そのため、異なるsingle-cell RNA-Seq実験同士、またはsingle-cell RNA-Seqとbulk-cell RNA-Seq同士では、そのままでは正当な比較が行えないと考えられる。現在は、ドロップアウトするような低発現な遺伝子には着目せず、細胞型特異的に変動する遺伝子にのみ着目し、細胞型を同定するためのアルゴリズムを開発している.
* DNA・遺伝子・染色体の違い:DNA=文字,遺伝子=文章,染色体=本 DNAはデオキシリボ核酸という「物質」　遺伝子は体を作るために必要な情報　染色体はDNAや遺伝子が集まったもの,人は23対46本の染色体を持っている
* single-cellに関する論文一覧(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/344686)
* 造血幹細胞からの分化(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/348117)(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/359809)

# EDA
* すべての行が0のカラムが存在している(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/350514)
* オープンクロマチン領域に関する知見(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/349766)
* 77位のEDA一覧(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/344824)
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

# everyone's solution
* knn approach(https://github.com/adavoudi/msci_knn)
* より良いアンサンブル手法(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/350222)
* 特徴量エンジニアリング(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/350668)


# past solution
* 去年のコンペの解法(https://www.youtube.com/watch?v=ZXDILOyiy7A)
* single-cell dataについて(https://openproblems.bio/neurips_docs/data/about_multimodal/)

# design
- 分析設計
    - 問題の理解:cite;遺伝子発現レベル>タンパク質発現レベル,multi;オープンクロマチン領域>遺伝子発現レベル
    - コンペの意義:測定量を使って幹細胞が何の役割を持った細胞に分化するか知ることができたらいい
    - コンペの目的:骨髄幹細胞がより成熟した血液細胞に成長する過程で、DNA、RNA、タンパク質の測定値が単一細胞内でどのように変動するかを予測すること
        - 細胞ではDNA→RNA→たんぱく質の順に情報が翻訳されて物質が生成される
        - 骨髄幹細胞(造血幹細胞):骨髄にある幹細胞.
        - 幹細胞:身体の特定の場所に幹細胞が待機していて、それが分裂・分化することにより新しい細胞が補充される.
        - 骨髄:骨の中心部にあり、血液細胞（白血球、赤血球、血小板）をつくる組織のこと。骨髄には、造血幹細胞と呼ばれる、すべての血液細胞に成長でき、かつ自分自身も複製することができる “血液の種”のような細胞が存在している.
    - 分析の設計:ローカルで実装
    - データセットについて:このコンペのデータセットは、4人の健康なヒトドナーから分離した動員末梢CD34+造血幹細胞および前駆細胞（HSPCs）から収集した単一細胞マルチオミクスデータから構成されている
        - 動員末梢CD34:骨髄由来の前駆細胞、特に造血および内皮前駆細胞のマーカー
        - 前駆細胞:幹細胞は前駆細胞を経て最終分化細胞へと分化するため、前駆細胞を幹細胞と最終分化細胞の中間に位置する細胞と捉えることができる
        - multiomeデータ:クロマチンアクセシビリティ(DNAの読み取り可能性)と遺伝子発現(RNAの量)を測定する(https://www.10xgenomics.com/products/single-cell-multiome-atac-plus-gene-expression)
        - citeseq:遺伝子発現と表面のタンパク質レベルを測定する(https://www.biolegend.com/ja-jp/products/totalseq-b-human-universal-cocktail-v1dot0-20960)(https://support.10xgenomics.com/permalink/getting-started-single-cell-gene-expression-with-feature-barcoding-technology)
        - 単一細胞の体積は小さいために測定値はまばらでノイズが多く、細胞間の分子サンプリング深さの違い（シーケンシング深さ）やバッチで細胞を扱うことによる技術的影響（バッチ効果）は生物学的な差異を分からなくしてしまう事が多々あります.
        - train/test_multi_inputs.h5:ATAC-seqピーク数をデフォルトのlog(TF) * log(IDF) 出力（DNA）を用いてTF-IDF変換したもの。行は細胞、列はアクセスレベル(DNA)を測定したゲノム上の位置（ここでは10x References - 2020-A (July 7, 2020) で提供した参照ゲノムGRCh38のゲノム座標で特定）に相当する。NOTE: TF-IDF変換：統計量への変換。この文脈ではDNA配列において特定の配列がいかに重要なのかを示す指標への変換。（ただしDNA配列の区切りがどこにあるのか理解していません）TFは特定配列の出現頻度、IDFは各区切りで特定配列が出現する割合で log(TF)∗log(IDF)で表す。NOTE: ゲノム座標：ゲノム座標は参照ゲノムの染色体名や開始位置、および終了位置が次の形式で含まれたもの。chr1:1234570-1234870
        - train_multi_targets.h5:RNA遺伝子発現レベル（同一細胞のライブラリサイズ正規化およびlog1p変換したカウント）NOTE: ライブラリサイズ正規化：同一細胞内の総和が１になるような正規化NOTE: log1p変換： f(x)=log(x+1)
        - train/test_cite_inputs.h5:RNAのライブラリサイズ正規化およびlog1p変換されたカウント（遺伝子発現量）で、行は細胞、列は{gene_name}_{gene_ensemble-ids}で与えられた遺伝子に対応する。
        - train_cite_targets.h5:dsbで正規化された同じ細胞の表面タンパク質レベル。NOTE: dsb：たんぱく質信号の背景処理 


* バリデーション設計

* データ前処理
標準化

* 特徴量エンジニアリング
行方向に標準化

* データセット作成/特徴量選択
SVD・PCA・

* バリデーション設計

* モデル学習

* アンサンブル

* 後処理


# Log
## 20221023
* adversal validation > trainとtestで分布の違う特徴量の削減 > CV↓PB↑

## 20221022
* citeにadversal validationを行なった(auc:0.97>0.67)
* multiにadversal validationを行なった(auc:0.97>0.71)

## 20221017
* discussionまとめた
* github整理した

## 20221012
* 論文読んだ

## 20221010
* code読んでbookmark付ける

## 20221009
* cv改善・実装した

## 20221008
* 特徴量が多すぎるため、adversal validationはやめることにした
* publicとprivateのデータの分け方が違うため,privateを反映したクロスバリデーションが必要
    - privateは既知のドナー3人と未知のドナー1人の将来のデータで構成されている.そのため,valデータセットは最終日の既知のドナー2人と未知のドナー1人で構成されるべき(つまり3fold)
* cvの構想を書いた

## 20221007
* kaggleに質問を投稿した(https://www.kaggle.com/competitions/open-problems-multimodal/discussion/358209)
* single-cell genomics:数千の遺伝子を一度に測定できるシステム

## 20221002
* privateに対して妥当なcvを作成し、trust cv
* meta.dayでgkfした

## 20221001
* discussion読んだ

## 20220930
* lb・cv理解
* cv実装

## 20220929
* データ圧縮
* multi/citeでbaseline
* 初sub

## 20220928
* join!
* 題材が難しい
* EDA確認した
