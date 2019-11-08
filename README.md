# Livedoor-Classification
Livedoorニュースの分類

Python 3.7, PyTorch 1.3

使用したもの↓  
Livedoorニュースコーパス　https://www.rondhuit.com/download.html#ldcc  
MeCab　https://taku910.github.io/mecab/#install  
Setencepiece　https://github.com/google/sentencepiece  

## Making_corpus.ipynb
ダウンロードしてきたデータをDataFrame形式に成形して、tsvとして保存する

## txt2tensor.ipynb
tsvファイルを読み込んで、BERTserver経由であらかじめEmbeddingをかけておく

## livedoor_wordbase.ipynb
単語トークナイズverの分類モデル。モデルの形は1層LSTM⇒2層FFN(BatchNormあり)。  
トークナイザー定義⇒Field・vocab定義⇒モデル定義⇒計算を回す⇒グラフを表示・テストデータで検証

## livedoor_sentencebase.ipynb
文トークナイズverの分類モデル。モデルの形は1層LSTM⇒3層FFN(BatchNormあり)。  
dataset/dataloaderの定義⇒モデルの定義⇒計算を回す⇒グラフを表示・テストデータで検証