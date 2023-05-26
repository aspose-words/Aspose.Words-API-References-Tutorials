---
title: Yazı Tipi Klasörlerini Ayarla
linktitle: Yazı Tipi Klasörlerini Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda belgelerinizi Aspose.Words for .NET kullanarak işlerken kullanılacak yazı tipi klasörlerini nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenen işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yazı Tipi Kaynaklarını Ayarlayın
 Ardından yazı tipi kaynaklarını kullanarak ayarlayabilirsiniz.`FontSettings.DefaultInstance` sınıf ve`SetFontsSources()` yöntem. Bu örnekte, hem bir sistem yazı tipi kaynağı hem de özel bir klasör yazı tipi kaynağı kullanıyoruz. Özel yazı tipleri klasörünün yolunu ihtiyaçlarınıza göre ayarladığınızdan emin olun.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 3. Adım: Oluşturulacak belgeyi yükleyin
 Artık belgeyi kullanarak işlenecek belgeyi yükleyebilirsiniz.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4. Adım: Oluşturulan belgeyi kaydedin
 Son olarak, işlenen belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Aspose.Words for .NET kullanan Set Fonts Klasörleri için örnek kaynak kodu 
```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi işlerken kullanılacak yazı tipi kaynaklarını kolayca belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle çalışmak için güçlü ve esnek bir API sunar. Bu bilgiyle, belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.