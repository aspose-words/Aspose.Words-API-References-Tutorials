---
title: Word 文書に Bidi マークを追加する
linktitle: Word 文書に Bidi マークを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に Bidi マークを追加し、プロフェッショナルな多言語文書を作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET は、C# アプリケーションで Word 文書を作成、編集、および操作するための強力なライブラリです。Aspose.Words が提供する機能の 1 つに、文書に Bidi (双方向) マークを追加する機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用して文書に Bidi マークを追加する方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、Word 文書での単語処理を簡単かつ効率的にする人気のライブラリです。Bidi マークの追加など、Word 文書の作成、編集、操作のための幅広い機能を提供します。

## ドキュメントの作成とコンテンツの追加

最初のステップは、新しいドキュメントを作成し、それにコンテンツを追加することです。Document クラスを使用して新しいドキュメント インスタンスを作成します。次に、DocumentBuilder クラスを使用してドキュメントにテキストを追加します。次に例を示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

この例では、新しいドキュメントを作成し、DocumentBuilder を使用してテキストを追加します。さまざまな言語でコンテンツを追加する方法を示すために、英語、ヘブライ語、アラビア語の 3 行のテキストを追加しました。

## Bidiマークを追加

コンテンツを追加したら、ドキュメントに Bidi マークを追加できます。そのためには、TxtSaveOptions クラスを使用し、AddBidiMarks プロパティを true に設定します。手順は次のとおりです。

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

この例では、TxtSaveOptions のインスタンスを作成し、AddBidiMarks プロパティを true に設定します。次に、Document クラスの Save メソッドを使用して、Bidi マークを含むドキュメントを保存します。

### Aspose.Words for .NET を使用した「Bidi マークの追加」機能のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、コンテンツを追加する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

//Bidiマークを追加する
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## 結論

このガイドでは、提供されている C# ソース コードを使用して、Aspose.Words for .NET で Word 文書に Bidi マークを追加する方法について説明しました。提供されている手順に従うと、C# アプリケーションで Word 文書に Bidi マークを簡単に追加できます。Aspose.Words は、テキストの書式設定と言語管理による Words 処理に優れた柔軟性とパワーを提供し、多言語文書をプロフェッショナルに作成できるようにします。

### よくある質問

#### Q: Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、C# アプリケーションで Word 文書を作成、編集、操作するための強力なライブラリです。Bidi (双方向) マークの追加など、Word 文書での Words Processing のための多くの機能を提供します。

#### Q: Aspose.Words for .NET にはどのような機能がありますか?
Aspose.Words for .NET は、Word 文書を作成、編集、操作するための幅広い機能を提供します。これらの機能には、文書の作成、コンテンツの追加、テキストの書式設定、表の管理、文書の結合と分割、文書の変換などがあります。

#### Q: Aspose.Words for .NET を使用して Word 文書に Bidi マークを追加するにはどうすればよいですか?
次の手順に従って、Word 文書に Bidi マークを追加できます。

新しいドキュメントを作成するには、`Document`クラス。

使用`DocumentBuilder`ドキュメントにコンテンツを追加するクラス。

コンテンツを追加したら、`TxtSaveOptions`クラスを設定し、`AddBidiMarks`財産に`true`.

 Bidiマーク付きの文書を保存するには、`Save`方法の`Document`クラス。

#### Q: Aspose.Words は Bidi マークを追加するために複数の言語をサポートしていますか?
はい、Aspose.Words は Bidi マークを追加するための複数の言語をサポートしています。Aspose.Words for .NET を使用すると、英語、ヘブライ語、アラビア語などのさまざまな言語のテキストに Bidi マークを追加できます。

#### Q: Bidi マーク付きのドキュメントを保存するための追加オプションはありますか?
はい、文書をBidiマーク付きで保存するときに、他のオプションを指定することができます。`TxtSaveOptions`クラス。たとえば、ドキュメントの保存形式やエンコード オプションなどを設定できます。