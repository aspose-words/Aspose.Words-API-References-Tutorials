---
title: Yapılandırılmış Belge Etiket Aralığı Xml Eşlemesini Başlat
linktitle: Yapılandırılmış Belge Etiket Aralığı Xml Eşlemesini Başlat
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir Word belgesinde yapılandırılmış bir belge etiketi aralığı başlangıcı için XML eşlemeyi nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Bu eğitimde, Aspose.Words for .NET kullanılarak bir Word belgesinde yapılandırılmış bir belge etiketi aralığı başlangıcı için XML eşlemenin nasıl kurulacağı açıklanmaktadır. XML eşleme, içerik denetimi içinde bir XML veri kaynağının belirli bölümlerini görüntülemenize olanak tanır.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# bilgisi ve Word belgeleriyle Kelime İşleme.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Belgeyi Yükleyin ve XML Bölümü Oluşturun
 Word belgesini kullanarak yükleyin`Document` yapıcı, belgenin yolunu parametre olarak iletir. Yapılandırılmış belge etiketi içinde görüntülemek istediğiniz verileri içeren bir XML bölümü oluşturun.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## 3. Adım: Yapılandırılmış Belge Etiketi için XML Eşlemesini Ayarlayın
Belgeden başlayarak yapılandırılmış belge etiketi aralığını alın. Ardından, yapılandırılmış belge etiketinin XML eşlemesini, bir XPath ifadesi kullanarak özel XML bölümünün belirli bir bölümünü görüntüleyecek şekilde ayarlayın.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Adım 4: Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Yapılandırılmış Belge Etiket Aralığı için örnek kaynak kodu Aspose.Words for .NET kullanarak Xml Eşlemesini Başlat 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Veri içeren bir XML parçası oluşturun ve bunu belgenin CustomXmlPart koleksiyonuna ekleyin.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Belgedeki CustomXmlPart içeriğimizi görüntüleyecek bir StructuredDocumentTag oluşturun.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// StructuredDocumentTag'imiz için bir eşleme ayarlarsak,
	// yalnızca XPath'ın işaret ettiği CustomXmlPart'ın bir bölümünü görüntüler.
	// Bu XPath, CustomXmlPart'ımızın ilk "<root>" öğesinin içeriğindeki ikinci "<text>" öğesine işaret edecektir.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Word belgenizde yapılandırılmış bir belge etiketi aralığı başlangıcı için XML eşlemesini başarıyla kurdunuz.