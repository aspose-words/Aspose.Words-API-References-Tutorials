---
title: PDF ドキュメントのカスタム プロパティをエクスポートする
linktitle: PDF ドキュメントのカスタム プロパティをエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを PDF に変換するときにカスタム プロパティをエクスポートする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/custom-properties-export/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ドキュメントのカスタム プロパティを PDF ドキュメントにエクスポートする手順を説明します。カスタム プロパティをエクスポートすると、生成された PDF ドキュメントに追加情報を含めることができます。以下の手順に従ってください。

## ステップ 1: ドキュメントの作成とカスタム プロパティの追加

まず、Document クラスのインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ2: カスタムプロパティを追加する
次に、必要なカスタムプロパティを追加します。たとえば、「Aspose」という値を持つ「Company」プロパティを追加するには、`Add` CustomDocumentProperties コレクションのメソッド:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

必要に応じてカスタム プロパティをいくつでも追加できます。

## ステップ3: PDFエクスポートオプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、カスタム プロパティをエクスポートする方法を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

このオプションは、PDF に変換するときにカスタム プロパティのエクスポートを制御します。

## ステップ4: ドキュメントをPDFに変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

変換した PDF を保存するには、正しいパスを指定してください。

### Aspose.Words for .NET を使用したカスタム プロパティのエクスポートのサンプル ソース コード

Aspose.Words for .NET を使用してドキュメントからカスタム プロパティをエクスポートするための完全なソース コードは次のとおりです。


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

これらの手順に従うと、Aspose.Words for .NET を使用して PDF に変換するときに、ドキュメントのカスタム プロパティを簡単にエクスポートできます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、ドキュメントから PDF ドキュメントにカスタム プロパティをエクスポートする方法について説明しました。説明されている手順に従うと、ドキュメントのカスタム プロパティをエクスポートすることで、生成された PDF ドキュメントに追加情報を簡単に含めることができます。Aspose.Words for .NET の機能を活用して、カスタム プロパティをエクスポートすることで PDF ドキュメントをパーソナライズし、充実させることができます。

### よくある質問

#### Q: カスタム プロパティを PDF ドキュメントにエクスポートするとはどういうことですか?
A: カスタム プロパティを PDF ドキュメントにエクスポートすると、生成された PDF ドキュメントに追加情報を含めることができます。カスタム プロパティは、タグ、キーワード、資格情報など、ドキュメントに固有のメタデータです。これらのカスタム プロパティをエクスポートすると、PDF ドキュメントを表示するときにユーザーがそれらを利用できるようにすることができます。

#### Q: Aspose.Words for .NET を使用してドキュメントのカスタム プロパティを PDF ドキュメントにエクスポートするにはどうすればよいですか?
A: Aspose.Words for .NET を使用してドキュメントのカスタム プロパティを PDF ドキュメントにエクスポートするには、次の手順に従います。

インスタンスを作成する`Document`クラス。

必要なカスタムプロパティを追加するには、`CustomDocumentProperties`コレクション。たとえば、`Add`値「Aspose」を持つ「Company」プロパティを追加する方法。

インスタンスを作成する`PdfSaveOptions`クラスを作成し、カスタムプロパティをエクスポートする方法を指定します。`CustomPropertiesExport`プロパティ。`PdfCustomPropertiesExport.Standard`値はデフォルト設定に従ってカスタム プロパティをエクスポートします。

使用`Save`方法の`Document`変換オプションを指定してドキュメントを PDF に変換するクラス。

#### Q: PDF ドキュメントのカスタム プロパティにアクセスするにはどうすればよいですか?
A: PDF ドキュメントのカスタム プロパティにアクセスするには、ドキュメント プロパティの表示をサポートする互換性のある PDF リーダーを使用できます。Adobe Acrobat Reader などの一般的な PDF リーダーのほとんどは、PDF ドキュメントのメタデータとプロパティへのアクセスを提供します。通常、これらのオプションは [ファイル] メニューの下、またはドキュメントを右クリックして [プロパティ] を選択することで見つかります。