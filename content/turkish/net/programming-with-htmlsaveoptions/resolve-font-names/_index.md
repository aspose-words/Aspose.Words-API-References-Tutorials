---
title: Yazı Tipi Adlarını Çözümle
linktitle: Yazı Tipi Adlarını Çözümle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile HTML'ye dönüştürürken eksik font adlarını çözmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Bu eğitimde, Aspose.Words for .NET ile eksik font adlarını çözmek için C# kaynak kodunu size anlatacağız. Bu özellik, bir belgeyi HTML'ye dönüştürürken eksik yazı tipi adlarını otomatik olarak çözmenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda işlenecek belgeyi yükleyeceğiz. Belgeyi belirtilen dizinden yüklemek için aşağıdaki kodu kullanın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Bu kod bir örneğini oluşturur`Document` Belgeyi belirtilen dizinden yükleyerek.

## 3. Adım: HTML yedekleme seçeneklerini yapılandırma

Şimdi dönüştürme sırasında eksik yazı tipi adlarını çözmek için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions`ve ayarlar`ResolveFontNames` seçeneği`true` HTML'ye dönüştürürken eksik yazı tipi adlarını çözmek için. Ayrıca`PrettyFormat` seçenek şu şekilde ayarlandı:`true` Güzel biçimlendirilmiş HTML kodu almak için.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Bu kod, eksik yazı tipi adlarını otomatik olarak çözümleyerek belgeyi HTML'ye dönüştürür ve dönüştürülen HTML dosyasını belirtilen dizine kaydeder.

### Aspose.Words for .NET kullanarak Yazı Tipi Adlarını Çözmek için örnek kaynak kodu

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

 Belgeler dizininin doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.