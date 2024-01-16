---
title: 新しい署名行を作成し、プロバイダー ID を設定する
linktitle: 新しい署名行を作成し、プロバイダー ID を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成し、プロバイダー ID を設定する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
このチュートリアルでは、Aspose.Words for .NET で新しい署名行の作成とプロバイダー ID の設定機能を使用する手順を説明します。この機能を使用すると、Word 文書に署名行を挿入し、カスタム オプションを設定して文書に署名することができます。以下の手順に従います。

## ステップ 1: ドキュメントとジェネレーターの作成

まず、Document クラスのインスタンスと DocumentBuilder オブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 署名行オプションを設定する

SignatureLineOptions クラスのインスタンスを作成し、必要なオプションを設定します。

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## ステップ 3: 署名欄を挿入する

DocumentBuilder オブジェクトの InsertSignatureLine() メソッドを使用して、文書に署名行を挿入します。

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## ステップ 4: プロバイダー ID を設定する

ProviderId プロパティを使用して、署名行のプロバイダー ID を設定します。

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

使用例に応じて正しいプロバイダー ID を指定してください。

## ステップ 5: ドキュメントを保存する

変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

ドキュメントを保存するには、必ず正しいパスとファイル名を指定してください。

## ステップ 6: 文書に署名する

ドキュメントに署名するには、署名オプションを設定し、DigitalSignatureUtil クラスを使用する必要があります。

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

ドキュメント、証明書、署名済みドキュメントの正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用した新しい署名行の作成とプロバイダー ID の設定のソース コード例

新しい署名行を作成し、Aspose.Words for .NET でプロバイダー ID を設定するための完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

これらの手順に従うと、Aspose.Words for .NET を使用して、新しい署名欄を簡単に作成し、Word 文書にプロバイダー ID を設定できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成し、プロバイダー ID を設定する機能を検討しました。示されている手順に従うことで、カスタム オプションを含む署名行を簡単に挿入し、プロバイダー ID を使用して特定のプロバイダーに関連付けることができます。署名欄を追加し、プロバイダー情報をカスタマイズすると、文書の信頼性と信頼性が高まります。 Aspose.Words for .NET は、Word 文書の署名欄とデジタル証明書を備えた Word Processing 用の強力な API を提供し、署名プロセスを自動化し、文書の有効性を確保できます。

### よくある質問

#### Q: 署名欄のプロバイダー ID とは何ですか?

A: 署名行のプロバイダー ID は、デジタル署名のプロバイダーを表す一意の識別子です。これは、署名に責任のあるソースまたは組織を特定するのに役立ちます。

#### Q: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書に新しい署名欄を作成するには、次の手順に従います。
1. のインスタンスを作成します。`Document`クラスと`DocumentBuilder`物体。
2. のインスタンスを作成します。`SignatureLineOptions`クラスを開き、必要な署名行オプションを設定します。
3. 使用`InsertSignatureLine`の方法`DocumentBuilder`オブジェクトを使用して署名行を文書に挿入します。

#### Q: 署名者の名前、タイトル、指示などの署名行のオプションをカスタマイズできますか?

 A: はい、署名欄のオプションをカスタマイズできます。の`SignatureLineOptions`クラスは、必要なオプションを設定するためのプロパティを提供します。`Signer`, `SignerTitle`, `Instructions`, `AllowComments`、など。署名行を挿入する前に、これらのプロパティを変更できます。

#### Q: 署名行にプロバイダー ID を設定する目的は何ですか?

A: 署名欄にプロバイダー ID を設定すると、デジタル署名を担当するソースまたは組織を特定するのに役立ちます。これにより、署名を特定のプロバイダーまたはエンティティに関連付けることができ、署名の発行元と信頼性に関する追加情報が提供されます。

#### Q: Aspose.Words for .NET を使用して署名行のプロバイダー ID を設定するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して署名行のプロバイダー ID を設定するには、次の手順に従います。
1. 署名行を挿入した後、`ProviderId`の財産`SignatureLine`物体。
2. をセットする`ProviderId`を使用して、プロパティを目的のプロバイダー ID 値に設定します。`Guid`データ・タイプ。

#### Q: 新しい署名欄を作成し、プロバイダー ID を設定した後、文書に署名できますか?

 A: はい、新しい署名欄を作成し、プロバイダー ID を設定した後、ドキュメントに署名できます。ドキュメントに署名するには、署名行 ID、プロバイダー ID、コメント、署名時刻などの署名オプションを設定する必要があります。次に、`DigitalSignatureUtil.Sign`デジタル証明書を使用してドキュメントに署名する方法。

#### Q: Word 文書の署名行ごとに特定のプロバイダー ID を指定できますか?

A: はい、Word 文書の署名行ごとに特定のプロバイダー ID を指定できます。各署名行を挿入した後、`ProviderId`それぞれの財産`SignatureLine`物体。

#### Q: 新しい署名欄を作成し、プロバイダー ID を設定した後、変更した文書を保存するにはどうすればよいですか?

 A: 新しい署名欄を作成し、プロバイダー ID を設定した後で、変更した文書を保存するには、`Save`の方法`Document`物体。正しいパスとファイル名を指定してドキュメントを保存します。

#### Q: Aspose.Words for .NET は、署名行の作成と署名のためにどのようなファイル形式をサポートしていますか?

A: Aspose.Words for .NET は、DOCX ファイル形式での署名行の作成と署名をサポートしています。提供されたメソッドとクラスを使用して、DOCX ファイルに署名行を作成し、署名できます。

#### Q: 署名後に署名行のプロバイダー ID やその他のオプションを変更できますか?

A: 署名欄が署名されると、それは文書のコンテンツの一部となり、個別に変更することはできません。プロバイダー ID やその他のオプションの変更など、署名行を変更するには、既存の署名を削除し、新しい署名行を作成する必要があります。