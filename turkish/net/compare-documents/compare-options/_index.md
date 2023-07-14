---
title: Seçenekleri Karşılaştır
linktitle: Seçenekleri Karşılaştır
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile Seçenekleri Karşılaştır özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/compare-documents/compare-options/
---

Bu eğitimde, Karşılaştırma Seçenekleri özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını açıklayacağız. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeleri özel seçeneklerle karşılaştırın

 Başlamak için, karşılaştırılacak iki belge yükleyin. Bu örnekte,`Clone()` orijinal belgenin bir kopyasını oluşturma yöntemi. İşte nasıl:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## 2. Adım: Karşılaştırma seçeneklerini yapılandırma

 Şimdi bir oluşturarak karşılaştırma seçeneklerini yapılandıracağız.`CompareOptions` nesne ve çeşitli özellikleri gerektiği gibi ayarlama. İşte nasıl:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## 3. Adım: Belgeleri özel seçeneklerle karşılaştırın

 şimdi kullanacağız`Compare()` iki belgeyi karşılaştırmak için özel seçenekleri geçirme yöntemi. Bu yöntem, orijinal belgedeki değişiklikleri işaretleyecektir. İşte nasıl:

```csharp
// Belgeleri özel seçeneklerle karşılaştırın
docA.Compare(docB, "user", DateTime.Now, options);

// Belgelerin eşit olup olmadığını kontrol edin
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Aspose.Words for .NET kullanan Karşılaştırma Seçenekleri için örnek kaynak kodu

Aspose.Words for .NET ile Karşılaştırma Seçenekleri özelliğinin tam kaynak kodu burada:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Bu kodla, Aspose.Words for .NET ile karşılaştırırken belirli öğeleri yok saymak için özel seçenekleri kullanarak iki belgeyi karşılaştırabilirsiniz.

