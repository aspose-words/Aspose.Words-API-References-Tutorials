---
title: Yazı Tipi Satır Aralığını Alın
linktitle: Yazı Tipi Satır Aralığını Alın
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET ile bir Word belgesinde yazı tipi satır aralığını nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-font-line-spacing/
---
Bu eğitimde, .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesinde yazı tipi satır aralığını nasıl alacağınızı anlatacağız. Yazı tipi satır aralığı, metin satırları arasındaki dikey boşluğu tanımlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 İlk olarak, örnekleyerek yeni bir belge oluşturacağız.`Document` sınıfı ve bir belge oluşturucuyu örnekleyerek`DocumentBuilder` sınıf.

```csharp
// Yeni bir belge oluştur
Document doc = new Document();

// Bir belge oluşturucu oluşturun
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Yazı tipini yapılandırın
 Ardından, ayarlayarak yazı tipini yapılandıracağız.`Name` belge oluşturucunun özelliği.

```csharp
//yazı tipini yapılandır
builder.Font.Name = "Calibri";
```

## 3. Adım: Belgeye metin ekleyin
Şimdi belgeye biçimlendirilmiş metin eklemek için belge oluşturucuyu kullanacağız.

```csharp
// Belgeye metin ekleyin
builder. Writen("qText");
```

## 4. Adım: Yazı Tipi Satır Aralığını Alın
 Şimdi erişeceğiz`Font` belgenin ilk paragrafının nesnesi ve değerini almak`LineSpacing` mülk.

```csharp
// Yazı tipinin satır aralığını alın
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Satırı Boşluğunu Getir için örnek kaynak kodu 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET ile bir Word belgesinde yazı tipi satır aralığının nasıl alınacağını gördük. Yazı tipi satırı aralığı, metin satırları arasındaki dikey aralığı kontrol etmek için önemlidir. Belgelerinizdeki metninizin görünümünü özelleştirmek için bu özelliği kullanmaktan çekinmeyin.
