---
title: 別のページ設定
linktitle: 別のページ設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、さまざまなページ設定設定を持つドキュメントを追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/different-page-setup/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、異なるページ設定設定を持つドキュメントを別のドキュメントに追加する方法について説明します。提供されているソース コードは、ソース ドキュメントと宛先ドキュメントに異なるページ設定を設定し、適切な継続と番号付けを保証する方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET ライブラリがインストールされています。からダウンロードできます[Aspose.Releases]https://releases.aspose.com/words/net/ または NuGet パッケージ マネージャーを使用してインストールします。
- ソースおよび宛先ドキュメントが配置されるドキュメント ディレクトリ パス。

## ステップ 2: ソース文書と宛先文書を開く

を使用して、ソースドキュメントと宛先ドキュメントを開きます。`Document`クラスコンストラクター。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを置き換えます。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ 3: ソースドキュメントのページ設定をセットアップする

ソース文書のページ設定設定を調整して、適切な継続と番号付けを確保します。この例では、セクションの開始を次のように設定します。`SectionStart.Continuous`そしてページ番号付けを再開します。また、ページの幅、高さ、方向が宛先ドキュメントの最後のセクションと一致していることも確認します。

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## ステップ 4: 段落の書式を変更する

適切な書式を維持するには、ソース文書内のすべての段落を繰り返し処理し、`KeepWithNext`財産を`true`。これにより、追加プロセス中に段落が一緒に保たれます。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ステップ 5: ソース文書を宛先文書に追加する

使用`AppendDocument`宛先ドキュメントのメソッドを使用して、ソースの書式を維持しながら、変更されたソースドキュメントを宛先ドキュメントに追加します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ 6: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを次のコマンドを使用して保存します。`Save`の方法`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

これで、Aspose.Words for .NET を使用して、異なるページ設定設定でドキュメントを追加する実装が完了しました。

### Aspose.Words for .NET を使用した別のページ設定のソース コードの例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ソース文書が宛先文書の終了直後に継続するように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//ソース文書の先頭でページ番号付けを再開します。
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//ソースドキュメントに異なるページ設定設定がある場合にこの問題が発生しないようにするには、
	//設定は、宛先ドキュメントの最後のセクション間で同一です。
	//ソース文書内にさらに連続したセクションがある場合、
	//これらのセクションに対してこれを繰り返す必要があります。
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	//ソース文書内のすべてのセクションを繰り返し処理します。
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```