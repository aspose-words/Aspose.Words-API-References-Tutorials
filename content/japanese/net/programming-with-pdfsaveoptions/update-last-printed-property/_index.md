---
title: PDF ドキュメントの最終印刷プロパティを更新する
linktitle: PDF ドキュメントの最終印刷プロパティを更新する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに、「最終印刷」プロパティを更新するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

この記事では、Aspose.Words for .NET の PDF ドキュメント更新機能で「最終印刷」プロパティを使用する方法について、ステップ バイ ステップ ガイドを提供します。コードの各部分を詳しく説明します。このチュートリアルの最後には、PDF に変換するときに「最終印刷」プロパティを更新するオプションを構成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントをアップロードする

次に、処理するドキュメントを読み込む必要があります。この例では、ドキュメントの名前は「Rendering.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 3: 更新された「最終印刷」プロパティを使用して PDF として保存オプションを構成する

PDFに変換するときに「最終印刷」プロパティを更新できるようにするには、`PdfSaveOptions`オブジェクトを設定し、`UpdateLastPrintedProperty`財産に`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## ステップ4: 「最終印刷」プロパティを更新してドキュメントをPDFとして保存します

最後に、以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

以上です。Aspose.Words for .NET を使用してドキュメントを PDF に変換するときに、「最終印刷」プロパティの更新を有効にできるようになりました。

### Aspose.Words for .NET で「最終印刷」プロパティを更新するためのサンプル ソース コード


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントの「最終印刷」プロパティを更新する方法について説明しました。指定された手順に従うことで、ドキュメントを PDF に変換するときに「最終印刷」プロパティを更新するオプションを簡単に構成できます。この機能を使用して、ドキュメントの使用状況と関連情報を追跡します。

### よくある質問

#### Q: PDF ドキュメントの「最終印刷」プロパティとは何ですか?
A: PDF ドキュメントの「最終印刷」プロパティは、ドキュメントが最後に印刷された日時を指します。このプロパティは、ドキュメントの使用状況と管理に関する情報を追跡するのに役立ちます。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントの「最終印刷」プロパティを更新するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントの「最終印刷」プロパティを更新するには、次の手順に従います。

インスタンスを作成する`Document` Word 文書へのパスを指定するクラス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`UpdateLastPrintedProperty`財産に`true` 「最終印刷」プロパティの更新を有効にします。

使用`Save`方法の`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: 生成された PDF ドキュメントで「最終印刷」プロパティが更新されたかどうかを確認するにはどうすればよいですか?
A: Adobe Acrobat Reader などの互換性のある PDF ビューアで PDF ファイルを開き、ドキュメント情報を表示することで、生成された PDF ドキュメントの「最終印刷」プロパティが更新されているかどうかを確認できます。最終印刷の日時は、PDF ドキュメントの生成日時と一致している必要があります。
