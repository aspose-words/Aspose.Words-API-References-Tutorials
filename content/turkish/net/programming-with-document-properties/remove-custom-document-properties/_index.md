---
title: Özel Belge Özelliklerini Kaldırma
linktitle: Özel Belge Özelliklerini Kaldırma
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeden özel özellikleri kaldırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-properties/remove-custom-document-properties/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeden özel özellikleri kaldırmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeden belirli bir özel özelliği kaldırmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, özel özellikleri kaldırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Özel özelliklerin silinmesi

Şimdi belirli bir özel özelliği belgeden kaldıralım. Aşağıdaki kodu kullanın:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Bu kod, "Yetki Tarihi" özel özelliğini belgeden kaldırır. "Yetki Tarihi"ni, kaldırmak istediğiniz özel özelliğin adıyla değiştirebilirsiniz.

### Aspose.Words for .NET kullanarak Özel Belge Özelliklerini Kaldır için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeden özel özelliklerin nasıl kaldırılacağını öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek özel özellikleri kendi belgelerinizden kolayca kaldırabilirsiniz.