---
title: Docx'i Mhtml'ye Dönüştürme ve E-posta Gönderme
linktitle: Docx'i Mhtml'ye Dönüştürme ve E-posta Gönderme
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım kılavuzda DOCX'i MHTML'ye nasıl dönüştüreceğinizi ve Aspose.Words for .NET kullanarak e-posta göndermeyi öğrenin. Kolay otomasyonla üretkenliğinizi artırın.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## giriiş

Günümüzün dijital çağında, belgeleri bir formattan diğerine dönüştürmek ve e-postayla göndermek yaygın bir görevdir. Bu makale, bir DOCX dosyasını MHTML formatına dönüştürme ve ardından Aspose.Words for .NET kullanarak e-posta olarak gönderme sürecinde size yol gösterecektir. Süreci baştan sona anlamanızı sağlamak için her adımı ayrıntılı, takip edilmesi kolay bir kılavuzda ele alacağız. Hadi dalalım!

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1. Aspose.Words for .NET: Aspose.Words for .NET kitaplığını indirip yükleyin.[Aspose sürümler sayfası](https://releases.aspose.com/words/net/).
2.  Aspose.Email for .NET: Aspose.Email for .NET kütüphanesini aşağıdaki adresten indirip yükleyin:[Aspose sürümler sayfası](https://releases.aspose.com/email/net/).
3. .NET Framework: Makinenizde .NET Framework'ün kurulu olduğundan emin olun.
4. SMTP Sunucusu: E-posta göndermek için bir SMTP sunucusuna erişmeniz gerekir.

## Ad Alanlarını İçe Aktar

Aspose.Words ve Aspose.Email'i projenizde kullanmak için gerekli ad alanlarını içe aktarmanız gerekir. C# dosyanızın en üstüne aşağıdaki kullanma yönergelerini ekleyin:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Her bir parçayı net bir şekilde anladığınızdan emin olmak için süreci birden fazla adıma ayıralım.

## Adım 1: DOCX Belgesini Yükleyin

 Öncelikle dönüştürmek istediğiniz DOCX belgesini yüklemeniz gerekir. Kullanın`Document` DOCX dosyanızı yüklemek için Aspose.Words'ten class.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Adım 2: Belgeyi MHTML olarak kaydedin

 Daha sonra yüklenen belgeyi MHTML dosyası olarak kaydedin. Bu, kullanılarak yapılır.`Save` yöntemi`Document` sınıf.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Aspose.Email'in okuyabilmesi için akışı başlangıca geri sarın.
stream.Position = 0;
```

## 3. Adım: Bir E-posta Mesajı Oluşturun

Şimdi Aspose.Email'i kullanarak MHTML akışından bir e-posta mesajı oluşturun. Kullanacaksın`MailMessage` Bu amaçla sınıf.

```csharp
// Akıştan bir Aspose.Email MIME e-posta mesajı oluşturun.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## 4. Adım: E-postayı Gönderin

 Son olarak e-postayı bir SMTP istemcisi kullanarak gönderin. SMTP istemcisini SMTP sunucu ayrıntılarınızla yapılandırın ve`Send` mesajı gönderme yöntemi.

```csharp
// Aspose.Email'i kullanarak mesajı gönderin.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Çözüm

Tebrikler! Bir DOCX belgesini başarıyla MHTML'ye dönüştürdünüz ve Aspose.Words for .NET'i kullanarak e-postayla gönderdiniz. Bu süreç, belgenin yüklenmesini, MHTML'ye dönüştürülmesini, bir e-posta mesajı oluşturulmasını ve bir SMTP istemcisi kullanılarak gönderilmesini içerir. Bu adımlarla uygulamalarınızdaki belgelerin dönüştürülmesini ve e-postayla gönderilmesini kolayca otomatikleştirebilirsiniz.

## SSS'ler

### Bu yöntemi diğer belge formatlarını dönüştürmek için kullanabilir miyim?
Evet, Aspose.Words çeşitli formatları destekler ve DOC, DOCX, RTF ve daha fazlası gibi belgeleri MHTML'ye dönüştürebilirsiniz.

### E-postaya nasıl ek ekleyebilirim?
 Şunu kullanabilirsiniz:`Attachments` mülkiyeti`MailMessage`E-postanıza ek eklemek için sınıf.

### Aspose.Words .NET Core ile uyumlu mu?
Evet, Aspose.Words .NET Core ile uyumludur. .NET Core uygulamalarında da kullanabilirsiniz.

### Aspose.Words ve Aspose.Email için lisansa ihtiyacım var mı?
 Evet, her iki kütüphane de lisans gerektirir. Geçici lisansı şu adresten alabilirsiniz:[Satın alma sayfasını atayın](https://purchase.aspose.com/temporary-license/) değerlendirme amaçlı.

### Daha fazla belgeyi nerede bulabilirim?
 Aspose.Words için ayrıntılı belgelere ulaşabilirsiniz.[Burada](https://reference.aspose.com/words/net/) ve Aspose.Email için[Burada](https://reference.aspose.com/email/net/).
