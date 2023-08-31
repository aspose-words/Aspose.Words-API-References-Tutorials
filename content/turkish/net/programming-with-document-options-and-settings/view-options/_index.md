---
title: Seçenekleri gör
linktitle: Seçenekleri gör
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile belge görüntüleme seçeneklerini yapılandırmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/view-options/
---

Bu eğitimde, Aspose.Words for .NET ile görüntü seçeneklerini yapılandırmak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgedeki görünüm modunu ve yakınlaştırma düzeyini özelleştirmenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda görüntüleme seçeneklerini yapılandırmak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Görüntüleme seçeneklerini yapılandırma

Şimdi belge görüntüleme seçeneklerini yapılandıracağız. Görüntüleme modunu ve yakınlaştırma düzeyini ayarlamak için aşağıdaki kodu kullanın:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Bu kod, görünüm modunu "PageLayout" ve yakınlaştırma düzeyini %50 olarak ayarlar.

### Aspose.Words for .NET kullanan Görünüm Seçenekleri için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET'i kullanarak belge görüntüleme seçeneklerini nasıl yapılandıracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek kendi belgelerinizin görünümünü kolayca özelleştirebilirsiniz.