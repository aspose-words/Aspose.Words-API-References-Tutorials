---
title: 証明書所有者を使用して PDF にデジタル署名を追加する
linktitle: 証明書所有者を使用して PDF にデジタル署名を追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で証明書ホルダーを使用して PDF にデジタル署名を追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

このチュートリアルでは、Aspose.Words for .NET で証明書ホルダーを使用して PDF にデジタル署名を追加する手順を説明します。デジタル署名により、PDF ドキュメントにセキュリティと整合性の層が追加されます。以下の手順に従います。

## ステップ 1: ドキュメントの作成とコンテンツの追加

まず、Document クラスのインスタンスを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ドキュメントにコンテンツを追加する

次に、`DocumentBuilder`ドキュメントにコンテンツを追加します。たとえば、「テスト署名済み PDF」というテキストを含む段落を追加するには、`Writeln`方法：

```csharp
builder.Writeln("Test Signed PDF.");
```

必要に応じて、他のコンテンツ項目を追加できます。

## ステップ 3: PDF 保存オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、デジタル署名の詳細を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

証明書への正しいパスと関連するパスワードを必ず指定してください。署名の理由と場所をカスタマイズすることもできます。

## ステップ 4: ドキュメントをデジタル署名付き PDF として保存する

使用`Save`保存オプションを指定してドキュメントを PDF として保存するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

デジタル署名された PDF を保存するための正しいパスを指定してください。

次の手順に従うと、Aspose.Words for .NET を使用して、証明書付きのデジタル署名された PDF を簡単に作成できます。

### Aspose.Words for .NET を使用した証明書ホルダーを使用したデジタル署名付き PDF のソース コードの例

Aspose.Words for .NET を使用してドキュメントの証明書所有者を使用してデジタル署名された PDF への完全なソース コードを次に示します。

```csharp

            //ドキュメントディレクトリへのパス。
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

このチュートリアルでは、Aspose.Words for .NET の証明書を使用して PDF ドキュメントにデジタル署名を追加する手順を説明しました。デジタル署名はドキュメントにセキュリティと完全性の層を追加するため、ドキュメントの信頼性が保証され、その後の変更を検出できるようになります。指定された手順に従うことで、Aspose.Words for .NET の証明書を使用してデジタル署名された PDF を簡単に作成できます。

### よくある質問

#### Q: デジタル署名とは何ですか? PDF ドキュメントでデジタル署名が重要なのはなぜですか?
A: デジタル署名は、PDF ファイルなどの電子ドキュメントの信頼性、完全性、および否認防止を保証するのに役立つセキュリティ技術です。デジタル証明書を使用してドキュメントにセキュリティ層を追加します。これにより、作成者の身元を確認し、コンテンツに対するその後の変更を検出できます。

#### Q: Aspose.Words for .NET の証明書を使用して PDF ドキュメントにデジタル署名を追加するにはどうすればよいですか?
A: Aspose.Words for .NET の証明書を使用して PDF ドキュメントにデジタル署名を追加するには、次の手順に従います。

のインスタンスを作成します。`Document`ドキュメントを表すクラス。

使用`DocumentBuilder`クラスを使用して、必要なコンテンツをドキュメントに追加します。

のインスタンスを作成します。`PdfSaveOptions`クラスを作成し、次のコマンドを使用してデジタル署名の詳細を指定します。`PdfDigitalSignatureDetails`クラス。証明書へのパスを指定する必要があります (`CertificateHolder.Create`)、関連するパスワード、署名の理由と場所。

使用`Save`保存オプションを指定してドキュメントを PDF 形式で保存するメソッド。

#### Q: PDF ドキュメントにデジタル署名を追加するための証明書を取得するにはどうすればよいですか?
A: PDF ドキュメントにデジタル署名を追加するための証明書を取得するには、通常、認証局 (CA) または信頼できるサービス プロバイダーに問い合わせることができます。これらのエンティティは、ユーザーの身元を確認し、リクエストを検証した後、デジタル証明書を発行します。証明書を取得したら、アプリケーションでそれを使用して PDF ドキュメントにデジタル署名を追加できます。

#### Q: デジタル署名の理由や場所などの詳細をカスタマイズすることはできますか?
 A: はい、署名の理由と場所を指定することで、デジタル署名の詳細をカスタマイズできます。提供されているサンプル コードでは、`reason`そして`location`作成時のパラメータ`PdfDigitalSignatureDetails`物体。 PDF ドキュメント内の署名の理由と場所を反映するために、各パラメータに適切な情報を必ず指定してください。