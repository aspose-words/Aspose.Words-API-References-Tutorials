---
title: Gerçek Şekil Sınır Noktaları Alın
linktitle: Gerçek Şekil Sınır Noktaları Alın
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesindeki noktalar (ölçüm birimi) olarak bir şeklin gerçek sınırlarını nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesindeki noktalar (ölçüm birimi) olarak bir şeklin gerçek sınırlarının nasıl alınacağını açıklar. Sınırlar, belgedeki şeklin boyutunu ve konumunu temsil eder.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir Görüntü Şekli Ekleyin
 Kullan`InsertImage` yöntemi`DocumentBuilder` belgeye bir görüntü şekli eklemek için nesne. Görüntü dosyasının yolunu bir parametre olarak sağlayın.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## 3. Adım: Gerçek Şekil Sınır Noktalarını Alın
 Şekle erişin`ShapeRenderer` kullanmak`GetShapeRenderer` yöntem. Ardından, şeklin gerçek sınırlarını nokta olarak alın.`BoundsInPoints` mülk.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Aspose.Words for .NET kullanarak Gerçek Şekil Sınır Noktalarını Al için örnek kaynak kodu 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki noktalardaki bir şeklin asıl sınırlarını başarıyla aldınız.