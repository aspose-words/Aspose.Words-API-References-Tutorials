---
title: Belirli Seçeneklerle Metin Filigranı Ekleyin
linktitle: Belirli Seçeneklerle Metin Filigranı Ekleyin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak belirli seçeneklerle metin filigranı eklemeyi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Bu öğreticide, Aspose.Words for .NET kullanarak belirli seçeneklerle nasıl metin filigranı ekleyeceğinizi size göstereceğiz. Metin filigranı, taslak, gizli vb. olduğunu belirtmek için bir belgenin üzerine eklenen metindir.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi yükleme

Belge yolunu kullanarak mevcut bir belgeyi yükleyeceğiz.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 3. Adım: Belirli seçeneklerle metin filigranı ekleyin

 örneğini oluşturacağız`TextWatermarkOptions` sınıfını seçin ve metin filigranı için istediğiniz seçenekleri ayarlayın.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## 4. Adım: Belgeyi kaydedin

Son olarak, eklenen metin filigranı ile belgeyi kaydedebiliriz.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Aspose.Words for .NET ile belirli seçeneklerle metin filigranı eklemek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Tebrikler! Artık Aspose.Words for .NET kullanarak belirli seçeneklerle metin filigranı eklemeyi öğrendiniz.

