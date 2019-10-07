# 参照サイト
https://medium.com/@oleg.agapov/full-stack-single-page-application-with-vue-js-and-flask-b1e036315532

# 環境
参照サイトはVueCLI2系での手順だが上記手順を参考にVueCLI3で構築

* Python: 3.6.3
* VueCLI3
* vue-router: 3.0.3
* vuetify: 2.0.0

# 参照サイトと異なるもの
cli3からビルドファイルの出力先などの設定はvue.config.jsに記載
https://cli.vuejs.org/config/

## Build Setup

``` bash
# install front-end
cd frontend
npm install

# serve with hot reload at localhost:8080
npm run dev

# フラスコ用のバンドルファイルを作成
npm run build


# install back-end
cd ../backend
python -m venv venv
## PowerShellでvenvを起動したい場合は以下を実行する必要がある
Set-ExecutionPolicy RemoteSigned -force -Scope Process
venv\Scripts\activate
pip install -r requirements.txt
cd ..

# serve back-end at localhost:5000
set FLASK_APP=run.py
set FLASK_DEBUG=1 ## デバックモードでの起動
## PowerShellの場合、環境変数の設定方法が異なる為以下で入力
$env:FLASK_APP = "run.py"
$env:FLASK_DEBUG = 1 ## デバックモードでの起動

flask run
```

