---
title: Özel Xml Parçasına Eşlenen Tablo Yinelenen Bölüm Oluşturma
linktitle: Özel Xml Parçasına Eşlenen Tablo Yinelenen Bölüm Oluşturma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde CustomXmlPart'a eşlenen yinelenen bölüm içeren bir tablonun nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## giriiş

Bu eğitimde, Aspose.Words for .NET'i kullanarak özel bir XML parçasıyla eşlenen yinelenen bölüm içeren bir tablo oluşturma sürecini anlatacağız. Bu özellikle yapılandırılmış verilere dayalı dinamik olarak belge oluşturmak için kullanışlıdır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
1.  Aspose.Words for .NET kütüphanesi kuruldu. adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/words/net/).
2. C# ve XML'in temel anlayışı.

## Ad Alanlarını İçe Aktar

Projenize gerekli ad alanlarını eklediğinizden emin olun:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## 1. Adım: Document ve DocumentBuilder'ı başlatın

 Öncelikle yeni bir belge oluşturun ve bir başlangıç değeri oluşturun.`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Özel XML Parçası Ekleme

Belgeye özel bir XML bölümü ekleyin. Bu XML, tablomuza eşlemek istediğimiz verileri içerir:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Adım 3: Tablo Yapısını Oluşturun

 Daha sonra şunu kullanın:`DocumentBuilder` tablo başlığını oluşturmak için:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Adım 4: Yinelenen Bölüm Oluşturun

 Bir oluştur`StructuredDocumentTag` (SDT) yinelenen bölüm için ve bunu XML verileriyle eşleyin:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Adım 5: Yinelenen Bölüm Öğesi Oluşturun

Yinelenen bölüm öğesi için bir SDT oluşturun ve bunu yinelenen bölüme ekleyin:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Adım 6: XML Verilerini Tablo Hücreleriyle Eşleyin

Başlık ve yazar için SDT'ler oluşturun, bunları XML verileriyle eşleştirin ve satıra ekleyin:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Adım 7: Belgeyi Kaydedin

Son olarak belgeyi belirtilen dizine kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Çözüm

Bu adımları izleyerek, Aspose.Words for .NET'i kullanarak özel bir XML parçasına eşlenen yinelenen bölümü olan bir tabloyu başarıyla oluşturdunuz. Bu, yapılandırılmış verilere dayalı dinamik içerik oluşturmaya olanak tanıyarak belge oluşturmayı daha esnek ve güçlü hale getirir.

## SSS'ler

### StructuredDocumentTag (SDT) nedir?
İçerik kontrolü olarak da bilinen SDT, bir belgede yapılandırılmış verileri barındırmak için kullanılan sınırlı bir bölgedir.

### Özel XML bölümünde diğer veri türlerini kullanabilir miyim?
Evet, özel XML parçanızı istediğiniz veri türüyle yapılandırabilir ve bunları buna göre eşleyebilirsiniz.

### Yinelenen bölüme nasıl daha fazla satır eklerim?
Yinelenen bölüm, eşlenen XML yolundaki her öğe için satır yapısını otomatik olarak çoğaltır.