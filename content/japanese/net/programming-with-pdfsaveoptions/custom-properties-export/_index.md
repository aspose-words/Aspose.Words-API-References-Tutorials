---
title: PDF ドキュメントのカスタム プロパティをエクスポートする
linktitle: PDF ドキュメントのカスタム プロパティをエクスポートする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを PDF に変換するときにカスタム プロパティをエクスポートする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/custom-properties-export/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ドキュメントのカスタム プロパティを PDF ドキュメントにエクスポートする手順を説明します。カスタム プロパティをエクスポートすると、生成された PDF ドキュメントに追加情報を含めることができます。以下の手順に従います。

## ステップ 1: ドキュメントの作成とカスタム プロパティの追加

まず、Document クラスのインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ 2: カスタム プロパティを追加する
次に、必要なカスタム プロパティを追加します。たとえば、値「Aspose」を持つ「Company」プロパティを追加するには、`Add` CustomDocumentProperties コレクションのメソッド:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

カスタム プロパティは必要なだけ追加できます。

## ステップ 3: PDF エクスポート オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、カスタム プロパティをエクスポートする方法を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

このオプションは、PDF への変換時のカスタム プロパティのエクスポートを制御します。

## ステップ 4: ドキュメントを PDF に変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用したカスタム プロパティ エクスポートのソース コード例

Aspose.Words for .NET を使用してドキュメントからカスタム プロパティをエクスポートするための完全なソース コードを次に示します。


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

これらの手順に従うことで、Aspose.Words for .NET を使用して PDF に変換するときにドキュメントのカスタム プロパティを簡単にエクスポートできます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してカスタム プロパティをドキュメントから PDF ドキュメントにエクスポートする方法を説明しました。説明されている手順に従って、ドキュメントのカスタム プロパティをエクスポートすることで、生成された PDF ドキュメントに追加情報を簡単に含めることができます。 Aspose.Words for .NET の機能を利用して、カスタム プロパティをエクスポートして PDF ドキュメントをカスタマイズし、内容を充実させます。

### よくある質問

#### Q: カスタム プロパティを PDF ドキュメントにエクスポートとは何ですか?
A: カスタム プロパティを PDF ドキュメントにエクスポートすると、生成された PDF ドキュメントに追加情報を含めることができます。カスタム プロパティは、タグ、キーワード、資格情報など、ドキュメントに固有のメタデータです。これらのカスタム プロパティをエクスポートすると、ユーザーが PDF ドキュメントを表示するときにそれらのプロパティを利用できるようになります。

#### Q: Aspose.Words for .NET を使用してドキュメントのカスタム プロパティを PDF ドキュメントにエクスポートするにはどうすればよいですか?
A: Aspose.Words for .NET を使用してドキュメントのカスタム プロパティを PDF ドキュメントにエクスポートするには、次の手順に従います。

のインスタンスを作成します。`Document`クラス。

を使用して、必要なカスタム プロパティを追加します。`CustomDocumentProperties`コレクション。たとえば、`Add`メソッドを使用して、値「Aspose」を持つ「Company」プロパティを追加します。

のインスタンスを作成します。`PdfSaveOptions`クラスを作成し、カスタム プロパティをエクスポートする方法を指定します。`CustomPropertiesExport`財産。の`PdfCustomPropertiesExport.Standard`value は、デフォルト設定に従ってカスタム プロパティをエクスポートします。

使用`Save`の方法`Document`変換オプションを指定してドキュメントを PDF に変換するクラス。

#### Q: PDF ドキュメントのカスタム プロパティにアクセスするにはどうすればよいですか?
A: PDF ドキュメントのカスタム プロパティにアクセスするには、ドキュメント プロパティの表示をサポートする互換性のある PDF リーダーを使用できます。 Adobe Acrobat Reader などの最も一般的な PDF リーダーは、PDF ドキュメントのメタデータとプロパティへのアクセスを提供します。これらのオプションは通常、[ファイル] メニューにあるか、ドキュメントを右クリックして [プロパティ] を選択することで見つけることができます。