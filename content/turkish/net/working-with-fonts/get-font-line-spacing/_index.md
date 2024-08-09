---
title: Yazı Tipi Satır Aralığını Alma
linktitle: Yazı Tipi Satır Aralığını Alma
second_title: Aspose.Words Belge İşleme API'si
description: Bu adım adım eğitimle Aspose.Words for .NET kullanarak yazı tipi satır aralığını nasıl elde edeceğinizi öğrenin. Geliştiriciler için mükemmel.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-font-line-spacing/
---
## giriiş

Aspose.Words for .NET, Word belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyan güçlü bir kitaplıktır. Gerçekleştirmeniz gerekebilecek yaygın görevlerden biri, bir belgedeki belirli bir yazı tipinin satır aralığını almaktır. Bu eğitimde, Aspose.Words for .NET'i kullanarak yazı tipi satır aralığını kolayca alabilmenizi sağlamak için size süreç boyunca adım adım yol göstereceğiz. 

## Önkoşullar

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

1.  Aspose.Words for .NET Library: En son sürümü şuradan indirin ve yükleyin:[Burada](https://releases.aspose.com/words/net/).
2. Geliştirme Ortamı: Visual Studio gibi bir IDE kurulumuna sahip olduğunuzdan emin olun.
3. Temel C# Bilgisi: Bu eğitimde, C# programlama konusunda temel bir anlayışa sahip olduğunuz varsayılmaktadır.

## Ad Alanlarını İçe Aktar

Öncelikle C# projenize gerekli ad alanlarını içe aktarmanız gerekir. Bu ad alanları Aspose.Words işlevlerine erişmenizi sağlayacaktır.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Yazı tipi satır aralığını alma sürecini basit, yönetilebilir adımlara ayıralım.

## 1. Adım: Yeni Bir Belge Oluşturun

İlk adım Aspose.Words for .NET'i kullanarak yeni bir Word belgesi örneği oluşturmaktır.

```csharp
Document doc = new Document();
```

## Adım 2: DocumentBuilder'ı başlatın

Daha sonra, başlatmamız gerekiyor`DocumentBuilder` nesne. Bu nesne belge içeriğini oluşturmamıza ve işlememize yardımcı olacaktır.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Yazı Tipi Özelliklerini Ayarlayın

Artık eklemek istediğimiz metnin yazı tipi özelliklerini ayarlıyoruz. Bu örnek için "Calibri" yazı tipini kullanacağız.

```csharp
builder.Font.Name = "Calibri";
```

## Adım 4: Belgeye Metin Yazma

 kullanarak`DocumentBuilder` nesne, belgeye bir miktar metin yazın. Bu metin, önceki adımda belirlediğimiz yazı tipi özelliklerini kullanacaktır.

```csharp
builder.Writeln("Sample Text");
```

## Adım 5: Yazı Tipi Nesnesini Alın

Satır aralığını elde etmek için yeni eklediğimiz metnin font nesnesine erişmemiz gerekiyor. Bu, belge yapısından ilk paragraf dizisine gidilerek yapılabilir.

```csharp
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
```

## Adım 6: Satır Aralığını Alın

Son olarak yazı tipi nesnesinden satır aralığını alıp konsola yazdırıyoruz.

```csharp
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Çözüm

Ve işte karşınızda! Aspose.Words for .NET'i kullanarak yazı tipi satır aralığını almak, bunu aşağıdaki basit adımlara ayırdığınızda çok kolaydır. İster yeni bir belge oluşturuyor olun ister mevcut bir belgeyle çalışıyor olun, Aspose.Words yazı tipi özelliklerini verimli bir şekilde yönetmek için ihtiyacınız olan tüm araçları sağlar.

## SSS'ler

### Aspose.Words for .NET nedir?
Aspose.Words for .NET, geliştiricilerin C# kullanarak Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır.

### Aspose.Words for .NET'i diğer .NET dillerinde kullanabilir miyim?
Evet, Aspose.Words for .NET'i VB.NET ve F# dahil herhangi bir .NET diliyle kullanabilirsiniz.

### Aspose.Words for .NET'i nasıl indirebilirim?
 Aspose.Words for .NET'in en son sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/net/).

### Aspose.Words for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, şu adresten ücretsiz deneme alabilirsiniz:[Burada](https://releases.aspose.com/).

### Aspose.Words for .NET belgelerini nerede bulabilirim?
 Aspose.Words for .NET'in belgeleri mevcuttur[Burada](https://reference.aspose.com/words/net/).