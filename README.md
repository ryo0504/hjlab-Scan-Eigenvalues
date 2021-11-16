# hjlab-Scan-Eigenvalues
scanのoutputfileからエネルギー値を取り出すプログラムです。
Wscanにも対応しています。
変化させる結合距離や角度を指定することで、エネルギー値に対応する表を出力します。

## ファイルの扱いと環境構築について

### env_build
Dockerfileが入ってます。

### src
ソースコードが入っています。
### single_scan.ipynb
outputfileの"HF="部分のエネルギー値を指定した結合距離や角度と対応させて、CSV形式で抜き出します。

### src/Wscan_from_HF=.ipynb
outputfileの"HF="部分のエネルギー値をCSV形式で抜き出します。
angle_E_from_summary.ipynbも基本的には同じですが、angle_E_from_HF=.ipynbの方が小数点が最後まで表示されるので、こちらを使う方が正確な評価ができます。

### src/Wscan_from_summary.ipynb
outputfileの"Summary"部分のエネルギー値をCSV形式で抜き出します。

### 環境構築の基本的な手順
- git clone <urlを入力>
- cd env_build
- docker build .
- docker run -p <任意のport番号>:8888 -v <srcのディレクトリを指定>/:/work --name <任意のコンテナ名> <コンテナID>
- (例)docker run -p 8888:8888 -v ~/Desktop/test_dir/src/:/work --name test_name 74f45e4b8084
