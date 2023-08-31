---
title: Word Belgesinde Mevcut İmza Satırını İmzalamak
linktitle: Word Belgesinde Mevcut İmza Satırını İmzalamak
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki mevcut bir imza satırını nasıl imzalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Bu öğreticide, Aspose.Words for .NET ile mevcut bir imza satırının imza özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesinde zaten mevcut olan bir imza satırını dijital olarak imzalamanıza olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve imza satırına erişme

Mevcut imza satırını içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2. Adım: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve imza satırı kimliği ve imza satırı görüntüsü dahil olmak üzere imza seçeneklerini ayarlayın:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

İmza satırı görüntüsüne giden doğru yolu belirttiğinizden emin olun.

## 3. Adım: Sertifikanın yüklenmesi

CertificateHolder sınıfını kullanarak imzalama sertifikasını yükleyerek başlayın:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Sertifikanızın ve ilişkili parolanızın doğru yolunu belirttiğinizden emin olun.

## 4. Adım: Mevcut imza satırının imzalanması

Mevcut imza satırını imzalamak için DigitalSignatureUtil sınıfını kullanın:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Kaynak belge, imzalı belge ve sertifika için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak Mevcut İmza Satırını İmzalamak için örnek kaynak kodu

Aspose.Words for .NET ile mevcut bir imza satırını imzalamak için eksiksiz kaynak kodu burada:


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

Bu adımları izleyerek bir Word belgesindeki mevcut bir imza satırını Aspose.Words for .NET ile kolayca imzalayabilirsiniz.

## Çözüm

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut bir imza satırının nasıl imzalanacağını öğrendik. Verilen adımları izleyerek belgeyi kolayca yükleyebilir, mevcut imza satırına erişebilir, imzalama seçeneklerini ayarlayabilir ve belgeyi imzalayabilirsiniz. Mevcut bir imza satırını imzalama yeteneği, Word belgelerinizdeki önceden tanımlanmış alanlara dijital imzalar eklemek için uygun bir yol sağlayarak belge bütünlüğünü ve kimlik doğrulamasını sağlar. Aspose.Words for .NET, imzalama sürecini özelleştirmenize ve Word belgelerinizin güvenliğini artırmanıza olanak tanıyan, dijital imzalarla Kelime İşleme için güçlü bir API sunar.

### SSS

#### S: Word belgesindeki mevcut imza satırı nedir?

C: Word belgesindeki mevcut bir imza satırı, imzanın yerleştirilebileceği önceden tanımlanmış bir alandır. Tipik olarak belgede bir şekil veya nesne ile temsil edilir ve imzalayanın dijital imzasını eklemesi için belirlenmiş bir alan görevi görür.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut bir imza satırını nasıl imzalayabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut bir imza satırını imzalamak için şu adımları takip edebilirsiniz:
1.  kullanarak belgeyi yükleyin.`Document` class ve belge dosyasının yolunu belirtin.
2.  Uygun yöntemi veya özelliği kullanarak mevcut imza satırına erişin. Örneğin, kullanabilirsiniz`GetChild` imza çizgisi şeklini alma yöntemi.
3.  örneğini oluşturun`SignOptions`sınıflandırın ve ayarlayın`SignatureLineId` özellik mevcut imza satırının kimliğine.
4.  Yı kur`SignatureLineImage` mülkiyeti`SignOptions` dijital imzayı temsil eden görüntüye sınıf.
5.  kullanarak imzalama sertifikasını yükleyin.`CertificateHolder` class ve gerekli sertifika ve şifreyi sağlayın.
6.  Kullan`DigitalSignatureUtil.Sign` dahil olmak üzere gerekli parametreleri sağlayarak belgeyi imzalama yöntemi`SignOptions` nesne.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut imza satırına nasıl erişebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki mevcut imza satırına erişmek için, belgenin yapısından imza satırı şeklini almak için uygun yöntemi veya özelliği kullanabilirsiniz. Örneğin,`GetChild` İstenen imza çizgisi şeklini elde etmek için uygun parametrelerle yöntem.

#### S: Dijital imzanın görünümünü mevcut bir imza satırında özelleştirebilir miyim?

C: Evet, imzayı temsil eden bir görüntü dosyası sağlayarak dijital imzanın mevcut bir imza satırındaki görünümünü özelleştirebilirsiniz. Görüntü bir logo, el yazısı imza veya imzanın başka herhangi bir grafik gösterimi olabilir. ayarlayabilirsiniz`SignatureLineImage` mülkiyeti`SignOptions` görüntü dosyasının baytlarına sınıf.

#### S: Bir Word belgesinde birden çok mevcut imza satırını imzalayabilir miyim?
 C: Evet, bir Word belgesinde birden çok mevcut imza satırını imzalayabilirsiniz. Her bir imza satırı için ayrı ayrı adımları izlemeniz ve uygun ayarı yapmanız gerekir.`SignatureLineId` Ve`SignatureLineImage` içindeki değerler`SignOptions` her imza satırı için nesne.

#### S: Mevcut bir imza satırındaki dijital imza için resim dosyası hangi formatta olmalıdır?

 Y: Mevcut bir imza satırındaki dijital imza için görüntü dosyası PNG, JPEG, BMP veya GIF gibi çeşitli biçimlerde olabilir. Dosya yolunu belirtebilir veya görüntü dosyasının baytlarını okuyabilir ve onu`SignatureLineImage` mülkiyeti`SignOptions` sınıf.
