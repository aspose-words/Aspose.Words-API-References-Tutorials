---
title: otomatik bağlantı
linktitle: otomatik bağlantı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile otomatik bağlantı eklemeyi öğrenin Adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-markdown/autolink/
---

Bu örnekte "Autolink" özelliğinin Aspose.Words for .NET ile nasıl kullanılacağını açıklayacağız. Bu özellik, belgenize otomatik olarak köprüler eklemenizi sağlar.

## 1. Adım: Bir belge oluşturucu kullanma

İlk olarak, belgemize içerik eklemek için bir belge oluşturucu kullanacağız.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. Adım: Köprü ekleme

 kullanarak bir köprü ekleyebiliriz.`InsertHyperlink` belge üreteci yöntemi. Bağlantı için görüntülenecek URL'yi ve metni belirliyoruz.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", yanlış);
```

## 3. Adım: Bağlantı olarak bir e-posta adresi ekleme

Ayrıca "mailto:" önekini kullanarak bir e-posta adresini bağlantı olarak ekleyebiliriz. Bu, kullanıcıların varsayılan e-posta istemcilerini açmak için bağlantıyı tıklamasına olanak tanır.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 4. Adım: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

### Aspose.Words for .NET kullanan Otomatik Bağlantı için Örnek Kaynak Kodu


```csharp
	// Belgeye içerik eklemek için bir belge oluşturucu kullanın.
	DocumentBuilder builder = new DocumentBuilder();

	//Köprü ekle.
	builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", yanlış);
	builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
            
```


Tebrikler! Artık "Autolink" özelliğini Aspose.Words for .NET ile nasıl kullanacağınızı öğrendiniz.

