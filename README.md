  
  
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
  
1. [構築](#構築 )
1. [配置](#配置 )
1. [運用](#運用 )
1. [開発](#開発 )
  
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
  
Nodeのインストールは[Node Version Manager](https://github.com/creationix/nvm )を使用する。
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
  
  
### 02 - Babel, ES6, ESLint, Flow, Jest, and Husky
  
#### Babel
  
> BableはES6のコードをES6のコードに変換するコンパイラ。モジュール性が高く異なる様々な環境で使われている。ReactコミュニティではES5コンパイラとして好まれている。
  
Bableのセットアップ
```bash
yarn add --dev babel-cli
yarn add --dev babel-preset-env
```
  
#### ES6
  
> ES6:JavaScript言語の最も重要な進化。
  
#### ESLint
  
> ESLintはES6用のリンター。リンターは一貫性のあるコードフォーマットに関する推奨を通知し、そしてチームで共有する。ESLintが見つけるJavaScriptに関する間違いを学ぶことは優れて方法だ。
  
```bash
npm info eslint-config-airbnb@latest peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs yarn add --dev eslint-config-airbnb@latest
yarn add --dev eslint
yarn add --dev eslint-plugin-compat
```
  
#### Flow
  
> Flow:Facebookによる静的型チェッカー。コード内の型不一致を検知する。要するに、数値型を使うところで文字型を使うとエラーを通知する。
  
```bash
yarn add --dev flow-bin babel-preset-flow babel-eslint eslint-plugin-flowtype
```
  
#### Jest
  
> Jest: FacebookによるJavaScriptテスティングライブラリ。必要となるテスティングライブライを簡単にセットアップできる。また、Reactコンポーネントもテストできる。
  
```bash
yarn add --dev jest babel-jest
```
  
#### Git Hooks with Husky
  
> Git Hooks: コミットやプッシュなどの決まったアクションが発生した時に実行されるスクリプト
  
```bash
yarn add --dev husky
```
  
### 03 - Express, Nodemon, and PM2
  
#### Express
  
> ExpressはNodeでおそらくもっともポピュラーなwebアプリケーションフレームワーク。シンプルかつ最小限のAPIを提供し、そしてミドルウェアにより機能を拡張できる。
  
```bash
yarn add express compression
```
  
#### Nodemon
  
> Nodemonはディレクトリ内のファイルが変更された時、自動的にNodeサーバーを再起動してくれるユーティリティ。
  
```bash
yarn add --dev nodemon
```
  
#### PM2
  
> PM2はNode用プロセスマネージャ。プロダクション環境でプロセスを維持する、そしてプロセスのモニタリングと管理機能を提供する。
  
```bash
yarn add --dev pm2
yarn add --dev rimraf
yarn add --dev cross-env
```
  
### 04 - Webpack, React, and Hot Module Replacement
  
#### Webpack
  
> Webpackはモジュールバンドラー。バンドルと呼ばれるクライアントから実行される唯一のJavaScriptファイルを様々なソースファイルから取りまとめて作る。
  
```bash
yarn add babel-polyfill
yarn add --dev webpack webpack-dev-server babel-core babel-loader
```
  
#### React
  
> ReactはFacebookが提供するユーザーインターフェース構築用ライブラリ。HTML要素表現とJavaScriptの効果を高めるコンポーネントを表現するJSXシンタックスを使う。
  
```bash
yarn add react react-dom
yarn add --dev babel-preset-react babel-plugin-flow-react-proptypes
```
  
#### Hot Module Replacement
  
> Hot Module Replacement(HMR)はページをリロードすることなくモジュールをすぐに更新する強力なWebpackの機能。
  
```bash
yarn add react-hot-loader@next
```
  
**[⬆ back to top](#構成 )**
  
## 配置
  
**[⬆ back to top](#構成 )**
  
## 運用
  
**[⬆ back to top](#運用 )**
  
## 開発
  
**[⬆ back to top](#構成 )**
  
# 参照 #
  
  