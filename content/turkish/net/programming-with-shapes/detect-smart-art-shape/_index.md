---
title: Akıllı Sanat Şeklini Algıla
linktitle: Akıllı Sanat Şeklini Algıla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde Akıllı Sanat şekillerini nasıl tespit edeceğinizi ve grafiksel gösterimleri nasıl tespit edeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/detect-smart-art-shape/
---

Bu eğitimde Aspose.Words for .NET kullanılarak bir Word belgesinde Smart Art şekillerinin nasıl tespit edileceği açıklanmaktadır. Akıllı Sanat şekilleri, bilgi ve fikirleri görsel olarak sunmak için kullanılan grafiksel temsillerdir.

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
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## 3. Adım: Akıllı Sanat Şekillerini Algılama
 Türün alt düğümleri arasında yineleme yapın`Shape` kullanarak belgede`GetChildNodes`yöntem. kullanarak her şeklin Smart Art'a sahip olup olmadığını kontrol edin.`HasSmart Art` mülk.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Adım 4: Sonucu Çıktılayın
Belgede Smart Art ile algılanan şekillerin sayısını yazdırın.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Aspose.Words for .NET kullanarak Akıllı Sanat Şeklini Algılama için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki Smart Art şekillerini başarıyla tespit ettiniz.