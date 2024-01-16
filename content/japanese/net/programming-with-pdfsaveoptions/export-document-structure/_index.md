---
title: Word ドキュメント構造を PDF ドキュメントにエクスポート
linktitle: Word ドキュメント構造を PDF ドキュメントにエクスポート
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメント構造を PDF ドキュメントにエクスポートするためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/export-document-structure/
---

この記事では、Aspose.Words for .NET で Word ドキュメント構造を PDF ドキュメントにエクスポート機能を使用する方法をステップごとに説明します。コードの各部分について詳しく説明します。このチュートリアルを終えると、ドキュメントの構造をエクスポートし、ドキュメントの構造が表示された PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする

次に、処理するドキュメントをロードする必要があります。この例では、ドキュメントが「Paragraphs.docx」という名前で、指定されたドキュメント ディレクトリに配置されていると仮定します。

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## ステップ 3: PDF として保存オプションを構成する

ドキュメント構造をエクスポートし、PDF ファイルの編集中に Adobe Acrobat Pro の「コンテンツ」ナビゲーション ペインにその構造が表示されるようにするには、`PdfSaveOptions`オブジェクトを使用して`ExportDocumentStructure`に設定されたプロパティ`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## ステップ 4: 文書構造を含む PDF として文書を保存する

最後に、前に設定した保存オプションを使用してドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

それだけです ！ Aspose.Words for .NET を使用して、ドキュメント構造が正常にエクスポートされ、ドキュメント構造が表示される PDF が生成されました。

### Aspose.Words for .NET を使用してドキュメント構造をエクスポートするためのサンプル ソース コード


```csharp

            //ドキュメントディレクトリへのパス。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            //ファイル サイズが大きくなり、その構造が [コンテンツ] ナビゲーション ペインに表示されます。
            // .pdf の編集中に Adobe Acrobat Pro を実行します。
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word ドキュメントの構造を PDF ドキュメントにエクスポートする方法を説明しました。概要を説明した手順に従うことで、文書構造が表示された PDF を簡単に生成でき、文書内の移動や検索が容易になります。 Aspose.Words for .NET の機能を使用して、Word 文書の構造をエクスポートし、適切に構造化された PDF を作成します。

### よくある質問

#### Q: Word 文書の構造を PDF 文書にエクスポートするとは何ですか?
A: Word 文書の構造を PDF 文書にエクスポートすると、表示可能な文書構造を持つ PDF が作成されます。文書構造には、通常、文書の見出し、セクション、段落、その他の構造化された要素などが含まれます。この構造は、PDF ドキュメント内のナビゲーションや検索に役立ちます。

#### Q: Aspose.Words for .NET を使用して Word ドキュメントの構造を PDF ドキュメントにエクスポートするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して Word ドキュメントの構造を PDF ドキュメントにエクスポートするには、次の手順に従います。

のインスタンスを作成します。`Document` Word ドキュメントへのパスを指定するクラス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`ExportDocumentStructure`財産を`true`。これにより、ドキュメント構造がエクスポートされ、PDF ファイルの編集時に Adobe Acrobat Pro の「コンテンツ」ナビゲーション ペインに表示されるようになります。

使用`Save`の方法`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: Adobe Acrobat Pro で PDF ドキュメントの構造を表示するにはどうすればよいですか?
A: Adobe Acrobat Pro を使用して PDF ドキュメントの構造を表示するには、次の手順に従います。

Adobe Acrobat Pro で PDF ドキュメントを開きます。

左側のナビゲーション バーで、[コンテンツ] アイコンをクリックして、[コンテンツ] ナビゲーション ペインを表示します。

「コンテンツ」ナビゲーション ペインには、見出し、セクション、その他の構造化要素を含むドキュメント構造が表示されます。