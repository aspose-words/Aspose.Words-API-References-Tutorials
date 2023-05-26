---
title: Eşit Karşılaştır
linktitle: Eşit Karşılaştır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Compare for Equals özelliğinin C# kaynak kodunu açıklayan adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/compare-documents/compare-for-equal/
---

Bu eğitimde, Compare for Equal özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını size göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belge karşılaştırması

 Başlamak için, karşılaştırılacak iki belge yükleyin. Bu örnekte,`Clone()` orijinal belgenin bir kopyasını oluşturma yöntemi. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## 2. Adım: Belge karşılaştırması

 şimdi kullanacağız`Compare()` İki belgeyi karşılaştırma yöntemi. Bu yöntem, orijinal belgedeki değişiklikleri işaretleyecektir. İşte nasıl:

```csharp
// Belgeleri karşılaştırın
docA.Compare(docB, "user", DateTime.Now);

// Belgelerin eşit olup olmadığını kontrol edin
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Aspose.Words for .NET kullanan Compare For Equal için örnek kaynak kodu

Aspose.Words for .NET ile Compare for Equals özelliğinin tam kaynak kodu burada:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA artık değişiklikleri revizyon olarak içeriyor.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Bu kodla, Aspose.Words for .NET'i kullanarak iki belgeyi karşılaştırabilecek ve bunların aynı olup olmadığını belirleyebileceksiniz.

