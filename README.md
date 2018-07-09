# survey  

## [Deep Learningを用いた音楽生成手法のまとめ](https://medium.com/@naotokui/deep-learning%E3%82%92%E7%94%A8%E3%81%84%E3%81%9F%E9%9F%B3%E6%A5%BD%E7%94%9F%E6%88%90%E6%89%8B%E6%B3%95%E3%81%AE%E3%81%BE%E3%81%A8%E3%82%81-%E3%82%B5%E3%83%BC%E3%83%99%E3%82%A4-1298d29f8101)  
### 評価軸  
・メロディー  
・ハーモニー  
・伴奏/コード進行  
・リード・シート（ジャズ等で使われるメロディーと和音、歌詞のみを書き起こした記法）  
・リズム  
### 表現（Representation） 
#### 音声信号を扱う ex.WaveNet
#### 移調（Transposition）
「Data Augmentation」と同様に，学習データにある曲を別のキーに移調することで，データ量を増やす  
### アーキテクチャー
#### 多層ニューラルネットワーク
RNNと比べて時系列を考慮しないので，一音一音生成するのではなく，ある入力に対して全体を出力する．
### RNN(Recurrent Neural Network)
一音一音生成する．発展系はLSTM．  
### Autoencoder  
入力に等しい出力，入力を真似するような出力を出すように学習するニューラルネットワーク．
AEに考え方が近いものとして，RBM(Restiricted Boltzman Machine)やVAE(Variational AE)などがある．
### CNN(Convolutional Neural Network)  
### GAN(Generative Adversarial Networks)  
GANは安定的に学習させるのが難しい  
(Generator/Discriminatorのどちらかが賢くなりすぎて相手を騙せなくなってしまう)  
GANを安定的に学習させる手法に関する研究が進むとともに、  
GANを用いた音楽生成も今後ホットなトピックになりそうです  
### RL(Reinforcement Learning)  
強化学習

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

## VAEとGANの違い  
[（参考）VAEとGANの違い](https://www.xcompass.com/blog/1039/)
### VAE(Variational Autoencoder， 変化のAE)  
#### VAEの学習の流れ  
⑴ データセットからデータをサンプリングしてEncoderに入力する  
⑵ Encoderは出力次元(多次元)に相当する潜在分布の平均と分散を出力する  
⑶ 潜在分布の平均と分散から、潜在変数zをサンプリングし、zを作る  
⑷ 潜在変数zをDecoderに入力し、Decoderはデータを出力する  
⑸ サンプリングされたデータそのものを復元するようにEncoderとDecoderを学習し、  
Encoderは復元の為の学習に加えて、仮定した事前分布に近くなるよう学習する  
#### VAEの問題点  
複雑なデータセットを用いると画像がぼやける  

### GAN(Genarative Adversarial Nets， 生成的敵対ネットワーク)  
#### GANの学習の流れ  
>(1)潜在空間(z)から`Generator`はデータを作成する  
>(2)`Discriminator`は、`Generator`から作られたデータか、実際のデータセットから来たデータかを判別する  
>(3)・`Generator`は作ったデータを`Discriminator`が実際のデータセットから来たデータだと間違えるように、  
実際のデータセットらしいデータを作成するように学習する  
・`Discriminator`はそれに騙されないように，実際のデータセットと`Generator`から作られたデータかを判別できるように学習する  
#### GANの問題点  
・`mode collapse`  
学習するにつれて，生成する分布が最頻値に寄ってしまう現象で，`Generator`が同じような画像を生成してしまう  
・途中でサンプリングが入るため，逆伝播できない
> Reparameterization trick?

## Importance Weighted Autoencoders（IWAE）  
モデルの容量を変化させた場合のパフォーマンスをVAEと比較．  
