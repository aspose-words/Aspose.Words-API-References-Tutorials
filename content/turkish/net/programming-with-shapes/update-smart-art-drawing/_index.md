---
title: Akıllı Sanat Çizimini Güncelle
linktitle: Akıllı Sanat Çizimini Güncelle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgesindeki Smart Art çizimini nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/update-smart-art-drawing/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesindeki Smart Art çiziminin nasıl güncelleneceği açıklanmaktadır. Belgedeki şekilleri yineleyerek ve bunların Smart Art'a sahip olup olmadığını kontrol ederek Smart Art çizimini, verilerinde yapılan değişiklikleri yansıtacak şekilde güncelleyebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin
 Smart Art çizimini içeren Word belgesini kullanarak yükleyin.`Document` sınıf yapıcısı.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 3. Adım: Akıllı Sanat Çizimini Güncelleyin
 kullanarak belgedeki şekilleri yineleyin.`GetChildNodes` yöntemi ile`NodeType.Shape` parametre. kullanarak her şeklin Smart Art'a sahip olup olmadığını kontrol edin.`HasSmartArt` mülk ve eğer doğruysa, arayın`UpdateSmartArtDrawing` Smart Art çizimini güncelleme yöntemi.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Aspose.Words for .NET kullanarak Akıllı Sanat Çizimini Güncelleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki Smart Art çizimini başarıyla güncellediniz.