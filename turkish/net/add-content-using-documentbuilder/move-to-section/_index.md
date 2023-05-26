---
title: Bölüme Taşı
linktitle: Bölüme Taşı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te Bölüme Taşı'yı kullanmak için adım adım kılavuz, Word belgelerindeki bölümleri ve paragrafları manipüle eder.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-section/
---

Bu örnekte, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in Bölüme Taşı özelliğini nasıl kullanacağınızı adım adım göstereceğiz. Bu özellik, bir Word belgesi içindeki farklı bölümlerde gezinmenizi ve bunları değiştirmenizi sağlar. Bu işlevi uygulamanıza entegre etmek için aşağıdaki adımları izleyin.

## 1. Adım: Yeni bir belge oluşturun ve bir bölüm ekleyin

Öncelikle yeni bir belge oluşturup ona bir bölüm eklememiz gerekiyor. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Bu kod yeni bir boş belge oluşturur ve bu belgeye bir bölüm ekler.

## 2. Adım: DocumentBuilder'ı ikinci bölüme taşıyın ve metin ekleyin

Ardından, DocumentBuilder'ı belgenin ikinci bölümüne taşımamız ve oraya biraz metin eklememiz gerekiyor. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Bu kod, mevcut belgeden bir DocumentBuilder oluşturur, ardından imleci DocumentBuilder'dan belgenin ikinci bölümüne taşır. Son olarak, belirtilen metni bu bölüme ekler.

## 3. Adım: Belgeyi mevcut paragraflarla yükleyin

Paragraf içeren mevcut bir belge ile çalışmak istiyorsanız, bu belgeyi aşağıdaki kodu kullanarak yükleyebilirsiniz:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Bu kod belirtilen belgeyi yükler ("MyDir + "Paragraphs.docx yerine""belgenizin gerçek yolu ile) ve belgenin ilk bölümünden paragraf koleksiyonuna erişir. Çizgi`Assert.AreEqual(22, paragraphs.Count);` belgenin 22 paragraf içerdiğini kontrol eder.

## 4. Adım: bir belge için DocumentBuilder oluşturun

Konum indekslerini kullanarak DocumentBuilder imlecini belirli bir paragrafa oluşturabilirsiniz.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## 5. Adım: İmleci belirli bir paragrafa taşıyın


Konum indekslerini kullanarak DocumentBuilder imlecini belirli bir paragrafa taşıyabilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Bu kod, DocumentBuilder'ın imlecini ikinci bölümün üçüncü paragrafına (paragraf 2'deki indeks) ve 10. konuma taşır. Ardından, biraz metin içeren yeni bir paragraf ekler ve imlecin bu yeni paragrafta iyi konumlandırıldığını kontrol eder.

### Aspose.Words for .NET kullanarak Move To Move To Section için örnek kaynak kodu

```csharp

	
	Document doc = new Document();
	doc.AppendChild(new Section(doc));

	// Bir DocumentBuilder'ı ikinci bölüme taşıyın ve metin ekleyin.
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToSection(1);
	builder.Writeln("Text added to the 2nd section.");

	// Paragraflarla belge oluşturun.
	doc = new Document(MyDir + "Paragraphs.docx");
	ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
	Assert.AreEqual(22, paragraphs.Count);

	//Bir belge için DocumentBuilder oluşturduğumuzda, imleci varsayılan olarak belgenin en başındadır,
	// ve DocumentBuilder tarafından eklenen herhangi bir içerik belgenin başına eklenecektir.
	builder = new DocumentBuilder(doc);
	Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

	// İmleci bir paragrafta herhangi bir konuma taşıyabilirsiniz.
	builder.MoveToParagraph(2, 10);
	Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
	builder.Writeln("This is a new third paragraph. ");
	Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
	
        
```

Bu kadar ! Sağlanan kaynak kodunu kullanarak Aspose.Words for .NET'in bölüme taşıma işlevini artık nasıl kullanacağınızı anladınız. Artık bu işlevi kendi uygulamanıza entegre edebilir ve Word belgelerinizin bölümlerini ve paragraflarını dinamik olarak değiştirebilirsiniz.

