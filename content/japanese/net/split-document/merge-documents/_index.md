---
title: Word 文書を結合する
linktitle: ドキュメントを結合する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して複数の Word ドキュメントを結合する方法を学びます。この強力な API により、ドキュメントの結合プロセスが簡素化され、効率的かつ簡単になります。
type: docs
weight: 10
url: /ja/net/split-document/merge-documents/
---

このチュートリアルでは、Aspose.Words for .NET のドキュメントの結合機能を使用して複数の Word ドキュメントを結合する方法を説明します。以下の手順に従ってソース コードを理解し、すべてのソース ドキュメントを含むマージされたドキュメントを取得します。

## ステップ 1: 結合するドキュメントを検索する

ドキュメントをマージする前に、マージするソース ドキュメントを見つける必要があります。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//結合するドキュメントを検索します。
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## ステップ 2: ドキュメントを結合する

次に、ドキュメントを 1 つずつ結合して、最終的な結合ドキュメントを作成します。その方法は次のとおりです。

```csharp
//作成されたドキュメントの最初の部分を開きます。
Document sourceDoc = new Document(sourceDocumentPath);

//新しい結果ドキュメントを作成します。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//文書を 1 つずつ結合します。
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Aspose.Words for .NET を使用したドキュメントの結合のソース コード例

Aspose.Words for .NET のドキュメントの結合機能の完全なソース コードは次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//マージに使用しているドキュメントを検索します。
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

//作成されたドキュメントの最初の部分を開きます。
Document sourceDoc = new Document(sourceDocumentPath);

//新しい結果ドキュメントを作成します。
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

//ドキュメントのパーツを 1 つずつ結合します。
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## 結論

おめでとう！ Aspose.Words for .NET のドキュメントの結合機能を使用して、複数の Word ドキュメントを結合する方法を学習しました。提供されたソース コードに従うことで、各ソース ドキュメントの書式設定を維持しながら、別々のドキュメントを 1 つの結合ドキュメントに結合できます。

ドキュメントの結合は、複数のソースからの情報を統合する場合、または個々の部分から統合されたドキュメントを作成する場合に便利です。 Aspose.Words for .NET は、ドキュメントの結合プロセスを簡素化し、効率的かつ簡単にする強力な API を提供します。

Aspose.Words for .NET が提供する他の機能を自由に探索して、ドキュメント処理機能を強化し、ワークフローを合理化してください。

### よくある質問

#### 異なる書式のドキュメントを結合するにはどうすればよいですか?

ドキュメントを結合する場合、Aspose.Words for .NET には、各ソース ドキュメントの書式設定を保持するオプションが用意されています。を使用することで、`ImportFormatMode.KeepSourceFormatting`オプションを選択すると、結合されたドキュメントは元のドキュメントの書式設定を保持します。結合されたドキュメント全体に一貫した書式設定を適用する場合は、ドキュメントの結合後に Aspose.Words API を使用して書式設定を変更できます。

#### 異なる形式のドキュメントを結合できますか?

はい、Aspose.Words for .NET は、DOCX、DOC、RTF などのさまざまな形式のドキュメントの結合をサポートしています。さまざまな形式のドキュメントを Aspose.Words API にロードし、元の形式に関係なく、それらを 1 つのドキュメントに結合できます。

#### 表や画像などの複雑な構造を持つドキュメントを結合できますか?

絶対に！ Aspose.Words for .NET は、テーブル、画像、ヘッダー、フッターなどを含む複雑な構造を持つドキュメントを結合できます。 API は、各ドキュメント内のコンテンツの整合性とレイアウトを維持しながら、結合プロセスを処理します。

#### ページの向きやサイズが異なる文書を結合することはできますか?

はい、Aspose.Words for .NET は、結合プロセス中にページの向きやサイズが異なるドキュメントを処理します。結合されたドキュメントは、ソース ドキュメントのさまざまなページの向きとサイズに対応します。