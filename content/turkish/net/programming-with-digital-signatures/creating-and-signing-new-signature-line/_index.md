---
title: Yeni İmza Satırı Oluşturma ve İmzalama
linktitle: Yeni İmza Satırı Oluşturma ve İmzalama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Word belgesinde yeni bir imza satırının nasıl oluşturulacağını ve imzalanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
Bu eğitimde, Aspose.Words for .NET ile yeni bir imza satırı oluşturma ve imzalama özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesine imza satırı eklemenizi, özel seçenekleri ayarlamanızı ve belgeyi imzalamanızı sağlar. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi ve Oluşturucuyu Oluşturma

Document sınıfının bir örneğini ve bir DocumentBuilder nesnesini oluşturarak başlayın:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: İmza satırını ekleme

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

### Aspose.Words for .NET Kullanarak Yeni İmza Satırı Oluşturmak ve İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile yeni bir imza satırı oluşturup imzalamak için gerekli kaynak kodun tamamı burada:

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

Bu adımları takip ederek Aspose.Words for .NET ile Word belgenizde kolayca yeni bir imza satırı oluşturup imzalayabileceksiniz.

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırının nasıl oluşturulacağını ve imzalanacağını öğrendik. Verilen adımları takip ederek belgenize kolayca bir imza satırı ekleyebilir, seçeneklerini özelleştirebilir ve belgeyi dijital sertifika kullanarak imzalayabilirsiniz. Belgelerinize imza satırları ve dijital imzalar eklemek, bunların özgünlüğünü ve bütünlüğünü geliştirerek onları daha güvenli ve güvenilir hale getirir. Aspose.Words for .NET, Word belgelerindeki imzalar ve dijital sertifikalarla Kelime İşleme için güçlü bir API sunarak imzalama sürecini otomatikleştirmenize ve belgelerinizin geçerliliğini sağlamanıza olanak tanır.

### SSS'ler

#### S: Word belgesindeki imza satırı nedir?

C: Word belgesindeki imza satırı, imzanın nereye yerleştirilmesi gerektiğini belirten bir yer tutucudur. Genellikle adı, unvanı ve tarihi içerir ve el yazısı veya dijital imza için alan sağlar.

#### S: Aspose.Words for .NET kullanarak bir Word belgesinde nasıl imza satırı oluşturabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde imza satırı oluşturmak için şu adımları takip edebilirsiniz:
1.  Bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` nesne.
2.  Kullan`InsertSignatureLine` yöntemi`DocumentBuilder` Belgeye yeni bir imza satırı eklemek için nesne.
3. Değiştirilen belgeyi kaydedin.

#### S: Ad, unvan ve tarih gibi imza satırı seçeneklerini özelleştirebilir miyim?

 C: Evet, imza satırı seçeneklerini özelleştirebilirsiniz.`SignatureLineOptions` sınıf, istenen seçenekleri ayarlamak için özellikler sağlar;`Signer`, `SignerTitle`, `ShowDate`, vb. İmza satırını eklemeden önce bu özellikleri değiştirebilirsiniz.

#### S: İmza satırı oluşturduktan sonra belgeyi nasıl imzalayabilirim?

 C: İmza satırı oluşturduktan sonra belgeyi imzalamak için imza seçeneklerini ayarlamanız ve`DigitalSignatureUtil` sınıf. İşte adımlar:
1.  Yı kur`SignatureLineId` içindeki mülk`SignOptions` İmza satırının ID'sine itiraz edin.
2.  Yı kur`SignatureLineImage` içindeki mülk`SignOptions` Kullanmak istediğiniz imzanın görseline itiraz edin.
3.  İmza sertifikasını şunu kullanarak yükleyin:`CertificateHolder` sınıf.
4.  Kullan`DigitalSignatureUtil.Sign` gerekli parametreleri sağlayarak belgeyi imzalama yöntemi.

#### S: Belgeyi imzalamak için dijital imza görseli kullanabilir miyim?

 C: Evet, belgeyi imzalamak için dijital imza görseli kullanabilirsiniz. Bunu yapmak için resim dosyasını sağlamanız gerekir.`SignOptions` kullanarak nesne`SignatureLineImage`mülk. Görüntü JPEG, PNG veya EMF gibi desteklenen herhangi bir görüntü formatında olabilir.

#### S: Word belgesinde yeni bir imza satırı oluşturmanın ve imzalamanın amacı nedir?

C: Aspose.Words for .NET kullanarak bir Word belgesinde yeni bir imza satırı oluşturup imzalamak, imza için bir yer tutucu eklemenize ve ardından belgeyi dijital bir sertifika kullanarak imzalamanıza olanak tanır. Bu süreç, onayın veya anlaşmanın kanıtını sunarak belgenin orijinalliğini ve bütünlüğünü sağlar.

#### S: Aspose.Words for .NET'i kullanarak bir Word belgesinde birden fazla imza satırı oluşturup imzalayabilir miyim?

C: Evet, Aspose.Words for .NET'i kullanarak bir Word belgesinde birden fazla imza satırı oluşturabilir ve imzalayabilirsiniz. Her imza satırının kendine özgü kimliği ve seçenekleri olabilir. Belgede ek imza satırları oluşturmak ve imzalamak için adımları tekrarlayabilirsiniz.

#### S: İmzalandıktan sonra imza satırını değiştirebilir miyim veya ek bilgi ekleyebilir miyim?

C: İmza satırı bir kez imzalandıktan sonra belgenin içeriğinin bir parçası haline gelir ve ayrı olarak değiştirilemez. Ancak imza satırından sonra ek bilgi veya içerik ekleyebilirsiniz.

#### S: İmza satırı içeren bir belgenin dijital imzasını doğrulayabilir miyim?

 C: Evet, Aspose.Words for .NET, imza satırı içeren bir belgenin dijital imzasını doğrulamak için işlevsellik sağlar. Şunu kullanabilirsiniz:`DigitalSignatureUtil.Verify` Dijital imzanın geçerliliğini ve orijinalliğini kontrol etme yöntemi.

#### S: Aspose.Words for .NET imza satırları oluşturmak ve imzalamak için hangi dosya formatını destekliyor?

C: Aspose.Words for .NET, DOCX dosya formatında imza satırları oluşturmayı ve imzalamayı destekler. Sağlanan yöntemleri ve sınıfları kullanarak DOCX dosyalarında imza satırları oluşturabilir ve imzalayabilirsiniz.