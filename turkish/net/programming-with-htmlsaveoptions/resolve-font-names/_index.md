---
title: Yazı Tipi Adlarını Çöz
linktitle: Yazı Tipi Adlarını Çöz
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile HTML'ye dönüştürürken eksik yazı tipi adlarını çözmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Bu eğitimde, Aspose.Words for .NET ile eksik yazı tipi adlarını çözmek için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belgeyi HTML'ye dönüştürürken eksik yazı tipi adlarını otomatik olarak çözmenizi sağlar.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, işlenecek belgeyi yükleyeceğiz. Belgeyi belirli bir dizinden yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Bu kod, örneğini oluşturur`Document` belgeyi belirtilen dizinden yükleyerek.

## 3. Adım: HTML yedekleme seçeneklerini yapılandırma

Şimdi dönüştürme sırasında eksik yazı tipi adlarını çözmek için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Bu kod, örneğini oluşturur`HtmlSaveOptions`ve ayarlar`ResolveFontNames` seçeneği`true` HTML'ye dönüştürürken eksik yazı tipi adlarını çözmek için. Ayrıca`PrettyFormat` seçeneği ayarlandı`true` güzel biçimlendirilmiş HTML kodu almak için.

## 4. Adım: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılmış HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Bu kod, eksik yazı tipi adlarını otomatik olarak çözerek belgeyi HTML'ye dönüştürür ve dönüştürülen HTML dosyasını belirtilen dizine kaydeder.

### Aspose.Words for .NET kullanarak Yazı Tipi Adlarını Çözümlemek için örnek kaynak kodu

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 içindeki belgeler dizinine giden doğru yolu belirttiğinizden emin olun.`dataDir` değişken.