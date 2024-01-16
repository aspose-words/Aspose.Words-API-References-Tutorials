---
title: 新しい署名欄の作成と署名
linktitle: 新しい署名欄の作成と署名
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成して署名する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
このチュートリアルでは、Aspose.Words for .NET を使用して新しい署名欄を作成して署名する機能を使用する手順を説明します。この機能を使用すると、Word 文書に署名行を挿入し、カスタム オプションを設定して文書に署名することができます。以下の手順に従います。

## ステップ 1: ドキュメントとジェネレーターの作成

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 署名欄を挿入する

DocumentBuilder オブジェクトの InsertSignatureLine() メソッドを使用して、新しい署名欄を文書に挿入します。

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## ステップ 3: ドキュメントを保存する

変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

ドキュメントを保存するには、必ず正しいパスとファイル名を指定してください。

## ステップ 4: 文書に署名する

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

文書、署名欄の画像、署名済み文書の正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用して新しい署名行を作成および署名するためのソース コードの例

Aspose.Words for .NET を使用して新しい署名欄を作成して署名するための完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
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

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書に新しい署名欄を簡単に作成して署名できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成し、署名する方法を学びました。示されている手順に従うことで、文書に署名行を挿入し、そのオプションをカスタマイズし、デジタル証明書を使用して文書に署名することが簡単にできます。文書に署名欄とデジタル署名を追加すると、文書の信頼性と完全性が強化され、文書の安全性と信頼性が高まります。 Aspose.Words for .NET は、Word 文書の署名とデジタル証明書を備えた Word Processing 用の強力な API を提供し、署名プロセスを自動化し、文書の有効性を確保できます。

### よくある質問

#### Q: Word 文書の署名欄とは何ですか?

A: Word 文書の署名行は、署名を配置する場所を示すプレースホルダーです。通常、名前、タイトル、日付が含まれ、手書きまたはデジタル署名のためのスペースが提供されます。

#### Q: Aspose.Words for .NET を使用して Word 文書に署名欄を作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に署名欄を作成するには、次の手順に従います。
1. のインスタンスを作成します。`Document`クラスと`DocumentBuilder`物体。
2. 使用`InsertSignatureLine`の方法`DocumentBuilder`オブジェクトを使用して、文書に新しい署名行を挿入します。
3. 変更したドキュメントを保存します。

#### Q: 名前、タイトル、日付などの署名欄のオプションをカスタマイズできますか?

 A: はい、署名欄のオプションをカスタマイズできます。の`SignatureLineOptions`クラスは、必要なオプションを設定するためのプロパティを提供します。`Signer`, `SignerTitle`, `ShowDate`、など。署名行を挿入する前に、これらのプロパティを変更できます。

#### Q: 署名欄を作成した後、文書に署名するにはどうすればよいですか?

 A: 署名欄を作成した後に文書に署名するには、署名オプションを設定し、`DigitalSignatureUtil`クラス。手順は次のとおりです。
1. をセットする`SignatureLineId`のプロパティ`SignOptions`オブジェクトを署名行の ID に設定します。
2. をセットする`SignatureLineImage`のプロパティ`SignOptions`使用したい署名の画像に反対します。
3. 次のコマンドを使用して署名証明書をロードします。`CertificateHolder`クラス。
4. 使用`DigitalSignatureUtil.Sign`必要なパラメータを指定してドキュメントに署名するメソッド。

#### Q: デジタル署名画像を使用してドキュメントに署名できますか?

 A: はい、デジタル署名画像を使用してドキュメントに署名できます。これを行うには、画像ファイルを`SignOptions`を使用したオブジェクト`SignatureLineImage`財産。画像は、JPEG、PNG、EMF など、サポートされている任意の画像形式にすることができます。

#### Q: Word 文書に新しい署名欄を作成して署名する目的は何ですか?

A: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成して署名すると、署名用のプレースホルダーを追加し、デジタル証明書を使用して文書に署名できます。このプロセスにより、文書の信頼性と完全性が保証され、承認または同意の証拠が提供されます。

#### Q: Aspose.Words for .NET を使用して、Word 文書内に複数の署名行を作成して署名できますか?

A: はい、Aspose.Words for .NET を使用して、Word 文書内に複数の署名行を作成して署名できます。各署名行には、独自の一意の ID とオプションを含めることができます。この手順を繰り返して、文書内に追加の署名行を作成して署名することができます。

#### Q: 署名後に署名欄を変更したり、追加情報を追加したりすることはできますか?

A: 署名欄が署名されると、それは文書のコンテンツの一部となり、個別に変更することはできません。ただし、署名済みの署名行の後に追加の情報やコンテンツを追加できます。

#### Q: 署名欄を含む文書のデジタル署名を検証できますか?

 A: はい、Aspose.Words for .NET は、署名行を含むドキュメントのデジタル署名を検証する機能を提供します。使用できます`DigitalSignatureUtil.Verify`デジタル署名の有効性と信頼性を確認する方法。

#### Q: Aspose.Words for .NET は、署名行の作成と署名のためにどのようなファイル形式をサポートしていますか?

A: Aspose.Words for .NET は、DOCX ファイル形式での署名行の作成と署名をサポートしています。提供されたメソッドとクラスを使用して、DOCX ファイルに署名行を作成し、署名できます。