---
title: Seçenekleri gör
linktitle: Seçenekleri gör
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile belge görüntüleme seçeneklerini yapılandırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/view-options/
---

Bu öğreticide, Aspose.Words for .NET ile görüntüleme seçeneklerini yapılandırmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgede görüntüleme modunu ve yakınlaştırma düzeyini özelleştirmenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, görüntüleme seçeneklerini yapılandırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Görüntü seçeneklerini yapılandırma

Şimdi belge görüntüleme seçeneklerini yapılandıracağız. Ekran modunu ve yakınlaştırma seviyesini ayarlamak için aşağıdaki kodu kullanın:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Bu kod, görüntüleme modunu "PageLayout" olarak ve yakınlaştırma seviyesini %50 olarak ayarlar.

### Aspose.Words for .NET kullanan Görünüm Seçenekleri için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak belge görüntüleme seçeneklerini nasıl yapılandıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek kendi belgelerinizin görünümünü kolayca özelleştirebilirsiniz.