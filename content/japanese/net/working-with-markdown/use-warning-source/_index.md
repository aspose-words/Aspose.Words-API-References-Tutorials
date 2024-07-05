---
title: 警告ソースを使用する
linktitle: 警告ソースを使用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で警告ソースを使用する方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/use-warning-source/
---

この例では、Aspose.Words for .NET で警告ソースを使用する方法を説明します。警告ソースは、コールバック関数を使用するときに警告の発生元を示します。

## ステップ1: ドキュメントの読み込み

警告を含む既存の文書をロードするには、`Load`方法の`Document`クラス。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## ステップ3: 警告ソースの使用

警告ソースを使用するには、ドキュメントの`WarningCallback`コレクションのプロパティ`WarningInfo`オブジェクト。

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## ステップ4: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Aspose.Words for .NET で警告ソースを使用するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

おめでとうございます。これで、Aspose.Words for .NET で警告ソースを使用する方法を学習しました。

### よくある質問

#### Q: 「警告」タグの外観をカスタマイズできますか?

 A: 「警告」タグの書式は、使用するMarkdownレンダラーによって異なります。ほとんどの場合、CSSを使用してターゲットを絞ることで外観をカスタマイズできます。`blockquote`ドキュメント内のタグ。

#### Q: 「警告」タグにアイコンを追加することは可能ですか?

A: はい、マークダウン文書のHTMLコードを使用して「警告」タグにアイコンを追加することは可能です。`span`警告テキストの横にアイコンを表示するには、適切なクラスのタグを使用します。

#### Q: 「警告」タグはすべての Markdown リーダーと互換性がありますか?

 A: 「警告」タグの互換性は、使用するMarkdownレンダリングに依存します。ほとんどのMarkdownリーダーは、`blockquote`強調表示されたテキストを表示するためのタグですが、実際の外観は異なる場合があります。