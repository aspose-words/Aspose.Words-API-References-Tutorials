---
title: Kalın yazı
linktitle: Kalın yazı
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET Adım adım kılavuz ile metni kalın yapmayı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/bold-text/
---

Bu örnekte, size Aspose.Words for .NET ile metni nasıl kalınlaştıracağınızı anlatacağız. Kalın yazı metni daha görünür hale getirir ve daha belirgin hale getirir.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Kalın Metin

 Belge oluşturucunun ayarını yaparak metni kalınlaştırabiliriz.`Font.Bold` mülkiyet`true`.

```csharp
builder.Font.Bold = true;
```

## 3. Adım: Belgeye içerik ekleyin

 Artık belge oluşturucu yöntemlerini kullanarak belgeye içerik ekleyebiliriz, örneğin`Writeln`, bir metin satırı ekler.

```csharp
builder.Writeln("This text will be bold");
```

## Aspose.Words for .NET kullanan Kalın Metin için Örnek Kaynak Kodu


```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Metni Kalın yapın.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Tebrikler! Artık Aspose.Words for .NET ile kalın yazı yazmayı öğrendiniz.


### SSS

#### S: Aspose.Words'te metni nasıl kalın yapabilirim?

 C: Aspose.Words'te metni kalın yapmak için`Font.Bold`mülkiyeti`Run`nesne. Bu özelliği şu şekilde ayarlayabilirsiniz:`true` belirli bir metni kalınlaştırmak için Örneğin, kullanabilirsiniz`run.Font.Bold=true` içindeki metni kalın yapmak için`Run` nesne.

#### S: Aynı paragrafta birkaç metin parçasını kalın yapmak mümkün mü?

 C: Evet, tek bir paragrafta birden çok metin parçasını birden çok kullanarak kalınlaştırabilirsiniz.`Run` nesneler. birden fazla oluşturabilirsiniz`Run` nesneleri ayarlayın ve`Font.Bold` mülkiyet`true` metnin istenen kısımlarını kalınlaştırmak için her nesne için. Ardından bunları kullanarak paragrafa ekleyebilirsiniz.`Paragraph.AppendChild(run)` yöntem.

#### S: Aspose.Words'te bir tablo veya hücredeki metni kalınlaştırabilir miyim?

 C: Evet, Aspose.Words'te bir tablo veya hücredeki metni kalın yapabilirsiniz. Uygun yöntemleri kullanarak istediğiniz hücreye veya paragrafa gidebilir ve ardından kalın biçimlendirmeyi kullanarak uygulayabilirsiniz.`Font.Bold`mülkiyeti`Run` veya`Paragraph` nesne.