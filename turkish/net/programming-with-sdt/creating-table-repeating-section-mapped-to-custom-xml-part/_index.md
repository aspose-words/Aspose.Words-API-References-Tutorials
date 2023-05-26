---
title: Özel Xml Bölümüne Eşlenen Tablo Yinelenen Bölüm Oluşturma
linktitle: Özel Xml Bölümüne Eşlenen Tablo Yinelenen Bölüm Oluşturma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir Word belgesinde bir CustomXmlPart'a eşlenen yinelenen bir bölümle tablo oluşturmayı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Bu eğitim, Aspose.Words for .NET kullanılarak bir Word belgesindeki Özel Xml Bölümüne eşlenen yinelenen bir bölüm içeren bir tablonun nasıl oluşturulacağını gösterir. Yinelenen bölüm, Özel Xml Bölümünde depolanan XML verilerine dayalı olarak satırları dinamik olarak eklemenize olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle çalışma.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"`belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`DocumentBuilder` Belgenin içeriğini oluşturmak için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir CustomXmlPart'a Özel XML Verileri Ekleyin
 Oluşturmak`CustomXmlPart` ve buna özel XML verileri ekleyin. Bu örnekte, başlıkları ve yazarlarıyla birlikte bir kitap koleksiyonunu temsil eden bir XML dizesi oluşturuyoruz.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## 4. Adım: Bir Tablo ve Tablo Yapısı Oluşturun
 kullanarak bir tablo oluşturmaya başlayın.`StartTable` yöntemi`DocumentBuilder` . kullanarak tablo hücreleri ve içerik ekleyin.`InsertCell` Ve`Write` yöntemler.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## 5. Adım: Özel XML ile Eşlenen Yinelenen Bölümü Oluşturun
 Oluşturmak`StructuredDocumentTag` ile`SdtType.RepeatingSection` yinelenen bölümü temsil etmek için. kullanarak yinelenen bölüm için XML eşlemesini ayarlayın.`SetMapping` yöntemi`XmlMapping` mülk. Bu örnekte, yinelenen bölümü şu şekilde eşliyoruz:`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## 6. Adım: Yinelenen Bölüm Öğesini Oluşturun ve Hücreleri Ekleyin
 Oluşturmak`StructuredDocumentTag` ile`SdtType.RepeatingSectionItem` yinelenen bölüm öğesini temsil etmek için. Yinelenen bölüme bir çocuk olarak ekleyin.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Oluşturmak`Row`yinelenen bölümdeki her bir öğeyi temsil etmek ve onu yinelenen bölüm öğesine eklemek.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## 7. Adım: Yinelenen Bölüme İçerik Kontrolleri Ekleyin
 Yaratmak`StructuredDocumentTag` olan nesneler`SdtType.PlainText`

  başlık ve yazar içerik denetimlerini temsil etmek için. kullanarak her içerik denetimi için XML eşlemesini ayarlayın.`SetMapping` yöntemi`XmlMapping` mülk. Bu örnekte, başlık kontrolünü şu şekilde eşliyoruz:`/books[1]/book[1]/title[1]` ve yazar kontrolü`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## 8. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Aspose.Words for .NET kullanarak Özel Xml Bölümüne Eşlenen Tablo Yinelenen Bölüm Oluşturma için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde bir CustomXmlPart'a eşlenen yinelenen bir bölüm içeren bir tabloyu başarıyla oluşturdunuz.