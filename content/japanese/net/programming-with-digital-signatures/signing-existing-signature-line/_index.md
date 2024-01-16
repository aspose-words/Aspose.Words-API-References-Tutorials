---
title: Word 文書の既存の署名行に署名する
linktitle: Word 文書の既存の署名行に署名する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/signing-existing-signature-line/
---
このチュートリアルでは、Aspose.Words for .NET で既存の署名欄の署名機能を使用する手順を説明します。この機能を使用すると、Word 文書にすでに存在する署名欄にデジタル署名できます。以下の手順に従います。

## ステップ 1: 文書をロードして署名欄にアクセスする

まず、既存の署名欄を含む文書をアップロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## ステップ 2: 署名オプションを設定する

SignOptions クラスのインスタンスを作成し、署名行 ID や署名行画像などの署名オプションを設定します。

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

署名欄の画像への正しいパスを指定してください。

## ステップ 3: 証明書のロード

まず、CertificateHolder クラスを使用して署名証明書をロードします。

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

証明書への正しいパスと関連するパスワードを必ず指定してください。

## ステップ 4: 既存の署名欄に署名する

DigitalSignatureUtil クラスを使用して、既存の署名欄に署名します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

ソース文書、署名済み文書、および証明書の正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用して既存の署名行に署名するためのソース コードの例

Aspose.Words for .NET を使用して既存の署名欄に署名するための完全なソース コードを次に示します。


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に簡単に署名できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名する方法を学びました。表示された手順に従うことで、ドキュメントのロード、既存の署名欄へのアクセス、署名オプションの設定、ドキュメントへの署名を簡単に行うことができます。既存の署名欄に署名できる機能により、Word 文書の事前定義された領域にデジタル署名を追加し、文書の整合性と認証を確保する便利な方法が提供されます。 Aspose.Words for .NET は、デジタル署名を備えた Word Processing 用の強力な API を提供し、署名プロセスをカスタマイズして Word 文書のセキュリティを強化できます。

### よくある質問

#### Q: Word 文書内の既存の署名欄とは何ですか?

A: Word 文書内の既存の署名欄は、署名を配置できる事前定義された領域です。通常、これは文書内の図形またはオブジェクトによって表され、署名者がデジタル署名を追加するための指定されたスペースとして機能します。

#### Q: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名するには、次の手順に従います。
1. を使用してドキュメントをロードします。`Document`クラスを作成し、ドキュメント ファイルへのパスを指定します。
2. 適切なメソッドまたはプロパティを使用して、既存の署名欄にアクセスします。たとえば、次のように使用できます`GetChild`署名線の形状を取得するメソッド。
3. のインスタンスを作成します。`SignOptions`クラスを設定して、`SignatureLineId`プロパティを既存の署名欄の ID に設定します。
4. をセットする`SignatureLineImage`の財産`SignOptions`クラスをデジタル署名を表すイメージに追加します。
5. 次のコマンドを使用して署名証明書をロードします。`CertificateHolder`クラスを選択し、必要な証明書とパスワードを指定します。
6. 使用`DigitalSignatureUtil.Sign`ドキュメントに署名するためのメソッド。`SignOptions`物体。

#### Q: Aspose.Words for .NET を使用して Word 文書内の既存の署名行にアクセスするにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄にアクセスするには、適切なメソッドまたはプロパティを使用して文書の構造から署名欄の形状を取得できます。たとえば、次のように使用できます。`GetChild`メソッドを適切なパラメータで使用して、必要な署名線の形状を取得します。

#### Q: 既存の署名欄のデジタル署名の外観をカスタマイズできますか?

A: はい、署名を表す画像ファイルを提供することで、既存の署名欄のデジタル署名の外観をカスタマイズできます。画像には、ロゴ、手書きの署名、または署名のその他のグラフィック表現を使用できます。設定できるのは、`SignatureLineImage`の財産`SignOptions`クラスを画像ファイルのバイトに変換します。

#### Q: Word 文書内の複数の既存の署名行に署名できますか?
 A: はい、Word 文書内の複数の既存の署名行に署名できます。各署名行の手順を個別に実行し、適切な設定を行う必要があります。`SignatureLineId`そして`SignatureLineImage`の値`SignOptions`各署名行のオブジェクト。

#### Q: 既存の署名欄のデジタル署名には、どのような形式の画像ファイルを使用する必要がありますか?

 A: 既存の署名欄のデジタル署名の画像ファイルは、PNG、JPEG、BMP、GIF などのさまざまな形式にすることができます。ファイルパスを指定するか、イメージファイルのバイトを読み取ってそれを`SignatureLineImage`の財産`SignOptions`クラス。
