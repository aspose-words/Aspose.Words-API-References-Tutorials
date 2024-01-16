---
title: 警告ソースを使用する
linktitle: 警告ソースを使用する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で警告ソースを使用する方法のステップバイステップ ガイドを学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/use-warning-source/
---

この例では、Aspose.Words for .NET で警告ソースを使用する方法を示します。警告ソースは、コールバック関数を使用する場合の警告の原因を示します。

## ステップ 1: ドキュメントをロードする

警告を含む既存のドキュメントをロードします。`Load`の方法`Document`クラス。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## ステップ 3: 警告ソースの使用

ドキュメントの設定により警告ソースを使用します。`WarningCallback`プロパティをコレクションに`WarningInfo`オブジェクト。

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## ステップ 4: ドキュメントを保存する

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
//ドキュメントディレクトリへのパス。
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

おめでとうございます！これで、Aspose.Words for .NET で警告ソースを使用する方法を学習しました。

### よくある質問

#### Q: 「警告」タグの外観をカスタマイズできますか?

 A: 「警告」タグの形式は、使用される Markdown レンダラーによって異なります。ほとんどの場合、CSS を使用して外観をカスタマイズできます。`blockquote`ドキュメント内のタグ。

#### Q: 「警告」タグにアイコンを追加することはできますか?

A: はい、Markdown ドキュメントの HTML コードを使用して「警告」タグにアイコンを追加できます。を挿入できます`span`タグを適切なクラスで使用すると、警告テキストの横にアイコンが表示されます。

#### Q: 「警告」タグはすべての Markdown リーダーと互換性がありますか?

 A: 「Warning」タグの互換性は、使用される Markdown レンダリングによって異なります。ほとんどの Markdown 読者は、`blockquote`タグを使用して強調表示されたテキストを表示しますが、正確な外観は異なる場合があります。