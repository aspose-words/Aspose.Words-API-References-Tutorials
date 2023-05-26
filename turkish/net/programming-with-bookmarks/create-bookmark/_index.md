---
title: Yer İşareti Oluştur
linktitle: Yer İşareti Oluştur
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgede yer imleri oluşturmayı ve bir PDF'de yer imi önizleme düzeylerini belirlemeyi öğrenin.
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