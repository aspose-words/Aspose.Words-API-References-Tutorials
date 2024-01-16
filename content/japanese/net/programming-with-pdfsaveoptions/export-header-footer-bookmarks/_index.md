---
title: Word ドキュメントのヘッダー フッターのブックマークを PDF ドキュメントにエクスポート
linktitle: Word ドキュメントのヘッダー フッターのブックマークを PDF ドキュメントにエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントのヘッダー フッター ブックマークを PDF ドキュメントのブックマークにエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

この記事では、Aspose.Words for .NET を使用して Word ドキュメントのヘッダー フッターのブックマークを PDF ドキュメント機能にエクスポートする方法に関するステップバイステップのガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、ドキュメントのヘッダーとフッターからブックマークをエクスポートし、適切なブックマークを含む PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする

次に、処理するドキュメントをロードする必要があります。この例では、ドキュメントの名前が「ヘッダーおよびフッターのブックマーク.docx」であり、指定されたドキュメント ディレクトリにあると仮定します。

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## ステップ 3: PDF として保存オプションを構成する

ヘッダーとフッターのブックマークをエクスポートするには、`PdfSaveOptions`物体。この例では、デフォルトのブックマークのアウトライン レベルを 1 に設定し、ヘッダーとフッターのブックマークのエクスポート モードを「最初」に設定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## ステップ 4: ヘッダーとフッターのブックマークを付けてドキュメントを PDF として保存する

最後に、前に設定した保存オプションを使用してドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

それだけです ！ Aspose.Words for .NET を使用して、ドキュメントからヘッダーとフッターのブックマークを正常にエクスポートし、適切なブックマークを含む PDF を生成しました。

### Aspose.Words for .NET を使用してヘッダーとフッターのブックマークをエクスポートするためのサンプル ソース コード

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、Word ドキュメントから PDF ドキュメントにヘッダーとフッターのブックマークをエクスポートする方法を説明しました。エクスポートされたブックマークにより、生成された PDF ドキュメント内の対応するヘッダーとフッターへの簡単なナビゲーションとクイック参照が可能になります。説明されている手順に従って、Aspose.Words for .NET を使用してドキュメントからヘッダーとフッターのブックマークをエクスポートし、適切なブックマークを含む PDF を生成します。必ずドキュメントへの正しいパスを指定し、必要に応じて保存オプションを構成してください。

### よくある質問

### Q: Word 文書から PDF 文書へのヘッダーとフッターのブックマークのエクスポートとは何ですか?
A: Word 文書から PDF 文書へのヘッダーおよびフッターのブックマークのエクスポートは、ヘッダーおよびフッターから PDF 文書内のブックマークを保持および生成する機能です。元の Word 文書のフッター。これにより、ユーザーはヘッダーとフッターに対応するブックマークを使用して、PDF ドキュメント内を迅速かつ簡単に移動できるようになります。

### Q: Aspose.Words for .NET を使用して、ヘッダーとフッターのブックマークを Word 文書から PDF 文書にエクスポートするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して、ヘッダーとフッターのブックマークを Word 文書から PDF 文書にエクスポートするには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

を使用して、処理するドキュメントをロードします。`Document`クラスを指定し、指定したドキュメント ディレクトリ内の Word ドキュメントへのパスを指定します。

のインスタンスを作成して、PDF として保存オプションを構成します。`PdfSaveOptions`クラスを変更し、適切なヘッダーとフッターのブックマーク オプションを設定します。

ドキュメントを PDF 形式で保存するには、`Save`の方法`Document`パスと保存オプションを指定するクラス。

### Q: ヘッダーとフッターのブックマークを PDF ドキュメントにエクスポートすると、どのような利点がありますか?
A: ヘッダーとフッターのブックマークを PDF ドキュメントにエクスポートする利点は次のとおりです。

簡単なナビゲーション: ブックマークを使用すると、ユーザーは特定のヘッダーとフッターを参照して PDF ドキュメント内を簡単に移動できます。

クイック リファレンス: ブックマークを使用すると、ユーザーはヘッダーとフッターに基づいて PDF ドキュメントの関連セクションをすばやく見つけることができます。