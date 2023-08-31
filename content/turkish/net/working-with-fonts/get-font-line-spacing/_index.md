---
title: Yazı Tipi Satır Aralığını Alma
linktitle: Yazı Tipi Satır Aralığını Alma
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde Aspose.Words for .NET ile bir Word belgesinde yazı tipi satır aralığının nasıl elde edileceğini öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-font-line-spacing/
---
Bu derste, .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesinde yazı tipi satır aralığını nasıl alacağınızı anlatacağız. Yazı tipi satır aralığı, metin satırları arasındaki dikey boşluğu tanımlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü

## 1. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 İlk olarak, örneği başlatarak yeni bir belge oluşturacağız.`Document` sınıf ve bir belge oluşturucuyu başlatarak`DocumentBuilder` sınıf.

```csharp
// Yeni bir belge oluştur
Document doc = new Document();

//Belge oluşturucu oluşturma
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Yazı tipini yapılandırın
 Daha sonra yazı tipini ayarlayarak yapılandıracağız.`Name` belge oluşturucunun özelliği.

```csharp
// Yazı tipini yapılandırma
builder.Font.Name = "Calibri";
```

## 3. Adım: Belgeye metin ekleyin
Artık belgeye biçimlendirilmiş metin eklemek için belge oluşturucuyu kullanacağız.

```csharp
// Belgeye metin ekleme
builder. Writen("qText");
```

## Adım 4: Yazı Tipi Satır Aralığını Alın
 Şimdi şuraya erişeceğiz:`Font` belgenin ilk paragrafının nesnesini bulun ve değerini alın`LineSpacing` mülk.

```csharp
// Yazı tipinin satır aralığını alın
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Satır Aralığını Alma için örnek kaynak kodu 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET ile bir Word belgesinde yazı tipi satır aralığının nasıl alınacağını gördük. Yazı tipi satır aralığı, metin satırları arasındaki dikey aralığı kontrol etmek için önemlidir. Belgelerinizdeki metninizin görünümünü özelleştirmek için bu özelliği kullanmaktan çekinmeyin.

### SSS'ler

#### S: Bir Word belgesindeki belirli bir metnin satır aralığını nasıl değiştirebilirim?

C: Aspose.Words ile bir Word belgesindeki belirli bir metnin satır aralığını kolayca değiştirebilirsiniz. İstediğiniz metni seçmek ve uygun değeri belirterek satırlar arasındaki boşluğu ayarlamak için API'yi kullanın.

#### S: Bir Word belgesinde satırlar arasında tam boşluk bırakmak mümkün müdür?

C: Evet, Aspose.Words, bir Word belgesindeki satırlar arasında tam boşluk bırakmanıza olanak tanır. API'yi kullanarak satır aralığı için kesin bir değer belirleyebilirsiniz.

#### S: Word belgesinin tamamı için satır aralığını nasıl ayarlayabilirim?

C: Aspose.Words ile tüm Word belgesinin satır aralığını kolayca ayarlayabilirsiniz. Belgenin tamamı için istenen satır aralığını belirtmek üzere API tarafından sağlanan yöntemleri kullanın.

#### S: Aspose.Words çoklu satır aralığını destekliyor mu?

C: Evet, Aspose.Words, Word belgelerinde birden fazla satır aralığını destekler. Metninizin satırları için 1,5 kat veya 2 kat normal aralık gibi çoklu aralıklar ayarlayabilirsiniz.

#### S: Satır aralığını ayarlarken satır çakışması sorunlarını nasıl önleyebilirim?

C: Satırlar arasındaki boşluğu ayarlarken satır çakışması sorunlarını önlemek için uygun aralık değerlerini seçtiğinizden emin olun. Ayrıca metnin okunabilir ve iyi biçimlendirilmiş olduğundan emin olmak için belgenizin son görüntüsünü de test edin.