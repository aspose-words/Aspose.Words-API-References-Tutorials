---
title: Vurgular
linktitle: Vurgular
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile vurguları (kalın ve italik) nasıl kullanacağınızı öğrenin. Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/emphases/
---

Bu örnekte Aspose.Words for .NET ile vurguların nasıl kullanılacağını açıklayacağız. Vurgu, metnin kalın ve italik gibi belirli kısımlarını vurgulamak için kullanılır.

## 1. Adım: Belgenin başlatılması

 İlk olarak, bir örneğini oluşturarak belgeyi başlatacağız.`Document` sınıf.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Adım 2: Belge oluşturucuyu kullanma

Daha sonra belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Vurgularla metin ekleyin

Belge oluşturucunun yazı tipi özelliklerini değiştirerek vurgulu metin ekleyebiliriz. Bu örnekte metnin farklı bölümlerini vurgulamak için kalın ve italik yazı tipini kullanıyoruz.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## 4. Adım: Belgeyi kaydetme

 Son olarak belgeyi istediğimiz formatta kaydedebiliriz. Bu örnekte, şunu kullanıyoruz:`.md` Markdown formatının uzantısı.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Tebrikler! Artık Aspose.Words for .NET ile vurguların nasıl kullanılacağını öğrendiniz.

### Aspose.Words for .NET kullanan Emphase'ler için örnek kaynak kodu


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### SSS'ler

#### S: Markdown'ı kullanarak metni nasıl vurgularım?

C: Markdown'ı kullanarak metni vurgulamak için metni uygun sembollerle çevrelemeniz yeterlidir. Kullanmak`*` veya`_` italikler için,`**` veya`__` kalın için ve`~~` üstü çizili için.

#### S: Farklı vurguları aynı metinde birleştirebilir miyiz?

 C: Evet, aynı metinde farklı vurguları birleştirmek mümkündür. Örneğin, her ikisini de kullanarak bir kelimeyi kalın ve italik hale getirebilirsiniz.`**`Ve`*` kelimenin etrafında.

#### S: Markdown'da hangi vurgulama seçenekleri mevcut?

C: Markdown'da mevcut olan vurgulama seçenekleri italiktir (`*` veya`_`), gözü pek (`**` veya`__`) ve üstü çizili (`~~`).

#### S: Metnin Markdown tarafından vurgulamak için kullanılan özel karakterleri içerdiği durumları nasıl ele alacağım?

 C: Metniniz Markdown tarafından vurgulamak için kullanılan özel karakterler içeriyorsa, önüne bir karakter koyarak bunlardan kurtulabilirsiniz.`\` . Örneğin,`\*` gerçek bir yıldız işareti gösterecektir.

#### S: CSS kullanarak vurgulamanın görünümünü özelleştirebilir miyiz?

C: Markdown'da vurgulama genellikle tarayıcının varsayılan stilleri kullanılarak oluşturulur. Markdown'ınızı HTML'ye dönüştürürseniz CSS kurallarını kullanarak vurgulamanın görünümünü özelleştirebilirsiniz.