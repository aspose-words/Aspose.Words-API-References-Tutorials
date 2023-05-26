---
title: Yazı Tipi Klasörlerini Öncelikli Olarak Ayarla
linktitle: Yazı Tipi Klasörlerini Öncelikli Olarak Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini öncelikli olarak ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-with-priority/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini öncelikli olarak ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, belgelerinizi Aspose.Words for .NET kullanarak işlerken özel arama önceliğine sahip çoklu yazı tipi klasörlerini nasıl belirteceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenen işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yazı tipi klasörlerini öncelikli olarak ayarlayın
 Ardından, yazı tipi klasörlerini öncelikli olarak ayarlayabilirsiniz.`FontSettings` sınıf ve`SetFontsSources()` yöntem. Örneklerini kullanarak birden çok yazı tipi kaynağı belirleyebilirsiniz.`SystemFontSource` Ve`FolderFontSource`. Bu örnekte, iki yazı tipi kaynağı tanımladık: varsayılan sistem yazı tipi kaynağı ve 1 önceliğe sahip özel bir yazı tipi klasörü.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Aspose.Words for .NET kullanarak Öncelikli Yazı Tipleri Klasörlerini Ayarlamak için örnek kaynak kodu 
```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini nasıl öncelikli olarak ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi işlerken özel arama önceliğine sahip birden çok yazı tipi klasörünü kolayca belirtebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle çalışmak için güçlü ve esnek bir API sunar. Bu bilgiyle, belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.