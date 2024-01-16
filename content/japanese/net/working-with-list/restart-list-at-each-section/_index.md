---
title: 各セクションのリスタートリスト
linktitle: 各セクションのリスタートリスト
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書の各セクションに番号付きリストをリセットする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-list/restart-list-at-each-section/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書の各セクションに番号付きリストをリセットする方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、開発環境に Aspose.Words for .NET がインストールされ、構成されていることを確認してください。まだライブラリをダウンロードしてインストールしていない場合は、次からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ドキュメントとリストの作成

まず、新しいドキュメントを作成し、デフォルトの番号付きリストを追加します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## ステップ 2: リストに項目を追加する

次に、`DocumentBuilder`リストに項目を追加します。ループを使用して複数の項目をリストに追加できます。

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

この例では、番号の再設定を示すために、15 番目のリスト項目の後にセクション区切りを挿入しています。

## ステップ 3: 変更したドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

それで ！ Aspose.Words for .NET を使用して、Word 文書の各セクションに番号付きリストを正常にリセットしました。

### 各セクションのリストをリセットするためのソース コードの例

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

このコードを独自のプロジェクトで自由に使用し、特定のニーズに合わせて変更してください。

### よくある質問

#### Q: Aspose.Words のすべてのセクションでリストを再開するにはどうすればよいですか?

 A: Aspose.Words のすべてのセクションでリストを再開するには、`List`クラスを作成し、それに番号付きリストを割り当てます。その後、使用できます`List.IsRestartAtEachSection`プロパティを使用して、各セクションで番号付けを再開するように指定します。このリストをドキュメントの 1 つ以上のセクションに関連付けると、各セクションで番号付けが正しく再開されるようになります。

#### Q: Aspose.Words のリストの番号付け形式をカスタマイズできますか?

A: はい、Aspose.Words でリストの番号付け形式をカスタマイズできます。の`List`クラスは、このために次のようないくつかのプロパティを提供します。`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`これらのプロパティを使用して、リストの種類 (番号付き、箇条書きなど)、番号付け形式 (アラビア数字、ローマ数字、文字など)、およびその他の番号付け形式オプションを設定できます。

#### Q: Aspose.Words の番号付きリストにレベルを追加することはできますか?

 A: はい、Aspose.Words の番号付きリストにレベルを追加することができます。の`ListLevel`クラスを使用すると、リストの各レベルの書式設定プロパティを設定できます。プレフィックス、サフィックス、配置、インデントなどのオプションを設定できます。これにより、複数レベルの階層を持つリストを作成できます。