---
title: Belirli Seçeneklerle Metin Filigranı Ekleme
linktitle: Belirli Seçeneklerle Metin Filigranı Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak belirli seçeneklerle nasıl metin filigranı ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Bu eğitimde, Aspose.Words for .NET'i kullanarak belirli seçeneklerle nasıl metin filigranı ekleyeceğinizi anlatacağız. Metin filigranı, belgenin taslak, gizli vb. olduğunu belirtmek için belgenin üzerine eklenen metindir.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi yükleme

Mevcut bir belgeyi belge yolunu kullanarak yükleyeceğiz.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## 3. Adım: Belirli seçeneklerle metin filigranı ekleyin

 Bunun bir örneğini oluşturacağız`TextWatermarkOptions` sınıfını seçin ve metin filigranı için istediğiniz seçenekleri ayarlayın.

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

Tebrikler! Artık Aspose.Words for .NET'i kullanarak belirli seçeneklerle metin filigranını nasıl ekleyeceğinizi öğrendiniz.

