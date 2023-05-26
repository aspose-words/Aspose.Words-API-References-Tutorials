---
title: Pdf'den Docx'e
linktitle: Pdf'den Docx'e
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak PDF belgelerini Docx formatına nasıl dönüştüreceğinizi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/pdf-to-docx/
---

Bu adım adım öğreticide, bir PDF belgesini Docx formatına dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` PDF belgenizin yolunu sağlayarak itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Adım 2: Belgeyi Docx Formatında Kaydetme

 Sonra, çağırarak belgeyi Docx formatında kaydedin.`Save` yöntemi`Document`nesne ve çıktı Docx belgesi için yol ve dosya adını sağlama:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir PDF belgesini başarıyla Docx formatına dönüştürdünüz.

### Aspose.Words for .NET kullanan Pdf To Docx için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.