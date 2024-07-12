---
title: 文末脚注オプションの設定
linktitle: 文末脚注オプションの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の文末脚注オプションを設定する方法を学びます。サンプル ソース コードを使用したステップバイステップのチュートリアルです。
type: docs
weight: 10
url: /ja/net/working-with-footnote-and-endnote/set-endnote-options/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の文末脚注オプションを設定する方法について説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

始めるには、開発環境にAspose.Words for .NETがインストールされ、セットアップされていることを確認してください。まだインストールされていない場合は、次の場所からライブラリをダウンロードしてインストールしてください。[Aspose.Releases]https://releases.aspose.com/words/net/.

## ステップ1: ドキュメントオブジェクトの初期化

まず、`Document`ソース ドキュメントへのパスを指定してオブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## ステップ 2: DocumentBuilder オブジェクトの初期化

次に、`DocumentBuilder`ドキュメントに対して操作を実行するオブジェクト:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: テキストと文末脚注の追加

使用`Write`方法の`DocumentBuilder`オブジェクトを使用して文書にテキストを追加し、`InsertFootnote`文末脚注を挿入する方法:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## ステップ4: Endnoteオプションの設定

アクセス`EndnoteOptions`ドキュメントのプロパティを使用して、文末脚注のオプションを変更します。この例では、再開ルールを各ページで再開するように設定し、位置をセクションの最後に設定しています。

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## ステップ5: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書の文末脚注オプションを正常に設定できました。

### Aspose.Words for .NET を使用して Endnote オプションを設定するためのサンプル ソース コード

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

#### Q: Aspose.Words で文末脚注のスタイルを設定するにはどうすればいいですか?

 A: Aspose.Wordsで文末脚注のスタイルを設定するには、`EndnoteOptions`クラスと`SeparatorNoteTextStyle`プロパティ。このプロパティを使用して、文末脚注のフォント スタイル、サイズ、色などを指定できます。

#### Q: 文書内の文末脚注の番号付けをカスタマイズすることは可能ですか?

 A: はい、文書内の文末脚注の番号付けをカスタマイズすることは可能です。`RestartRule`そして`NumberStyle`の特性`EndnoteOptions`特定の再開ルールと番号付けスタイルを定義するクラス。

#### Q: 文書内で文末脚注を配置するにはどうすればよいでしょうか?

A: 文書内で文末脚注を配置するには、`Position`の財産`EndnoteOptions`クラス。文末脚注を各ページの下部、各セクションの末尾、または文書の末尾に配置するかどうかを指定できます。

#### Q: 文末脚注の番号付け形式をカスタマイズできますか?

 A: はい、Aspose.Wordsでは文末脚注の番号付けの形式をカスタマイズできます。`NumberFormat`の財産`EndnoteOptions`アラビア数字、ローマ数字、文字などの希望の形式を設定するクラス。

#### Q: 文書のセクション間で文末脚注の番号付けを継続することは可能ですか?

 A: はい、文書のセクション間で文末脚注の番号を継続することは可能です。`RestartRule`の財産`EndnoteOptions`クラスに設定して`RestartContinuous`セクション間で番号を継続できるようにするため。