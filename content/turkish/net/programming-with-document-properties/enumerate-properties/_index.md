---
title: Özellikleri Numaralandır
linktitle: Özellikleri Numaralandır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belge özelliklerini numaralandırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/enumerate-properties/
---

Bu eğitimde, Aspose.Words for .NET ile belge özelliklerini numaralandırmak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgenin yerleşik ve özel özelliklerine erişmenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda özelliklerini listelemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Özellikleri numaralandırma

Şimdi hem yerleşik hem de özel özellikler olmak üzere belge özelliklerini listeleyelim. Aşağıdaki kodu kullanın:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Bu kod, belge adını görüntüler ve ardından adlarını ve değerlerini görüntüleyen yerleşik ve özel özellikleri listeler.

### Aspose.Words for .NET kullanan Enumerate Properties için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET'i kullanarak belge özelliklerini nasıl numaralandıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu takip ederek kendi belgelerinizin özelliklerine kolayca erişebilir ve bunları görüntüleyebilirsiniz.

