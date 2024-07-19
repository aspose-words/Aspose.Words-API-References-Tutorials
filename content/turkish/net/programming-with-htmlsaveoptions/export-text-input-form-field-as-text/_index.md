---
title: Metin Giriş Formu Alanını Metin Olarak Dışa Aktar
linktitle: Metin Giriş Formu Alanını Metin Olarak Dışa Aktar
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile metin girişi form alanlarını düz metin olarak dışa aktarmak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

Bu eğitimde, Aspose.Words for .NET ile metin giriş formu alanlarını düz metin olarak dışa aktarmak için C# kaynak kodunu size anlatacağız. Bu özellik, metin girişi form alanlarını HTML giriş öğeleri olarak dışa aktarmak yerine okunabilir metin olarak dışa aktarmanıza olanak tanır.

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

Şimdi metin giriş formu alanlarını düz metin olarak dışa aktarmak için HTML kaydetme seçeneklerini yapılandıracağız. Aşağıdaki kodu kullanın:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Belirtilen klasör mevcut ve boş olmalıdır.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Bu kod bir örneğini oluşturur`HtmlSaveOptions` ve ayarlar`ExportTextInputFormFieldAsText` seçeneği`true` metin giriş formu alanlarını düz metin olarak dışa aktarmak için. Ayrıca çıkarılan görsellerin kaydedileceği klasörü de belirtir.

## Adım 4: Belgeyi HTML'ye dönüştürme ve kaydetme

Son olarak, daha önce yapılandırılan HTML kaydetme seçeneklerini kullanarak belgeyi HTML'ye dönüştüreceğiz. Aşağıdaki kodu kullanın:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Bu kod, metin girişi form alanlarını düz metin olarak dışa aktararak belgeyi HTML'ye dönüştürür ve dışa aktarılan HTML dosyasını belirtilen dizine kaydeder.

### Aspose.Words for .NET kullanarak Metin Giriş Formu Alanını Metin Olarak Dışa Aktarma için örnek kaynak kodu


```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Belirtilen klasörün mevcut olması ve boş olması gerekir.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Form alanlarını HTML giriş öğeleri olarak değil, düz metin olarak dışa aktarma seçeneğini ayarlayın.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Belgeler dizininin doğru yolunu belirttiğinizden emin olun.`dataDir` değişken.