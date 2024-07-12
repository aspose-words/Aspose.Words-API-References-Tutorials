---
title: Yeni İmza Satırı Oluşturma ve İmzalama
linktitle: Yeni İmza Satırı Oluşturma ve İmzalama
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım eğitimle Aspose.Words for .NET kullanarak bir Word belgesinde nasıl imza satırı oluşturulacağını ve dijital olarak imzalanacağını öğrenin. Belge otomasyonu için mükemmeldir.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## giriiş

Selam! Yani bir Word belgeniz var ve bir imza satırı eklemeniz ve ardından bunu dijital olarak imzalamanız gerekiyor. Zor görünüyor mu? Hiç de bile! Aspose.Words for .NET sayesinde bunu yalnızca birkaç satır kodla sorunsuz bir şekilde başarabilirsiniz. Bu eğitimde, ortamınızı ayarlamaktan belgenizi yeni ve parlak bir imzayla kaydetmeye kadar tüm süreç boyunca size yol göstereceğiz. Hazır? Hadi dalalım!

## Önkoşullar

Koda geçmeden önce ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1.  Aspose.Words for .NET - Yapabilirsin[buradan indir](https://releases.aspose.com/words/net/).
2. .NET Geliştirme Ortamı - Visual Studio önemle tavsiye edilir.
3. İmzalanacak Belge - Basit bir Word belgesi oluşturun veya mevcut bir belgeyi kullanın.
4.  Sertifika Dosyası - Bu, dijital imzalar için gereklidir. Bir kullanabilirsiniz`.pfx` dosya.
5. İmza Satırı Görselleri - İsteğe bağlı olarak imza için bir görsel dosyası.

## Ad Alanlarını İçe Aktar

Öncelikle gerekli ad alanlarını içe aktarmamız gerekiyor. Bu adım, Aspose.Words işlevlerinin kullanılmasına yönelik ortamı oluşturduğu için çok önemlidir.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Adım 1: Belge Dizinini Ayarlama

Her projenin iyi bir başlangıca ihtiyacı vardır. Belge dizininizin yolunu ayarlayalım. Burası belgelerinizin kaydedileceği ve alınacağı yerdir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Yeni Bir Belge Oluşturma

Şimdi Aspose.Words kullanarak yeni bir Word belgesi oluşturalım. Bu, imza satırını ekleyeceğimiz tuvalimiz olacak.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 3: İmza Satırını Ekleme

 Sihir yapılan yer burasıdır. Kullanarak belgemize bir imza satırı ekliyoruz.`DocumentBuilder` sınıf.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Adım 4: Belgeyi İmza Satırıyla Kaydetme

İmza satırı yerleştirildikten sonra belgeyi kaydetmemiz gerekiyor. Bu, imzalamaya geçmeden önce bir ara adımdır.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Adım 5: İmzalama Seçeneklerini Ayarlama

Şimdi belgeyi imzalama seçeneklerini ayarlayalım. Bu, imza satırı kimliğinin ve kullanılacak görüntünün belirtilmesini içerir.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Adım 6: Sertifikayı Yükleme

Dijital imzalar bir sertifika gerektirir. Burada belgeyi imzalamak için kullanılacak sertifika dosyasını yüklüyoruz.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Adım 7: Belgeyi İmzalama

 Bu son adımdır. biz kullanıyoruz`DigitalSignatureUtil`belgeyi imzalamak için sınıf. İmzalanan belge yeni bir adla kaydedilir.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Çözüm

İşte buyur! Bu adımlarla başarılı bir şekilde yeni bir Word belgesi oluşturdunuz, bir imza satırı eklediniz ve onu Aspose.Words for .NET kullanarak dijital olarak imzaladınız. Belge otomasyonunu çocuk oyuncağı haline getiren güçlü bir araçtır. İster sözleşmelerle, anlaşmalarla ister herhangi bir resmi belgeyle ilgileniyor olun, bu yöntem bunların güvenli bir şekilde imzalanmasını ve doğrulanmasını sağlar.

## SSS'ler

### İmza satırı için başka resim formatlarını kullanabilir miyim?
Evet, PNG, JPG, BMP vb. gibi çeşitli resim formatlarını kullanabilirsiniz.

###  Kullanmak gerekli mi?`.pfx` file for the certificate?
 Evet A`.pfx` dosyası, sertifikalar ve özel anahtarlar dahil olmak üzere kriptografik bilgileri depolamak için yaygın bir formattır.

### Tek bir belgeye birden fazla imza satırı ekleyebilir miyim?
Kesinlikle! Her imza için ekleme adımını tekrarlayarak birden fazla imza satırı ekleyebilirsiniz.

### Dijital sertifikam yoksa ne olur?
Güvenilir bir sertifika yetkilisinden dijital sertifika almanız veya OpenSSL gibi araçları kullanarak bir sertifika oluşturmanız gerekir.

### Belgedeki dijital imzayı nasıl doğrularım?
İmzalı belgeyi Word'de açabilir ve imzanın gerçekliğini ve bütünlüğünü doğrulamak için imza ayrıntılarına gidebilirsiniz.