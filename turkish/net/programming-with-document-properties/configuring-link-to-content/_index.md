---
title: İçeriğe Bağlantıyı Yapılandırma
linktitle: İçeriğe Bağlantıyı Yapılandırma
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgedeki içeriğe bağlantı kurmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/configuring-link-to-content/
---

Bu eğitimde, Aspose.Words for .NET ile içeriğe bağlantı kurmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgedeki belirli içeriğe bağlantı vermenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi ve Oluşturucuyu Oluşturma

Bu adımda yeni bir belge oluşturacağız ve yapıcıyı başlatacağız. Aşağıdaki kodu kullanın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Bir yer imi oluşturun

Şimdi belgede bir yer imi oluşturacağız. İçinde metin bulunan bir yer imi oluşturmak için aşağıdaki kodu kullanın:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Bu kod, "MyBookmark" adlı bir yer imi oluşturur ve içine biraz metin ekler.

## 4. Adım: İçerik bağlantısını ayarlama

Şimdi, belge özelliklerini kullanarak içeriğe giden bağlantıyı yapılandıracağız. İçeriğe bağlantı eklemek ve almak için aşağıdaki kodu kullanın:

```csharp
// Belgedeki tüm özel özelliklerin listesini alın.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// İçeriğe bağlı bir özellik ekleyin.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Bu kod, "Yer İmi" adlı içerikle ilgili bir özelliği "MyBookmark" yer imi ile ekler. Ardından, bağlantı durumu, bağlantı kaynağı ve özellik değeri gibi içerikle ilgili özellik bilgilerini alır.

### Aspose.Words for .NET kullanarak İçerik Bağlantısını Yapılandırma için örnek kaynak kodu

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Dosyadan tüm özel belge özelliklerinin bir listesini alın.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// İçerik özelliğine bağlı ekleyin.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Artık Aspose.Words for .NET kullanarak bir belgedeki içerik bağlantısını nasıl yapılandıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, kendi belgelerinizdeki belirli içeriklere kolayca bağlantılar oluşturabilir ve yapılandırabilirsiniz.