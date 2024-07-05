---
title: 異なるページ設定
linktitle: 異なるページ設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、異なるページ設定でドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/different-page-setup/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、異なるページ設定を持つドキュメントを別のドキュメントに追加する方法について説明します。提供されているソース コードは、ソース ドキュメントと宛先ドキュメントに異なるページ設定を設定し、適切な継続と番号付けを確実に行う方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが配置されているドキュメント ディレクトリ パス。

## ステップ2: ソースドキュメントと宛先ドキュメントを開く

ソース文書と宛先文書を`Document`クラスコンストラクタ。置換`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## ステップ3: ソースドキュメントのページ設定を設定する

ソース文書のページ設定を調整して、適切な継続と番号付けを確実にします。この例では、セクションの開始を次のように設定しています。`SectionStart.Continuous`ページ番号付けを再開します。また、ページの幅、高さ、向きが、宛先ドキュメントの最後のセクションと一致していることを確認します。

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## ステップ4: 段落の書式を変更する

適切な書式を維持するには、ソース文書内のすべての段落を反復処理し、`KeepWithNext`財産に`true`これにより、追加プロセス中に段落が一緒に保持されます。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## ステップ5: ソース文書を宛先文書に追加する

使用`AppendDocument`宛先ドキュメントのメソッドを使用して、ソースの書式設定を保持したまま、変更されたソース ドキュメントを宛先ドキュメントに追加します。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## ステップ6: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

これで、Aspose.Words for .NET を使用して異なるページ設定でドキュメントを追加する実装が完了します。

### Aspose.Words for .NET を使用した異なるページ設定のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//ソース ドキュメントを、宛先ドキュメントの終了後すぐに継続するように設定します。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//ソース ドキュメントの先頭からページ番号付けを再開します。
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//ソース文書のページ設定が異なる場合にこの問題が発生しないようにするには、
	//設定は、宛先ドキュメントの最後のセクション間で同一です。
	//ソース文書にさらに連続したセクションがある場合、
	//これらのセクションに対してこれを繰り返す必要があります。
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	//ソース ドキュメント内のすべてのセクションを反復処理します。
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```