---
title: Fontları Base Olarak Dışa Aktar 64
linktitle: Fontları Base Olarak Dışa Aktar 64
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgeyi kaydederken 64 tabanlı yazı tiplerini dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Bu eğitimde, Aspose.Words for .NET ile 64 tabanlı yazı tiplerini dışa aktarmak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeyi HTML biçiminde kaydederken yazı tiplerini temel 64 verileri olarak dışa aktarmanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, dışa aktarılacak belgeyi yükleyeceğiz. Belgeyi belirli bir dizinden yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Bu kod, örneğini oluşturur`Document` belgeyi belirtilen dizinden yükleyerek.

## 3. Adım: HTML yedekleme seçeneklerini yapılandırma

Şimdi, temel 64 yazı tiplerini dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Bu kod, örneğini oluşturur`HtmlSaveOptions` ve ayarlar`ExportFontsAsBase64` ile`true` HTML olarak kaydederken yazı tiplerinin temel 64 verileri olarak dışa aktarılması gerektiğini belirtmek için.

## 4. Adım: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılmış HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Bu kod, belgeyi HTML'ye dönüştürür ve temel 64 verileri olarak dışa aktarılan yazı tipleriyle bir dosyaya kaydeder.

### Aspose.Words for .NET kullanarak Yazı Tiplerini Base 64 Olarak Dışa Aktarma için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 içindeki belgeler dizinine giden doğru yolu belirttiğinizden emin olun.`dataDir` değişken.

Artık bir belgeyi Aspose.Words for .NET kullanarak HTML olarak kaydederken 64 tabanlı yazı tiplerini nasıl dışa aktaracağınızı öğrendiniz. Bu eğitimde sağlanan adım adım kılavuzu izleyerek, yazı tiplerini güvenli bir şekilde ve HTML belgelerinize katıştırarak kolayca dışa aktarabilirsiniz.