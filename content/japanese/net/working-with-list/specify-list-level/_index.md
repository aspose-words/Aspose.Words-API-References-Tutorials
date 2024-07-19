---
title: リストレベルを指定する
linktitle: リストレベルを指定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のリスト レベルを指定する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-list/specify-list-level/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のリスト レベルを指定する方法を説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

始めるには、開発環境にAspose.Words for .NETがインストールされ、構成されていることを確認してください。まだインストールしていない場合は、次の場所からライブラリをダウンロードしてインストールしてください。[Aspose.Releases]https://releases.aspose.com/words/net/.

## ステップ1: ドキュメントとドキュメントジェネレーターの作成

まず、新しいドキュメントと関連するドキュメント ジェネレーターを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: 番号付きリストの作成と適用

次に、Microsoft Word のリスト テンプレートの 1 つに基づいて番号付きリストを作成し、それをドキュメント ビルダーの現在の段落に適用します。

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## ステップ3: リストレベルの仕様

ドキュメントビルダーの`ListLevelNumber`リスト レベルを指定し、段落にテキストを追加するプロパティ:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

これらの手順を繰り返してリスト レベルを指定し、各レベルでテキストを追加します。

## ステップ4: 箇条書きリストの作成と適用

Microsoft Word のリスト テンプレートのいずれかを使用して、箇条書きリストを作成して適用することもできます。

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## ステップ5: 箇条書きリストレベルにテキストを追加する

使用`ListLevelNumber`プロパティを再度使用して、箇条書きリストのレベルを指定し、テキストを追加します。

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## ステップ6: リストの書式設定を停止する

リストの書式設定を停止するには、`null`に`List`ドキュメントジェネレータのプロパティ:

```csharp
builder. ListFormat. List = null;
```

## ステップ7: 変更したドキュメントを保存する

変更したドキュメントを保存します。

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

これで、Aspose.Words for .NET を使用して Word 文書のリスト レベルを正常に指定できました。

### リストレベルを指定するためのサンプルソースコード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Microsoft Wordのリストテンプレートの1つに基づいて番号付きリストを作成します
//それをドキュメント ビルダーの現在の段落に適用します。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

//このリストには 9 つのレベルがあります。すべて試してみましょう。
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Wordのリストテンプレートの1つに基づいて箇条書きリストを作成します
//それをドキュメント ビルダーの現在の段落に適用します。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//これはリストのフォーマットを停止する方法です。
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### よくある質問

#### Q: Aspose.Words でリスト レベルを指定するにはどうすればよいですか?

 A: Aspose.Wordsでリストレベルを指定するには、`List`クラスを作成し、番号付きリストを作成します。その後、`Paragraph.ListFormat.ListLevelNumber`各リスト項目のレベルを指定するプロパティ。このリストをドキュメントのセクションに関連付けることで、リスト項目が目的のレベルになるようにすることができます。

#### Q: Aspose.Words のリスト項目の番号付け形式を変更することは可能ですか?

 A: はい、Aspose.Wordsのリスト項目の番号付け形式を変更することができます。`ListLevel`クラスは、これに関するいくつかのプロパティを提供します。`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`これらのプロパティを使用して、アラビア数字、ローマ数字、文字など、リスト項目の番号付け形式を設定できます。

#### Q: Aspose.Words の番号付きリストに追加のレベルを追加できますか?

 A: はい、Aspose.Wordsでは番号付きリストにレベルを追加することができます。`ListLevel`クラスを使用すると、リストの各レベルの書式設定プロパティを設定できます。プレフィックス、サフィックス、配置、インデントなどのオプションを設定できます。これにより、複数の階層レベルを持つリストを作成できます。


