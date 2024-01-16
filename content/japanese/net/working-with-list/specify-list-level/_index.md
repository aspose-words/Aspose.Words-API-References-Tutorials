---
title: リストレベルの指定
linktitle: リストレベルの指定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のリスト レベルを指定する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-list/specify-list-level/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のリスト レベルを指定する方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、開発環境に Aspose.Words for .NET がインストールされ、構成されていることを確認してください。まだライブラリをダウンロードしてインストールしていない場合は、次からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ドキュメントとドキュメント ジェネレーターの作成

まず、新しいドキュメントと関連するドキュメント ジェネレーターを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 番号付きリストの作成と適用

次に、Microsoft Word のリスト テンプレートの 1 つに基づいて番号付きリストを作成し、それをドキュメント ビルダーの現在の段落に適用します。

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## ステップ 3: リストレベルの仕様

ドキュメントビルダーを使用する`ListLevelNumber`プロパティを使用してリスト レベルを指定し、段落にテキストを追加します。

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

これらの手順を繰り返してリスト レベルを指定し、各レベルにテキストを追加します。

## ステップ 4: 箇条書きリストの作成と適用

Microsoft Word のリスト テンプレートのいずれかを使用して、箇条書きリストを作成して適用することもできます。

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## ステップ 5: 箇条書きレベルにテキストを追加する

使用`ListLevelNumber`プロパティを再度使用して箇条書きレベルを指定し、テキストを追加します。

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## ステップ 6: リストのフォーマットを停止する

リストの書式設定を停止するには、次のように設定します`null`に`List`ドキュメント ジェネレーターのプロパティ:

```csharp
builder. ListFormat. List = null;
```

## ステップ 7: 変更したドキュメントを保存する

変更したドキュメントを保存します。

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

それで ！ Aspose.Words for .NET を使用して、Word 文書内のリスト レベルを正常に指定しました。

### リストレベルを指定するサンプルソースコード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Microsoft Word リスト テンプレートの 1 つに基づいて番号付きリストを作成します。
//そしてそれをドキュメントビルダーの現在の段落に適用します。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

//このリストには 9 つのレベルがあります。すべて試してみましょう。
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Word リスト テンプレートの 1 つに基づいて箇条書きリストを作成します。
//そしてそれをドキュメントビルダーの現在の段落に適用します。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//これはリストの書式設定を停止する方法です。
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### よくある質問

#### Q: Aspose.Words でリスト レベルを指定するにはどうすればよいですか?

 A: Aspose.Words でリスト レベルを指定するには、`List`クラスを作成し、それに番号付きリストを与えます。その後、使用できます`Paragraph.ListFormat.ListLevelNumber`プロパティを使用して、各リスト項目のレベルを指定します。このリストをドキュメントのセクションに関連付けて、リスト項目が目的のレベルになるようにすることができます。

#### Q: Aspose.Words のリスト項目の番号付け形式を変更することはできますか?

 A: はい、Aspose.Words でリスト項目の番号付け形式を変更できます。の`ListLevel`クラスは、このために次のようないくつかのプロパティを提供します。`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`これらのプロパティを使用して、アラビア数字、ローマ数字、文字などのリスト項目の番号付け形式を設定できます。

#### Q: Aspose.Words の番号付きリストにレベルを追加できますか?

 A: はい、Aspose.Words の番号付きリストにレベルを追加することができます。の`ListLevel`クラスを使用すると、リストの各レベルの書式設定プロパティを設定できます。プレフィックス、サフィックス、配置、インデントなどのオプションを設定できます。これにより、複数レベルの階層を持つリストを作成できます。


