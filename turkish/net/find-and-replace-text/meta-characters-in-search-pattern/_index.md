---
title: Arama Modelindeki Meta Karakterler
linktitle: Arama Modelindeki Meta Karakterler
second_title: Aspose.Words for .NET API Referansı
description: Word belgelerini işlemek için Aspose.Words for .NET ile arama modelinde meta karakterleri nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/find-and-replace-text/meta-characters-in-search-pattern/
---

Bu makalede, Aspose.Words for .NET kitaplığında Meta Karakterler Arama Modeli işlevinin nasıl kullanılacağını anlamak için yukarıdaki C# kaynak kodunu inceleyeceğiz. Bu özellik, Word belgelerinde gelişmiş aramalar ve değiştirmeler yapmak için özel metakarakterler kullanmanıza olanak tanır.

## Önkoşullar

- C# dili hakkında temel bilgi.
- Aspose.Words kütüphanesinin kurulu olduğu .NET geliştirme ortamı.

## 1. Adım: Yeni Belge Oluşturma

 Arama modelinde meta karakterleri kullanmaya başlamadan önce Aspose.Words for .NET kullanarak yeni bir belge oluşturmamız gerekiyor. Bu, bir örneği başlatarak yapılabilir.`Document` nesne:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2. Adım: Belgeye metin ekleyin

 Bir belgemiz olduğunda, bir metin kullanarak metin ekleyebiliriz.`DocumentBuilder` nesne. Örneğimizde,`Writeln` Ve`Write` iki satır metin ekleme yöntemleri:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## 3. Adım: Metni bulun ve meta karakterlerle değiştirin

 Şimdi kullanacağız`Range.Replace` özel metakarakterler içeren bir arama deseni kullanarak metni arama ve değiştirme işlevi. Örneğimizde, "Bu satır 1&pBu satır 2" ifadesini "Bu satır değiştirildi" ile değiştiriyoruz.`&p` paragraf sonunu temsil eden meta karakter:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## 4. Adım: Belgeye sayfa sonu ekleme

 Başka bir meta karakterin kullanımını göstermek için, belgeye bir sayfa sonu ekleyeceğiz.`InsertBreak` ile yöntem`BreakType.PageBreak` parametre. Önce imleci hareket ettiriyoruz`DocumentBuilder` belgenin sonuna, ardından sayfa sonunu ve yeni bir metin satırı ekliyoruz:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## 5. Adım: Bulun ve başka bir meta karakterle değiştirin

 Şimdi başka bir arama gerçekleştireceğiz ve`&m` sayfa sonunu temsil eden meta karakter. "Bu satır 1&mBu satır 2" ifadesini "Sayfa sonu yeni metinle değiştirildi" ile değiştiriyoruz. :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## 6. Adım: Düzenlenen belgeyi kaydetme

 Son olarak, değiştirilmiş belgeyi kullanarak belirtilen bir dizine kaydediyoruz.`Save` yöntem:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Aspose.Words for .NET kullanan Arama Modelindeki Meta Karakterler için örnek kaynak kodu

Aspose.Words for .NET ile arama modelinde meta karakterlerin kullanımını gösteren tam örnek kaynak kodu burada:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Çözüm

Bu makalede, Aspose.Words for .NET arama modelinde meta karakterlerin nasıl kullanılacağını anlamak için C# kaynak kodunu inceledik. Bir belge oluşturmak, metin eklemek, özel meta karakterleri kullanarak arama yapmak ve değiştirmek, sayfa sonları eklemek ve düzenlenen belgeyi kaydetmek için adım adım bir kılavuz izledik.
