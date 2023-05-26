---
title: Docx'ten Mhtml'ye ve E-posta Gönderme
linktitle: Docx'ten Mhtml'ye ve E-posta Gönderme
second_title: Aspose.Words for .NET API Referansı
description: Word belgelerini Docx'ten MHTML'ye nasıl dönüştüreceğinizi ve bunları Aspose.Words ve Aspose.Email kullanarak e-posta olarak göndermeyi öğrenin. Adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Bu adım adım öğreticide, Docx formatındaki bir Word belgesini MHTML'ye dönüştürmek ve Aspose.Email kullanarak bir e-posta olarak göndermek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda hem Aspose.Words for .NET hem de Aspose.Email kitaplıklarının kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplıkları resmi web sitelerinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` Docx biçimindeki kaynak belgenizin yolunu içeren nesne:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Adım 2: Belgeyi MHTML Formatında Kaydetme

 Ardından, belgeyi bir`Stream` MHTML biçimindeki nesne:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## 3. Adım: Akışı Geri Sarma

Aspose.Email'in akışı baştan okuması gerektiğinden akışı başa geri sarın:

```csharp
stream.Position = 0;
```

## Adım 4: Bir Aspose.Email MIME Mesajı Oluşturma

 Oluşturmak`MailMessage` kullanarak akıştan nesne`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Gönderen, alıcı ve konu gibi mesaj özelliklerini özelleştirmekten çekinmeyin.

## 5. Adım: E-postayı Gönderme

 Aspose.Email'i kullanın`SmtpClient` e-postayı göndermek için:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Doğru SMTP sunucusu ana bilgisayar adresini sağladığınızdan emin olun.

Bu kadar! Docx formatındaki bir Word belgesini başarıyla MHTML'ye dönüştürdünüz ve bunu Aspose.Words for .NET ve Aspose.Email kullanarak bir e-posta olarak gönderdiniz.

### Aspose.Words for .NET kullanarak Docx To Mhtml ve E-posta Gönderme için örnek kaynak kodu

```csharp

	// Belge belgesi = yeni Belge(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// Aspose.Email'in okuyabilmesi için akışı başa geri sarın.
	stream.Position = 0;

	// Akıştan bir Aspose.Email MIME e-posta mesajı oluşturun.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Aspose.Email'i kullanarak mesajı gönderin.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.