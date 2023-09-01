---
title: SDT'yi Özel Xml Parçasına Bağla
linktitle: SDT'yi Özel Xml Parçasına Bağla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir SDT'yi Özel Xml Parçasına nasıl bağlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Bu eğitimde Aspose.Words for .NET kullanılarak Yapılandırılmış Belge Etiketinin (SDT) Özel Xml Parçasına nasıl bağlanacağı gösterilmektedir. SDT'ler, bir Word belgesine yapılandırılmış içerik denetimleri eklemenizi sağlar ve CustomXmlParts, belgeyle ilişkili özel XML verilerini depolamanın bir yolunu sağlar.

## Önkoşullar
Bu öğreticiyi takip etmek için aşağıdakilere sahip olmanız gerekir:

- Aspose.Words for .NET kütüphanesi kuruldu.
- Temel C# ve XML bilgisi.

## 1. Adım: Belge Dizinini Ayarlayın
 Belge dizininizin yolunu ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belgeyi kaydetmek istediğiniz dizinin gerçek yolu ile birlikte.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Belge ve CustomXmlPart Oluşturun
 Yeni bir örneğini oluşturun`Document` sınıf ve bir`CustomXmlPart` özel XML verilerini depolamak için. Özel XML geçerli XML biçiminde olmalıdır. Bu örnekte basit bir XML dizesi kullanıyoruz`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## 3. Adım: Belgeye bir StructuredDocumentTag (SDT) ekleyin
 Ekle`StructuredDocumentTag` İçerik kontrolü görevi görecek şekilde belgeye. Belirtin`SdtType` gibi`PlainText` ve`MarkupLevel` gibi`Block` Blok düzeyinde bir SDT oluşturmak için.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## 4. Adım: SDT için XML Eşlemesini Ayarlayın
 SDT'yi şuraya eşleyin:`CustomXmlPart` kullanarak`SetMapping` yöntemi`XmlMapping` mülk. Belirtin`CustomXmlPart` , istenen XML düğümünü bulmak için XPath ifadesi ve gerekiyorsa ad alanı öneki. Bu örnekte SDT'yi şu şekilde eşliyoruz:`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Adım 5: Belgeyi Kaydedin
 Değiştirilen belgeyi aşağıdaki komutu kullanarak belirtilen dizine kaydedin:`Save` yöntem. İstediğiniz dosya adını uygun dosya uzantısıyla sağlayın. Bu örnekte belgeyi "WorkingWithSdt.BindSDTtoCustomXmlPart.doc" olarak kaydediyoruz.

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Aspose.Words for .NET kullanan Bind Sd Tto Custom Xml Part için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir SDT'yi Word belgenizdeki bir CustomXmlPart'a başarıyla bağladınız.