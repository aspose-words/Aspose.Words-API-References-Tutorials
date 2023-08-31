---
title: İçeriğe Bağlantıyı Yapılandırma
linktitle: İçeriğe Bağlantıyı Yapılandırma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgedeki içeriğe bağlantı kurma konusunda adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/configuring-link-to-content/
---

Bu eğitimde, Aspose.Words for .NET ile içeriğe bağlantı kurmanızı sağlayacak C# kaynak kodunu size anlatacağız. Bu özellik, bir belgedeki belirli içeriğe bağlantı vermenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi ve Oluşturucuyu Oluşturma

Bu adımda yeni bir belge oluşturacağız ve yapıcıyı başlatacağız. Aşağıdaki kodu kullanın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Yer imi oluşturun

Şimdi belgede bir yer imi oluşturacağız. İçinde metin bulunan bir yer imi oluşturmak için aşağıdaki kodu kullanın:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Bu kod, "MyBookmark" adında bir yer imi oluşturur ve içine bazı metinler ekler.

## 4. Adım: İçerik bağlantısını ayarlama

Şimdi belge özelliklerini kullanarak içeriğe olan bağlantıyı yapılandıracağız. İçeriğe bağlantı eklemek ve almak için aşağıdaki kodu kullanın:

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

Bu kod, "MyBookmark" yer imiyle birlikte "Yer İşareti" adı verilen içerikle ilgili bir özellik ekler. Daha sonra bağlantı durumu, bağlantı kaynağı ve özellik değeri gibi içerikle ilgili özellik bilgilerini alır.

### Aspose.Words for .NET kullanarak İçerik Bağlantısını Yapılandırmak için örnek kaynak kodu

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

Artık Aspose.Words for .NET kullanarak bir belgedeki içerik bağlantısını nasıl yapılandıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, kendi belgelerinizdeki belirli içeriğe yönelik bağlantıları kolayca oluşturabilir ve yapılandırabilirsiniz.