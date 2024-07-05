---
title: 証明書ホルダーを使用してPDFにデジタル署名を追加する
linktitle: 証明書ホルダーを使用してPDFにデジタル署名を追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Certificate Holder を使用して PDF にデジタル署名を追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

このチュートリアルでは、Aspose.Words for .NET の証明書ホルダーを使用して PDF にデジタル署名を追加する手順を説明します。デジタル署名により、PDF ドキュメントにセキュリティと整合性の層が追加されます。以下の手順に従ってください。

## ステップ1: ドキュメントの作成とコンテンツの追加

まず、Document クラスのインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: ドキュメントにコンテンツを追加する

次に、`DocumentBuilder`文書にコンテンツを追加します。たとえば、「Test Signed PDF」というテキストを含む段落を追加するには、`Writeln`方法：

```csharp
builder.Writeln("Test Signed PDF.");
```

必要に応じて他のコンテンツ項目を追加できます。

## ステップ3: PDF保存オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、デジタル署名の詳細を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

証明書と関連するパスワードへの正しいパスを必ず指定してください。署名の理由と場所をカスタマイズすることもできます。

## ステップ4: 文書をデジタル署名されたPDFとして保存する

使用`Save`保存オプションを指定してドキュメントを PDF として保存する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

デジタル署名された PDF を保存するには、正しいパスを指定してください。

これらの手順に従うと、Aspose.Words for .NET を使用して、証明書付きのデジタル署名付き PDF を簡単に作成できます。

### Aspose.Words for .NET を使用した証明書ホルダーを使用したデジタル署名付き PDF のサンプル ソース コード

以下は、Aspose.Words for .NET を使用してドキュメントから証明書ホルダーを使用して PDF にデジタル署名するための完全なソース コードです。

```csharp

            //ドキュメント ディレクトリへのパス。
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## 結論

このチュートリアルでは、Aspose.Words for .NET で証明書を使用して PDF ドキュメントにデジタル署名を追加する手順について説明しました。デジタル署名はドキュメントにセキュリティと整合性の層を追加し、その信頼性を保証し、その後の変更を検出できるようにします。指定された手順に従うことで、Aspose.Words for .NET で証明書を使用してデジタル署名された PDF を簡単に作成できます。

### よくある質問

#### Q: デジタル署名とは何ですか? PDF 文書でデジタル署名が重要なのはなぜですか?
A: デジタル署名は、PDF ファイルなどの電子文書の信頼性、整合性、否認防止を保証するセキュリティ技術です。デジタル証明書を使用して文書にセキュリティ層を追加し、作成者の身元を確認し、その後のコンテンツの変更を検出するのに役立ちます。

#### Q: Aspose.Words for .NET で証明書を使用して PDF ドキュメントにデジタル署名を追加するにはどうすればよいですか?
A: Aspose.Words for .NET で証明書を使用して PDF ドキュメントにデジタル署名を追加するには、次の手順に従います。

インスタンスを作成する`Document`ドキュメントを表すクラス。

使用`DocumentBuilder`ドキュメントに必要なコンテンツを追加するクラスです。

インスタンスを作成する`PdfSaveOptions`クラスを作成し、デジタル署名の詳細を`PdfDigitalSignatureDetails`クラス。証明書へのパスを指定する必要があります（`CertificateHolder.Create`）、関連付けられているパスワード、署名の理由と場所が表示されます。

使用`Save`保存オプションを指定してドキュメントを PDF 形式で保存する方法。

#### Q: PDF ドキュメントにデジタル署名を追加するための証明書を取得するにはどうすればよいですか?
A: PDF ドキュメントにデジタル署名を追加するための証明書を取得するには、通常、証明機関 (CA) または信頼サービス プロバイダーに問い合わせます。これらの機関は、ユーザーの身元を確認し、要求を検証した後、デジタル証明書を発行します。証明書を取得したら、アプリケーションでその証明書を使用して PDF ドキュメントにデジタル署名を追加できます。

#### Q: デジタル署名の理由や場所などの詳細をカスタマイズすることは可能ですか?
 A: はい、署名の理由と場所を指定してデジタル署名の詳細をカスタマイズできます。提供されているサンプルコードでは、`reason`そして`location`作成時のパラメータ`PdfDigitalSignatureDetails`オブジェクト。PDF ドキュメント内の署名の理由と場所を反映するために、各パラメータに適切な情報を必ず提供してください。