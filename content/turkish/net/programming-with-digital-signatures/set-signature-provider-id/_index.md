---
title: Word Belgesinde İmza Sağlayıcı Kimliğini Ayarlama
linktitle: Word Belgesinde İmza Sağlayıcı Kimliğini Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinde imza sağlayıcı kimliğini nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/set-signature-provider-id/
---
Bu eğitimde, İmza Sağlayıcı Kimliğini Ayarla özelliğini Aspose.Words for .NET ile kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesindeki imza satırı için imza sağlayıcı kimliğini belirtmenize olanak tanır. Aşağıdaki adımları takip et:

## Adım 1: Belgeyi yükleme ve imza satırına erişme

İmza satırını içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Adım 2: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve sağlayıcı kimliği de dahil olmak üzere imzalama seçeneklerini ayarlayın:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## 3. Adım: Belgeyi imzalama

Belgeyi imzalamak için DigitalSignatureUtil sınıfını kullanmalı ve imzalama sertifikasını belirtmelisiniz:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Belge, sertifika ve imzalı belge için doğru yolları belirttiğinizden emin olun.

### Aspose.Words for .NET kullanarak İmza Sağlayıcı Kimliğini Ayarlama için örnek kaynak kodu

Aspose.Words for .NET ile imza sağlayıcı kimliğini ayarlamak için gereken kaynak kodun tamamı burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Aspose.Words for .NET ile Word belgenizdeki İmza Sağlayıcı Kimliğini tamamlayın.


## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırı için imza sağlayıcı kimliğinin nasıl ayarlanacağını öğrendik. Verilen adımları takip ederek belgeyi kolayca yükleyebilir, imza satırına erişebilir, sağlayıcı kimliğini ayarlayabilir ve belgeyi imzalayabilirsiniz. İmza sağlayıcı kimliğini ayarlama yeteneği, imzalayanın kimliğinin ve güvenilirliğinin belirlenmesine yardımcı olarak Word belgelerinizin güvenliğini ve bütünlüğünü artırır. Aspose.Words for .NET, dijital imzalarla Kelime İşleme için güçlü bir API sunarak imza sürecini kolaylıkla özelleştirmenize ve yönetmenize olanak tanır.

### Word belgesinde imza sağlayıcı kimliğini ayarlamakla ilgili SSS

#### S: Word belgesindeki imza sağlayıcı kimliği nedir?

C: Word belgesindeki imza sağlayıcı kimliği, dijital imza sağlayıcısını belirten benzersiz bir tanımlayıcıdır. Dijital imzanın oluşturulmasından ve yönetilmesinden sorumlu kurum veya kuruluşun belirlenmesine yardımcı olur.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırı için imza sağlayıcı kimliğini nasıl ayarlayabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırı için imza sağlayıcı kimliğini ayarlamak için şu adımları takip edebilirsiniz:
1.  Belgeyi kullanarak yükleyin`Document` sınıfını seçin ve belge dosyasının yolunu belirtin.
2.  Uygun yöntemi veya özelliği kullanarak imza satırına erişin. Örneğin, kullanabilirsiniz`GetChild` İmza çizgisi şeklini alma yöntemi.
3. Sağlayıcı kimliğini imza satırından alın.
4.  Bir örneğini oluşturun`SignOptions`sınıfı seçin ve ayarlayın`ProviderId` özelliği alınan sağlayıcı kimliğine aktarın.
5.  Kullan`DigitalSignatureUtil.Sign` dahil olmak üzere gerekli parametreleri sağlayarak belgeyi imzalama yöntemi`SignOptions` nesne.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırına nasıl erişebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırına erişmek için, imza çizgisi şeklini belgenin yapısından almak üzere uygun yöntemi veya özelliği kullanabilirsiniz. Örneğin, şunları kullanabilirsiniz:`GetChild` İstenilen imza çizgisi şeklini elde etmek için uygun parametrelerle yöntem.

#### S: Bir Word belgesindeki birden çok imza satırı için imza sağlayıcı kimliğini ayarlayabilir miyim?

 C: Evet, bir Word belgesindeki birden çok imza satırı için imza sağlayıcı kimliğini ayarlayabilirsiniz. Belgedeki imza satırlarının koleksiyonunu yineleyebilir ve her imza satırı için sağlayıcı kimliğini ayrı ayrı ayarlayabilirsiniz.`SignOptions.ProviderId` mülk.

#### S: Word belgesindeki imza sağlayıcı kimliğinin amacı nedir?

C: Bir Word belgesindeki imza sağlayıcı kimliği, dijital imzayı oluşturmaktan ve yönetmekten sorumlu kuruluş veya kuruluşu tanımlama amacına hizmet eder. Dijital imzayı belirli bir sağlayıcıyla ilişkilendirerek orijinalliğini ve güvenilirliğini belirlemeye yardımcı olur.

#### S: Bir Word belgesinde imza sağlayıcı kimliğini ayarlamak için ne tür dijital sertifikalar kullanılabilir?

C: Bir Word belgesinde imza sağlayıcı kimliğini ayarlamak için X.509 dijital sertifikalarını uygun sağlayıcı bilgileriyle birlikte kullanabilirsiniz. Dijital sertifika, güvenilir bir sertifika yetkilisi (CA) tarafından verilmeli ve sağlayıcıyı tanımlamak için gerekli meta verileri içermelidir.