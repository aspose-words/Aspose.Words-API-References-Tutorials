---
title: Word Belgesine Bidi İşaretleri Ekleme
linktitle: Word Belgesine Bidi İşaretleri Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak bir Word belgesine Bidi işaretleri eklemeyi öğrenin ve çok dilli profesyonel belgeler oluşturun.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmaya, düzenlemeye ve işlemeye yönelik güçlü bir kitaplıktır. Aspose.Words'ün sunduğu özellikler arasında bir belgeye Bidi (Çift yönlü) işaretler ekleyebilme yeteneği de vardır. Bu kılavuzda, bir belgeye Bidi işaretlerini eklemek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kütüphanesini anlama

Koda dalmadan önce .NET için Aspose.Words kütüphanesini anlamak önemlidir. Aspose.Words, Word belgeleriyle Kelime İşlemeyi kolay ve verimli hale getiren popüler bir kütüphanedir. Bidi işaretleri eklemek de dahil olmak üzere Word belgelerini oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar.

## Belgeyi oluşturma ve içerik ekleme

İlk adım, yeni bir belge oluşturmak ve ona içerik eklemektir. Yeni bir belge örneği oluşturmak için Document sınıfını kullanın. Daha sonra belgeye metin eklemek için DocumentBuilder sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Bu örnekte yeni bir belge oluşturuyoruz ve metin eklemek için DocumentBuilder'ı kullanıyoruz. Farklı dillerde içerik eklemeyi göstermek için üç satırlık metin ekledik: biri İngilizce, biri İbranice ve biri de Arapça.

## Bidi işaretleri eklendi

İçerik eklendikten sonra artık Bidi işaretlerini belgeye ekleyebiliriz. Bunun için TxtSaveOptions sınıfını kullanıyoruz ve AddBidiMarks özelliğini true olarak ayarlıyoruz. İşte nasıl:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Bu örnekte bir TxtSaveOptions örneği oluşturuyoruz ve AddBidiMarks özelliğini true olarak ayarlıyoruz. Daha sonra Document sınıfının Save metodunu kullanarak belgeyi Bidi işaretleriyle kaydediyoruz.

### Aspose.Words for .NET ile "Bidi İşaretleri Ekle" işlevi için örnek kaynak kodu

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Belgeyi oluşturun ve içerik ekleyin
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Bidi işaretleri ekleyin
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Çözüm

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir Word belgesine Bidi işaretlerini eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıkladık. Verilen adımları takip ederek Bidi işaretlerini C# uygulamanızda Word belgelerinize kolayca ekleyebilirsiniz. Aspose.Words, metin biçimlendirme ve dil yönetimi ile Kelime İşleme için muazzam bir esneklik ve güç sunarak, çok dilli belgeleri profesyonelce oluşturmanıza olanak tanır.

### Sıkça Sorulan Sorular

#### S: Aspose.Words for .NET nedir?
Aspose.Words for .NET, bir C# uygulamasında Word belgelerini oluşturmak, düzenlemek ve değiştirmek için güçlü bir kütüphanedir. Bidi (çift yönlü) işaretlerin eklenmesi dahil, Word belgeleriyle Kelime İşleme için birçok özellik sunar.

#### S: Aspose.Words for .NET hangi özellikleri sunuyor?
Aspose.Words for .NET, Word belgelerini oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar. Bu özelliklerden bazıları belge oluşturma, içerik ekleme, metni biçimlendirme, tabloları yönetme, belgeleri birleştirme ve bölme, belgeleri dönüştürme ve daha fazlasını içerir.

#### S: Aspose.Words for .NET kullanarak bir Word belgesine Bidi işaretlerini nasıl ekleyebilirim?
Aşağıdaki adımları izleyerek bir Word belgesine Bidi işaretleri ekleyebilirsiniz:

 kullanarak yeni bir belge oluşturun.`Document` sınıf.

 Kullan`DocumentBuilder` Belgeye içerik eklemek için sınıf.

 İçeriği ekledikten sonra,`TxtSaveOptions`sınıfı seçin ve ayarlayın`AddBidiMarks` mülkiyet`true`.

 Belgeyi Bidi işaretleriyle kaydedin.`Save` yöntemi`Document` sınıf.

#### S: Aspose.Words Bidi işaretlerini eklemek için birden fazla dili destekliyor mu?
Evet, Aspose.Words Bidi işaretlerini eklemek için birden fazla dili destekler. Aspose.Words for .NET'i kullanarak İngilizce, İbranice ve Arapça gibi farklı dillerdeki metne Bidi işaretleri ekleyebilirsiniz.

#### S: Belgeyi Bidi işaretleriyle kaydetmeye yönelik ek seçenekler var mı?
 Evet, belgeyi Bidi işaretleriyle kaydederken diğer seçenekleri belirleyebilirsiniz.`TxtSaveOptions` sınıf. Örneğin belge kaydetme biçimini, kodlama seçeneklerini vb. ayarlayabilirsiniz.