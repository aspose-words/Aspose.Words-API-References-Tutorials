---
title: Word文書に署名する
linktitle: Word文書に署名する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にデジタル署名する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/sign-document/
---
このチュートリアルでは、Aspose.Words for .NET でドキュメント署名機能を使用する手順を説明します。この機能を使用すると、証明書を使用して Word ドキュメントにデジタル署名できます。以下の手順に従ってください。

## ステップ1: 証明書の読み込み

まず、CertificateHolder クラスを使用して署名証明書を読み込みます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

証明書と関連するパスワードへの正しいパスを必ず指定してください。

## ステップ2: 文書に署名する

DigitalSignatureUtil クラスを使用してドキュメントに署名します。

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

ソース ドキュメントと署名済みドキュメントの正しいパスを必ず指定してください。

### Aspose.Words for .NET を使用してドキュメントに署名するためのサンプル ソース コード

Aspose.Words for .NET を使用してドキュメントに署名するための完全なソース コードは次のとおりです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書に簡単に署名できます。

## 結論

このチュートリアルでは、Aspose.Words for .NETのドキュメント署名機能について説明しました。署名証明書を読み込み、`DigitalSignatureUtil.Sign`この方法を使用すると、Word 文書にデジタル署名することができます。文書に署名すると認証が提供され、文書の内容の整合性が保証されるため、安全で信頼できる文書管理に役立つ機能となります。

### サインワード文書に関するFAQ

#### Q: Aspose.Words for .NET のドキュメント署名とは何ですか?

A: Aspose.Words for .NET でのドキュメント署名とは、証明書を使用して Word ドキュメントにデジタル署名するプロセスを指します。この機能は、ドキュメントにデジタル署名を追加し、ドキュメントの内容の信頼性、整合性、および否認不可性を提供します。

#### Q: Aspose.Words for .NET で署名証明書を読み込むにはどうすればいいですか?

 A: Aspose.Words for .NETで署名証明書を読み込むには、`CertificateHolder`クラスのインスタンスを作成します`CertificateHolder`証明書ファイルへのパスと関連するパスワードを指定します。次に例を示します。

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

証明書への正しいパスと関連するパスワードを必ず指定してください。

#### Q: Aspose.Words for .NET を使用して Word 文書に署名するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してWord文書に署名するには、`DigitalSignatureUtil`クラス。`Sign`メソッドは、ソース文書へのパス、署名された文書（出力）へのパス、および`CertificateHolder`オブジェクト。次に例を示します。

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

ソース ドキュメントと署名済みドキュメント (出力) の正しいパスを指定していることを確認してください。

#### Q: 文書に署名する目的は何ですか?

A: ドキュメントの署名は、ドキュメントの信頼性と整合性を保証する方法として機能します。ドキュメントにデジタル署名することで、その出所を証明し、その内容が変更されていないことを確認し、否認防止を確立できます。ドキュメントの署名は、法律、財務、機密文書によく使用されます。

#### Q: Aspose.Words for .NET でのドキュメント署名に任意の証明書を使用できますか?

A: Aspose.Words for .NET でドキュメントに署名するには、有効な X.509 証明書を使用する必要があります。この証明書は、信頼できる証明機関 (CA) から取得するか、テスト目的で自己署名証明書を使用できます。

#### Q: Aspose.Words for .NET はドキュメント署名にどのファイル形式をサポートしていますか?

 A: Aspose.Words for .NETは、DOCXファイル形式のWord文書の署名をサポートしています。DOCXファイルには、`DigitalSignatureUtil`クラスと適切な証明書。

#### Q: 同じ証明書を使用して複数の Word 文書に署名できますか?

A: はい、同じ証明書を使用して複数のWord文書に署名できます。`CertificateHolder`クラスを再利用して、`DigitalSignatureUtil.Sign`ソース パスと署名済みドキュメント パスが異なるメソッド。

#### Q: 文書に署名すると元の文書は変更されますか?

A: Aspose.Words for .NET によるドキュメントの署名では、元のドキュメントは変更されません。代わりに、元のドキュメントはそのまま残して、ドキュメントのデジタル署名されたコピーが作成されます。デジタル署名されたコピーには追加されたデジタル署名が含まれており、ドキュメントの内容の整合性が確保されます。

#### Q: Aspose.Words for .NET を使用して署名されたドキュメントのデジタル署名を検証できますか?

 A: はい、Aspose.Words for .NETには署名された文書のデジタル署名を検証する機能があります。`DigitalSignatureUtil.Verify`デジタル署名の有効性と信頼性を確認する方法。