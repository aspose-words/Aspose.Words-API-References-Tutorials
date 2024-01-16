---
title: Kalın yazı
linktitle: Kalın yazı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile metni nasıl kalınlaştıracağınızı öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/bold-text/
---

Bu örnekte size Aspose.Words for .NET ile kalın metinlerin nasıl yazılacağını anlatacağız. Kalınlaştırılmış metin, metni daha görünür hale getirir ve daha fazla öne çıkmasını sağlar.

## 1. Adım: Belge oluşturucuyu kullanma

Öncelikle belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Adım 2: Kalın Metin

 Belge oluşturucunun ayarını yaparak metni kalınlaştırabiliriz.`Font.Bold`mülkiyet`true`.

```csharp
builder.Font.Bold = true;
```

## 3. Adım: Belgeye içerik ekleyin

 Artık belge oluşturucu yöntemlerini kullanarak belgeye içerik ekleyebiliriz:`Writeln`, bir metin satırı ekler.

```csharp
builder.Writeln("This text will be bold");
```

## Aspose.Words for .NET kullanılarak Kalın Metin için Örnek Kaynak Kodu


```csharp
// Belgeye içerik eklemek için belge oluşturucuyu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Metni Kalın yapın.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Tebrikler! Artık Aspose.Words for .NET ile kalın metinlerin nasıl yazılacağını öğrendiniz.


### SSS'ler

#### S: Aspose.Words'te metni nasıl kalın yapabilirim?

 C: Aspose.Words'te metni kalın yapmak için`Font.Bold` mülkiyeti`Run` nesne. Bu özelliği şu şekilde ayarlayabilirsiniz:`true` Belirli bir metni kalın yapmak için. Örneğin, kullanabilirsiniz`run.Font.Bold=true` içindeki metni kalınlaştırmak için`Run` nesne.

#### S: Aynı paragrafta birkaç metin parçasını kalın harflerle yazmak mümkün müdür?

C: Evet, tek bir paragrafta birden çok metin parçasını birden çok harf kullanarak kalınlaştırabilirsiniz.`Run` nesneler. Birden fazla oluşturabilirsiniz`Run` nesneleri ayarlayın ve`Font.Bold`mülkiyet`true` Her nesne için metnin istenen bölümlerini kalınlaştırmak için. Daha sonra bunları kullanarak paragrafa ekleyebilirsiniz.`Paragraph.AppendChild(run)` yöntem.

#### S: Aspose.Words'te bir tablo veya hücredeki metni kalınlaştırabilir miyim?

 C: Evet, Aspose.Words'te tablo veya hücredeki metni kalınlaştırabilirsiniz. Uygun yöntemleri kullanarak istediğiniz hücreye veya paragrafa gidebilir ve ardından kalın biçimlendirmeyi aşağıdaki düğmeyi kullanarak uygulayabilirsiniz:`Font.Bold` mülkiyeti`Run` veya`Paragraph` nesne.