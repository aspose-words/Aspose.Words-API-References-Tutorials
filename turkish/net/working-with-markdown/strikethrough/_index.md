---
title: Üstü çizili
linktitle: Üstü çizili
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET Adım adım kılavuz ile üzeri çizili metin stilini nasıl uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/strikethrough/
---


Bu örnekte, üstü çizili metin stilini Aspose.Words for .NET kullanarak nasıl uygulayacağınızı size göstereceğiz. Üstü çizili metin, metnin silindiğini veya artık geçerli olmadığını belirtmek için kullanılır.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Üstü çizili metin stilini uygulayın

 Ayarlayarak üstü çizili metin stilini etkinleştireceğiz.`StrikeThrough` mülkiyeti`Font` itiraz etmek`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 3. Adım: Üstü çizili metin ekleyin

 Artık belge oluşturucuyu kullanarak üstü çizili metin ekleyebiliriz.`Writeln` yöntem.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Aspose.Words for .NET ile üstü çizili metin için örnek kaynak kodu

```csharp
// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
DocumentBuilder builder = new DocumentBuilder();

// Metni üstü çizili yapın.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Tebrikler! Artık üstü çizili metin stilini Aspose.Words for .NET ile nasıl uygulayacağınızı öğrendiniz.

### SSS

#### S: Üstü çizili metni Aspose.Words'a nasıl ekleyebilirim?

 C: Üstü çizili metni Aspose.Words'e eklemek için`Font.StrikeThrough` mülkiyeti`Run`nesne. Bu özelliği şu şekilde ayarlayabilirsiniz:`true` Belirli bir metne üstü çizili metin eklemek için. Örneğin, kullanabilirsiniz`run.Font.StrikeThrough=true` üstü çizili metni eklemek için`Run` nesne.

#### S: Üstü çizili metni aynı paragraftaki birkaç metin parçasına eklemek mümkün müdür?

 C: Evet, birden çok paragraf kullanarak metnin birden çok bölümüne üstü çizili metin ekleyebilirsiniz.`Run` nesneler. birden fazla oluşturabilirsiniz`Run` nesneleri ayarlayın ve`Font.StrikeThrough` mülkiyet`true`Üstü çizili metni istenen metin bölümlerine eklemek için her nesne için. Ardından bunları kullanarak paragrafa ekleyebilirsiniz.`Paragraph.AppendChild(run)` yöntem.

#### S: Aspose.Words'te bir tablo veya hücredeki metne üstü çizili metin ekleyebilir miyim?

 C: Evet, Aspose.Words'te bir tablo veya hücredeki metne üstü çizili metin ekleyebilirsiniz. Uygun yöntemleri kullanarak istediğiniz hücreye veya paragrafa atlayabilir ve ardından üstü çizili metin biçimlendirmesini kullanarak uygulayabilirsiniz.`Font.StrikeThrough` mülkiyeti`Run` veya`Paragraph` nesne.