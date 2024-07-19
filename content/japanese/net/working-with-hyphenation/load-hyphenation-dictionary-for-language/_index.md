---
title: 言語のハイフネーション辞書を読み込む
linktitle: 言語のハイフネーション辞書を読み込む
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で特定の言語のハイフネーション辞書を読み込む方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

このステップバイステップのチュートリアルでは、特定の言語のハイフネーション辞書を Aspose.Words for .NET に読み込む方法を説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

始めるには、開発環境にAspose.Words for .NETがインストールされ、構成されていることを確認してください。まだインストールしていない場合は、次の場所からライブラリをダウンロードしてインストールしてください。[Aspose.Releases]https://releases.aspose.com/words/net/.

## ステップ1: ドキュメントの読み込み

まず、指定されたディレクトリからドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## ステップ2: ハイフネーション辞書の読み込み

次に、ハイフネーション辞書ファイルへのストリームを開き、目的の言語用に保存します。この例では、スイスドイツ語 (de-CH) の辞書を読み込みます。

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

データ ディレクトリに適切な辞書ファイルがあることを確認してください。

## ステップ3: 変更したドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

これで、Aspose.Words for .NET に特定の言語のハイフネーション辞書が正常に読み込まれました。

### Aspose.Words for .NET を使用して言語のハイフネーション辞書を読み込むためのサンプル ソース コード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

このコードを自分のプロジェクトで自由に使用し、特定のニーズに合わせて変更してください。

### よくある質問

#### Q: Aspose.Words で特定の言語の音節化辞書を読み込むにはどうすればいいですか?

 A: Aspose.Wordsで特定の言語の音節辞書を読み込むには、`Hyphenation`クラスと`LoadDictionary()`メソッドのインスタンスを作成します`Hyphenation`クラスを呼び、`LoadDictionary()`目的の言語の音節化辞書ファイルへのパスを指定するメソッド。これにより、音節化辞書が Aspose.Words に読み込まれます。

#### Q: さまざまな言語の音節化辞書ファイルはどこにありますか?

A: さまざまな言語の音節化辞書ファイルは、さまざまなオンライン リソースで見つけることができます。これらのファイルは通常、XML または TEX 形式です。さまざまな言語のオープン ソース音節化辞書は、言語学プロジェクト専用の Web サイトやソース コード リポジトリで見つけることができます。

#### Q: 読み込んだ音節辞書を Aspose.Words のドキュメントに適用するにはどうすればよいですか?

A: 読み込まれた音節化辞書をAspose.Wordsのドキュメントに適用するには、ドキュメント内の単語を反復処理し、`Hyphenate()`方法の`Hyphenation`クラスを使用して単語の音節化を取得します。その後、音節間にハイフンを追加するなど、必要に応じて音節化された単語をフォーマットできます。

#### Q: Aspose.Words の音節化ではどの言語がサポートされていますか?

A: Aspose.Words は、英語、フランス語、スペイン語、ドイツ語、イタリア語、オランダ語、ロシア語、ポルトガル語、スウェーデン語、ノルウェー語、デンマーク語、フィンランド語、ポーランド語、チェコ語など、複数の言語の音節化をサポートしています。音節化がサポートされている言語の完全なリストについては、Aspose.Words のドキュメントを確認してください。