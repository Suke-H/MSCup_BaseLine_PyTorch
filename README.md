\#MScup Baseline PyTorch Version
=====================

このコードは、[Solafune](https://solafune.com/)社様主催の
「[市街地画像の超解像化](https://solafune.com/competitions/3c7a473f-61f4-472f-a812-92eb07cc4541) #MScup」での
[ベースライン](https://zenn.dev/ren_uechi/articles/ab9eea97ec42e5)をPyTorchで書き直したものです。

注意
-----
`cf. @solafune(https://solafune.com)` \
コンテストの参加以外を目的とした利用及び商用利用は禁止されています。\
商用利用・その他当コンテスト以外で利用したい場合はお問い合わせください。(https://solafune.com)

動作確認環境
-----
- CUDA (11.0)
- pytorch (1.7.1)
- torchvision (0.8.2)
- cudatoolkit (11.0.221)
- scilit-image (0.18.3)
- tqdm (4.62.3)

Anaconda環境にて、以下のコマンドから環境構築しました。
```
conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=11.0 -c pytorch
conda install scikit-image tqdm
```

コード説明
-----
1. ESPCN.sample.py: [ベースライン](https://zenn.dev/ren_uechi/articles/ab9eea97ec42e5)をPyTorchで書き直したコードです。学習まで行います。
1. SSIM_score.py: 学習済モデルから学習用画像を用いてSSIMを算出します。
1. submit.py: 学習済モデルから評価用画像を高解像度化したものを出力、zip化します。