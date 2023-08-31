---
title: Mhtml Kaynakları İçin Cid URL'lerini Dışa Aktarma
linktitle: Mhtml Kaynakları İçin Cid URL'lerini Dışa Aktarma
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi kaydederken MHTML kaynaklarının CID URL'lerini dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Bu eğitimde, Aspose.Words for .NET ile MHTML kaynaklarının CID URL'lerini dışa aktarmak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgeyi MHTML biçiminde kaydederken MHTML kaynaklarının CID URL'lerini dışa aktarmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda dışa aktarılacak belgeyi yükleyeceğiz. Belgeyi belirtilen dizinden yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Bu kod bir örneğini oluşturur`Document` Belgeyi belirtilen dizinden yükleyerek.

## 3. Adım: HTML yedekleme seçeneklerini yapılandırma

Şimdi MHTML kaynaklarının CID URL'lerini dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` kaydetme biçimi MHTML olarak ayarlandığında. Ayrıca MHTML kaynaklarının CID URL'lerinin aşağıdaki ayarları yaparak dışa aktarılmasını da sağlar:`ExportCidUrlsForMhtmlResources` ile`true`.

## Adım 4: Belgeyi MHTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılan HTML kaydetme seçeneklerini kullanarak belgeyi MHTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Bu kod, belgeyi MHTML'ye dönüştürür ve dışa aktarılan MHTML kaynaklarının CID URL'lerini içeren bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Mhtml Kaynakları İçin Cid URL'lerini Dışa Aktarma için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Belgeler dizininin doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeyi MHTML formatında kaydederken MHTML kaynaklarının CID URL'lerini nasıl dışa aktaracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek dışa aktarılan MHTML belgelerinizdeki CID URL'lerini kolayca yönetebilirsiniz.

