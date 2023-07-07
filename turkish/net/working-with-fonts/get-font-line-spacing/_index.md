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

//Bir belge oluşturucu oluşturun
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Yazı tipini yapılandırın
 Ardından, ayarlayarak yazı tipini yapılandıracağız.`Name` belge oluşturucunun özelliği.

```csharp
// yazı tipini yapılandır
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

### SSS

#### S: Bir Word belgesindeki belirli bir metnin satır aralığını nasıl değiştirebilirim?

C: Aspose.Words ile bir Word belgesindeki belirli bir metnin satır aralığını kolayca değiştirebilirsiniz. İstenen metni seçmek için API'yi kullanın ve uygun değeri belirterek satırlar arasındaki boşluğu ayarlayın.

#### S: Bir Word belgesinde satırlar arasında tam aralık uygulamak mümkün mü?

C: Evet, Aspose.Words, bir Word belgesindeki satırlar arasında tam aralık uygulamanıza izin verir. API'yi kullanarak satır aralığı için kesin bir değer belirleyebilirsiniz.

#### S: Word belgesinin tamamı için satır aralığını nasıl ayarlayabilirim?

C: Aspose.Words ile Word belgesinin tamamı için satır aralığını kolayca ayarlayabilirsiniz. Tüm belge için istenen satır aralığını belirtmek için API tarafından sağlanan yöntemleri kullanın.

#### S: Aspose.Words çoklu satır aralığını destekliyor mu?

C: Evet, Aspose.Words, Word belgelerinde çoklu satır aralığını destekler. Metninizin satırları için 1,5 kat veya normal aralığın 2 katı gibi birden çok boşluk ayarlayabilirsiniz.

#### S: Satır aralığını ayarlarken satır çakışması sorunlarını nasıl önleyebilirim?

A: Satırlar arasındaki aralığı ayarlarken satır çakışma sorunlarını önlemek için uygun aralık değerlerini seçtiğinizden emin olun. Metnin okunabilir ve iyi biçimlendirilmiş durumda kaldığından emin olmak için belgenizin son halini de test edin.