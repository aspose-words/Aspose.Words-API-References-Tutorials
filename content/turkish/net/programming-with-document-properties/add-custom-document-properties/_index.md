---
title: Özel Belge Özellikleri Ekle
linktitle: Özel Belge Özellikleri Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeye özel özellikler eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/add-custom-document-properties/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeye özel özellikler eklemek için size C# kaynak kodunda yol göstereceğiz. Bu özellik, belgeye özel bilgiler eklemenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, özel özellikler eklemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
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

Bu kod ilk olarak "Yetkili" özelliğinin özel özelliklerde zaten var olup olmadığını kontrol eder. Varsa, işlem kesintiye uğrar. Aksi takdirde, özel özellikler belgeye eklenir.

### Aspose.Words for .NET kullanarak Add Custom Document Properties için örnek kaynak kodu

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

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeye nasıl özel özellikler ekleyeceğinizi öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek kendi özel özelliklerinizi belgelerinize kolayca ekleyebilirsiniz.