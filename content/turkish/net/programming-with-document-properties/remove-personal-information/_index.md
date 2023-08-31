---
title: Kişisel Bilgileri Kaldır
linktitle: Kişisel Bilgileri Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile kişisel bilgilerin bir belgeden kaldırılmasına ilişkin adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/remove-personal-information/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeden kişisel bilgileri kaldırmak için C# kaynak kodunu size anlatacağız. Bu özellik, yazar kimlik verileri gibi hassas kişisel bilgileri bir belgeden kaldırmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda kişisel bilgileri kaldırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Kişisel bilgileri silin

 Artık kişisel bilgilerin kaldırılmasını ayarlayarak etkinleştireceğiz.`RemovePersonalInformation` mülkiyet`true`. Aşağıdaki kodu kullanın:

```csharp
doc.RemovePersonalInformation = true;
```

Bu kod, belgedeki kişisel bilgilerin silinmesini etkinleştirir.

## 4. Adım: Belgeyi kaydetme

Son olarak, kişisel bilgilerin kaldırıldığı belgeyi kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Bu kod, kişisel bilgilerin kaldırıldığı belgeyi yeni bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Kişisel Bilgileri Kaldırmak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak kişisel bilgileri bir belgeden nasıl kaldıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek hassas bilgileri kendi belgelerinizden kolayca kaldırabilirsiniz.