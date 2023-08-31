---
title: Kişisel Bilgileri Kaldır
linktitle: Kişisel Bilgileri Kaldır
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeden kişisel bilgileri kaldırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/remove-personal-information/
---

Bu öğreticide, Aspose.Words for .NET ile bir belgeden kişisel bilgileri kaldırmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, yazar tanımlama verileri gibi hassas kişisel bilgileri bir belgeden kaldırmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, kişisel bilgileri kaldırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Kişisel bilgileri silin

 Şimdi ayarlayarak kişisel bilgilerin kaldırılmasını sağlayacağız.`RemovePersonalInformation` mülkiyet`true`. Aşağıdaki kodu kullanın:

```csharp
doc.RemovePersonalInformation = true;
```

Bu kod, belgedeki kişisel bilgilerin silinmesini etkinleştirir.

## 4. Adım: Belgeyi kaydetme

Son olarak, kişisel bilgiler çıkarılmış olarak belgeyi kaydedeceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Bu kod, belgeyi kişisel bilgiler kaldırılarak yeni bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Kişisel Bilgileri Kaldırmak için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeden kişisel bilgileri nasıl kaldıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek hassas bilgileri kendi belgelerinizden kolayca kaldırabilirsiniz.