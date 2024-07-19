---
title: Kaynakları Dışa Aktar
linktitle: Kaynakları Dışa Aktar
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile HTML olarak kaydederken belge kaynaklarını dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-resources/
---

Bu eğitimde, Aspose.Words for .NET ile belge kaynaklarını dışa aktarmak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgeyi HTML biçiminde kaydederken yazı tipleri gibi kaynakları harici dosyalar olarak dışa aktarmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda dışa aktarılacak belgeyi yükleyeceğiz. Belgeyi belirtilen dizinden yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu kod bir örneğini oluşturur`Document` Belgeyi belirtilen dizinden yükleyerek.

## 3. Adım: HTML yedekleme seçeneklerini yapılandırma

Şimdi belge kaynaklarını dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` ve aşağıdaki seçenekleri ayarlar:

- `CssStyleSheetType` ayarlandı`CssStyleSheetType.External` CSS stil sayfasını harici bir dosyaya aktarmak için.
- `ExportFontResources` ayarlandı`true` yazı tipi kaynaklarını dışa aktarmak için.
- `ResourceFolder` kaynakların kaydedileceği hedef dizini belirtir.
- `ResourceFolderAlias`kaynaklara erişmek için kullanılacak URL takma adını belirtir.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve belirtilen URL takma adını kullanarak kaynakları belirtilen dizine kaydeder.

### Aspose.Words for .NET kullanarak Kaynakları Dışa Aktarma için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Belgeler dizininin doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.