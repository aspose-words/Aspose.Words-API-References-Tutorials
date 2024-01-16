---
title: Word 文書に署名プロバイダー ID を設定する
linktitle: Word 文書に署名プロバイダー ID を設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に署名プロバイダー ID を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/set-signature-provider-id/
---
このチュートリアルでは、Aspose.Words for .NET で署名プロバイダー ID の設定機能を使用する手順を説明します。この機能を使用すると、Word 文書の署名行に署名プロバイダー ID を指定できます。以下の手順に従います。

## ステップ 1: 文書をロードして署名欄にアクセスする

まず、署名欄を含む文書をアップロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## ステップ 2: 署名オプションを設定する

SignOptions クラスのインスタンスを作成し、プロバイダー ID を含む署名オプションを設定します。

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## ステップ 3: 文書に署名する

ドキュメントに署名するには、DigitalSignatureUtil クラスを使用し、署名証明書を指定する必要があります。

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

ドキュメント、証明書、署名済みドキュメントの正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用した署名プロバイダー ID の設定のソース コード例

Aspose.Words for .NET で署名プロバイダー ID を設定する完全なソース コードは次のとおりです。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Aspose.Words for .NET を使用して、Word 文書内の署名プロバイダー ID を完成させます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の署名行に署名プロバイダー ID を設定する方法を学習しました。表示された手順に従うことで、ドキュメントのロード、署名欄へのアクセス、プロバイダー ID の設定、ドキュメントへの署名を簡単に行うことができます。署名プロバイダー ID を設定できる機能は、署名者の身元と信頼性を確立するのに役立ち、Word 文書のセキュリティと整合性を強化します。 Aspose.Words for .NET は、デジタル署名を備えた Words Processing 用の堅牢な API を提供し、署名プロセスを簡単にカスタマイズおよび管理できるようにします。

### Word 文書での署名プロバイダー ID の設定に関する FAQ

#### Q: Word 文書の署名プロバイダー ID とは何ですか?

A: Word 文書の署名プロバイダー ID は、デジタル署名のプロバイダーを指定する一意の識別子です。これは、デジタル署名の作成と管理を担当するエンティティまたは組織を特定するのに役立ちます。

#### Q: Aspose.Words for .NET を使用して Word 文書の署名行に署名プロバイダー ID を設定するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書の署名行の署名プロバイダー ID を設定するには、次の手順を実行できます。
1. を使用してドキュメントをロードします。`Document`クラスを作成し、ドキュメント ファイルへのパスを指定します。
2. 適切なメソッドまたはプロパティを使用して署名行にアクセスします。たとえば、次のように使用できます`GetChild`署名線の形状を取得するメソッド。
3. 署名行からプロバイダー ID を取得します。
4. のインスタンスを作成します。`SignOptions`クラスを設定して、`ProviderId`プロパティを取得したプロバイダー ID に設定します。
5. 使用`DigitalSignatureUtil.Sign`ドキュメントに署名するためのメソッド。`SignOptions`物体。

#### Q: Aspose.Words for .NET を使用して Word 文書の署名行にアクセスするにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書内の署名欄にアクセスするには、適切なメソッドまたはプロパティを使用して文書の構造から署名欄の形状を取得できます。たとえば、次のように使用できます。`GetChild`メソッドを適切なパラメータで使用して、必要な署名線の形状を取得します。

#### Q: Word 文書内の複数の署名行に署名プロバイダー ID を設定できますか?

 A: はい、Word 文書内の複数の署名行に署名プロバイダー ID を設定できます。ドキュメント内の署名行のコレクションを繰り返し処理し、各署名行のプロバイダー ID を個別に設定できます。`SignOptions.ProviderId`財産。

#### Q: Word 文書内の署名プロバイダー ID の目的は何ですか?

A: Word 文書内の署名プロバイダー ID は、デジタル署名の作成と管理を担当するエンティティまたは組織を識別する目的で使用されます。デジタル署名を特定のプロバイダーに関連付けることにより、デジタル署名の信頼性と信頼性を確立するのに役立ちます。

#### Q: Word 文書で署名プロバイダー ID を設定するために使用できるデジタル証明書の種類は何ですか?

A: 適切なプロバイダー情報を持つ X.509 デジタル証明書を使用して、Word 文書に署名プロバイダー ID を設定できます。デジタル証明書は信頼できる認証局 (CA) によって発行され、プロバイダーを識別するために必要なメタデータが含まれている必要があります。