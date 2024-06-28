---
title: 文末脚注オプションの設定
linktitle: 文末脚注オプションの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に文末脚注オプションを設定する方法を学習します。サンプルソースコードを含むステップバイステップのチュートリアル。
type: docs
weight: 10
url: /ja/net/working-with-footnote-and-endnote/set-endnote-options/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に文末脚注オプションを設定する方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、Aspose.Words for .NET が開発環境にインストールされ、セットアップされていることを確認してください。まだ行っていない場合は、からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ドキュメント オブジェクトの初期化

まず、初期化します`Document`ソースドキュメントへのパスを指定してオブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## ステップ 2: DocumentBuilder オブジェクトの初期化

次に、初期化します`DocumentBuilder`ドキュメントに対して操作を実行するオブジェクト:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: テキストと文末脚注を追加する

使用`Write`の方法`DocumentBuilder`オブジェクトを使用してドキュメントにテキストを追加します。`InsertFootnote`文末脚注を挿入するメソッド:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## ステップ 4: 文末脚注オプションの設定

にアクセスしてください`EndnoteOptions`文書のプロパティを使用して文末脚注のオプションを変更します。この例では、各ページで再開するように再開ルールを設定し、位置をセクションの終わりに設定します。

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## ステップ 5: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して Word 文書に文末脚注オプションを設定することに成功しました。

### Aspose.Words for .NET を使用した文末脚注オプションの設定のソース コード例

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

このコードを独自のプロジェクトで自由に使用し、特定の要件に応じて変更してください。

### よくある質問

#### Q: Aspose.Words で文末脚注のスタイルを設定するにはどうすればよいですか?

A: Aspose.Words で文末脚注のスタイルを設定するには、`EndnoteOptions`クラスと`SeparatorNoteTextStyle`財産。このプロパティを使用して、文末脚注のフォント スタイル、サイズ、色などを指定できます。

#### Q: 文書内の文末脚注の番号をカスタマイズすることはできますか?

 A: はい、文書内の文末脚注の番号をカスタマイズすることができます。使用できます`RestartRule`そして`NumberStyle`のプロパティ`EndnoteOptions`クラスを使用して、特定の再起動ルールと番号付けスタイルを定義します。

#### Q: 文書内で文末脚注を配置するにはどうすればよいですか?

 A: 文書内に文末脚注を配置するには、`Position`の財産`EndnoteOptions`クラス。文末脚注を各ページの下部、各セクションの最後、または文書の最後に配置するかどうかを指定できます。

#### Q: 文末脚注の番号付け形式をカスタマイズできますか?

 A: はい、Aspose.Words で文末脚注の番号付け形式をカスタマイズできます。使用`NumberFormat`の財産`EndnoteOptions`クラスを使用して、アラビア数字、ローマ数字、文字などの目的の形式を設定します。

#### Q: 文書のセクション間で文末脚注の番号付けを継続することは可能ですか?

A: はい、文書のセクション間で文末脚注の番号付けを継続することができます。使用`RestartRule`の財産`EndnoteOptions`クラスを作成し、次のように設定します`RestartContinuous`セクション間で番号付けを継続できるようにします。