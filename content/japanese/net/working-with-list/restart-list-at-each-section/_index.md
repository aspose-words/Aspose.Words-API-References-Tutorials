---
title: 各セクションでリストを再開する
linktitle: 各セクションでリストを再開する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の各セクションに番号付きリストをリセットする方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-list/restart-list-at-each-section/
---

このステップ バイ ステップのチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の各セクションに番号付きリストをリセットする方法を説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

始めるには、開発環境にAspose.Words for .NETがインストールされ、構成されていることを確認してください。まだインストールしていない場合は、次の場所からライブラリをダウンロードしてインストールしてください。[Aspose.Releases]https://releases.aspose.com/words/net/.

## ステップ1: ドキュメントとリストの作成

まず、新しいドキュメントを作成し、デフォルトの番号付きリストを追加します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## ステップ2: リストにアイテムを追加する

次に、`DocumentBuilder`リストにアイテムを追加します。ループを使用して、リストに複数のアイテムを追加できます。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

この例では、番号の再割り当てを示すために、15 番目のリスト項目の後にセクション区切りを挿入しています。

## ステップ3: 変更したドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

これで、Aspose.Words for .NET を使用して、Word 文書内の各セクションに番号付きリストを正常にリセットできました。

### 各セクションでリストをリセットするためのサンプルソースコード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

このコードを自分のプロジェクトで自由に使用し、特定のニーズに合わせて変更してください。

### よくある質問

#### Q: Aspose.Words の各セクションでリストを再開するにはどうすればよいですか?

 A: Aspose.Wordsでセクションごとにリストを再開するには、`List`クラスを作成し、番号付きリストを割り当てます。その後、`List.IsRestartAtEachSection`プロパティを使用して、各セクションで番号付けを再開することを指定します。このリストをドキュメントの 1 つ以上のセクションに関連付けると、各セクションで番号付けが正しく再開されます。

#### Q: Aspose.Words のリストの番号付け形式をカスタマイズできますか?

 A: はい、Aspose.Wordsではリストの番号付け形式をカスタマイズできます。`List`クラスはこれに関するいくつかのプロパティを提供します。`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`これらのプロパティを使用して、リストの種類 (番号付き、箇条書きなど)、番号の形式 (アラビア数字、ローマ数字、文字など)、およびその他の番号の書式設定オプションを設定できます。

#### Q: Aspose.Words の番号付きリストに追加のレベルを追加することは可能ですか?

 A: はい、Aspose.Wordsでは番号付きリストにレベルを追加することができます。`ListLevel`クラスを使用すると、リストの各レベルの書式設定プロパティを設定できます。プレフィックス、サフィックス、配置、インデントなどのオプションを設定できます。これにより、複数の階層レベルを持つリストを作成できます。