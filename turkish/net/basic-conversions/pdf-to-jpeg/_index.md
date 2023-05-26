---
title: Pdf'den Jpeg'e
linktitle: Pdf'den Jpeg'e
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak PDF belgelerini JPEG görüntülere nasıl dönüştüreceğinizi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/pdf-to-jpeg/
---

Bu adım adım eğitimde, bir PDF belgesini JPEG görüntülere dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` PDF belgenizin yolunu sağlayarak itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Adım 2: Belgeyi Jpeg Görüntüleri Olarak Kaydetme

 Ardından, belgeyi arayarak Jpeg görüntüleri olarak kaydedin.`Save` yöntemi`Document` nesne ve çıktı Jpeg görüntüleri için yol ve dosya adı sağlama:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

Bu kadar! Aspose.Words for .NET kullanarak bir PDF belgesini başarıyla Jpeg resimlere dönüştürdünüz.

### Aspose.Words for .NET kullanan Pdf To Jpeg için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.