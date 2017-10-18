---
markdown:
  image_dir: /assets
  path: README.md
  ignore_from_front_matter: true
  absolute_image_path: false
---

# Etude for Express
---
# 目的
Expressアプリケーションのための練習プログラム集

# 前提
| ソフトウェア   | バージョン   | 備考        |
|:---------------|:-------------|:------------|
| node           |8.6.0    |             |
| npm            |5.3.0  |             |
| yarn           |1.2.1   |             |


# 構成
1. [構築](#構築)
1. [配置](#配置)
1. [運用](#運用)
1. [開発](#開発)

## 構築
### 仮想マシン起動
```bash
vagrant up
vagrant ssh
```
### 01 - Node, Yarn, and package.json
#### Node
>   Node.jsはJavaScriptランタタイム環境。バックエンドの開発だけでなく、一般的なスクリプティングにも使われている。フロンエンド開発においては、リント、テストそしてファイルのアセンブリングなどのタスクに使われている。

#### Node Version Management Tools
Nodeのインストールは[Node Version Manager](https://github.com/creationix/nvm)を使用する。
```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash
nvm install 8.6.0
nvm use 8.6.0
```

#### NPM
NPMはNodeのデフォルトパッケージマネージャー。Node一緒に自動的にインストールされる。以下では他のパッケージマネージャーであるYarnを使う。

#### Yarn
> YarnはNPMより高速なNode.jsパッケージマネージャー、オフラインサポートと正確な依存管理ができる。

Yarnのインストール。
```bash
curl -o- -L https://yarnpkg.com/install.sh | bash
```

#### package.json
> package.jsonはJavaScriptプロジェクトの記述と設定に使われるファイル。一般な情報（プロジェクト名、バージョン、貢献者、ライセンス等）、使用するツールの設定オプションそして実行するタスクが含まれる。

package.jsonのセットアップ
````bash
cd /vagrant
yarn init
````

#### Two kinds of dependencies
+ Dependenciesはアプリケーションで必要なライブラリ (React, Redux, Lodash, jQuery, etc)。`yarn add [package].`でインストールする。
+ Dev Dependenciesは開発中またはアプリケーションのビルド(Webpack, SASS, linters, testing frameworks, etc)。`yarn add --dev [package]`でインストールする。

**[⬆ back to top](#構成)**

## 配置
**[⬆ back to top](#構成)**

## 運用
**[⬆ back to top](#運用)**

## 開発
**[⬆ back to top](#構成)**

# 参照 #
