---
title: Mhtml Kaynakları İçin Cid URL'lerini Dışa Aktar
linktitle: Mhtml Kaynakları İçin Cid URL'lerini Dışa Aktar
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir belgeyi kaydederken MHTML kaynaklarının CID URL'lerini dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Bu eğitimde, Aspose.Words for .NET ile MHTML kaynakları için CID URL'lerini dışa aktarmak üzere C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeyi MHTML biçiminde kaydederken MHTML kaynaklarının CID URL'lerini dışa aktarmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, dışa aktarılacak belgeyi yükleyeceğiz. Belgeyi belirli bir dizinden yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Bu kod, örneğini oluşturur`Document` belgeyi belirtilen dizinden yükleyerek.

## 3. Adım: HTML yedekleme seçeneklerini yapılandırma

Şimdi, MHTML kaynaklarının CID URL'lerini dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Bu kod, örneğini oluşturur`HtmlSaveOptions` kaydetme biçimi MHTML olarak ayarlıyken. Ayrıca ayarlayarak MHTML kaynaklarının CID URL'lerinin dışa aktarılmasını sağlar.`ExportCidUrlsForMhtmlResources` ile`true`.

## 4. Adım: Belgeyi MHTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılmış HTML kaydetme seçeneklerini kullanarak belgeyi MHTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

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

 içindeki belgeler dizinine giden doğru yolu belirttiğinizden emin olun.`dataDir` değişken.

Artık bir belgeyi Aspose.Words for .NET kullanarak MHTML formatında kaydederken MHTML kaynaklarının CID URL'lerini nasıl dışa aktaracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, dışa aktarılan MHTML belgelerinizdeki CID URL'lerini kolayca yönetebilirsiniz.

