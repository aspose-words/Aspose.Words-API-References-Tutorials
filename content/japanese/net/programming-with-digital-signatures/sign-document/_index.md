---
title: Word 文書に署名する
linktitle: Word 文書に署名する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にデジタル署名する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/sign-document/
---
このチュートリアルでは、Aspose.Words for .NET でドキュメント署名機能を使用する手順を説明します。この機能を使用すると、証明書を使用して Word 文書にデジタル署名できます。以下の手順に従います。

## ステップ 1: 証明書のロード

まず、CertificateHolder クラスを使用して署名証明書をロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

証明書への正しいパスと関連するパスワードを必ず指定してください。

## ステップ 2: 文書に署名する

DigitalSignatureUtil クラスを使用してドキュメントに署名します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

ソース文書と署名済み文書の正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用した署名ドキュメントのソース コード例

Aspose.Words for .NET を使用してドキュメントに署名するための完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

次の手順に従うと、Aspose.Words for .NET を使用して Word 文書に簡単に署名できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET のドキュメント署名機能を検討しました。署名証明書をロードし、`DigitalSignatureUtil.Sign`このメソッドを使用すると、Word 文書にデジタル署名できます。ドキュメント署名は認証を提供し、ドキュメントの内容の整合性を保証するため、安全で信頼できるドキュメント管理にとって貴重な機能となります。

### 手話文書に関する FAQ

#### Q: Aspose.Words for .NET のドキュメント署名とは何ですか?

A: Aspose.Words for .NET でのドキュメント署名とは、証明書を使用して Word ドキュメントにデジタル署名するプロセスを指します。この機能は、ドキュメントにデジタル署名を追加し、ドキュメントの内容の信頼性、完全性、および否認防止を実現します。

#### Q: Aspose.Words for .NET に署名証明書をロードするにはどうすればよいですか?

 A: Aspose.Words for .NET に署名証明書をロードするには、`CertificateHolder`クラス。のインスタンスを作成します`CertificateHolder`証明書ファイルへのパスと関連するパスワードを指定します。以下に例を示します。

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

証明書への正しいパスと関連するパスワードを必ず指定してください。

#### Q: Aspose.Words for .NET を使用して Word 文書に署名するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書に署名するには、`DigitalSignatureUtil`クラス。電話してください`Sign`メソッド。ソース文書へのパス、署名済み文書 (出力) へのパス、および`CertificateHolder`物体。以下に例を示します。

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

ソース文書と署名済み文書 (出力) への正しいパスを指定していることを確認してください。

#### Q: 文書に署名する目的は何ですか?

A: 文書署名は、文書の信頼性と完全性を保証する方法として機能します。ドキュメントにデジタル署名することにより、その出所の証明を提供し、その内容が変更されていないことを確認し、否認防止を確立することができます。文書署名は、法律文書、財務文書、機密文書によく使用されます。

#### Q: Aspose.Words for .NET でのドキュメント署名に任意の証明書を使用できますか?

A: Aspose.Words for .NET でのドキュメント署名には、有効な X.509 証明書を使用する必要があります。この証明書は、信頼できる認証局 (CA) から取得することも、自己署名証明書をテスト目的に使用することもできます。

#### Q: Aspose.Words for .NET はドキュメント署名のためにどのようなファイル形式をサポートしていますか?

 A: Aspose.Words for .NET は、DOCX ファイル形式の Word ドキュメントのドキュメント署名をサポートしています。 DOCX ファイルに署名するには、`DigitalSignatureUtil`クラスと適切な証明書。

#### Q: 同じ証明書を使用して複数の Word 文書に署名できますか?

A: はい、同じ証明書を使用して複数の Word 文書に署名できます。を使用して証明書をロードしたら、`CertificateHolder`クラスを呼び出すことで、それを再利用して複数のドキュメントに署名できます。`DigitalSignatureUtil.Sign`ソースと署名されたドキュメントのパスが異なるメソッド。

#### Q: 文書に署名すると、元の文書が変更されますか?

A: Aspose.Words for .NET を使用してドキュメントに署名しても、元のドキュメントは変更されません。代わりに、元の文書をそのまま残したまま、デジタル署名された文書のコピーが作成されます。デジタル署名されたコピーには追加のデジタル署名が含まれており、文書の内容の完全性が保証されます。

#### Q: Aspose.Words for .NET を使用して、署名されたドキュメントのデジタル署名を検証できますか?

 A: はい、Aspose.Words for .NET は、署名されたドキュメントのデジタル署名を検証する機能を提供します。使用できます`DigitalSignatureUtil.Verify`デジタル署名の有効性と信頼性を確認する方法。