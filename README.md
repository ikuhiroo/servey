# survey  

## [（参考）MusicVAE](https://magenta.tensorflow.org/music-vae)
[(参考)MusicVAEの日本語資料(1)](https://github.com/arXivTimes/arXivTimes/issues/680)  
### どんなものか？  
音楽を「混ぜる」ことができる．  
名前の通りVAEがベースで、Encoderは双方向LSTM、Decoderは階層上の構成(バッチで生成を行うイメージで、現バッチ生成用の潜在表現を作るLSTMと、そこから音符を生成するLSTMの二段構造)になっている．  

>[VAE（Variatioinal Autoencoder）について](https://qiita.com/kenmatsu4/items/b029d697e9995d93aa24)  
生成モデルの１つで，訓練データを元にその特徴を捉えて訓練データセットと似たデータを生成することができる．  
>> 生成モデルとは？  
データ分布p(X)を推定する  

### 通常のAutoencoderと異なる点  
> Autoencoderとは，  
教師なし学習，データを表現する特徴を獲得するためのニューラルネットワーク  
>>・Encoderとは，  
入力データXから潜在変数zに変換するニューラルネットワーク  
この時，zの次元がXの次元よりも小さい場合，「次元削減」とみなせる．  
>>・Decoderとは，  
潜在変数zを入力して元画像を復元するニューラルネットワーク  
  
VAEは潜在変数zが正規分布に従うように設計されている．  
潜在変数zが正規分布として分布するように学習させて，p(X)（エビデンス）を推定する．     

### 技術や手法  
#### Latent spaceの特徴   
1, `Expression`  
高次元の任意の点は低次元の「the latent space」に写像され，元の高次元空間に写像可能  
ex. 音声を生成可能
2, `Realism`
「the latent space」上の点は，複数の音色に対応する．   
3, `Smoothness`
似た形状のもの（同じクラス）を近くに引き寄せる効果がある．   

#### SketchRNN
「the latent space」上の点と点の間を補間するためにする学習法  

##### latent constraints  
「the latent space」上で点と点の計算が可能．  
与えられたデータセットを紐解きが可能．  

##### how to learn?


#### Nsynth
