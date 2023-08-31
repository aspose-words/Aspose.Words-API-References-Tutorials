---
title: Word Belgesinde Çok Düzeyli Liste Biçimlendirmesi
linktitle: Word Belgesinde Çok Düzeyli Liste Biçimlendirmesi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile çok düzeyli bir liste oluşturmayı ve word belgesinde özel formatlamayı nasıl uygulayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/document-formatting/multilevel-list-formatting/
---
Bu eğitimde size Aspose.Words for .NET ile word belgesinde çok seviyeli liste formatlama özelliğinin nasıl kullanılacağını göstereceğiz. Kaynak kodunu anlamak ve değişiklikleri uygulamak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi oluşturma ve yapılandırma

Başlamak için yeni bir belge ve ilişkili bir DocumentBuilder nesnesi oluşturun. İşte nasıl:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Çok düzeyli listeyi biçimlendirme

Şimdi DocumentBuilder nesnesinde bulunan yöntemleri kullanarak çok düzeyli liste formatını uygulayacağız. İşte nasıl:

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

 Metin giriş formu alanını ekledikten sonra, belgeyi kullanarak belgeyi istediğiniz konuma kaydedin.`Save` yöntem. Uygun dosya yolunu sağladığınızdan emin olun:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Aspose.Words for .NET kullanılarak Çok Düzeyli Liste Formatlaması için örnek kaynak kodu

Aspose.Words for .NET'in çok seviyeli liste formatlama özelliğinin tam kaynak kodu:


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

Bu kodla çok seviyeli bir liste oluşturabilecek ve Aspose.Words for .NET'i kullanarak her seviyeye uygun formatlamayı uygulayabileceksiniz.


## Çözüm

Bu eğitimde, Aspose.Words for .NET ile bir Word belgesinde çok seviyeli liste formatlama özelliğini kullanma sürecini inceledik. Özetlenen adımları izleyerek, birden çok düzeyde iyi organize edilmiş listeler oluşturabilir, belgelerinizin yapısını ve okunabilirliğini geliştirebilirsiniz.

### SSS'ler

#### S: Word belgesindeki çok düzeyli liste nedir?

C: Word belgesindeki çok düzeyli liste, öğeleri çeşitli alt öğe düzeyleri halinde düzenlemenize olanak tanıyan hiyerarşik bir listedir. Bilginin yapılandırılmış bir şekilde sunulmasına yardımcı olarak okuyucuların içeriği anlamasını kolaylaştırır.

#### S: Çok düzeyli listenin görünümünü özelleştirebilir miyim?

C: Evet, Word belgenizdeki çok düzeyli listenin görünümünü özelleştirebilirsiniz. Madde işaretleri, sayılar veya harfler gibi farklı stiller uygulayarak ve girintiyi ve aralığı ayarlayarak görsel olarak çekici ve düzenli bir liste oluşturabilirsiniz.

#### S: Aspose.Words for .NET diğer liste formatlama seçeneklerini destekliyor mu?

C: Evet, Aspose.Words for .NET liste formatlama için kapsamlı bir dizi özellik sunuyor. Madde işaretli listeler, numaralı listeler ve çok düzeyli listeler dahil olmak üzere çeşitli liste türlerini destekler. Listelerin biçimlendirmesini değiştirebilir, öğe ekleyebilir veya kaldırabilir ve görünümlerini özelleştirebilirsiniz.

#### S: Aspose.Words for .NET'i diğer belge öğeleriyle çalışmak için kullanabilir miyim?

C: Evet, Aspose.Words for .NET paragraflar, tablolar, resimler ve daha fazlası gibi çeşitli belge öğeleriyle çalışmak için kapsamlı yetenekler sunar. Word belgelerini programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanıyarak belge işleme görevlerini kolaylaştırır.