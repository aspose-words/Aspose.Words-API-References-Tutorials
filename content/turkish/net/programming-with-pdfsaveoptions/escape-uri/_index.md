---
title: PDF Belgesinde URI'dan Kaçış
linktitle: PDF Belgesinde URI'dan Kaçış
second_title: Aspose.Words Belge İşleme API'si
description: Adım adım kılavuz Aspose.Words for .NET ile PDF Belgesinde URI'den Nasıl Kaçılır.
type: docs
weight: 10
url: /tr/net/programming-with-pdfsaveoptions/escape-uri/
---

Bu makale, Aspose.Words for .NET ile PDF Belgesinde URI'den Nasıl Çıkış Yapılacağı konusunda adım adım bir kılavuz sağlar. Kodun her bölümünü ayrıntılı olarak açıklayacağız. Bu eğitimin sonunda, bir belgeye kaçışlı Uri içeren köprülerin nasıl ekleneceğini anlayabileceksiniz.

Başlamadan önce projenize Aspose.Words for .NET kütüphanesini kurup yapılandırdığınızdan emin olun. Kütüphaneyi ve kurulum talimatlarını Aspose web sitesinde bulabilirsiniz.

## 1. Adım: Belge dizinini tanımlayın

 Başlamak için belgelerinizin bulunduğu dizinin yolunu tanımlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` Belgeler dizininizin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir belge ve DocumentBuilder oluşturun

 Daha sonra yeni bir tane oluşturmamız gerekiyor`Document` nesne ve bir`DocumentBuilder` belgeyi oluşturma nesnesi.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Kaçışlı Uri ile köprüler ekleyin

 Kullan`InsertHyperlink` yöntemi`DocumentBuilder` Belgeye köprü eklemek için nesne. Uri kullanılarak kaçılmalıdır`Uri.EscapeUriString` Biçim hatalarını önlemek için işlev.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## 4. Adım: Belgeyi PDF olarak kaydedin

 Son olarak belgeyi PDF olarak kaydedebiliriz.`Save` yöntemi`Document` nesne. Çıkış dosyası adını belirtin.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Bu kadar ! Aspose.Words for .NET kullanarak bir belgeye, kaçışlı Uri'ler içeren köprüleri başarıyla eklediniz.

### Aspose.Words for .NET ile kaçan Uri için örnek kaynak kodu


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

Bu eğitimde Aspose.Words for .NET kullanarak bir PDF belgesinde URI'lerden nasıl çıkış yapılacağını anlattık. URI'lerden kaçınarak biçimlendirme hatalarını önleyebilir ve köprülerin PDF belgesinde doğru şekilde yorumlanıp görüntülenmesini sağlayabilirsiniz. Kaçışlı URI'lere sahip köprüleri PDF belgenize eklemek için özetlenen adımları izleyin. Kaçtığınızdan emin olun.

### Sıkça Sorulan Sorular

#### S: PDF belgesindeki kaçış URI'si nedir ve neden önemlidir?
C: Bir PDF belgesindeki Kaçış URI'si, biçim hatalarını önlemek için bir URL'deki özel karakterleri kaçış dizilerine dönüştürme yöntemini ifade eder. Bu önemlidir çünkü bir URL'deki özel karakterler, URL'nin yapısını bozabilir ve yanlış yorumlanmaya veya yanlış oluşturmaya yol açabilir. Özel karakterlerden kaçınarak URL'nin PDF belgesinde doğru şekilde yorumlandığını ve görüntülendiğini garanti ederiz.

#### S: Bir PDF belgesindeki URI'lerden kaçmak için Aspose.Words for .NET'i nasıl kullanabilirim?
C: Aspose.Words for .NET kullanarak bir PDF belgesindeki URI'lerden kaçmak için şu adımları izleyin:

 Belgelerinizin bulunduğu dizin yolunu değiştirerek ayarlayın.`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` belgeyi oluşturma nesnesi.

 Kullan`InsertHyperlink` yöntemi`DocumentBuilder` Belgeye köprü eklemek için nesne. kullanarak URI'den kaçtığınızdan emin olun.`Uri.EscapeUriString` Biçim hatalarını önlemek için işlev.

 Kullan`Save` yöntemi`Document` Çıktı dosyasının adını belirterek belgeyi PDF formatında kaydetme nesnesini seçin.

#### S: Bir PDF belgesinde URI'lerden kaçmanın faydaları nelerdir?
C: Bir PDF belgesinde URI'nin kaçmasının faydaları şunlardır:

Biçim hatalarının önlenmesi: URI kaçışı, URL'deki özel karakterlerden kaynaklanan biçim hatalarının önlenmesine yardımcı olarak URL'nin PDF belgesinde doğru şekilde yorumlanmasını ve görüntülenmesini sağlar.

PDF okuyucularla uyumluluk: Kaçışlı URI'ler genellikle PDF okuyucular tarafından iyi bir şekilde desteklenir ve daha iyi uyumluluk ve tutarlı bir kullanıcı deneyimi sağlar.

#### S: Bir URI'de hangi özel karakterlerden kaçınılmalıdır?
 C: Bir URI'de çıkış yapılması gereken özel karakterler şunlardır: space, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.