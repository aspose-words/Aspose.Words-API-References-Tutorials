---
title: Word Belgesinde Bölüme Taşı
linktitle: Word Belgesinde Bölüme Taşı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in word belgesinde Bölüme Taşı özelliğinin Word belgelerindeki bölümleri ve paragrafları işlemek için adım adım kılavuzu.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-section/
---
Bu örnekte, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in word belgesinde Bölüme Taşı özelliğini nasıl kullanacağınızı adım adım anlatacağız. Bu özellik, bir Word belgesinin farklı bölümlerinde gezinmenize ve bunları değiştirmenize olanak tanır. Bu işlevselliği uygulamanıza entegre etmek için aşağıdaki adımları izleyin.

## 1. Adım: Yeni bir belge oluşturun ve bölüm ekleyin

Öncelikle yeni bir belge oluşturup ona bir bölüm eklememiz gerekiyor. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Bu kod yeni bir boş belge oluşturur ve bu belgeye bir bölüm ekler.

## Adım 2: DocumentBuilder'ı ikinci bölüme taşıyın ve metin ekleyin

Daha sonra DocumentBuilder'ı belgenin ikinci bölümüne taşımamız ve oraya bir miktar metin eklememiz gerekiyor. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Bu kod, mevcut belgeden bir DocumentBuilder oluşturur ve ardından imleci DocumentBuilder'dan belgenin ikinci bölümüne taşır. Son olarak belirtilen metni bu bölüme ekler.

## 3. Adım: Mevcut paragrafları içeren bir belge yükleyin

Paragraf içeren mevcut bir belgeyle çalışmak istiyorsanız bu belgeyi aşağıdaki kodu kullanarak yükleyebilirsiniz:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Bu kod belirtilen belgeyi yükler ("MyDir + "Paragraphs.docx ile değiştirin)"" belgenizin gerçek yolu ile birlikte) ve belgenin ilk bölümündeki paragraf koleksiyonuna erişir. Çizgi`Assert.AreEqual(22, paragraphs.Count);` belgenin 22 paragraf içerip içermediğini kontrol eder.

## Adım 4: Bir belge için DocumentBuilder oluşturun

Konumsal indeksleri kullanarak DocumentBuilder imlecini belirli bir paragrafa oluşturabilirsiniz.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Adım 5: İmleci belirli bir paragrafa taşıyın


DocumentBuilder imlecini konumsal indeksleri kullanarak belirli bir paragrafa taşıyabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Bu kod, DocumentBuilder'ın imlecini ikinci bölümün üçüncü paragrafına (indeks 2'deki paragraf) ve 10. konuma taşır. Daha sonra bazı metinler içeren yeni bir paragraf ekler ve imlecin bu yeni paragrafta iyi konumlandığını kontrol eder.

### Aspose.Words for .NET kullanarak Bölüme Taşı için örnek kaynak kodu

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// DocumentBuilder'ı ikinci bölüme taşıyın ve metin ekleyin.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Paragraflarla belge oluşturun.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Bir belge için DocumentBuilder oluşturduğumuzda, imleci varsayılan olarak belgenin en başındadır,
// ve DocumentBuilder tarafından eklenen herhangi bir içerik belgenin başına eklenecektir.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//İmleci paragrafta herhangi bir konuma taşıyabilirsiniz.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Bu kadar ! Artık sağlanan kaynak kodunu kullanarak Aspose.Words for .NET'in bölüme taşıma işlevini nasıl kullanacağınızı anladınız. Artık bu işlevselliği kendi uygulamanıza entegre edebilir ve Word belgelerinizin bölümlerini ve paragraflarını dinamik olarak değiştirebilirsiniz.

## Çözüm

Bu örnekte Aspose.Words for .NET'in Bölüme Taşı özelliğini inceledik. Yeni bir belge oluşturmayı, ona bölümler eklemeyi ve bir Word belgesindeki belirli bölümlere ve paragraflara gitmek için DocumentBuilder sınıfını kullanmayı öğrendik. Bu özellik, geliştiricilere Aspose.Words for .NET kullanarak Word belgelerinin içeriğini ve yapısını programlı bir şekilde değiştirebilmeleri için güçlü araçlar sağlar.

### Word belgesindeki bölüme geçişle ilgili SSS'ler

#### S: Aspose.Words for .NET'teki Bölüme Taşı özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Bölüme Taşı özelliği, geliştiricilerin bir Word belgesi içindeki farklı bölümlere programlı olarak gitmesine ve bunları değiştirmesine olanak tanır. Belgenin belirli bölümlerine içerik ekleme, değiştirme veya silme olanağı sağlar.

#### S: DocumentBuilder'ı bir Word belgesindeki belirli bir bölüme nasıl taşıyabilirim?

C: DocumentBuilder'ı bir Word belgesindeki belirli bir bölüme taşımak için DocumentBuilder sınıfının MoveToSection yöntemini kullanabilirsiniz. Bu yöntem hedef bölümün indeksini parametre olarak alır ve imleci o bölümün başına yerleştirir.

#### S: Bölüme Taşı özelliğini kullanarak belirli bir bölüme taşındıktan sonra içerik ekleyebilir veya değiştirebilir miyim?

C: Evet, DocumentBuilder MoveToSection kullanılarak istenen bölüme konumlandırıldığında, o bölümün içeriğini eklemek veya değiştirmek için DocumentBuilder sınıfının Writeln, Write veya InsertHtml gibi çeşitli yöntemlerini kullanabilirsiniz.

#### S: Bölüme Taşı özelliğini kullanarak bir belgedeki mevcut paragraflarla nasıl çalışabilirim?

C: Belge yapıcısını kullanarak paragraflar içeren mevcut bir belgeyi yükleyebilir ve ardından FirstSection.Body.Paragraphs özelliğini kullanarak istediğiniz bölümdeki paragraf koleksiyonuna erişebilirsiniz.

#### S: Bölüme Taşı özelliğini kullanarak DocumentBuilder imlecini bölüm içindeki belirli bir paragrafa taşıyabilir miyim?

C: Evet, MoveToParagraph yöntemini kullanarak DocumentBuilder imlecini bölüm içindeki belirli bir paragrafa taşıyabilirsiniz. Bu yöntem, hedef paragrafın indekslerini ve paragraf içindeki karakter konumunu (offset) parametre olarak alır.