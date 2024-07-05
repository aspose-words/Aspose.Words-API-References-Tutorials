---
title: 暗号化された Word 文書に署名する
linktitle: 暗号化された Word 文書に署名する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して暗号化された Word 文書にデジタル署名する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/signing-encrypted-document/
---
このチュートリアルでは、Aspose.Words for .NET を使用して暗号化された Word 文書に署名する機能を使用する手順を説明します。この機能を使用すると、復号化パスワードを使用して暗号化された Word 文書にデジタル署名できます。以下の手順に従ってください。

## ステップ1: 署名オプションの設定

SignOptions クラスのインスタンスを作成し、復号化パスワードを設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

暗号化されたドキュメントには必ず正しい復号化パスワードを指定してください。

## ステップ2: 証明書の読み込み

まず、CertificateHolder クラスを使用して署名証明書を読み込みます。

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

証明書と関連するパスワードへの正しいパスを必ず指定してください。

## ステップ3: 暗号化された文書に署名する

暗号化されたドキュメントに署名するには、DigitalSignatureUtil クラスを使用します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

暗号化されたドキュメント、署名されたドキュメント、および証明書の正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用して暗号化されたドキュメントに署名するためのサンプル ソース コード

Aspose.Words for .NET を使用して暗号化されたドキュメントに署名するための完全なソース コードは次のとおりです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
これらの手順に従うと、Aspose.Words for .NET を使用して暗号化された Word 文書に簡単に署名できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して暗号化された Word 文書に署名するプロセスについて説明しました。復号化パスワードと署名証明書を提供することで、暗号化された文書にデジタル署名を追加できます。暗号化された文書に署名すると、その信頼性と整合性が確保され、セキュリティがさらに強化されます。Aspose.Words for .NET を使用すると、暗号化された文書に署名し、Word ファイルのセキュリティと信頼性を維持できます。

### よくある質問

#### Q: Aspose.Words for .NET のドキュメント署名とは何ですか?

A: Aspose.Words for .NET でのドキュメント署名とは、Word ドキュメントにデジタル署名して、その信頼性、整合性、否認不可性を保証するプロセスを指します。証明書を使用してドキュメントにデジタル署名を追加します。

#### Q: 暗号化された Word 文書とは何ですか?

A: 暗号化された Word 文書は、パスワードを使用して暗号化された文書です。暗号化は、文書の内容をスクランブルして正しい復号化パスワードがなければ読み取れないようにすることで、文書の内容を保護するセキュリティ対策です。

#### Q: Aspose.Words for .NET を使用して暗号化された Word 文書に署名するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して暗号化された Word 文書に署名するには、署名証明書とともに復号化パスワードを提供する必要があります。次の手順に従います。
1. 復号化パスワードを`SignOptions`物体。
2. 署名証明書をロードするには、`CertificateHolder`クラス。
3. 使用`DigitalSignatureUtil.Sign`必要なパラメータを指定して暗号化されたドキュメントに署名する方法。

#### Q: 暗号化された文書に署名する目的は何ですか?

A: Aspose.Words for .NET を使用して暗号化されたドキュメントに署名すると、ドキュメントが暗号化されている場合でも、そのドキュメントにデジタル署名を追加できます。これにより、セキュリティがさらに強化され、暗号化されたコンテンツの信頼性と整合性が確保されます。受信者はドキュメントの出所を確認し、改ざんを検出することができます。

#### Q: 復号化パスワードを入力せずに暗号化された文書に署名できますか?

A: いいえ、暗号化された文書に署名するには、正しい復号化パスワードを入力する必要があります。復号化パスワードは、デジタル署名を適用する前に、文書の暗号化されたコンテンツにアクセスして変更するために必要です。

#### Q: 任意の証明書を使用して暗号化された Word 文書に署名できますか?

A: Aspose.Words for .NET を使用して暗号化された Word 文書に署名するには、有効な X.509 証明書が必要です。証明書は、信頼できる証明機関 (CA) から取得するか、テスト目的で自己署名証明書を使用することができます。

#### Q: 同じ証明書を使用して複数の暗号化された Word 文書に署名できますか?

 A: はい、同じ証明書を使用して複数の暗号化されたWord文書に署名できます。`CertificateHolder`クラスを使用すると、それを再利用して複数の暗号化されたドキュメントに署名できます。

#### Q: 署名された暗号化文書のデジタル署名を検証できますか?

 A: はい、Aspose.Words for .NETには、署名された暗号化されたドキュメントのデジタル署名を検証する機能があります。`DigitalSignatureUtil.Verify`デジタル署名の有効性と信頼性を確認する方法。

#### Q: Aspose.Words for .NET は暗号化されたドキュメントの署名にどのファイル形式をサポートしていますか?

 A: Aspose.Words for .NETは、DOCXファイル形式の暗号化されたWord文書への署名をサポートしています。暗号化されたDOCXファイルに署名するには、`DigitalSignatureUtil.Sign`必要な復号化パスワードと証明書とともにメソッドを使用します。

#### Q: 暗号化された文書に署名すると、暗号化にどのような影響がありますか?

A: Aspose.Words for .NET を使用して暗号化されたドキュメントに署名しても、ドキュメントの暗号化には影響しません。暗号化はそのまま残り、暗号化されたコンテンツにデジタル署名が追加されます。デジタル署名により、ドキュメントに適用された暗号化を損なうことなく、セキュリティと検証が強化されます。