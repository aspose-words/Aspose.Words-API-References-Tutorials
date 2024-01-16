---
title: Docx を Mhtml に変換して電子メールを送信する
linktitle: Docx を Mhtml に変換して電子メールを送信する
second_title: Aspose.Words ドキュメント処理 API
description: Word ドキュメントを Docx から MHTML に変換し、Aspose.Words と Aspose.Email を使用して電子メールとして送信する方法を学びます。ステップバイステップのチュートリアル。
type: docs
weight: 10
url: /ja/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して、Docx 形式の Word ドキュメントを MHTML に変換し、Aspose.Email を使用して電子メールとして送信する方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、Aspose.Words for .NET ライブラリと Aspose.Email ライブラリの両方が開発環境にインストールされ、セットアップされていることを確認してください。まだ行っていない場合は、次の場所からライブラリをダウンロードしてインストールします。[Aspose.リリース](https://releases.aspose.com/words/net/).

## ステップ 1: ドキュメント オブジェクトの初期化

まず、初期化します`Document`Docx 形式のソースドキュメントへのパスを含むオブジェクト:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## ステップ 2: ドキュメントを MHTML 形式で保存する

次に、ドキュメントを次の場所に保存します。`Stream` MHTML 形式のオブジェクト:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## ステップ 3: ストリームを巻き戻す

Aspose.Email はストリームを最初から読み取る必要があるため、ストリームを最初まで巻き戻します。

```csharp
stream.Position = 0;
```

## ステップ 4: Aspose.Email MIME メッセージの作成

を作成します`MailMessage`を使用してストリームからのオブジェクト`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

送信者、受信者、件名などのメッセージのプロパティを自由にカスタマイズできます。

## ステップ 5: 電子メールを送信する

Aspose.Email を使用する`SmtpClient`電子メールを送信するには:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

正しい SMTP サーバーのホスト アドレスを指定していることを確認してください。

それでおしまい！ Docx 形式の Word 文書を MHTML に変換し、Aspose.Words for .NET と Aspose.Email を使用して電子メールとして送信することができました。

### Docx To Mhtml と Aspose.Words for .NET を使用した電子メール送信のサンプル ソース コード

```csharp

	//ドキュメント doc = 新しい Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Aspose.Email がストリームを読み取れるように、ストリームを先頭まで巻き戻します。
	stream.Position = 0;

	//ストリームから Aspose.Email MIME 電子メール メッセージを作成します。
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Aspose.Email を使用してメッセージを送信します。
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

このコードを独自のプロジェクトで自由に使用し、特定の要件に応じて変更してください。

### よくある質問

#### DOCX ファイルを MHTML に変換するにはどうすればよいですか?

DOCX ファイルを MHTML に変換するには、この機能を提供するソフトウェア ツールまたはライブラリを使用できます。 Aspose.Words for .NET は、この変換の信頼できるオプションです。ライブラリ API を使用して DOCX ファイルをロードし、MHTML 形式で保存できます。

#### MHTML ファイルを添付した電子メールを送信するにはどうすればよいですか?

MHTML ファイルを添付ファイルとして電子メールを送信するには、.NET の System.Net.Mail など、電子メール送信に固有のライブラリまたはツールを使用できます。電子メール メッセージを作成し、受信者、件名、コンテンツを指定して、送信する前にメッセージに添付ファイルとして MHTML ファイルを追加する必要があります。

#### 電子メールの変換および送信プロセスにはどのような制限がありますか?

電子メールの変換および送信プロセスの制限は、使用している特定のツールによって異なります。一部のツールには、ファイル サイズ、セキュリティ設定、サポートされている電子メール プロトコルに関連する制限がある場合があります。ニーズに合ったツールを選択し、実装する際にはこれらの制限を考慮することが重要です。

#### Aspose は、DOCX から MHTML への変換と電子メール送信のための信頼できるツールですか?

はい、Aspose.Words for .NET は、DOCX から MHTML への変換と電子メール送信のための信頼できるツールです。そのパフォーマンスと品質により、開発者や専門家によって広く使用されています。このツールは、包括的なドキュメント、高度な機能、専用の技術サポートを提供するため、これらのタスクに推奨される選択肢となっています。