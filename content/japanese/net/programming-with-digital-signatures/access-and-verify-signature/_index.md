---
title: Word 文書の署名にアクセスして検証する
linktitle: Word 文書の署名にアクセスして検証する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のデジタル署名にアクセスし、検証する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-digital-signatures/access-and-verify-signature/
---
このチュートリアルでは、Aspose.Words for .NET のアクセスおよび署名検証機能を使用する手順を説明します。この機能を使用すると、Word 文書内のデジタル署名にアクセスし、その有効性を検証できます。以下の手順に従ってください。

## ステップ1: ドキュメントを読み込み、署名にアクセスする

まず、デジタル署名を含むドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## ステップ2: デジタル署名を参照する

ループを使用して、ドキュメント内のすべてのデジタル署名をループします。

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	//署名情報にアクセスする
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	//このプロパティは MS Word 文書でのみ使用できます。
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

表示メッセージは必要に応じてカスタマイズしてください。

### Aspose.Words for .NET を使用して署名にアクセスして検証するためのサンプル ソース コード

Aspose.Words for .NET を使用したアクセスおよび署名検証の完全なソース コードは次のとおりです。

```csharp
	
	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		//このプロパティは MS Word 文書でのみ使用できます。
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書内のデジタル署名に簡単にアクセスして検証できるようになります。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のデジタル署名にアクセスし、検証する機能について説明しました。提供されている手順に従うことで、文書を簡単に読み込み、そのデジタル署名にアクセスし、その有効性を検証できます。デジタル署名にアクセスして検証する機能により、Word 文書の整合性と信頼性を確保できます。Aspose.Words for .NET は、デジタル署名を使用した Words Processing 用の強力な API を提供し、検証プロセスを自動化して文書のセキュリティを強化できます。

### よくある質問

#### Q: Word 文書のデジタル署名とは何ですか?

A: Word 文書のデジタル署名は、文書の整合性と発行元を認証する方法を提供する電子署名です。デジタル署名はデジタル証明書と暗号化アルゴリズムを使用して作成されるため、受信者は文書が改ざんされていないこと、信頼できるソースから送信されたことを確認できます。

#### Q: Aspose.Words for .NET を使用して Word 文書内のデジタル署名にアクセスするにはどうすればよいでしょうか?

A: Aspose.Words for .NET を使用して Word 文書内のデジタル署名にアクセスするには、次の手順に従います。
1. ドキュメントをロードするには、`Document`クラスを作成し、ドキュメント ファイルへのパスを指定します。
2. ループを使用して、`DigitalSignatures`ドキュメントのコレクション。各反復はデジタル署名を表します。

#### Q: Word 文書のデジタル署名からどのような情報にアクセスできますか?

A: Word 文書のデジタル署名からは、次のようなさまざまな情報にアクセスできます。
- 有効性: 署名が有効かどうかを確認します。
- コメント: 署名者が指定した署名理由を取得します。
- 署名時刻: 文書が署名された時刻を取得します。
- サブジェクト名: 署名者または証明書のサブジェクトの名前を取得します。
- 発行者名: 証明書の発行者の名前を取得します。

#### Q: Aspose.Words for .NET を使用して Word 文書内のデジタル署名の有効性を検証できますか?

 A: はい、Aspose.Words for .NETを使用してWord文書のデジタル署名の有効性を検証できます。`IsValid`の財産`DigitalSignature`オブジェクトを使用すると、署名が有効かどうかを判断できます。

#### Q: Aspose.Words for .NET を使用して Word 文書内のデジタル署名の有効性を検証するにはどうすればよいですか?

A: Aspose.Words for .NET を使用して Word 文書内のデジタル署名の有効性を検証するには、次の手順に従います。
1. アクセス`DigitalSignatures`文書の収集。
2. それぞれを繰り返す`DigitalSignature`コレクション内のオブジェクト。
3. 使用`IsValid`の財産`DigitalSignature`署名が有効かどうかを確認するオブジェクト。

#### Q: Word 文書のデジタル署名から署名者のコメントや署名理由を取得できますか?

A: はい、Word文書のデジタル署名から署名者のコメントや署名理由を取得できます。`Comments`の財産`DigitalSignature`オブジェクトは、署名プロセス中に署名者によって指定されたコメントへのアクセスを提供します。

#### Q: Aspose.Words for .NET の署名検証機能はどのような種類のドキュメントをサポートしていますか?

A: Aspose.Words for .NET の署名検証機能は、DOCX ファイル形式の Word 文書のデジタル署名の検証をサポートしています。この機能を使用して、DOCX ファイルの署名を検証できます。

#### Q: Aspose.Words for .NET を使用して Word 文書内のデジタル署名の証明書の詳細にアクセスするにはどうすればよいでしょうか?

 A: Aspose.Words for .NETを使用してWord文書のデジタル署名の証明書の詳細にアクセスするには、`CertificateHolder`の財産`DigitalSignature`オブジェクト。`CertificateHolder`オブジェクトを使用すると、サブジェクト名や発行者名など、証明書のさまざまな詳細を取得できます。

#### Q: Aspose.Words for .NET を使用して、Word 文書内のデジタル署名の表示や処理をカスタマイズできますか?

 A: はい、Aspose.Words for .NETを使用してWord文書のデジタル署名の表示や処理をカスタマイズできます。`DigitalSignature`オブジェクトを使用すると、必要な情報を抽出したり、追加の検証を実行したり、署名検証プロセスをアプリケーションのワークフローに統合したりできます。

#### Q: Aspose.Words for .NET を使用して Word 文書内の複数のデジタル署名を検証することは可能ですか?

 A: はい、Aspose.Words for .NETを使用してWord文書内の複数のデジタル署名を検証することは可能です。`DigitalSignatures`ドキュメントのコレクションでは、各デジタル署名に個別にアクセスして検証できます。

