---
title: Word Belgesinde Yer İşareti Oluşturma
linktitle: Word Belgesinde Yer İşareti Oluşturma
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak word belgesinde yer imleri oluşturmayı ve bir PDF'de yer imi önizleme düzeylerini belirlemeyi öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-bookmarks/create-bookmark/
---

Bu makalede, Aspose.Words for .NET kitaplığında Yer İşareti Oluştur işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, bir belgede yer imleri oluşturmanıza ve bir çıktı PDF dosyasında yer imi önizleme düzeylerini belirlemenize olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Belgeyi ve Oluşturucuyu Oluşturma

 Yer imleri oluşturmadan önce, kullanarak bir belge ve bir belge oluşturucu oluşturmamız gerekir.`Document` Ve`DocumentBuilder` nesneler:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Ana yer imini oluşturma

 biz kullanıyoruz`StartBookmark` ana yer imi başlatma yöntemi ve`EndBookmark` bitirme yöntemi. Arada metin ve diğer yer imlerini ekleyebiliriz:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Buraya daha fazla yer imi veya metin ekleyin.

builder. EndBookmark("My Bookmark");
```

## 3. Adım: İç İçe Yer İmleri Oluşturma

 Ana yer iminin içinde iç içe yer imleri de oluşturabiliriz. aynısını kullanıyoruz`StartBookmark` Ve`EndBookmark` iç içe yer imleri oluşturma ve sonlandırma yöntemleri:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## 4. Adım: Çıktı PDF dosyasında yer imi önizleme düzeylerini belirleme

 biz kullanıyoruz`PdfSaveOptions` Çıktı PDF dosyasındaki yer imi önizleme düzeylerini belirtmek için nesne. biz kullanıyoruz`BookmarksOutlineLevels` mülk

  ana yer imlerini ve iç içe yer imlerini kendi düzeyleriyle eklemek için:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Aspose.Words for .NET kullanarak Create Bookmark için örnek kaynak kodu

Aspose.Words for .NET kullanarak yer imleri oluşturmayı gösteren tam örnek kaynak kodu burada:

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

Bu makalede, Aspose.Words for .NET'in Yer İşareti Oluştur işlevinin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belgede yer imleri oluşturmak ve bir çıktı PDF dosyasında yer imi önizleme düzeylerini belirlemek için adım adım bir kılavuz izledik.

### SSS

#### S: Aspose.Words for .NET'te "Yer imleri oluştur" işlevini kullanmanın ön koşulları nelerdir?

C: Aspose.Words for .NET'te "Yer imleri oluştur" işlevini kullanmak için temel C# dili bilgisine sahip olmanız gerekir. Ayrıca Aspose.Words kütüphanesinin kurulu olduğu bir .NET geliştirme ortamına ihtiyacınız var.

#### S: Aspose.Words for .NET'te bir belge nasıl oluşturulur?

 C: Aspose.Words for .NET'te bir belge oluşturmak için`Document`sınıf. İşte örnek bir kod:

```csharp
Document doc = new Document();
```

#### S: Aspose.Words for .NET kullanarak bir belgede ana yer imi nasıl oluşturulur?

 C: Aspose.Words for .NET kullanarak bir belgede ana yer imi oluşturmak için`StartBookmark` yer imini başlatmak, içine metin veya başka yer imleri eklemek için yöntemi kullanın, ardından` EndBookmark` bitirmek için İşte örnek bir kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### S: Aspose.Words for .NET kullanarak bir ana yer iminin içinde iç içe geçmiş bir yer imi nasıl oluşturulur?

 C: Aspose.Words for .NET'i kullanarak bir ana yer iminin içinde yuvalanmış bir yer imi oluşturmak için aynısını kullanabilirsiniz.`StartBookmark` Ve`EndBookmark` iç içe yer imini başlatma ve bitirme yöntemleri. İşte örnek bir kod:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### S: Aspose.Words for .NET kullanarak bir çıktı PDF'sinde yer imi önizleme seviyeleri nasıl belirlenir?

 C: Aspose.Words for .NET kullanarak bir çıktı PDF'sinde yer imi önizleme düzeylerini belirtmek için`PdfSaveOptions` sınıf ve`BookmarksOutlineLevels` mülk. Ana yer imlerini ve iç içe yer imlerini ilgili seviyeleri ile ekleyebilirsiniz. İşte örnek bir kod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### S: Aspose.Words for .NET kullanarak yer imleri oluşturduktan sonra bir belge nasıl kaydedilir?

 C: Aspose.Words for .NET kullanarak yer imleri oluşturduktan sonra bir belgeyi kaydetmek için`Save` yöntemi`Document` hedef dosya yolunu belirten nesne. İşte örnek bir kod:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### S: Aspose.Words for .NET kullanarak bir çıktı PDF'sinde yer imi önizleme seviyeleri nasıl belirlenir?

 C: Aspose.Words for .NET kullanarak bir çıktı PDF'sinde yer imi önizleme düzeylerini belirtmek için`PdfSaveOptions` sınıf ve`BookmarksOutlineLevels` mülk. Ana yer imlerini ve iç içe yer imlerini ilgili seviyeleri ile ekleyebilirsiniz. İşte örnek bir kod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### S: Aspose.Words for .NET kullanarak bir ana yer iminin içinde iç içe yer imleri nasıl oluşturulur?

 C: Aspose.Words for .NET kullanarak bir ana yer iminin içinde iç içe geçmiş yer imleri oluşturmak için aynısını kullanabilirsiniz.`StartBookmark` Ve`EndBookmark` iç içe yer imlerini başlatma ve bitirme yöntemleri. çağrılırken ana yer imini bir parametre olarak belirttiğinizden emin olun.`StartBookmark` yöntem. İşte örnek bir kod:

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

 C: Aspose.Words for .NET kullanarak bir yer iminin içine metin eklemek için`Write` yöntemi`DocumentBuilder` eklenecek metni belirten nesne. İşte örnek bir kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### S: Aspose.Words for .NET kullanarak bir belgede ana yer imi nasıl oluşturulur?

 C: Aspose.Words for .NET kullanarak bir belgede ana yer imi oluşturmak için`StartBookmark` yer imini başlatma yöntemi ve`EndBookmark` bitirme yöntemi. İşte örnek bir kod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```