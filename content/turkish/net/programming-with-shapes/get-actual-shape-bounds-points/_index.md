---
title: Gerçek Şekil Sınır Noktalarını Alın
linktitle: Gerçek Şekil Sınır Noktalarını Alın
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde bir şeklin gerçek sınırlarını nokta (ölçü birimi) cinsinden nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Bu eğitimde, Aspose.Words for .NET kullanılarak bir Word belgesindeki bir şeklin gerçek sınırlarının nokta (ölçüm birimi) cinsinden nasıl alınacağı açıklanmaktadır. Sınırlar, şeklin belge içindeki boyutunu ve konumunu temsil eder.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyle çalışmaya itiraz edin.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Görüntü Şekli Ekleme
 Kullan`InsertImage` yöntemi`DocumentBuilder`Belgeye bir görüntü şekli eklemek için nesne. Görüntü dosyasının yolunu parametre olarak belirtin.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Adım 3: Gerçek Şekil Sınır Noktalarını Alın
 Şeklin erişim`ShapeRenderer` kullanmak`GetShapeRenderer` yöntem. Ardından, şeklin gerçek sınırlarını noktalar halinde alın.`BoundsInPoints` mülk.

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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizdeki bir şeklin nokta cinsinden gerçek sınırlarını başarıyla aldınız.