---
title: Word Belgesinde Çok Düzeyli Liste Biçimlendirme
linktitle: Word Belgesinde Çok Düzeyli Liste Biçimlendirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile çok düzeyli bir liste oluşturmayı ve word belgesinde özel biçimlendirme uygulamayı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/multilevel-list-formatting/
---
Bu öğreticide, size Aspose.Words for .NET ile word belgesi özelliğinde çok düzeyli liste biçimlendirmesini nasıl kullanacağınızı göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

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


## Çözüm

Bu eğitimde, Aspose.Words for .NET ile bir Word belgesinde çok düzeyli liste biçimlendirme özelliğini kullanma sürecini inceledik. Ana hatları verilen adımları izleyerek, belgelerinizin yapısını ve okunabilirliğini iyileştirerek, çok düzeyli iyi organize edilmiş listeler oluşturabilirsiniz.

### SSS

#### S: Word belgesindeki çok düzeyli liste nedir?

C: Bir Word belgesindeki çok düzeyli bir liste, öğeleri çeşitli alt öğe düzeyleri halinde düzenlemenizi sağlayan hiyerarşik bir listedir. Bilginin yapılandırılmış bir şekilde sunulmasına yardımcı olur ve okuyucuların içeriği anlamasını kolaylaştırır.

#### S: Çok düzeyli listenin görünümünü özelleştirebilir miyim?

C: Evet, Word belgenizdeki çok düzeyli listenin görünümünü özelleştirebilirsiniz. Madde işaretleri, sayılar veya harfler gibi farklı stiller uygulayarak ve girinti ve aralığı ayarlayarak görsel olarak çekici ve düzenli bir liste oluşturabilirsiniz.

#### S: Aspose.Words for .NET diğer liste biçimlendirme seçeneklerini destekliyor mu?

C: Evet, Aspose.Words for .NET, liste biçimlendirme için kapsamlı bir dizi özellik sağlar. Madde işaretli listeler, numaralı listeler ve çok düzeyli listeler dahil olmak üzere çeşitli liste türlerini destekler. Listelerin biçimlendirmesini değiştirebilir, öğe ekleyebilir veya kaldırabilir ve görünümlerini özelleştirebilirsiniz.

#### S: Aspose.Words for .NET'i diğer belge öğeleriyle çalışmak için kullanabilir miyim?

C: Evet, Aspose.Words for .NET paragraflar, tablolar, resimler ve daha fazlası gibi çeşitli belge öğeleriyle çalışmak için kapsamlı yetenekler sunar. Belge işleme görevlerini kolaylaştırarak Word belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanır.