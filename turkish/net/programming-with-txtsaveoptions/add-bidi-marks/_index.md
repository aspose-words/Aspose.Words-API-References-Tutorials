---
title: Word Belgesine Bidi İşaretleri Ekleme
linktitle: Word Belgesine Bidi İşaretleri Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesine Bidi işaretleri eklemeyi öğrenin ve profesyonel çok dilli belgeler oluşturun.
type: docs
weight: 10
url: /tr/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, düzenlemek ve değiştirmek için güçlü bir kitaplıktır. Aspose.Words'ün sunduğu özellikler arasında bir belgeye Bidi (Çift Yönlü) işaretleri ekleyebilme özelliği vardır. Bu kılavuzda, bir belgeye Bidi işaretleri eklemek için Aspose.Words for .NET'in C# kaynak kodunu nasıl kullanacağınız konusunda size yol göstereceğiz.

## Aspose.Words kitaplığını anlama

Koda dalmadan önce, .NET için Aspose.Words kitaplığını anlamak önemlidir. Aspose.Words, Word belgeleriyle çalışmayı kolay ve verimli hale getiren popüler bir kitaplıktır. Bidi işaretleri eklemek de dahil olmak üzere Word belgeleri oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar.

## Belge oluşturma ve içerik ekleme

İlk adım, yeni bir belge oluşturmak ve ona içerik eklemektir. Yeni bir belge örneği oluşturmak için Document sınıfını kullanın. Ardından, belgeye metin eklemek için DocumentBuilder sınıfını kullanın. İşte bir örnek :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Bu örnekte, yeni bir belge oluşturuyoruz ve metin eklemek için DocumentBuilder'ı kullanıyoruz. Farklı dillerde içerik eklendiğini göstermek için biri İngilizce, biri İbranice ve biri Arapça olmak üzere üç satır metin ekledik.

## Bidi işaretleri eklendi

İçerik eklendikten sonra artık belgeye Bidi işaretleri ekleyebiliriz. Bunun için TxtSaveOptions sınıfını kullanıyoruz ve AddBidiMarks özelliğini true olarak ayarlıyoruz. İşte nasıl:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Bu örnekte, bir TxtSaveOptions örneği oluşturuyoruz ve AddBidiMarks özelliğini true olarak ayarlıyoruz. Ardından, belgeyi Bidi işaretleriyle kaydetmek için Document sınıfının Save yöntemini kullanıyoruz.

### Aspose.Words for .NET ile "Add Bidi Marks" işlevi için örnek kaynak kodu

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

Bu kılavuzda, sağlanan C# kaynak kodunu kullanarak bir Word belgesine Bidi işaretleri eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıkladık. Verilen adımları izleyerek, Bidi işaretlerini C# uygulamanızda Word belgelerinize kolayca ekleyebilirsiniz. Aspose.Words, metin formatlama ve dil yönetimi ile çalışmak için muazzam bir esneklik ve güç sunarak, çok dilli belgeleri profesyonelce oluşturmanıza olanak tanır.

### Sıkça Sorulan Sorular

#### S: Aspose.Words for .NET nedir?
Aspose.Words for .NET, bir C# uygulamasında Word belgeleri oluşturmak, düzenlemek ve değiştirmek için güçlü bir kitaplıktır. Bidi (çift yönlü) işaretleri eklemek de dahil olmak üzere Word belgeleriyle çalışmak için birçok özellik sunar.

#### S: Aspose.Words for .NET hangi özellikleri sunuyor?
Aspose.Words for .NET, Word belgeleri oluşturmak, düzenlemek ve değiştirmek için çok çeşitli özellikler sunar. Bu özelliklerden bazıları, belge oluşturma, içerik ekleme, metni biçimlendirme, tabloları yönetme, belgeleri birleştirme ve bölme, belgeleri dönüştürme ve daha fazlasını içerir.

#### S: Aspose.Words for .NET kullanarak Bidi işaretlerini bir Word belgesine nasıl ekleyebilirim?
Aşağıdaki adımları izleyerek Bidi işaretlerini bir Word belgesine ekleyebilirsiniz:

 kullanarak yeni bir belge oluşturun.`Document` sınıf.

 Kullan`DocumentBuilder` belgeye içerik eklemek için sınıf.

 İçeriği ekledikten sonra,`TxtSaveOptions` sınıflandırın ve ayarlayın`AddBidiMarks` mülkiyet`true`.

 kullanarak belgeyi Bidi işaretleriyle kaydedin.`Save` yöntemi`Document` sınıf.

#### S: Aspose.Words, Bidi işaretleri eklemek için birden çok dili destekliyor mu?
Evet, Aspose.Words, Bidi işaretleri eklemek için birden çok dili destekler. Aspose.Words for .NET'i kullanarak İngilizce, İbranice ve Arapça gibi farklı dillerdeki metne Bidi işaretleri ekleyebilirsiniz.

#### S: Belgeyi Bidi işaretleriyle kaydetmek için herhangi bir ek seçenek var mı?
Evet, Bidi işaretleriyle belgeyi kaydederken diğer seçenekleri belirleyebilirsiniz.`TxtSaveOptions` sınıf. Örneğin, belge kaydetme biçimini, kodlama seçeneklerini vb. ayarlayabilirsiniz.