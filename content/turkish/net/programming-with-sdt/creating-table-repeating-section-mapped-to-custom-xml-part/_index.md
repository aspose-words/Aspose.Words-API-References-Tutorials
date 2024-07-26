---
title: Özel Xml Parçasına Eşlenen Tablo Yinelenen Bölüm Oluşturma
linktitle: Özel Xml Parçasına Eşlenen Tablo Yinelenen Bölüm Oluşturma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde CustomXmlPart'a eşlenen yinelenen bölüm içeren bir tablonun nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Bu eğitimde, Aspose.Words for .NET kullanılarak bir Word belgesindeki Özel Xml Parçasına eşlenen yinelenen bölüm içeren bir tablonun nasıl oluşturulacağı gösterilmektedir. Yinelenen bölüm, Özel Xml Bölümünde depolanan XML verilerine dayalı olarak dinamik olarak satır eklemenizi sağlar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Bir Document ve DocumentBuilder Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`DocumentBuilder` Belgenin içeriğini oluşturmak için.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: CustomXmlPart'a Özel XML Verileri Ekleme
 Oluşturmak`CustomXmlPart` ve buna özel XML verileri ekleyin. Bu örnekte, başlıkları ve yazarlarıyla birlikte bir kitap koleksiyonunu temsil eden bir XML dizesi oluşturuyoruz.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Adım 4: Tablo ve Tablo Yapısı Oluşturun
kullanarak bir tablo oluşturmaya başlayın.`StartTable` yöntemi`DocumentBuilder` . kullanarak tablo hücreleri ve içerik ekleyin.`InsertCell`Ve`Write` yöntemler.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Adım 5: Özel XML ile Eşlenen Yinelenen Bölümü Oluşturun
 Oluşturmak`StructuredDocumentTag` ile`SdtType.RepeatingSection` yinelenen bölümü temsil etmek için. Yinelenen bölüm için XML eşlemesini kullanarak ayarlayın.`SetMapping` yöntemi`XmlMapping` mülk. Bu örnekte, yinelenen bölümü şu şekilde eşliyoruz:`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Adım 6: Yinelenen Bölüm Öğesini Oluşturun ve Hücreleri Ekleyin
 Oluşturmak`StructuredDocumentTag` ile`SdtType.RepeatingSectionItem` yinelenen bölüm öğesini temsil etmek için. Tekrarlanan bölüme çocuk olarak ekleyin.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Oluşturmak`Row` yinelenen bölümdeki her bir öğeyi temsil etmek ve onu yinelenen bölüm öğesine eklemek için.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Adım 7: Yinelenen Bölüme İçerik Kontrolleri Ekleyin
 Yaratmak`StructuredDocumentTag` olan nesneler`SdtType.PlainText`

  başlık ve yazar içerik kontrollerini temsil etmek için. Her içerik denetimi için XML eşlemesini aşağıdakileri kullanarak ayarlayın:`SetMapping` yöntemi`XmlMapping` mülk. Bu örnekte, başlık kontrolünü şuna eşliyoruz:`/books[1]/book[1]/title[1]` ve yazar kontrolü`/books[1]/book[1]/author[1]`.

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

## Adım 8: Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save`yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Aspose.Words for .NET Kullanarak Özel Xml Parçasına Eşlenen Tablo Yinelenen Bölüm Oluşturmak için örnek kaynak kodu 

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

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde CustomXmlPart'a eşlenen yinelenen bölümü olan bir tabloyu başarıyla oluşturdunuz.