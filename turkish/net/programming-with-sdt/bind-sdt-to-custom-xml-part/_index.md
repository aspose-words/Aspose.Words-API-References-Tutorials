---
title: SDT'yi Özel Xml Bölümüne Bağla
linktitle: SDT'yi Özel Xml Bölümüne Bağla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir SDT'yi Özel Xml Bölümüne nasıl bağlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Bu öğretici, Aspose.Words for .NET kullanılarak bir Yapılandırılmış Belge Etiketinin (SDT) bir Özel Xml Bölümüne nasıl bağlanacağını gösterir. SDT'ler, bir Word belgesine yapılandırılmış içerik denetimleri eklemenize olanak tanır ve CustomXmlParts, belgeyle ilişkili özel XML verilerini depolamak için bir yol sağlar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kitaplığı yüklendi.
- Temel C# ve XML bilgisi.

## 1. Adım: Belge Dizinini kurun
 Belge dizininize giden yolu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Bir Belge ve CustomXmlPart Oluşturun
 Yeni bir örneğini oluştur`Document` sınıf ve bir`CustomXmlPart` özel XML verilerini depolamak için. Özel XML, geçerli XML biçiminde olmalıdır. Bu örnekte, basit bir XML dizesi kullanıyoruz.`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 3. Adım: Belgeye bir StructuredDocumentTag (SDT) ekleyin
 Ekle`StructuredDocumentTag` içerik kontrolü olarak hizmet verecek belgeye. belirtin`SdtType` gibi`PlainText` ve`MarkupLevel` gibi`Block` blok düzeyinde bir SDT oluşturmak için.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Adım 4: SDT için XML Eşlemesini Ayarlayın
 SDT'yi`CustomXmlPart` kullanarak`SetMapping` yöntemi`XmlMapping` mülk. belirtin`CustomXmlPart` , istenen XML düğümünü bulmak için XPath ifadesi ve gerekirse ad alanı öneki. Bu örnekte, SDT'yi şu şekilde eşliyoruz:`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## 5. Adım: Belgeyi Kaydedin
 Değiştirilen belgeyi belirtilen dizine kaydedin.`Save` yöntem. İstenen dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.BindSDTtoCustomXmlPart.doc" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Aspose.Words for .NET kullanan Bind Sd Tto Custom Xml Part için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Bu kadar! Aspose.Words for .NET kullanarak bir SDT'yi Word belgenizdeki bir CustomXmlPart'a başarıyla bağladınız.