---
title: PDF Belgesinde Escape URI
linktitle: PDF Belgesinde Escape URI
second_title: Aspose.Words Belge İşleme API'sı
description: Adım adım kılavuz Aspose.Words for .NET ile PDF Belgesinde URI'den Nasıl Çıkılır.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/escape-uri/
---

Bu makale, Aspose.Words for .NET ile PDF Belgesinde URI'den nasıl Escape yapılacağına dair adım adım bir kılavuz sunmaktadır. Kodun her bir bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgeye çıkış karakterli Uri ile köprülerin nasıl ekleneceğini öğrenebileceksiniz.

Başlamadan önce, projenizde Aspose.Words for .NET kitaplığını kurduğunuzdan ve yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için, belgelerinizin bulunduğu dizine giden yolu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeler dizininize giden gerçek yolla.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir belge ve bir DocumentBuilder oluşturun

 Sonra, yeni bir tane oluşturmamız gerekiyor`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturmak için nesne.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Çıkış karakterli Uri ile köprüler ekleyin

 Kullan`InsertHyperlink` yöntemi`DocumentBuilder` belgeye köprüler eklemek için nesne. Uri kullanılarak kaçılmalıdır`Uri.EscapeUriString` Biçim hatalarını önlemek için işlev.

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

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir PDF belgesinde URI'lerden nasıl kaçılacağını ele aldık. URI'lerden çıkış yaparak biçimlendirme hatalarını önleyebilir ve köprülerin doğru şekilde yorumlanmasını ve PDF belgesinde görüntülenmesini sağlayabilirsiniz. PDF belgenize çıkış URI'leri olan köprüler eklemek için özetlenen adımları izleyin. Kaçtığınızdan emin olun.

### Sıkça Sorulan Sorular

#### S: Bir PDF belgesindeki kaçış URI'si nedir ve neden önemlidir?
Y: Bir PDF belgesindeki Escape URI, biçim hatalarını önlemek için bir URL'deki özel karakterleri kaçış dizilerine dönüştürme yöntemini ifade eder. Bu önemlidir, çünkü bir URL'deki özel karakterler URL'nin yapısını bozabilir ve yanlış yorumlamaya veya yanlış oluşturmaya yol açabilir. Özel karakterlerden kaçarak, URL'nin doğru şekilde yorumlandığını ve PDF belgesinde görüntülendiğini garanti ediyoruz.

#### S: Bir PDF belgesindeki URI'lerden kaçmak için Aspose.Words for .NET'i nasıl kullanabilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesindeki URI'lerden kaçmak için şu adımları izleyin:

 Değiştirerek belgelerinizin bulunduğu dizin yolunu ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belgeler dizininizin gerçek yolu ile.

 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` belgeyi oluşturmak için nesne.

 Kullan`InsertHyperlink` yöntemi`DocumentBuilder` belgeye köprüler eklemek için nesne. kullanarak URI'den kaçtığınızdan emin olun.`Uri.EscapeUriString` Biçim hatalarını önlemek için işlev.

 Kullan`Save` yöntemi`Document` çıktı dosyasının adını belirterek belgeyi PDF biçiminde kaydetmek için nesne.

#### S: Bir PDF belgesinde URI'lerden kaçmanın faydaları nelerdir?
Y: Bir PDF belgesinde URI çıkışının faydaları şunlardır:

Biçim hatalarının önlenmesi: URI çıkışı, bir URL'deki özel karakterlerin neden olduğu biçim hatalarının önlenmesine yardımcı olarak URL'nin doğru şekilde yorumlanmasını ve PDF belgesinde görüntülenmesini sağlar.

PDF okuyucularla uyumluluk: Çıkış karakterli URI'ler genellikle PDF okuyucular tarafından iyi desteklenir ve daha iyi uyumluluk ve tutarlı bir kullanıcı deneyimi sağlar.

#### S: Bir URI'de hangi özel karakterlerden çıkış yapılmalıdır?
 A: Bir URI'de kaçması gereken özel karakterler şunlardır: boşluk, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.