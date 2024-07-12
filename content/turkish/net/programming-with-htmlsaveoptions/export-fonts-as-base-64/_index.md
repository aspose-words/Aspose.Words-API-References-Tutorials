---
title: Yazı Tiplerini Base 64 Olarak Dışa Aktar
linktitle: Yazı Tiplerini Base 64 Olarak Dışa Aktar
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi kaydederken temel 64 yazı tipini dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Bu eğitimde, temel 64 yazı tiplerini Aspose.Words for .NET ile dışa aktarmak için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgeyi HTML biçiminde kaydederken yazı tiplerini temel 64 verileri olarak dışa aktarmanıza olanak tanır.

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

Şimdi temel 64 yazı tipini dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` ve setler`ExportFontsAsBase64` ile`true` HTML olarak kaydederken yazı tiplerinin temel 64 verileri olarak dışa aktarılması gerektiğini belirtmek için.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve temel 64 verileri olarak dışa aktarılan yazı tipleriyle birlikte bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Yazı Tiplerini Base 64 Olarak Dışa Aktarma için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Belgeler dizininin doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanarak bir belgeyi HTML olarak kaydederken temel 64 yazı tipini nasıl dışa aktaracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, yazı tiplerini güvenli bir şekilde dışa aktarabilir ve HTML belgelerinize katıştırabilirsiniz.