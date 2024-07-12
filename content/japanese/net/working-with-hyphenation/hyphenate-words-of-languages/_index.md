---
title: 言語の単語をハイフンでつなぐ
linktitle: 言語の単語をハイフンでつなぐ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のさまざまな言語の単語をハイフンで区切る方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-hyphenation/hyphenate-words-of-languages/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のさまざまな言語の単語をハイフンで区切る方法について説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

開始するには、開発環境に Aspose.Words for .NET がインストールされ、構成されていることを確認してください。まだインストールしていない場合は、公式サイトからライブラリをダウンロードしてインストールしてください。

## ステップ1: ドキュメントオブジェクトの初期化

まず、`Document`異なる言語のテキストを含むソース ドキュメントへのパスを指定してオブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## ステップ2: ハイフネーション辞書の保存

次に、処理するさまざまな言語のハイフネーション辞書を保存します。この例では、アメリカ英語とスイスドイツ語の辞書を登録します。

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

データ ディレクトリに適切な辞書ファイルがあることを確認してください。

## ステップ3: ハイフネーションによる単語の処理

ハイフネーション機能を使用して、さまざまな言語の単語を処理できるようになりました。`Document`または`DocumentBuilder`お客様の特定のニーズに応じて異なります。

```csharp
//例: DocumentBuilder のハイフネーション メソッドの使用
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## ステップ4: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

これで、Aspose.Words for .NET を使用して、Word 文書内のさまざまな言語の単語をハイフンで区切って処理することができました。

### Aspose.Words for .NET を使用した単語のハイフネーションのサンプル ソース コード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

このコードを自分のプロジェクトで自由に使用し、特定のニーズに合わせて変更してください。

### よくある質問

#### Q: Aspose.Words を使用して特定の言語の単語を音節化するにはどうすればよいですか?

 A: Aspose.Wordsで特定の言語の単語を音節化するには、`Hyphenation`クラスと`Hyphenate()`メソッドのインスタンスを作成します`Hyphenation`希望する言語を指定するクラスを呼び出し、`Hyphenate()`メソッドは、引数として音節化する単語を渡します。これにより、指定された言語での単語の音節が返されます。

#### Q: Aspose.Words で音節化言語を指定するには、どの言語コードを使用すればよいですか?

A: Aspose.Words で音節化言語を指定するには、適切な言語コードを使用する必要があります。たとえば、英語の場合は「en」、フランス語の場合は「fr」、スペイン語の場合は「es」、ドイツ語の場合は「de」などを使用できます。サポートされている言語コードの完全なリストについては、Aspose.Words のドキュメントを参照してください。

#### Q: Aspose.Words ではすべての言語で音節化が機能しますか?

A: Aspose.Words の音節化は、言語固有の音節化ルールに依存します。Aspose.Words は幅広い言語をサポートしていますが、一部の言語はサポートされていないか、音節化が利用できない場合があります。音節化がサポートされている言語を確認するには、Aspose.Words のドキュメントを確認してください。