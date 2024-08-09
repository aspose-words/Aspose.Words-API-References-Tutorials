---
title: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
linktitle: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde yeni bir imza satırı oluşturmayı ve sağlayıcı kimliğini nasıl ayarlayacağınızı öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## giriiş

Merhaba teknoloji tutkunları! Word belgelerinize program aracılığıyla nasıl imza satırı ekleyeceğinizi hiç merak ettiniz mi? Bugün Aspose.Words for .NET'i kullanarak tam da buna dalacağız. Bu kılavuz size her adımda yol gösterecek ve yeni bir imza satırı oluşturmanızı ve Word belgelerinizde sağlayıcı kimliğini ayarlamanızı çok kolaylaştıracaktır. İster belge işlemeyi otomatikleştiriyor olun, ister yalnızca iş akışınızı kolaylaştırmak istiyor olun, bu eğitim size yardımcı olacaktır.

## Önkoşullar

Ellerimizi kirletmeden önce ihtiyacımız olan her şeye sahip olduğumuzdan emin olalım:

1.  Aspose.Words for .NET: Henüz yapmadıysanız indirin[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio veya başka herhangi bir C# geliştirme ortamı.
3. .NET Framework: .NET Framework'ün kurulu olduğundan emin olun.
4. PFX Sertifikası: Belgeleri imzalamak için bir PFX sertifikasına ihtiyacınız olacaktır. Güvenilir bir sertifika yetkilisinden bir tane alabilirsiniz.

## Ad Alanlarını İçe Aktar

Öncelikle C# projenize gerekli ad alanlarını aktaralım:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Tamam, asıl meseleye geçelim. Yeni bir imza satırı oluşturmak ve sağlayıcı kimliğini ayarlamak için her adımın ayrıntılı bir dökümünü burada bulabilirsiniz.

## 1. Adım: Yeni Bir Belge Oluşturun

Başlamak için yeni bir Word belgesi oluşturmamız gerekiyor. Bu imza çizgimizin tuvali olacak.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Bu kod parçasında yeni bir başlangıç başlatıyoruz`Document` ve bir`DocumentBuilder` .`DocumentBuilder` belgemize öğeler eklememize yardımcı olur.

## Adım 2: İmza Satırı Seçeneklerini Tanımlayın

Daha sonra imza satırımız için seçenekleri tanımlıyoruz. Buna imzalayanın adı, unvanı, e-posta adresi ve diğer ayrıntılar dahildir.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Bu seçenekler imza satırını kişiselleştirerek onu net ve profesyonel hale getirir.

## Adım 3: İmza Satırını Ekleyin

Seçeneklerimizi ayarladığımızda artık imza satırını belgeye ekleyebiliriz.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Burada,`InsertSignatureLine` yöntemi imza satırını ekler ve biz ona benzersiz bir sağlayıcı kimliği atarız.

## Adım 4: Belgeyi Kaydedin

İmza satırını ekledikten sonra belgeyi kaydedelim.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Bu, belgenizi yeni eklenen imza satırıyla kaydeder.

## 5. Adım: İmzalama Seçeneklerini Ayarlayın

Şimdi belgeyi imzalama seçeneklerini ayarlamamız gerekiyor. Buna imza satırı kimliği, sağlayıcı kimliği, yorumlar ve imzalama süresi dahildir.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Bu seçenekler belgenin doğru ayrıntılarla imzalanmasını sağlar.

## Adım 6: Sertifika Sahibi Oluşturun

Belgeyi imzalamak için PFX sertifikası kullanacağız. Bunun için bir sertifika sahibi oluşturalım.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Değiştirdiğinizden emin olun`"morzal.pfx"` gerçek sertifika dosyanızla ve`"aw"` Sertifika şifrenizle.

## Adım 7: Belgeyi İmzalayın

Son olarak dijital imza yardımcı programını kullanarak belgeyi imzalıyoruz.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Bu, belgeyi imzalar ve yeni bir dosya olarak kaydeder.

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak başarılı bir şekilde yeni bir imza satırı oluşturdunuz ve sağlayıcı kimliğini bir Word belgesinde ayarladınız. Bu güçlü kitaplık, belge işleme görevlerini yönetmeyi ve otomatikleştirmeyi inanılmaz derecede kolaylaştırır. Bir deneyin ve iş akışınızı nasıl kolaylaştırabileceğini görün.

## SSS'ler

### İmza çizgisinin görünümünü özelleştirebilir miyim?
Kesinlikle! Çeşitli seçenekleri ayarlayabilirsiniz.`SignatureLineOptions` İhtiyaçlarınıza uyacak şekilde.

### PFX sertifikam yoksa ne olur?
Güvenilir bir sertifika yetkilisinden bir sertifika almanız gerekir. Belgeleri dijital olarak imzalamak için gereklidir.

### Bir belgeye birden fazla imza satırı ekleyebilir miyim?
Evet, ekleme işlemini farklı seçeneklerle tekrarlayarak dilediğiniz kadar imza satırı ekleyebilirsiniz.

### Aspose.Words for .NET, .NET Core ile uyumlu mu?
Evet, Aspose.Words for .NET, .NET Core'u destekleyerek farklı geliştirme ortamları için çok yönlü olmasını sağlar.

### Dijital imzalar ne kadar güvenli?
Aspose.Words ile oluşturulan dijital imzalar, geçerli ve güvenilir bir sertifika kullanmanız koşuluyla son derece güvenlidir.