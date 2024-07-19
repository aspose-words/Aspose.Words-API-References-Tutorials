---
title: Gidiş Dönüş Bilgilerini Dışa Aktar
linktitle: Gidiş Dönüş Bilgilerini Dışa Aktar
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir belgeyi HTML olarak kaydederken gidiş dönüş bilgilerini dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Bu eğitimde, Aspose.Words for .NET ile bir belgeden gidiş-dönüş bilgilerini dışa aktarmak için C# kaynak kodunu size anlatacağız. Bu özellik, dışa aktarılan HTML dosyasına gidiş-dönüş bilgilerini eklemenizi sağlayarak orijinal belgede yapılan değişiklikleri almayı kolaylaştırır.

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

Şimdi belgenin gidiş dönüş bilgilerini dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` ve ayarlar`ExportRoundtripInformation` seçeneği`true` dışa aktarma sırasında gidiş dönüş bilgilerini dahil etmek için.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Bu kod, belgeyi gidiş dönüş bilgileri dahil olmak üzere HTML'ye dönüştürür ve dışa aktarılan HTML dosyasını belirtilen dizine kaydeder.

### Aspose.Words for .NET kullanarak Gidiş-Dönüş Bilgilerini Dışa Aktarma için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Belgeler dizininin doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.