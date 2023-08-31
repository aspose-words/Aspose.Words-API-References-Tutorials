---
title: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
linktitle: Yeni İmza Satırı Oluşturun ve Sağlayıcı Kimliğini Ayarlayın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgesinde yeni bir imza satırı oluşturmayı ve sağlayıcı kimliğini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
Bu eğitimde, Aspose.Words for .NET ile Yeni İmza Satırı Oluşturma ve Sağlayıcı Kimliğini Ayarlama özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesine imza satırı eklemenizi, özel seçenekleri ayarlamanızı ve belgeyi imzalamanızı sağlar. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi ve Oluşturucuyu Oluşturma

Document sınıfının bir örneğini ve bir DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: İmza Hattı Seçeneklerini Ayarlama

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

## 3. Adım: İmza satırını ekleme

İmza satırını belgeye eklemek için DocumentBuilder nesnesinin InsertSignatureLine() yöntemini kullanın:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## 4. Adım: Sağlayıcı Kimliğini Ayarlayın

ProviderId özelliğini kullanarak imza satırının sağlayıcı kimliğini ayarlayın:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Kullanım durumunuz için doğru sağlayıcı kimliğini belirttiğinizden emin olun.

## Adım 5: Belgeyi Kaydedin

Değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Belgeyi kaydetmek için doğru yolu ve dosya adını belirttiğinizden emin olun.

## Adım 6: Belgeyi imzalama

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

Aspose.Words for .NET ile yeni bir imza satırı oluşturmak ve sağlayıcı kimliğini ayarlamak için tam kaynak kodu:

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

Bu adımları izleyerek Aspose.Words for .NET ile kolayca yeni bir imza satırı oluşturabilir ve sağlayıcı kimliğini Word belgenizde ayarlayabilirsiniz.

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturma ve sağlayıcı kimliğini ayarlama özelliğini araştırdık. Verilen adımları takip ederek, özel seçeneklerle kolayca bir imza satırı ekleyebilir ve bunu sağlayıcı kimliğini kullanarak belirli bir sağlayıcıyla ilişkilendirebilirsiniz. İmza satırları eklemek ve sağlayıcı bilgilerini özelleştirmek belgelerinizin orijinalliğini ve güvenilirliğini artırır. Aspose.Words for .NET, Word belgelerindeki imza satırları ve dijital sertifikalarla Kelime İşleme için güçlü bir API sunarak imzalama sürecini otomatikleştirmenize ve belgelerinizin geçerliliğini sağlamanıza olanak tanır.

### SSS'ler

#### S: İmza satırındaki sağlayıcı kimliği nedir?

C: İmza satırındaki sağlayıcı kimliği, dijital imzanın sağlayıcısını temsil eden benzersiz bir tanımlayıcıdır. İmzadan sorumlu kaynağın veya kuruluşun belirlenmesine yardımcı olur.

#### S: Aspose.Words for .NET'i kullanarak bir Word belgesinde nasıl yeni bir imza satırı oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturmak için şu adımları takip edebilirsiniz:
1.  Bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Bir örneğini oluşturun`SignatureLineOptions` sınıfını seçin ve istediğiniz imza satırı seçeneklerini ayarlayın.
3.  Kullan`InsertSignatureLine` yöntemi`DocumentBuilder` İmza satırını belgeye eklemek için nesne.

#### S: İmza satırının imzalayanın adı, unvanı ve talimatları gibi seçeneklerini özelleştirebilir miyim?

 C: Evet, imza satırının seçeneklerini özelleştirebilirsiniz.`SignatureLineOptions` sınıf, istenen seçenekleri ayarlamak için özellikler sağlar;`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, vb. İmza satırını eklemeden önce bu özellikleri değiştirebilirsiniz.

#### S: Bir imza satırı için sağlayıcı kimliğini ayarlamanın amacı nedir?

C: İmza satırı için sağlayıcı kimliğinin ayarlanması, dijital imzadan sorumlu kaynağın veya kuruluşun belirlenmesine yardımcı olur. İmzanın kaynağı ve güvenilirliği hakkında ek bilgi sağlayarak imzayı belirli bir sağlayıcı veya kuruluşla ilişkilendirmenize olanak tanır.

#### S: Aspose.Words for .NET'i kullanarak bir imza satırının sağlayıcı kimliğini nasıl ayarlayabilirim?

C: Aspose.Words for .NET kullanarak bir imza satırının sağlayıcı kimliğini ayarlamak için şu adımları takip edebilirsiniz:
1.  İmza satırını ekledikten sonra şuraya erişin:`ProviderId` mülkiyeti`SignatureLine` nesne.
2.  Yı kur`ProviderId` özelliğini kullanarak istenen sağlayıcı kimliği değerine ayarlayın.`Guid` veri tipi.

#### S: Yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra belgeyi imzalayabilir miyim?

 C: Evet, yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra belgeyi imzalayabilirsiniz. Belgeyi imzalamak için imza satırı kimliği, sağlayıcı kimliği, yorumlar ve imzalama zamanı dahil olmak üzere imza seçeneklerini ayarlamanız gerekir. Daha sonra şunu kullanın:`DigitalSignatureUtil.Sign` belgeyi dijital sertifika kullanarak imzalama yöntemi.

#### S: Bir Word belgesindeki her imza satırı için belirli bir sağlayıcı kimliği belirtebilir miyim?

C: Evet, bir Word belgesindeki her imza satırı için belirli bir sağlayıcı kimliği belirtebilirsiniz. Her imza satırını ekledikten sonra, söz konusu imza satırı için sağlayıcı kimliğini şu adrese erişerek ayarlayabilirsiniz:`ProviderId` ilgilinin mülkiyeti`SignatureLine` nesne.

#### S: Yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra değiştirilen belgeyi nasıl kaydedebilirim?

 C: Yeni bir imza satırı oluşturduktan ve sağlayıcı kimliğini ayarladıktan sonra değiştirilen belgeyi kaydetmek için`Save` yöntemi`Document` nesne. Belgeyi kaydetmek için doğru yolu ve dosya adını belirtin.

#### S: Aspose.Words for .NET imza satırları oluşturmak ve imzalamak için hangi dosya formatını destekliyor?

C: Aspose.Words for .NET, DOCX dosya formatında imza satırları oluşturmayı ve imzalamayı destekler. Sağlanan yöntemleri ve sınıfları kullanarak DOCX dosyalarında imza satırları oluşturabilir ve imzalayabilirsiniz.

#### S: İmzalandıktan sonra imza satırının sağlayıcı kimliğini veya diğer seçeneklerini değiştirebilir miyim?

C: İmza satırı bir kez imzalandıktan sonra belgenin içeriğinin bir parçası haline gelir ve ayrı olarak değiştirilemez. Sağlayıcı kimliğinin veya diğer seçeneklerin değiştirilmesi gibi imza satırında yapılacak herhangi bir değişiklik, mevcut imzanın kaldırılmasını ve yeni bir imza satırı oluşturulmasını gerektirir.