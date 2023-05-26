---
title: Çok Düzeyli Liste Biçimlendirme
linktitle: Çok Düzeyli Liste Biçimlendirme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile çok düzeyli bir liste oluşturmayı ve özel biçimlendirme uygulamayı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/multilevel-list-formatting/
---

Bu eğitimde, size Aspose.Words for .NET ile çok düzeyli liste biçimlendirme özelliğini nasıl kullanacağınızı göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Çok düzeyli listeyi biçimlendirme

Şimdi çok düzeyli liste biçimlendirmesini DocumentBuilder nesnesinde bulunan yöntemleri kullanarak uygulayacağız. İşte nasıl:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## 3. Adım: Belgeyi kaydetme

 Metin giriş formu alanını ekledikten sonra, belgeyi istenen konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Aspose.Words for .NET kullanan Çok Düzeyli Liste Biçimlendirme için örnek kaynak kodu

Aspose.Words for .NET ile çok düzeyli liste biçimlendirme özelliği için eksiksiz kaynak kodu burada:


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyNumberDefault();
	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.1");
	builder.Writeln("Item 2.2");
	
	builder.ListFormat.ListIndent();
	builder.Writeln("Item 2.2.1");
	builder.Writeln("Item 2.2.2");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 2.3");

	builder.ListFormat.ListOutdent();
	builder.Writeln("Item 3");

	builder.ListFormat.RemoveNumbers();
	
	doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Bu kodla, çok düzeyli bir liste oluşturabilecek ve Aspose.Words for .NET'i kullanarak her düzeye uygun biçimlendirmeyi uygulayabileceksiniz.