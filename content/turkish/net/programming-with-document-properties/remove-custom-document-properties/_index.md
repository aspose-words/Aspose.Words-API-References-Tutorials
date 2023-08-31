---
title: Özel Belge Özelliklerini Kaldır
linktitle: Özel Belge Özelliklerini Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeden özel özellikleri kaldırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/remove-custom-document-properties/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeden özel özellikleri kaldırmak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgeden belirli bir özel özelliği kaldırmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda özel özelliklerini kaldırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Özel özellikleri silme

Şimdi belirli bir özel özelliği belgeden kaldıralım. Aşağıdaki kodu kullanın:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Bu kod, "Yetkili Tarih" özel özelliğini belgeden kaldırır. "Yetkili Tarih"i, kaldırmak istediğiniz özel özelliğin adıyla değiştirebilirsiniz.

### Aspose.Words for .NET kullanarak Özel Belge Özelliklerini Kaldırmak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak özel özellikleri bir belgeden nasıl kaldıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek özel özellikleri kendi belgelerinizden kolayca kaldırabilirsiniz.