# 機械学習を用いた 特許・技術文書の解析と動向抽出
# ③ pythonを使った特許文書の教師なし学習による可視化と教師あり学習による分類・スクリーニング

## 使い方
Googleアカウントを取得してGoogle Driveが使えるようになっていることを前提としています。

/content/drive/My Drive/Colab Notebook/20200302

/content/drive/My Drive/data

/content/drive/My Drive/trend

/content/drive/My Drive/word_cloud

/content/drive/My Drive/network

のフォルダがないことを確認してから実行してください。

１．setup.ipynbをクリックして開きます。
  
２．Open in Colab をクリックしてノートブックを開きます。

３．ドライブに保存せずにそのまま実行します。

４．google driveにアクセスするために、Go to this URL in a browser: のリンクをクリックしてアカウント認証し、コピーしたコードを　Enter your authorization code: 欄に入力してください。

５．ファイルがコピーされます。

６．google drive 上に Colab Notebooks\20200302 というフォルダができていれば成功です。

## はじめに
特許データベースからダウンロードしたExcelファイルから時系列パテントマップを作成します。

## １．形態素解析とキーワード可視化
MeCab、sentencepiece、GiNZA（Sudachi）で形態素解析します。
TermExtractを用いてキーワード抽出と共起計算して可視化を行います。
WirdCloudでキーワードを可視化します。

## ２．文書ベクトル化
単語ID、BoWおよびTF-IDFによる文書ベクトルを作成します。
Doc2VecとGiNZAで分散表現（文書ベクトル）を作成します。
分散表現ベクトルを用いてcos類似度を求めます。

## ３．教師なし学習による可視化
多次元ベクトルである単語ベクトルや文書ベクトルを2次元に圧縮して、2次元平面にプロットします。
k-means法によるクラスタリングをします。
自己組織化マップで2次元平面にプロットします。
SVMで2値分類します。教師ありデータですが、ニューラルネットワークでないのでここで扱います。

## ４．ニューラルネットワークを用いた教師あり学習
MNIST（手書き数字）の分類を解説します。
１次元CNNによる特許データの２値分類をします。
活性化関数を設定することにより確率値を取り出します。
4値分類に拡張します。
