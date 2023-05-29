---
title: Uri'den Kaçış
linktitle: Uri'den Kaçış
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Uri'den kaçmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/escape-uri/
---

Bu makale, Uri escape özelliğinin Aspose.Words for .NET ile nasıl kullanılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgeye çıkış karakterli Uri ile köprülerin nasıl ekleneceğini öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir belge ve bir DocumentBuilder oluşturun

 Ardından, yeni bir tane oluşturmamız gerekiyor`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Çıkış karakterli Uri ile köprüler ekleyin

 Kullan`InsertHyperlink` yöntemi`DocumentBuilder`belgeye köprüler eklemek için nesne. Uri kullanılarak kaçılmalıdır`Uri.EscapeUriString` Biçim hatalarını önlemek için işlev.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## 4. Adım: Belgeyi PDF olarak kaydedin

 Son olarak, belgeyi kullanarak belgeyi PDF olarak kaydedebiliriz.`Save` yöntemi`Document` nesne. Çıkış dosyası adını belirtin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Bu kadar ! Aspose.Words for .NET kullanarak bir belgeye kaçış Uri'leri olan köprüleri başarıyla eklediniz.

### Aspose.Words for .NET ile çıkış yapan Uri için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```
