---
title: Word 文書内の既存の署名欄に署名する
linktitle: Word 文書内の既存の署名欄に署名する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/signing-existing-signature-line/
---
このチュートリアルでは、Aspose.Words for .NET で既存の署名欄の署名機能を使用する手順を説明します。この機能を使用すると、Word 文書に既に存在する署名欄にデジタル署名することができます。以下の手順に従ってください。

## ステップ1: 文書を読み込み、署名欄にアクセスする

まず、既存の署名行を含むドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## ステップ2: 署名オプションの設定

SignOptions クラスのインスタンスを作成し、署名行 ID や署名行画像などの署名オプションを設定します。

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

署名行画像への正しいパスを必ず指定してください。

## ステップ3: 証明書の読み込み

まず、CertificateHolder クラスを使用して署名証明書を読み込みます。

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

証明書と関連するパスワードへの正しいパスを必ず指定してください。

## ステップ4: 既存の署名欄に署名する

既存の署名行に署名するには、DigitalSignatureUtil クラスを使用します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

ソース ドキュメント、署名済みドキュメント、および証明書の正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用して既存の署名欄に署名するためのサンプル ソース コード

Aspose.Words for .NET を使用して既存の署名行に署名するための完全なソース コードは次のとおりです。


```csharp

	//ドキュメント ディレクトリへのパス。
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

以下の手順に従うと、Aspose.Words for .NET を使用して Word 文書内の既存の署名行に簡単に署名できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名する方法を学習しました。提供されている手順に従うことで、文書を簡単に読み込み、既存の署名欄にアクセスし、署名オプションを設定して、文書に署名することができます。既存の署名欄に署名する機能は、Word 文書内の定義済み領域にデジタル署名を追加する便利な方法を提供し、文書の整合性と認証を保証します。Aspose.Words for .NET は、デジタル署名を使用した Words 処理用の強力な API を提供し、署名プロセスをカスタマイズして Word 文書のセキュリティを強化できます。

### よくある質問

#### Q: Word 文書内の既存の署名行とは何ですか?

A: Word 文書内の既存の署名欄は、署名を配置できる定義済みの領域です。通常、署名欄は文書内の図形またはオブジェクトで表され、署名者がデジタル署名を追加するための指定スペースとして機能します。

#### Q: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書内の既存の署名欄に署名するには、次の手順に従います。
1. ドキュメントをロードするには、`Document`クラスを作成し、ドキュメント ファイルへのパスを指定します。
2. 適切なメソッドまたはプロパティを使用して既存の署名欄にアクセスします。たとえば、`GetChild`署名線の形状を取得する方法。
3. インスタンスを作成する`SignOptions`クラスを設定し、`SignatureLineId`プロパティを既存の署名行の ID に追加します。
4. をセットする`SignatureLineImage`の財産`SignOptions`デジタル署名を表す画像にクラスを追加します。
5. 署名証明書をロードするには、`CertificateHolder`クラスに登録し、必要な証明書とパスワードを入力します。
6. 使用`DigitalSignatureUtil.Sign`文書に署名する方法。必要なパラメータを指定して、`SignOptions`物体。

#### Q: Aspose.Words for .NET を使用して Word 文書内の既存の署名行にアクセスするにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してWord文書内の既存の署名欄にアクセスするには、適切なメソッドまたはプロパティを使用して、文書の構造から署名欄の形状を取得します。たとえば、`GetChild`適切なパラメータを使用してメソッドを実行し、希望する署名線の形状を取得します。

#### Q: 既存の署名行のデジタル署名の外観をカスタマイズできますか?

A: はい、署名を表す画像ファイルを提供することで、既存の署名欄のデジタル署名の外観をカスタマイズできます。画像は、ロゴ、手書きの署名、または署名のその他のグラフィカル表現にすることができます。`SignatureLineImage`の財産`SignOptions`クラスを画像ファイルのバイトに割り当てます。

#### Q: Word 文書内の複数の既存の署名行に署名できますか?
 A: はい、Word文書内の複数の署名欄に署名することができます。署名欄ごとに適切な署名を設定する必要があります。`SignatureLineId`そして`SignatureLineImage`の価値観`SignOptions`各署名行のオブジェクト。

#### Q: 既存の署名行のデジタル署名の画像ファイルの形式はどのようなものにすればよいですか?

 A: 既存の署名欄のデジタル署名の画像ファイルは、PNG、JPEG、BMP、GIFなど、さまざまな形式にすることができます。ファイルパスを指定するか、画像ファイルのバイトを読み取って、`SignatureLineImage`の財産`SignOptions`クラス。
