---
title: Word 文書の構造を PDF 文書にエクスポートする
linktitle: Word 文書の構造を PDF 文書にエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書構造を PDF 文書にエクスポートするためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/export-document-structure/
---

この記事では、Aspose.Words for .NET の Word 文書構造を PDF 文書にエクスポートする機能を使用する方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、文書の構造をエクスポートし、文書の構造が表示された PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントをアップロードする

次に、処理するドキュメントを読み込む必要があります。この例では、ドキュメントの名前が「Paragraphs.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## ステップ3: PDFとして保存オプションを設定する

文書構造をエクスポートし、PDFファイルの編集中にAdobe Acrobat Proの「コンテンツ」ナビゲーションパネルに構造を表示するには、`PdfSaveOptions`オブジェクト`ExportDocumentStructure`プロパティが設定されている`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## ステップ4: 文書構造をPDFとして保存する

最後に、以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

これで完了です。Aspose.Words for .NET を使用してドキュメント構造を正常にエクスポートし、ドキュメント構造が表示された PDF を生成しました。

### Aspose.Words for .NET を使用してドキュメント構造をエクスポートするためのサンプル ソース コード


```csharp

            //ドキュメント ディレクトリへのパス。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            //ファイルサイズが大きくなり、構造が「コンテンツ」ナビゲーションパネルに表示されます。
            // Adobe Acrobat Pro を使用して .pdf を編集します。
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の構造を PDF 文書にエクスポートする方法について説明しました。説明されている手順に従うことで、文書構造を表示した PDF を簡単に生成でき、文書内の移動や検索が簡単になります。Aspose.Words for .NET の機能を使用して Word 文書の構造をエクスポートし、適切に構造化された PDF を作成します。

### よくある質問

#### Q: Word 文書の構造を PDF 文書にエクスポートするとはどういうことですか?
A: Word 文書の構造を PDF 文書にエクスポートすると、目に見える文書構造を持つ PDF が作成されます。文書構造には通常、見出し、セクション、段落、および文書のその他の構造化要素などが含まれます。この構造は、PDF 文書内のナビゲーションや検索に役立ちます。

#### Q: Aspose.Words for .NET を使用して Word 文書の構造を PDF 文書にエクスポートするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して Word 文書の構造を PDF 文書にエクスポートするには、次の手順に従います。

インスタンスを作成する`Document` Word 文書へのパスを指定するクラス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`ExportDocumentStructure`財産に`true`これにより、ドキュメント構造がエクスポートされ、PDF ファイルを編集するときに Adobe Acrobat Pro の「コンテンツ」ナビゲーション ペインに表示されるようになります。

使用`Save`方法の`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: Adobe Acrobat Pro で PDF ドキュメントの構造を表示するにはどうすればいいですか?
A: Adobe Acrobat Pro を使用して PDF ドキュメントの構造を表示するには、次の手順に従います。

Adobe Acrobat Pro で PDF ドキュメントを開きます。

左側のナビゲーション バーで、[コンテンツ] アイコンをクリックして、[コンテンツ] ナビゲーション ペインを表示します。

「コンテンツ」ナビゲーション ペインには、見出し、セクション、その他の構造化された要素を含むドキュメント構造が表示されます。