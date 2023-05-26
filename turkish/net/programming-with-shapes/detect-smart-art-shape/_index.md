---
title: Akıllı Sanat Şeklini Algıla
linktitle: Akıllı Sanat Şeklini Algıla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki Akıllı Sanat şekillerini nasıl algılayacağınızı öğrenin, grafik temsilleri tanımlayın.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/detect-smart-art-shape/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki Akıllı Sanat şekillerinin nasıl algılanacağını açıklar. Akıllı Sanat şekilleri, bilgi ve fikirleri görsel olarak sunmak için kullanılan grafik temsillerdir.

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
 kullanarak Word belgesini yükleyin.`Document` yapıcı, belgenin yolunu bir parametre olarak iletir.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## 3. Adım: Akıllı Sanat Şekillerini Tespit Etme
Türün alt düğümlerini yineleyin`Shape` kullanarak belgede`GetChildNodes` yöntem. kullanarak her şeklin Smart Art'a sahip olup olmadığını kontrol edin.`HasSmart Art` mülk.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Adım 4: Sonucu Çıkarın
Belgede algılanan Smart Art ile şekillerin sayısını yazdırın.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Aspose.Words for .NET kullanarak Akıllı Sanat Şeklini Algıla için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde Akıllı Sanat şekillerini başarıyla tespit ettiniz.