---
title: Word 文書のヘッダー フッター ブックマークを PDF 文書にエクスポートする
linktitle: Word 文書のヘッダー フッター ブックマークを PDF 文書にエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書のヘッダー フッター ブックマークを PDF 文書のブックマークにエクスポートする手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

この記事では、Aspose.Words for .NET を使用して Word 文書のヘッダー フッター ブックマークを PDF 文書機能にエクスポートする方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、文書のヘッダーとフッターからブックマークをエクスポートし、適切なブックマークを含む PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントをアップロードする

次に、処理するドキュメントを読み込む必要があります。この例では、ドキュメントの名前が「Bookmarks in headers and footers.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## ステップ3: PDFとして保存オプションを設定する

ヘッダーとフッターのブックマークをエクスポートするには、`PdfSaveOptions`オブジェクト。この例では、既定のブックマーク アウトライン レベルを 1 に設定し、ヘッダーとフッターのブックマークのエクスポート モードを「最初」に設定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## ステップ4: ヘッダーとフッターのブックマークを付けて文書をPDFとして保存する

最後に、以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

これで完了です。Aspose.Words for .NET を使用して、ドキュメントからヘッダーとフッターのブックマークを正常にエクスポートし、適切なブックマークを含む PDF を生成しました。

### Aspose.Words for .NET を使用してヘッダーとフッターのブックマークをエクスポートするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書から PDF 文書にヘッダーとフッターのブックマークをエクスポートする方法について説明しました。エクスポートされたブックマークを使用すると、生成された PDF 文書内の対応するヘッダーとフッターを簡単にナビゲートしてすばやく参照できます。説明されている手順に従って、文書からヘッダーとフッターのブックマークをエクスポートし、Aspose.Words for .NET を使用して適切なブックマークを含む PDF を生成します。文書への正しいパスを指定し、必要に応じて保存オプションを構成するようにしてください。

### よくある質問

### Q: Word 文書から PDF 文書にヘッダーとフッターのブックマークをエクスポートするとはどういうことですか?
A: Word 文書から PDF 文書にヘッダーとフッターのブックマークをエクスポートすると、元の Word 文書のヘッダーとフッターから PDF 文書にブックマークを保存および生成する機能です。これにより、ユーザーはヘッダーとフッターに対応するブックマークを使用して、PDF 文書内をすばやく簡単に移動できます。

### Q: Aspose.Words for .NET を使用して、Word 文書のヘッダーとフッターのブックマークを PDF 文書にエクスポートするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して Word 文書から PDF 文書にヘッダーとフッターのブックマークをエクスポートするには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

処理したい文書をロードします。`Document`クラスを作成し、指定されたドキュメント ディレクトリ内の Word ドキュメントへのパスを指定します。

 PDFとして保存オプションを設定するには、`PdfSaveOptions`クラスと適切なヘッダーおよびフッターのブックマーク オプションを設定します。

ドキュメントをPDF形式で保存するには、`Save`方法の`Document`パスと保存オプションを指定するクラス。

### Q: ヘッダーとフッターのブックマークを PDF ドキュメントにエクスポートする利点は何ですか?
A: ヘッダーとフッターのブックマークを PDF ドキュメントにエクスポートする利点は次のとおりです。

簡単なナビゲーション: ブックマークを使用すると、ユーザーは特定のヘッダーとフッターを参照して PDF ドキュメントを簡単にナビゲートできます。

クイック リファレンス: ブックマークを使用すると、ユーザーはヘッダーとフッターに基づいて PDF ドキュメントの関連セクションをすばやく見つけることができます。