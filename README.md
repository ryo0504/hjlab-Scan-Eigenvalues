# hjlab-Scan-Eigenvalues
Scanのoutputfileからエネルギー値を取り出すプログラムです。

## ファイルの扱いと環境構築について

### env_build
Dockerfileが入ってます。

### src
ソースコードが入っています。
### src/scan_eigenvalues_ver2
outputfileの"HF="以降のエネルギー値をCSV形式で抜き出します。

### 環境構築の基本的な手順
- git clone <urlを入力>
- cd env_build
- docker build .
- docker run -p <任意のport番号>:8888 -v <srcのディレクトリを指定>/:/work --name <任意のコンテナ名> <コンテナID>
- (例)docker run -p 8888:8888 -v ~/Desktop/test_dir/src/:/work --name test_name 74f45e4b8084
