---
title: Docx'ten Epub'a
linktitle: Docx'ten Epub'a
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini Docx'ten Epub formatına nasıl dönüştüreceğinizi öğrenin. Örnek kaynak koduyla adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-epub/
---

Bu adım adım öğreticide, Docx formatındaki bir Word belgesini Epub formatına dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak, başlatmanız gerekir`Document` kaynak belgenizin yolunu Docx biçiminde sağlayarak nesne. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu gerçek dizin yolu ile ve`"Document.docx"` kaynak belgenizin adıyla. İşte kod parçacığı:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Adım 2: Belgeyi Epub Formatına Dönüştürme

 Ardından, dönüştürme işlemine devam edebilirsiniz. Ara`Save` yöntemi`Document` nesne ve çıktı belgesi için yol ve dosya adını Epub formatında sağlayın. Bu örnekte, onu şu şekilde kaydedeceğiz:`"BaseConversions.DocxToEpub.epub"`. İşte kod parçacığı:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Docx formatındaki bir Word belgesini başarıyla Epub formatına dönüştürdünüz.

### Aspose.Words for .NET kullanan Docx To Epub için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.