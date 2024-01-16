---
title: 暗号化された Word 文書に署名する
linktitle: 暗号化された Word 文書に署名する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、暗号化された Word ドキュメントにデジタル署名する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/signing-encrypted-document/
---
このチュートリアルでは、Aspose.Words for .NET を使用して暗号化された Word ドキュメントに署名する機能を使用する手順を説明します。この機能を使用すると、復号化パスワードを使用して暗号化された Word 文書にデジタル署名できます。以下の手順に従います。

## ステップ 1: 署名オプションを設定する

SignOptions クラスのインスタンスを作成し、復号化パスワードを設定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

暗号化されたドキュメントの正しい復号化パスワードを必ず指定してください。

## ステップ 2: 証明書のロード

まず、CertificateHolder クラスを使用して署名証明書をロードします。

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

証明書への正しいパスと関連するパスワードを必ず指定してください。

## ステップ 3: 暗号化されたドキュメントに署名する

DigitalSignatureUtil クラスを使用して、暗号化されたドキュメントに署名します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

暗号化されたドキュメント、署名されたドキュメント、および証明書の正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用して暗号化されたドキュメントに署名するためのソース コードの例

Aspose.Words for .NET を使用して暗号化されたドキュメントに署名するための完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
次の手順に従うと、Aspose.Words for .NET を使用して暗号化された Word 文書に簡単に署名できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、暗号化された Word ドキュメントに署名するプロセスについて説明しました。復号化パスワードと署名証明書を提供することで、暗号化されたドキュメントにデジタル署名を追加できます。暗号化されたドキュメントに署名すると、その信頼性と完全性が保証され、追加のセキュリティ層が提供されます。 Aspose.Words for .NET を使用すると、暗号化されたドキュメントに署名し、Word ファイルのセキュリティと信頼性を維持できます。

### よくある質問

#### Q: Aspose.Words for .NET のドキュメント署名とは何ですか?

A: Aspose.Words for .NET でのドキュメント署名とは、Word ドキュメントの信頼性、整合性、および否認防止を保証するために、Word ドキュメントにデジタル署名するプロセスを指します。これには、証明書を使用してドキュメントにデジタル署名を追加することが含まれます。

#### Q: 暗号化された Word 文書とは何ですか?

A: 暗号化された Word 文書は、パスワードを使用して暗号化された文書です。暗号化は、文書をスクランブル化し、正しい復号化パスワードがなければ読めないようにすることで文書の内容を保護するセキュリティ対策です。

#### Q: Aspose.Words for .NET を使用して、暗号化された Word 文書に署名するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して暗号化された Word 文書に署名するには、署名証明書とともに復号パスワードを指定する必要があります。次の手順を実行します：
1. 復号化パスワードを設定します。`SignOptions`物体。
2. 次のコマンドを使用して署名証明書をロードします。`CertificateHolder`クラス。
3. 使用`DigitalSignatureUtil.Sign`必要なパラメータを指定して、暗号化されたドキュメントに署名するメソッド。

#### Q: 暗号化された文書に署名する目的は何ですか?

A: Aspose.Words for .NET を使用して暗号化されたドキュメントに署名すると、暗号化されている場合でもドキュメントにデジタル署名を追加できます。これにより、追加のセキュリティ層が提供され、暗号化されたコンテンツの信頼性と完全性が保証されます。これにより、受信者はドキュメントの出所を確認し、改ざんを検出できるようになります。

#### Q: 復号化パスワードを入力せずに、暗号化されたドキュメントに署名できますか?

A: いいえ、暗号化されたドキュメントに署名するには、正しい復号化パスワードを指定する必要があります。デジタル署名を適用する前に、ドキュメントの暗号化されたコンテンツにアクセスして変更するには、復号化パスワードが必要です。

#### Q: 任意の証明書を使用して、暗号化された Word 文書に署名できますか?

A: Aspose.Words for .NET を使用して暗号化された Word 文書に署名するには、有効な X.509 証明書が必要です。証明書は、信頼できる認証局 (CA) から取得することも、自己署名証明書をテスト目的に使用することもできます。

#### Q: 同じ証明書を使用して、複数の暗号化された Word 文書に署名できますか?

 A: はい、同じ証明書を使用して、複数の暗号化された Word 文書に署名できます。を使用して証明書をロードしたら、`CertificateHolder`クラスを使用すると、複数の暗号化されたドキュメントに署名するために再利用できます。

#### Q: 署名された暗号化ドキュメントのデジタル署名を検証できますか?

 A: はい、Aspose.Words for .NET は、署名された暗号化ドキュメントのデジタル署名を検証する機能を提供します。使用できます`DigitalSignatureUtil.Verify`デジタル署名の有効性と信頼性を確認する方法。

#### Q: Aspose.Words for .NET は、暗号化されたドキュメントに署名するためにどのようなファイル形式をサポートしていますか?

 A: Aspose.Words for .NET は、DOCX ファイル形式での暗号化された Word ドキュメントへの署名をサポートしています。暗号化された DOCX ファイルに署名するには、`DigitalSignatureUtil.Sign`メソッドと、必要な復号化パスワードおよび証明書を指定します。

#### Q: 暗号化されたドキュメントに署名すると、暗号化にどのような影響がありますか?

A: Aspose.Words for .NET を使用して暗号化されたドキュメントに署名しても、ドキュメントの暗号化には影響しません。暗号化はそのまま残り、暗号化されたコンテンツにデジタル署名が追加されます。デジタル署名は、ドキュメントに適用される暗号化を損なうことなく、追加のセキュリティと検証を提供します。