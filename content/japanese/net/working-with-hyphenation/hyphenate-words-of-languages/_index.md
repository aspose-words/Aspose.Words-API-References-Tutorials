---
title: 言語の単語をハイフンで区切る
linktitle: 言語の単語をハイフンで区切る
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のさまざまな言語の単語をハイフネーションする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-hyphenation/hyphenate-words-of-languages/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のさまざまな言語の単語をハイフネーションする方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、開発環境に Aspose.Words for .NET がインストールされ、構成されていることを確認してください。まだライブラリをダウンロードしていない場合は、公式サイトからライブラリをダウンロードしてインストールします。

## ステップ 1: ドキュメント オブジェクトの初期化

まず、初期化します`Document`さまざまな言語のテキストを含むソースドキュメントへのパスを指定してオブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## ステップ 2: ハイフネーション辞書の保存

次に、処理するさまざまな言語のハイフネーション辞書を保存します。この例では、アメリカ英語とスイスドイツ語の辞書を登録します。

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

データ ディレクトリに適切な辞書ファイルがあることを確認してください。

## ステップ 3: ハイフネーションによる単語の処理

ハイフネーション機能を使用して、さまざまな言語の単語を処理できるようになりました。さまざまな方法を使用できます`Document`または`DocumentBuilder`特定のニーズに応じて。

```csharp
//例: DocumentBuilder の Hyphenate メソッドの使用
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## ステップ 4: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

それで ！ Aspose.Words for .NET を使用して、Word 文書内でさまざまな言語で単語をハイフネーションすることで、単語を正常に処理できました。

### Aspose.Words for .NET を使用した単語ハイフネーションのサンプル ソース コード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

このコードを独自のプロジェクトで自由に使用し、特定のニーズに合わせて変更してください。

### よくある質問

#### Q: Aspose.Words を使用して特定の言語の単語を音節化するにはどうすればよいですか?

 A: Aspose.Words を使用して特定の言語の単語を音節化するには、`Hyphenation`クラスと`Hyphenate()`方法。のインスタンスを作成します。`Hyphenation`目的の言語を指定するクラスを呼び出して、`Hyphenate()`音節化する単語を引数として渡すメソッド。これにより、指定した言語での単語の音節が得られます。

#### Q: Aspose.Words で音節言語を指定するにはどの言語コードを使用する必要がありますか?

A: Aspose.Words で音節言語を指定するには、適切な言語コードを使用する必要があります。たとえば、英語には「en」、フランス語には「fr」、スペイン語には「es」、ドイツ語には「de」などを使用できます。サポートされている言語コードの完全なリストについては、Aspose.Words ドキュメントを参照してください。

#### Q: Aspose.Words では音節化はすべての言語で機能しますか?

A: Aspose.Words の音節化は、言語固有の音節化ルールに依存します。 Aspose.Words は幅広い言語をサポートしていますが、一部の言語はサポートされていないか、音節化が利用できない場合があります。どの言語が音節化でサポートされているかについては、Aspose.Words のドキュメントを確認してください。