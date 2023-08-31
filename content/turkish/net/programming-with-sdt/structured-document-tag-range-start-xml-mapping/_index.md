---
title: Yapılandırılmış Belge Etiket Aralığı Xml Eşlemesini Başlat
linktitle: Yapılandırılmış Belge Etiket Aralığı Xml Eşlemesini Başlat
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesinde başlayan yapılandırılmış bir belge etiketi aralığı için XML eşlemeyi nasıl kuracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Word belgesinde yapılandırılmış bir belge etiket aralığı başlangıcı için XML eşlemenin nasıl kurulacağını açıklar. XML eşleme, içerik denetimi içinde bir XML veri kaynağının belirli bölümlerini görüntülemenizi sağlar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belgeyi Yükleyin ve XML Parçası Oluşturun
 kullanarak Word belgesini yükleyin.`Document` yapıcı, belgenin yolunu bir parametre olarak iletir. Yapılandırılmış belge etiketi içinde görüntülemek istediğiniz verileri içeren bir XML bölümü oluşturun.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 3. Adım: Yapılandırılmış Belge Etiketi için XML Eşlemesini Ayarlayın
Belgeden başlayarak yapılandırılmış belge etiketi aralığını alın. Ardından, yapılandırılmış belge etiketi için XML eşlemesini, bir XPath ifadesi kullanarak özel XML bölümünün belirli bir bölümünü gösterecek şekilde ayarlayın.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## 4. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Yapılandırılmış Belge Etiket Aralığı için örnek kaynak kodu Aspose.Words for .NET kullanarak Xml Eşlemeyi Başlat 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Veri içeren bir XML bölümü oluşturun ve bunu belgenin CustomXmlPart koleksiyonuna ekleyin.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Belgede CustomXmlPart'ımızın içeriğini gösterecek bir StructuredDocumentTag oluşturun.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// StructuredDocumentTag'imiz için bir eşleme ayarlarsak,
	// yalnızca XPath'ın işaret ettiği CustomXmlPart'ın bir bölümünü görüntüler.
	// Bu XPath, CustomXmlPart'ımızın ilk "<root>" öğesinin ikinci "<text>" öğesinin içeriğine işaret edecektir.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak Word belgenizde yapılandırılmış bir belge etiketi aralığı başlangıcı için XML eşlemeyi başarıyla kurdunuz.