---
title: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
linktitle: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde yeni bir imza satırı oluşturmayı ve sağlayıcı kimliğini ayarlamayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
Bu eğitimde, Aspose.Words for .NET ile Yeni İmza Satırı Oluştur ve Sağlayıcı Kimliği Ayarla özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesine imza satırı eklemenize, özel seçenekler ayarlamanıza ve belgeyi imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi ve Oluşturucuyu Oluşturma

Document sınıfının bir örneğini ve DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İmza Satırı Seçeneklerini Ayarlama

SignatureLineOptions sınıfının bir örneğini oluşturun ve istediğiniz seçenekleri ayarlayın:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## 3. Adım: İmza satırının eklenmesi

İmza satırını belgeye eklemek için DocumentBuilder nesnesinin InsertSignatureLine() yöntemini kullanın:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 4. Adım: Sağlayıcı Kimliğini Ayarlayın

ProviderId özelliğini kullanarak imza satırı için sağlayıcı kimliğini ayarlayın:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Kullanım durumunuz için doğru sağlayıcı kimliğini belirttiğinizden emin olun.

## 5. Adım: Belgeyi Kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

## 6. Adım: Belgeyi imzalama

Belgeyi imzalamak için imza seçeneklerini ayarlamanız ve DigitalSignatureUtil sınıfını kullanmanız gerekir:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Belge, sertifika ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Yeni İmza Satırı Oluşturma ve Sağlayıcı Kimliğini Ayarlama için örnek kaynak kodu

Aspose.Words for .NET ile yeni bir imza satırı oluşturmak ve sağlayıcı kimliğini ayarlamak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

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

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Bu adımları izleyerek, Aspose.Words for .NET ile kolayca yeni bir imza satırı oluşturabilir ve Word belgenizde sağlayıcı kimliğini ayarlayabilirsiniz.

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturma ve sağlayıcı kimliğini ayarlama özelliğini inceledik. Sağlanan adımları izleyerek, özel seçeneklerle kolayca bir imza satırı ekleyebilir ve sağlayıcı kimliğini kullanarak belirli bir sağlayıcıyla ilişkilendirebilirsiniz. İmza satırları eklemek ve sağlayıcı bilgilerini özelleştirmek, belgelerinizin gerçekliğini ve güvenilirliğini artırır. Aspose.Words for .NET, Word belgelerinde imza satırları ve dijital sertifikalar içeren, Word İşleme için güçlü bir API sağlayarak imzalama sürecini otomatikleştirmenize ve belgelerinizin geçerliliğini sağlamanıza olanak tanır.

### SSS

#### S: İmza satırındaki sağlayıcı kimliği nedir?

C: İmza satırındaki sağlayıcı kimliği, dijital imzanın sağlayıcısını temsil eden benzersiz bir tanımlayıcıdır. İmzadan sorumlu kaynağı veya kuruluşu belirlemeye yardımcı olur.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinde nasıl yeni bir imza satırı oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturmak için şu adımları takip edebilirsiniz:
1.  örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  örneğini oluşturun`SignatureLineOptions` class'ı seçin ve istediğiniz imza satırı seçeneklerini ayarlayın.
3.  Kullan`InsertSignatureLine` yöntemi`DocumentBuilder` imza satırını belgeye eklemek için nesne.

#### S: İmzalayanın adı, unvanı ve talimatlar gibi imza satırı seçeneklerini özelleştirebilir miyim?

 C: Evet, imza satırı seçeneklerini özelleştirebilirsiniz. bu`SignatureLineOptions` class gibi istenen seçenekleri ayarlamak için özellikler sağlar.`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, vb. İmza satırını eklemeden önce bu özellikleri değiştirebilirsiniz.

#### S: Bir imza satırı için sağlayıcı kimliğini belirlemenin amacı nedir?

Y: Bir imza satırı için sağlayıcı kimliğinin ayarlanması, dijital imzadan sorumlu kaynağın veya kuruluşun belirlenmesine yardımcı olur. İmzanın kaynağı ve güvenilirliği hakkında ek bilgi sağlayarak, imzayı belirli bir sağlayıcı veya kuruluşla ilişkilendirmenize olanak tanır.

#### S: Aspose.Words for .NET kullanarak bir imza satırı için sağlayıcı kimliğini nasıl ayarlayabilirim?

C: Aspose.Words for .NET kullanarak bir imza satırı için sağlayıcı kimliğini ayarlamak için şu adımları takip edebilirsiniz:
1.  İmza satırını ekledikten sonra,`ProviderId` mülkiyeti`SignatureLine` nesne.
2.  Yı kur`ProviderId` özelliğini kullanarak istenen sağlayıcı kimliği değerine`Guid` veri tipi.

#### S: Yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra belgeyi imzalayabilir miyim?

 C: Evet, yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra belgeyi imzalayabilirsiniz. Belgeyi imzalamak için imza satırı kimliği, sağlayıcı kimliği, yorumlar ve imza zamanı gibi imza seçeneklerini ayarlamanız gerekir. Ardından,`DigitalSignatureUtil.Sign` dijital sertifika kullanarak belgeyi imzalama yöntemi.

#### S: Bir Word belgesindeki her imza satırı için belirli bir sağlayıcı kimliği belirtebilir miyim?

C: Evet, bir Word belgesindeki her imza satırı için belirli bir sağlayıcı kimliği belirtebilirsiniz. Her bir imza satırını ekledikten sonra, şu adrese erişerek söz konusu imza satırı için sağlayıcı kimliğini ayarlayabilirsiniz:`ProviderId` ilgili mülkiyet`SignatureLine` nesne.

#### S: Yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra değiştirilen belgeyi nasıl kaydedebilirim?

 C: Yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra değiştirilen belgeyi kaydetmek için`Save` yöntemi`Document` nesne. Belgeyi kaydetmek için doğru yolu ve dosya adını belirtin.

#### S: Aspose.Words for .NET, imza satırları oluşturmak ve imzalamak için hangi dosya formatını destekliyor?

Y: Aspose.Words for .NET, DOCX dosya biçiminde imza satırları oluşturmayı ve imzalamayı destekler. Sağlanan yöntemleri ve sınıfları kullanarak DOCX dosyalarında imza satırları oluşturabilir ve imzalayabilirsiniz.

#### S: İmzalandıktan sonra bir imza satırının sağlayıcı kimliğini veya diğer seçeneklerini değiştirebilir miyim?

C: Bir imza satırı imzalandıktan sonra, belgenin içeriğinin bir parçası haline gelir ve ayrıca değiştirilemez. Sağlayıcı kimliğini veya diğer seçenekleri değiştirmek gibi imza satırında yapılacak herhangi bir değişiklik, mevcut imzanın kaldırılmasını ve yeni bir imza satırı oluşturulmasını gerektirecektir.