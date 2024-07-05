---
title: 新しい署名欄の作成と署名
linktitle: 新しい署名欄の作成と署名
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成し、署名する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
このチュートリアルでは、Aspose.Words for .NET で新しい署名欄を作成して署名する機能を使用する手順を説明します。この機能を使用すると、Word 文書に署名欄を挿入し、カスタム オプションを設定して文書に署名することができます。以下の手順に従ってください。

## ステップ1: ドキュメントとジェネレーターの作成

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: 署名欄の挿入

DocumentBuilder オブジェクトの InsertSignatureLine() メソッドを使用して、ドキュメントに新しい署名行を挿入します。

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## ステップ3: ドキュメントを保存する

変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

ドキュメントを保存するには、正しいパスとファイル名を必ず指定してください。

## ステップ4: 文書に署名する

ドキュメントに署名するには、署名オプションを設定し、DigitalSignatureUtil クラスを使用する必要があります。

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

ドキュメント、署名行の画像、署名済みドキュメントの正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用して新しい署名欄を作成し、署名するためのサンプル ソース コード

Aspose.Words for .NET を使用して新しい署名行を作成し、署名するための完全なソース コードは次のとおりです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書に新しい署名欄を簡単に作成し、署名できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成し、署名する方法を学びました。提供されている手順に従うことで、文書に署名欄を簡単に挿入し、オプションをカスタマイズし、デジタル証明書を使用して文書に署名することができます。文書に署名欄とデジタル署名を追加すると、文書の信頼性と整合性が高まり、より安全で信頼できるものになります。Aspose.Words for .NET は、Word 文書の署名とデジタル証明書を使用した強力な Words Processing API を提供し、署名プロセスを自動化して文書の有効性を確保できます。

### よくある質問

#### Q: Word 文書の署名欄とは何ですか?

A: Word 文書の署名欄は、署名を配置する場所を示すプレースホルダーです。通常は、名前、肩書き、日付が含まれ、手書き署名またはデジタル署名用のスペースが提供されます。

#### Q: Aspose.Words for .NET を使用して Word 文書に署名欄を作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に署名欄を作成するには、次の手順に従います。
1. インスタンスを作成する`Document`クラスと`DocumentBuilder`物体。
2. 使用`InsertSignatureLine`方法の`DocumentBuilder`ドキュメントに新しい署名行を挿入するオブジェクト。
3. 変更したドキュメントを保存します。

#### Q: 名前、肩書き、日付などの署名行のオプションをカスタマイズできますか?

 A: はい、署名欄のオプションをカスタマイズできます。`SignatureLineOptions`クラスは、次のようなオプションを設定するためのプロパティを提供します。`Signer`, `SignerTitle`, `ShowDate`など。署名行を挿入する前にこれらのプロパティを変更できます。

#### Q: 署名欄を作成した後、文書に署名するにはどうすればよいですか?

 A: 署名欄を作成した後に文書に署名するには、署名オプションを設定し、`DigitalSignatureUtil`クラス。手順は次のとおりです。
1. をセットする`SignatureLineId`の財産`SignOptions`署名行の ID にオブジェクトを追加します。
2. をセットする`SignatureLineImage`の財産`SignOptions`使用したい署名の画像に異議を唱えます。
3. 署名証明書をロードするには、`CertificateHolder`クラス。
4. 使用`DigitalSignatureUtil.Sign`必要なパラメータを指定してドキュメントに署名する方法。

#### Q: 文書に署名するためにデジタル署名画像を使用できますか?

 A: はい、デジタル署名画像を使用して文書に署名することができます。これを行うには、画像ファイルを`SignOptions`オブジェクトを使用して`SignatureLineImage`プロパティ。画像は、JPEG、PNG、EMF など、サポートされている任意の画像形式にすることができます。

#### Q: Word 文書に新しい署名欄を作成して署名する目的は何ですか?

A: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成し、署名すると、署名用のプレースホルダーを追加し、デジタル証明書を使用して文書に署名できます。このプロセスにより、文書の信頼性と整合性が確保され、承認または同意の証拠が提供されます。

#### Q: Aspose.Words for .NET を使用して Word 文書に複数の署名行を作成して署名できますか?

A: はい、Aspose.Words for .NET を使用して、Word 文書に複数の署名行を作成し、署名することができます。署名行ごとに固有の ID とオプションを設定できます。この手順を繰り返して、文書に追加の署名行を作成し、署名することができます。

#### Q: 署名後に署名欄を変更したり、追加情報を追加したりすることはできますか?

A: 署名欄に署名すると、その署名欄は文書のコンテンツの一部となり、個別に変更することはできません。ただし、署名欄の後に情報やコンテンツを追加することは可能です。

#### Q: 署名行を含む文書のデジタル署名を検証できますか?

 A: はい、Aspose.Words for .NETには署名欄を含む文書のデジタル署名を検証する機能があります。`DigitalSignatureUtil.Verify`デジタル署名の有効性と信頼性を確認する方法。

#### Q: Aspose.Words for .NET は署名欄の作成と署名にどのようなファイル形式をサポートしていますか?

A: Aspose.Words for .NET は、DOCX ファイル形式での署名行の作成と署名をサポートしています。提供されているメソッドとクラスを使用して、DOCX ファイルに署名行を作成し、署名することができます。