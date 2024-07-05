---
title: Word Belgesinde Mevcut İmza Satırının İmzalanması
linktitle: Word Belgesinde Mevcut İmza Satırının İmzalanması
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde mevcut bir imza satırını nasıl imzalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Bu eğitimde, mevcut bir imza satırının imza özelliğini Aspose.Words for .NET ile kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesinde zaten mevcut olan bir imza satırını dijital olarak imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi yükleme ve imza satırına erişme

Mevcut imza satırını içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Adım 2: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve imza satırı kimliği ve imza satırı görüntüsü de dahil olmak üzere imza seçeneklerini ayarlayın:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

İmza satırı resminin doğru yolunu belirttiğinizden emin olun.

## 3. Adım: Sertifikayı yükleme

SertifikaHolder sınıfını kullanarak imzalama sertifikasını yükleyerek başlayın:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Sertifikanızın ve ilişkili şifrenizin doğru yolunu belirttiğinizden emin olun.

## Adım 4: Mevcut imza satırını imzalama

Mevcut imza satırını imzalamak için DigitalSignatureUtil sınıfını kullanın:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Kaynak belge, imzalı belge ve sertifika için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET Kullanarak Mevcut İmza Satırını İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile mevcut bir imza satırını imzalamak için gereken kaynak kodun tamamı burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Bu adımları izleyerek, Aspose.Words for .NET ile bir Word belgesindeki mevcut bir imza satırını kolayca imzalayabilirsiniz.

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinde mevcut bir imza satırının nasıl imzalanacağını öğrendik. Verilen adımları takip ederek belgeyi kolayca yükleyebilir, mevcut imza satırına erişebilir, imzalama seçeneklerini ayarlayabilir ve belgeyi imzalayabilirsiniz. Mevcut bir imza satırını imzalama yeteneği, Word belgelerinizdeki önceden tanımlanmış alanlara dijital imzalar eklemenin kolay bir yolunu sağlayarak belge bütünlüğünü ve kimlik doğrulamasını sağlar. Aspose.Words for .NET, dijital imzalarla Kelime İşleme için güçlü bir API sunarak imzalama sürecini özelleştirmenize ve Word belgelerinizin güvenliğini artırmanıza olanak tanır.

### SSS'ler

#### S: Word belgesindeki mevcut imza satırı nedir?

C: Word belgesindeki mevcut imza satırı, imzanın yerleştirilebileceği önceden tanımlanmış bir alandır. Genellikle belgede bir şekil veya nesne ile temsil edilir ve imzalayanın dijital imzasını eklemesi için belirlenmiş bir alan görevi görür.

#### S: Aspose.Words for .NET'i kullanarak bir Word belgesinde mevcut bir imza satırını nasıl imzalayabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesinde mevcut bir imza satırını imzalamak için şu adımları takip edebilirsiniz:
1.  Belgeyi kullanarak yükleyin`Document` sınıfını seçin ve belge dosyasının yolunu belirtin.
2.  Uygun yöntemi veya özelliği kullanarak mevcut imza satırına erişin. Örneğin şunları kullanabilirsiniz:`GetChild` İmza çizgisi şeklini alma yöntemi.
3.  Bir örneğini oluşturun`SignOptions` sınıfı seçin ve ayarlayın`SignatureLineId` özelliği mevcut imza satırının kimliğine aktarın.
4.  Yı kur`SignatureLineImage` mülkiyeti`SignOptions` dijital imzayı temsil eden görüntüye sınıf.
5.  İmza sertifikasını şunu kullanarak yükleyin:`CertificateHolder` sınıfa girin ve gerekli sertifikayı ve şifreyi sağlayın.
6.  Kullan`DigitalSignatureUtil.Sign` dahil olmak üzere gerekli parametreleri sağlayarak belgeyi imzalama yöntemi`SignOptions` nesne.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut imza satırına nasıl erişebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut imza satırına erişmek için, belgenin yapısından imza çizgisi şeklini almak üzere uygun yöntemi veya özelliği kullanabilirsiniz. Örneğin, şunları kullanabilirsiniz:`GetChild` İstenilen imza çizgisi şeklini elde etmek için uygun parametrelerle yöntem.

#### S: Dijital imzanın görünümünü mevcut bir imza satırında özelleştirebilir miyim?

C: Evet, imzayı temsil eden bir görüntü dosyası sağlayarak dijital imzanın mevcut imza satırındaki görünümünü özelleştirebilirsiniz. Görüntü bir logo, el yazısı imza veya imzanın başka herhangi bir grafiksel temsili olabilir. Ayarlayabilirsiniz`SignatureLineImage` mülkiyeti`SignOptions` görüntü dosyasının baytlarına göre sınıf.

#### S: Bir Word belgesinde birden fazla mevcut imza satırını imzalayabilir miyim?
 C: Evet, bir Word belgesinde mevcut birden fazla imza satırını imzalayabilirsiniz. Her imza satırı için adımları ayrı ayrı izlemeniz ve uygun imza satırını ayarlamanız gerekir.`SignatureLineId` Ve`SignatureLineImage` içindeki değerler`SignOptions` Her imza satırı için nesne.

#### S: Mevcut bir imza satırındaki dijital imza için görüntü dosyası hangi formatta olmalıdır?

 C: Mevcut bir imza satırındaki dijital imzanın görüntü dosyası PNG, JPEG, BMP veya GIF gibi çeşitli formatlarda olabilir. Dosya yolunu belirtebilir veya görüntü dosyasının baytlarını okuyabilir ve bunu`SignatureLineImage` mülkiyeti`SignOptions` sınıf.
