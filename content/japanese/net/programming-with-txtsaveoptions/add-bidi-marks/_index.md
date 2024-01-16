---
title: Word 文書に Bidi マークを追加する
linktitle: Word 文書に Bidi マークを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に Bidi マークを追加し、プロフェッショナルな多言語文書を作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET は、C# アプリケーションで Word ドキュメントを作成、編集、操作するための強力なライブラリです。 Aspose.Words が提供する機能の中には、文書に Bidi (双方向) マークを追加する機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用してドキュメントに Bidi マークを追加する方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、Word 文書のワープロ処理を簡単かつ効率的に行う人気のライブラリです。 Bidi マークの追加など、Word 文書を作成、編集、操作するための幅広い機能を提供します。

## ドキュメントの作成とコンテンツの追加

最初のステップは、新しいドキュメントを作成し、そこにコンテンツを追加することです。 Document クラスを使用して、新しいドキュメント インスタンスを作成します。次に、DocumentBuilder クラスを使用してドキュメントにテキストを追加します。以下に例を示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

この例では、新しいドキュメントを作成し、DocumentBuilder を使用してテキストを追加します。さまざまな言語でコンテンツを追加する方法を示すために、英語、ヘブライ語、アラビア語の 3 行のテキストを追加しました。

## Bidi マークを追加しました

コンテンツを追加したら、ドキュメントに Bidi マークを追加できます。このために、TxtSaveOptions クラスを使用し、AddBidiMarks プロパティを true に設定します。その方法は次のとおりです。

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

この例では、TxtSaveOptions のインスタンスを作成し、AddBidiMarks プロパティを true に設定します。次に、Document クラスの Save メソッドを使用して、Bidi マーク付きのドキュメントを保存します。

### Aspose.Words for .NET を使用した「Bidi マークの追加」機能のソース コード例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成してコンテンツを追加する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

//Bidi マークを追加する
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## 結論

このガイドでは、Aspose.Words for .NET を使用して、提供されている C# ソース コードを使用して Word 文書に Bidi マークを追加する方法を説明しました。指定された手順に従うことで、C# アプリケーションの Word 文書に Bidi マークを簡単に追加できます。 Aspose.Words は、テキストの書式設定と言語管理を備えたワード処理に優れた柔軟性と機能を提供し、多言語ドキュメントを専門的に作成できるようにします。

### よくある質問

#### Q: Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、C# アプリケーションで Word ドキュメントを作成、編集、操作するための強力なライブラリです。 Bidi (双方向) マークの追加など、Word 文書でのワード処理のための多くの機能を提供します。

#### Q: Aspose.Words for .NET はどのような機能を提供しますか?
Aspose.Words for .NET は、Word ドキュメントを作成、編集、操作するための幅広い機能を提供します。これらの機能には、ドキュメントの作成、コンテンツの追加、テキストの書式設定、テーブルの管理、ドキュメントの結合と分割、ドキュメントの変換などが含まれます。

#### Q: Aspose.Words for .NET を使用して Word 文書に Bidi マークを追加するにはどうすればよいですか?
次の手順に従って、Word 文書に Bidi マークを追加できます。

を使用して新しいドキュメントを作成します。`Document`クラス。

使用`DocumentBuilder`ドキュメントにコンテンツを追加するクラス。

コンテンツを追加したら、`TxtSaveOptions`クラスを設定して、`AddBidiMarks`財産を`true`.

を使用して、Bidi マークを付けてドキュメントを保存します。`Save`の方法`Document`クラス。

#### Q: Aspose.Words は、Bidi マークを追加するために複数の言語をサポートしていますか?
はい、Aspose.Words は、Bidi マークを追加するために複数の言語をサポートしています。 Aspose.Words for .NET を使用して、英語、ヘブライ語、アラビア語などのさまざまな言語のテキストに Bidi マークを追加できます。

#### Q: Bidi マークを付けてドキュメントを保存するための追加オプションはありますか?
はい、Bidi マークを含むドキュメントを保存するときに、`TxtSaveOptions`クラス。たとえば、ドキュメントの保存形式、エンコード オプションなどを設定できます。