---
title: Word Belgesinde Yer İşareti Oluştur
linktitle: Word Belgesinde Yer İşareti Oluştur
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak word belgesinde nasıl yer imleri oluşturulacağını ve PDF'de yer imi önizleme düzeylerini nasıl belirleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/create-bookmark/
---

Bu makalede, Aspose.Words for .NET kütüphanesinde Create Bookmark fonksiyonunun nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgede yer imleri oluşturmanıza ve çıktı PDF dosyasında yer imi önizleme düzeylerini belirlemenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## Adım 1: Belgeyi ve Oluşturucuyu Oluşturma

 Yer imleri oluşturmadan önce, bir belge ve belge oluşturucuyu kullanarak oluşturmamız gerekir.`Document` Ve`DocumentBuilder` nesneler:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Ana yer imini oluşturma

 biz kullanıyoruz`StartBookmark` bir ana yer imini başlatma yöntemi ve`EndBookmark` sonlandırmanın yöntemi. Araya metin ve diğer yer imlerini ekleyebiliriz:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Buraya daha fazla yer işareti veya metin ekleyin.

builder. EndBookmark("My Bookmark");
```

## 3. Adım: İç İçe Yer İmleri Oluşturma

Ana yer iminin içinde iç içe yer imleri de oluşturabiliriz. Biz de aynısını kullanıyoruz`StartBookmark` Ve`EndBookmark` iç içe yer imleri oluşturma ve sonlandırma yöntemleri:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 4. Adım: Çıktı PDF dosyasında yer imi önizleme düzeylerini belirtme

 biz kullanıyoruz`PdfSaveOptions` Çıktı PDF dosyasındaki yer imi önizleme düzeylerini belirtmek için nesne. biz kullanıyoruz`BookmarksOutlineLevels` mülk

  ana yer imlerini ve iç içe yer imlerini ilgili düzeyleriyle eklemek için:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Aspose.Words for .NET kullanarak Yer İşareti Oluşturma için örnek kaynak kodu

Aspose.Words for .NET kullanarak yer imleri oluşturmayı gösteren tam örnek kaynak kodu burada bulabilirsiniz:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Çözüm

Bu makalede Aspose.Words for .NET'in Create Bookmark fonksiyonunun nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belgede yer imleri oluşturmak ve çıktı PDF dosyasında yer imi önizleme düzeylerini belirlemek için adım adım bir kılavuz izledik.

### SSS

#### S: Aspose.Words for .NET'te "Yer imleri oluştur" fonksiyonunu kullanmanın önkoşulları nelerdir?

C: Aspose.Words for .NET'te "Yer imleri oluştur" işlevini kullanmak için C# dili hakkında temel bilgiye sahip olmanız gerekir. Ayrıca Aspose.Words kütüphanesinin kurulu olduğu bir .NET geliştirme ortamına da ihtiyacınız var.

#### S: Aspose.Words for .NET'te nasıl belge oluşturulur?

 C: Aspose.Words for .NET'te bir belge oluşturmak için`Document` sınıf. İşte örnek bir kod:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgede ana yer imi nasıl oluşturulur?

 C: Aspose.Words for .NET kullanarak bir belgede ana yer imi oluşturmak için`StartBookmark` yer imini başlatma, içine metin veya başka yer imleri ekleme ve ardından` EndBookmark` bitirmek için. İşte örnek bir kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### S: Aspose.Words for .NET kullanarak ana yer iminin içinde yuvalanmış bir yer imi nasıl oluşturulur?

 C: Aspose.Words for .NET'i kullanarak ana yer iminin içinde yuvalanmış bir yer imi oluşturmak için aynı yöntemi kullanabilirsiniz.`StartBookmark` Ve`EndBookmark` iç içe yer imini başlatma ve bitirme yöntemleri. İşte örnek bir kod:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### S: Aspose.Words for .NET kullanılarak çıktı PDF'sinde yer imi önizleme düzeyleri nasıl belirlenir?

 C: Aspose.Words for .NET'i kullanarak çıktı PDF'sinde yer imi önizleme seviyelerini belirlemek için`PdfSaveOptions` sınıf ve`BookmarksOutlineLevels` mülk. Ana yer imlerini ve iç içe yer imlerini ilgili düzeyleriyle ekleyebilirsiniz. İşte örnek bir kod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### S: Aspose.Words for .NET kullanarak yer imleri oluşturduktan sonra bir belge nasıl kaydedilir?

 C: Aspose.Words for .NET'i kullanarak yer imleri oluşturduktan sonra bir belgeyi kaydetmek için`Save` yöntemi`Document` Hedef dosya yolunu belirten nesne. İşte örnek bir kod:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### S: Aspose.Words for .NET kullanılarak çıktı PDF'sinde yer imi önizleme düzeyleri nasıl belirlenir?

 C: Aspose.Words for .NET'i kullanarak çıktı PDF'sinde yer imi önizleme seviyelerini belirlemek için`PdfSaveOptions` sınıf ve`BookmarksOutlineLevels` mülk. Ana yer imlerini ve iç içe yer imlerini ilgili düzeyleriyle ekleyebilirsiniz. İşte örnek bir kod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### S: Aspose.Words for .NET kullanarak ana yer iminin içinde iç içe yer imleri nasıl oluşturulur?

 C: Aspose.Words for .NET'i kullanarak ana yer iminin içinde iç içe yer imleri oluşturmak için aynı yöntemi kullanabilirsiniz.`StartBookmark` Ve`EndBookmark` iç içe yer imlerini başlatma ve bitirme yöntemleri. Çağrırken ana yer imini parametre olarak belirttiğinizden emin olun.`StartBookmark` yöntem. İşte örnek bir kod:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### S: Aspose.Words for .NET kullanarak bir yer iminin içine nasıl metin eklenir?

 C: Aspose.Words for .NET'i kullanarak bir yer iminin içine metin eklemek için`Write` yöntemi`DocumentBuilder`Eklenecek metni belirten nesne. İşte örnek bir kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### S: Aspose.Words for .NET kullanarak bir belgede ana yer imi nasıl oluşturulur?

 C: Aspose.Words for .NET kullanarak bir belgede ana yer imi oluşturmak için`StartBookmark` yer imini başlatma yöntemi ve`EndBookmark` sonlandırmanın yöntemi. İşte örnek bir kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```