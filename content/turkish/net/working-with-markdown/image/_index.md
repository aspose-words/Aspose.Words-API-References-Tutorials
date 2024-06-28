---
title: Resim
linktitle: Resim
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile görüntüyü nasıl ekleyeceğinizi ve özelleştireceğinizi öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/image/
---

Bu örnekte Aspose.Words for .NET ile görüntü özelliğinin nasıl kullanılacağını açıklayacağız. Resimler bir belgeye resim ve grafik eklemenizi sağlar.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Resim ekleme

 kullanarak bir resim ekleyebiliriz.`Shape` sınıf ve görüntünün türünü belirterek burada`ShapeType.Image` . Ayrıca görüntünün sarma türünü de ayarladık.`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## 3. Adım: Görüntü Özelleştirme

 Resmi tam yolunu belirterek özelleştiriyoruz, örneğin`"/attachment/1456/pic001.png"`ve resme bir başlık ekleyin.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Aspose.Words for .NET içeren görseller için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Resim ekle.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Tebrikler! Artık Aspose.Words for .NET ile görseller özelliğini nasıl kullanacağınızı öğrendiniz.


### SSS'ler

#### S: Yerel bir dosyadan Aspose.Words'e nasıl resim ekleyebilirim?

 C: Yerel bir dosyadan Aspose.Words'e resim eklemek için`Shape` sınıf ve`InsertImage` yöntem.

#### S: Aspose.Words'e bir URL'den resim ekleyebilir miyim?

 C: Evet, Aspose.Words'teki bir URL'den resim ekleyebilirsiniz. Aynısını kullanabilirsiniz`InsertImage`yöntemini kullanın ve yerel dosya yolu yerine resim URL'sini belirtin.

#### S: Aspose.Words'te bir resmi nasıl yeniden boyutlandırabilirim?

 C: Aspose.Words'te bir resmi yeniden boyutlandırmak için`Width` Ve`Height` özellikleri`Shape` nesne.

#### S: Aspose.Words'teki görsellere filtre uygulayabilir miyim?

 C: Evet, Aspose.Words'te görsellere filtre uygulayabilirsiniz. Örneğin, bir görüntüye bulanıklık filtresi uygulayabilirsiniz.`ApplyGaussianBlur` yöntemi`Shape` nesne.

#### S: Aspose.Words'te bir görseli diğeriyle nasıl değiştirebilirim?

 C: Aspose.Words'te bir görüntüyü diğeriyle değiştirmek için`Replace` yöntemi`Shape` sınıf. Bu yöntem parametre olarak`Shape` değiştirilecek görüntünün nesnesi ve`Shape` yeni görüntünün nesnesi.