---
title: Özel Belge Özellikleri Ekle
linktitle: Özel Belge Özellikleri Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeye özel özellikler eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/add-custom-document-properties/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeye özel özellikler eklemek için C# kaynak kodunu size anlatacağız. Bu özellik, belgeye özel bilgiler eklemenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda özel özellikler eklemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Özel özellikler ekleyin

Şimdi belgeye özel özellikler ekleyelim. Özellikleri eklemek için aşağıdaki kodu kullanın:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Bu kod öncelikle özel özelliklerde "Yetkili" özelliğinin zaten mevcut olup olmadığını kontrol eder. Varsa süreç kesintiye uğrar. Aksi takdirde özel özellikler belgeye eklenir.

### Aspose.Words for .NET kullanarak Özel Belge Özellikleri Ekleme için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeye özel özelliklerin nasıl ekleneceğini öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek kendi özel özelliklerinizi belgelerinize kolayca ekleyebilirsiniz.