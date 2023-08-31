---
title: İmza Sağlayıcı Kimliğini Word Belgesinde Ayarlama
linktitle: İmza Sağlayıcı Kimliğini Word Belgesinde Ayarlama
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinde imza sağlayıcı kimliğinin nasıl ayarlanacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-digital-signatures/set-signature-provider-id/
---
Bu eğitimde, Aspose.Words for .NET ile Signature Provider ID özelliğini kullanma adımlarında size yol göstereceğiz. Bu özellik, bir Word belgesindeki bir imza satırı için imza sağlayıcı kimliğini belirtmenize olanak tanır. Aşağıdaki adımları takip et:

## 1. Adım: Belgeyi yükleme ve imza satırına erişme

İmza satırını içeren belgeyi yükleyerek başlayın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2. Adım: İmza Seçeneklerini Ayarlama

SignOptions sınıfının bir örneğini oluşturun ve sağlayıcı kimliği dahil imzalama seçeneklerini ayarlayın:

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

### Aspose.Words for .NET kullanarak Signature Provider Id Ayarlamak için örnek kaynak kodu

Aspose.Words for .NET ile imza sağlayıcı kimliğini ayarlamak için eksiksiz kaynak kodu burada:

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

Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki bir imza satırı için imza sağlayıcı kimliğinin nasıl ayarlanacağını öğrendik. Verilen adımları izleyerek belgeyi kolayca yükleyebilir, imza satırına erişebilir, sağlayıcı kimliğini ayarlayabilir ve belgeyi imzalayabilirsiniz. İmza sağlayıcı kimliğini ayarlama yeteneği, Word belgelerinizin güvenliğini ve bütünlüğünü artırarak imzalayanın kimliğini ve güvenilirliğini belirlemeye yardımcı olur. Aspose.Words for .NET, imza sürecini kolaylıkla özelleştirmenize ve yönetmenize olanak tanıyan, dijital imzalarla Kelime İşleme için sağlam bir API sağlar.

### Word belgesinde imza sağlayıcı kimliğini ayarlamak için SSS

#### S: Word belgesindeki imza sağlayıcı kimliği nedir?

Y: Word belgesindeki imza sağlayıcı kimliği, dijital imza sağlayıcısını belirten benzersiz bir tanımlayıcıdır. Dijital imzayı oluşturmaktan ve yönetmekten sorumlu varlık veya organizasyonu belirlemeye yardımcı olur.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki bir imza satırı için imza sağlayıcı kimliğini nasıl ayarlayabilirim?

C: Aspose.Words for .NET kullanarak bir Word belgesindeki bir imza satırı için imza sağlayıcı kimliğini ayarlamak için şu adımları takip edebilirsiniz:
1.  kullanarak belgeyi yükleyin.`Document` class ve belge dosyasının yolunu belirtin.
2.  Uygun yöntemi veya özelliği kullanarak imza satırına erişin. Örneğin, kullanabilirsiniz`GetChild` imza çizgisi şeklini alma yöntemi.
3. Sağlayıcı kimliğini imza satırından alın.
4.  örneğini oluşturun`SignOptions`sınıflandırın ve ayarlayın`ProviderId` özellik, alınan sağlayıcı kimliğine.
5.  Kullan`DigitalSignatureUtil.Sign` dahil olmak üzere gerekli parametreleri sağlayarak belgeyi imzalama yöntemi`SignOptions` nesne.

#### S: Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırına nasıl erişebilirim?

 C: Aspose.Words for .NET kullanarak bir Word belgesindeki imza satırına erişmek için, imza satırı şeklini belgenin yapısından almak için uygun yöntemi veya özelliği kullanabilirsiniz. Örneğin,`GetChild` İstenen imza çizgisi şeklini elde etmek için uygun parametrelerle yöntem.

#### S: Bir Word belgesinde birden çok imza satırı için imza sağlayıcı kimliğini ayarlayabilir miyim?

 C: Evet, bir Word belgesinde birden çok imza satırı için imza sağlayıcı kimliğini ayarlayabilirsiniz. Belgedeki imza satırları koleksiyonunu yineleyebilir ve her imza satırı için sağlayıcı kimliğini ayrı ayrı ayarlayabilirsiniz.`SignOptions.ProviderId` mülk.

#### S: Bir Word belgesindeki imza sağlayıcı kimliğinin amacı nedir?

C: Bir Word belgesindeki imza sağlayıcı kimliği, dijital imzayı oluşturmaktan ve yönetmekten sorumlu kişi veya kuruluşu belirleme amacına hizmet eder. Dijital imzayı belirli bir sağlayıcıyla ilişkilendirerek özgünlüğünün ve güvenilirliğinin oluşturulmasına yardımcı olur.

#### S: Bir Word belgesinde imza sağlayıcı kimliğini ayarlamak için ne tür dijital sertifikalar kullanılabilir?

Y: Bir Word belgesinde imza sağlayıcı kimliğini ayarlamak için X.509 dijital sertifikalarını uygun sağlayıcı bilgileriyle kullanabilirsiniz. Dijital sertifika, güvenilir bir sertifika yetkilisi (CA) tarafından verilmeli ve sağlayıcıyı tanımlamak için gerekli meta verileri içermelidir.