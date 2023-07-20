---
title: Yeni İmza Hattı Oluşturma ve İmzalama
linktitle: Yeni İmza Hattı Oluşturma ve İmzalama
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde yeni bir imza satırı oluşturmayı ve imzalamayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
Bu öğreticide, Aspose.Words for .NET ile yeni bir imza satırı oluştur ve imzala özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesine imza satırı eklemenize, özel seçenekler ayarlamanıza ve belgeyi imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi ve Oluşturucuyu Oluşturma

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İmza satırının eklenmesi

Belgeye yeni bir imza satırı eklemek için DocumentBuilder nesnesinin InsertSignatureLine() yöntemini kullanın:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 3. Adım: Belgeyi kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

## 4. Adım: Belgeyi imzalama

Belgeyi imzalamak için imza seçeneklerini ayarlamanız ve DigitalSignatureUtil sınıfını kullanmanız gerekir:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Belge, imza satırı resmi ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Yeni İmza Satırı Oluşturmak ve İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile yeni bir imza satırı oluşturmak ve imzalamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile Word belgenizde kolayca yeni bir imza satırı oluşturabilecek ve imzalayabileceksiniz.

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturmayı ve imzalamayı öğrendik. Sağlanan adımları izleyerek, belgenize kolayca bir imza satırı ekleyebilir, seçeneklerini özelleştirebilir ve belgeyi bir dijital sertifika kullanarak imzalayabilirsiniz. Belgelerinize imza satırları ve dijital imzalar eklemek, orijinalliklerini ve bütünlüklerini geliştirerek onları daha güvenli ve güvenilir hale getirir. Aspose.Words for .NET, Word belgelerinde imzalar ve dijital sertifikalar ile Word Processing için güçlü bir API sağlayarak, imzalama sürecini otomatikleştirmenize ve belgelerinizin geçerliliğini sağlamanıza olanak tanır.

### SSS

#### S: Word belgesindeki imza satırı nedir?

C: Word belgesindeki imza satırı, imzanın nereye yerleştirilmesi gerektiğini gösteren bir yer tutucudur. Genellikle adı, unvanı ve tarihi içerir ve el yazısı veya dijital imza için alan sağlar.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinde nasıl imza satırı oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde imza satırı oluşturmak için şu adımları takip edebilirsiniz:
1.  örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Kullan`InsertSignatureLine` yöntemi`DocumentBuilder` Belgeye yeni bir imza satırı eklemek için nesne.
3. Değiştirilen belgeyi kaydedin.

#### S: Ad, unvan ve tarih gibi imza satırı seçeneklerini özelleştirebilir miyim?

 C: Evet, imza satırı seçeneklerini özelleştirebilirsiniz. bu`SignatureLineOptions` class gibi istenen seçenekleri ayarlamak için özellikler sağlar.`Signer`, `SignerTitle`, `ShowDate`, vb. İmza satırını eklemeden önce bu özellikleri değiştirebilirsiniz.

#### S: İmza satırı oluşturduktan sonra belgeyi nasıl imzalayabilirim?

 A: İmza satırı oluşturduktan sonra belgeyi imzalamak için imza seçeneklerini ayarlamanız ve`DigitalSignatureUtil` sınıf. İşte adımlar:
1.  Yı kur`SignatureLineId` mülkiyet`SignOptions` imza satırının kimliğine itiraz edin.
2.  Yı kur`SignatureLineImage` mülkiyet`SignOptions` Kullanmak istediğiniz imzanın görüntüsüne itiraz edin.
3.  kullanarak imzalama sertifikasını yükleyin.`CertificateHolder` sınıf.
4.  Kullan`DigitalSignatureUtil.Sign` gerekli parametreleri sağlayarak belgeyi imzalama yöntemi.

#### S: Belgeyi imzalamak için dijital imza görüntüsü kullanabilir miyim?

 Y: Evet, belgeyi imzalamak için dijital imza görüntüsü kullanabilirsiniz. Bunu yapmak için, görüntü dosyasını sağlamanız gerekir.`SignOptions` kullanarak nesne`SignatureLineImage`mülk. Görüntü, JPEG, PNG veya EMF gibi desteklenen herhangi bir görüntü biçiminde olabilir.

#### S: Bir Word belgesinde yeni bir imza satırı oluşturmanın ve imzalamanın amacı nedir?

C: Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturmak ve imzalamak, imza için bir yer tutucu eklemenize ve ardından bir dijital sertifika kullanarak belgeyi imzalamanıza olanak tanır. Bu süreç, onay veya anlaşma kanıtı sağlayarak belgenin orijinalliğini ve bütünlüğünü sağlar.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinde birden fazla imza satırı oluşturabilir ve imzalayabilir miyim?

C: Evet, Aspose.Words for .NET kullanarak bir Word belgesinde birden çok imza satırı oluşturabilir ve imzalayabilirsiniz. Her imza satırının kendine özgü kimliği ve seçenekleri olabilir. Belgede ek imza satırları oluşturmak ve imzalamak için adımları tekrarlayabilirsiniz.

#### S: İmza satırını değiştirebilir miyim veya imzalandıktan sonra ek bilgiler ekleyebilir miyim?

C: Bir imza satırı imzalandıktan sonra, belgenin içeriğinin bir parçası haline gelir ve ayrıca değiştirilemez. Ancak, imzalı imza satırından sonra ek bilgi veya içerik ekleyebilirsiniz.

#### S: İmza satırı içeren bir belgenin dijital imzasını doğrulayabilir miyim?

 C: Evet, Aspose.Words for .NET, imza satırı içeren bir belgenin dijital imzasını doğrulamak için işlevsellik sağlar. kullanabilirsiniz`DigitalSignatureUtil.Verify` dijital imzanın geçerliliğini ve gerçekliğini kontrol etme yöntemi.

#### S: Aspose.Words for .NET, imza satırları oluşturmak ve imzalamak için hangi dosya formatını destekliyor?

Y: Aspose.Words for .NET, DOCX dosya biçiminde imza satırları oluşturmayı ve imzalamayı destekler. Sağlanan yöntemleri ve sınıfları kullanarak DOCX dosyalarında imza satırları oluşturabilir ve imzalayabilirsiniz.