---
title: Bidi İşaretleri Ekleyin
linktitle: Bidi İşaretleri Ekleyin
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