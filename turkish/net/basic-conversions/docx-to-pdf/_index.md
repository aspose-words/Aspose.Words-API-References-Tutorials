---
title: Docx'ten Pdf'ye
linktitle: Docx'ten Pdf'ye
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini Docx'ten PDF'ye nasıl dönüştüreceğinizi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-pdf/
---

Bu adım adım öğreticide, Docx formatındaki bir Word belgesini PDF'ye dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` Docx biçimindeki kaynak belgenizin yolunu içeren nesne:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 2. Adım: Belgeyi PDF Formatında Kaydetme

 Ardından, çağrı yaparak belgeyi PDF formatında kaydedin.`Save` yöntemi`Document` nesne ve çıktı PDF belgesi için yol ve dosya adını sağlama:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Docx formatındaki bir Word belgesini başarıyla PDF'ye dönüştürdünüz.

### Aspose.Words for .NET kullanan Docx To Pdf için örnek kaynak kodu

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.
