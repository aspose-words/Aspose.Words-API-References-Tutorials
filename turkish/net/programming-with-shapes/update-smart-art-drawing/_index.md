---
title: Akıllı Sanat Çizimini Güncelle
linktitle: Akıllı Sanat Çizimini Güncelle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki Smart Art çizimini nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/update-smart-art-drawing/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki Smart Art çiziminin nasıl güncelleneceğini açıklar. Belgedeki şekilleri yineleyerek ve Smart Art'a sahip olup olmadıklarını kontrol ederek, Smart Art çizimini verilerinde yapılan değişiklikleri yansıtacak şekilde güncelleyebilirsiniz.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin
 Smart Art çizimini içeren Word belgesini yükleyin.`Document` sınıf oluşturucu

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 3. Adım: Akıllı Sanat Çizimini Güncelleyin
 kullanarak belgedeki şekiller arasında yineleme yapın.`GetChildNodes` ile yöntem`NodeType.Shape` parametre. kullanarak her şeklin Smart Art'a sahip olup olmadığını kontrol edin.`HasSmartArt` özellik ve doğruysa,`UpdateSmartArtDrawing` Smart Art çizimini güncelleme yöntemi.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Aspose.Words for .NET kullanarak Akıllı Sanat Çizimini Güncellemek için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki Smart Art çizimini başarıyla güncellediniz.