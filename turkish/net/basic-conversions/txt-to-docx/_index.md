---
title: Docx'e Metin
linktitle: Docx'e Metin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak düz metin dosyalarını (Txt) Word belgelerine (Docx) nasıl dönüştüreceğinizi öğrenin. Örnek kod ile adım adım öğretici.
type: docs
weight: 10
url: /tr/net/basic-conversions/txt-to-docx/
---

Bu adım adım öğreticide, bir düz metin dosyasını (Txt) Docx formatında bir Word belgesine dönüştürmek için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` düz metin dosyanızın yolunu sağlayarak nesne:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Adım 2: Belgeyi Docx Formatında Kaydetme

 Sonra, çağırarak belgeyi Docx biçiminde kaydedin.`Save` yöntemi`Document`nesne ve çıktı Docx belgesi için yol ve dosya adını sağlama:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak bir düz metin dosyasını (Txt) Docx formatında bir Word belgesine başarıyla dönüştürdünüz.

### Aspose.Words for .NET kullanan Txt To Docx için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Metin dosyasının kodlaması otomatik olarak algılanır.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.