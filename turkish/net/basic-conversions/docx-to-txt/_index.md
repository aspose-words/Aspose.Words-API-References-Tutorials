---
title: Docx'ten Metin'e
linktitle: Docx'ten Metin'e
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini Docx'ten düz metne (Txt) dönüştürmeyi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-txt/
---

Bu adım adım öğreticide, Docx formatındaki bir Word belgesini düz metne (Txt) dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` Docx biçimindeki kaynak belgenizin yolunu içeren nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Adım 2: Belgeyi Txt Formatında Kaydetme

 Ardından, belgeyi çağırarak düz metin (Txt) biçiminde kaydedin.`Save` yöntemi`Document` nesne ve çıktı Txt belgesi için yol ve dosya adını sağlama:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Docx formatındaki bir Word belgesini düz metne (Txt) başarıyla dönüştürdünüz.

### Aspose.Words for .NET kullanan Docx To Txt için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.