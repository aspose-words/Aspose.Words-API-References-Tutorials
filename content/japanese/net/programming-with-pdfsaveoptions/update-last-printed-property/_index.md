---
title: PDF ドキュメントの最終印刷プロパティを更新する
linktitle: PDF ドキュメントの最終印刷プロパティを更新する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに「最終印刷」プロパティを更新するためのステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

この記事では、Aspose.Words for .NET で PDF ドキュメント更新機能の「最終印刷」プロパティを使用する方法について、ステップバイステップのガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルの最後では、PDF に変換するときに「最終印刷」プロパティを更新するオプションを構成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする

次に、処理するドキュメントをロードする必要があります。この例では、ドキュメントが「Rendering.docx」という名前で、指定されたドキュメント ディレクトリに配置されていると仮定します。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 3: 更新された「最終印刷日」プロパティを使用して PDF として保存オプションを構成する

PDF への変換時に「最終印刷」プロパティの更新を有効にするには、`PdfSaveOptions`オブジェクトを設定して、`UpdateLastPrintedProperty`財産を`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## ステップ 4: 「最終印刷」プロパティを更新してドキュメントを PDF として保存する

最後に、前に設定した保存オプションを使用してドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

それだけです ！ Aspose.Words for .NET を使用してドキュメントを PDF に変換するときに、「最終印刷」プロパティの更新が正常に有効になりました。

### Aspose.Words for .NET を使用して「最終印刷」プロパティを更新するためのソース コードの例


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントの「最終印刷」プロパティを更新する方法を説明しました。指定された手順に従うことで、ドキュメントを PDF に変換するときに「最終印刷」プロパティを更新するオプションを簡単に設定できます。この機能を使用して、ドキュメントの使用状況と関連情報を追跡します。

### よくある質問

#### Q: PDF ドキュメントの「最終印刷」プロパティとは何ですか?
A: PDF ドキュメントの「最終印刷」プロパティは、ドキュメントが最後に印刷された日時を指します。このプロパティは、ドキュメントの使用と管理に関する情報を追跡するのに役立ちます。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントの「最終印刷日」プロパティを更新するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントの「最終印刷日」プロパティを更新するには、次の手順に従います。

のインスタンスを作成します。`Document` Word ドキュメントへのパスを指定するクラス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`UpdateLastPrintedProperty`財産を`true` 「最終印刷」プロパティの更新を有効にします。

使用`Save`の方法`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: 生成された PDF ドキュメントの「最終印刷日」プロパティが更新されたかどうかを確認するにはどうすればよいですか?
A: Adobe Acrobat Reader などの互換性のある PDF ビューアで PDF ファイルを開いてドキュメント情報を表示することで、生成された PDF ドキュメントの「最終印刷」プロパティが更新されたかどうかを確認できます。最終印刷の日時は、PDF ドキュメントの生成日時と一致している必要があります。
