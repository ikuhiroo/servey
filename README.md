# survey  

## [（参考）MusicVAE](https://magenta.tensorflow.org/music-vae)
[(参考)MusicVAEの日本語資料(1)](https://github.com/arXivTimes/arXivTimes/issues/680)  
### どんなものか？  
音楽を「混ぜる」ことができる．  
名前の通りVAEがベースで、  
Encoderは双方向LSTM、  
Decoderは階層上の構成  
（バッチで生成を行うイメージで、現バッチ生成用の潜在表現を作るLSTMと、そこから音符を生成するLSTMの二段構造)  
になっている．  

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
#### Latent-spaces（潜在空間）の特徴   
1, `Expression`  
高次元空間上の任意の点は，低次元のLatent-spacesに写像される．  
また，Latent-spaceの点は元の高次元空間に写像可能である．    
2, `Realism`
Latent-spaces上の点は，複数の音色に対応するため，  
学習標本にない音色も生成可能である．  
3, `Smoothness`
Latent-spaces上において，近い点同士は似た音色となる． 

・`Expression` & `Smoothness`  
Latent-spaces上の点と点の間を補間するSketchRNNを用いる．  
・`Realism`  
Latent-spaces上から任意に選んだ点をdecodeすると，  
学習標本と似たような新しい生成物ができる．  
人間の理解の幅を超えた生成物を作れる．  

##### ・latent constraints（意味的な制約） 
高次元空間で難しいような操作を，  
Latent-spaces上でベクトル同士の演算で可能．  
→ 与えられたデータセットの紐解きが可能．  
→ Latent-spaces上の点の平均は， 求められている生成物を表す．   

##### ・how to learn?
NsynthはAutoencoderの一例．  
多変量正規分布を考慮したLatent-codesを生成する．  
損失関数に`the variational loss`を用いることがポイント．  
・Autoencoderの問題点  
「the latent space」に穴があるため，高次元空間に写像できない可能性がある．  
つまり，音色を生成できない．  

##### ・実験  
MusicVAEモデルを使わない場合と使う場合で実験．  
使う方がより自然に切り替えができる．  

##### ・Long-term Structure  
・novel hierarchical decoder  
それぞれのlatent-space上の点からlong-term structureを生成できる．  

##### ・subtract/Add Note Density Vector  
latent-codeへ「note density vector」を加えることで，音色を調整する．  
latent-codeから「note density vector」を取り除くことで，音色を調整する．  
