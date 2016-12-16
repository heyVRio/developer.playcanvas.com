---
title: レガシースクリプティング
template: usermanual-page.tmpl.html
position: 10
---

これは、レガシースクリプトシステムのドキュメントです。レガシースクリプトシステムは、新規プロジェクトや既存プロジェクトでも使用できます。新しいプロジェクトを作成する際、使用するスクリプトシステムの選択肢が与えられます。

基本的に、新しいスクリプトシステムを使用することをお勧めします。ただし、従来のスクリプトシステムが必要な場合もあります。次の場合は、従来のスクリプトシステムを使用します：

- "ローカルワークフロー"が必要。例えば、マシンのテキストエディタでスクリプトを編集する場合
- GitやMercurialのようなバージョン管理システムとの統合が必要
- 再作成したくない既存のプロジェクトがある

レガシースクリプトシステムのドキュメントは以下です。

---

スクリプトはゲームをインタラクティブにします。スクリプトは**JavaScript**で書きます。これはあらゆるウェブページで使用されているプログラミング言語です。

アプリケーションは二つの個別のコードベースに分かれています。一つはPlayCanvasが提供するエンジンです。これは、グラフィックレンダリング、入力処理、音声、PlayCanvasツールのインターフェイスなどを含む基本的な機能を実装します。もう一つはスクリプトです。これは多くの場合、便利な挙動を提供する再利用可能なブロックか、アプリケーション特有のものです。

基本的には、エンジンコードは<script>タグでアプリケーションに含まれる単一のJavaScriptファイルなので、気にかける必要はありません。エンジンの一部を書き換える場合、スクリプティングに関するこの導入は必要ないでしょう。

スクリプトとはPlayCanvas Editorを通して[エンティティ][2]のスクリプト[コンポーネント][1]に追加される個別のJavaScriptファイルです。基本的に、スクリプトファイルは添付されているエンティティ毎に一度インスタンス化される単一のJavaScriptオブジェクトを定義するべきです。

**スクリプトがブラウザによりキャッシュされないよう注意してください。キャッシュされると、スクリプトへの変更による結果が確認できません。[こちらを確認][3]**

## 用語

まず、いくつかの用語を定義しましょう。

* ***Script*** スクリプトとはスクリプトオブジェクトを定義するための正しいJavaScriptを含む単一のJavaScriptファイルです。
* ***Script Component*** スクリプトコンポーネントはPlayCanvasエンジンで定義され、ゲームエンティティにスクリプトを読み込みスクリプトオブジェクトを作成する機能を与えます。
* ***Script Object*** スクリプトオブジェクトはPlayCanvasエンジンでレジスタされるスタンダードなJavaScriptオブジェクトです。新規のスクリプトコンポーネントが作成される際にインスタンス化することができます。基本的に、アプリケーションのタイプ毎に存在するスクリプトオブジェクトは一つです。
* ***Script Instance*** スクリプトインスタンスは、JavaScriptでnewキーワードを使用して実行時にインスタンス化されたスクリプトオブジェクトです。スクリプトインスタンスはそのスクリプトが添付されている全てのエンティティに対して作成されます。

[1]: /user-manual/packs/components/
[2]: /user-manual/packs/entities/
[3]: /user-manual/scripting/debugging/
