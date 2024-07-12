---
title: Japoncayı Düzenleme Dili Olarak Ekle
linktitle: Japoncayı Düzenleme Dili Olarak Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile Japonca'yı düzenleme dili olarak eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Bu eğitimde, Aspose.Words for .NET ile Japonca'yı düzenleme dili olarak eklemenin işlevselliğini anlamanız ve uygulamanız için sizi adım adım yönlendireceğiz. Bu özellik, bir belgeyi yüklerken dil tercihlerini ayarlamanıza ve düzenleme dili olarak Japonca eklemenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Projenizde Aspose.Words for .NET kütüphanesine başvurulduğundan emin olun.

## Adım 2: Belgeyi yükleme

Bu adımda varsayılan düzenleme dili içermeyen ve Japonca eklemek istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
LoadOptions loadOptions = new LoadOptions();

//Belgeyi yüklerken kullanılacak dil tercihlerini ayarlayın.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## 3. Adım: Varsayılan dili kontrol etme

Belgeyi yükledikten sonra varsayılan düzenleme dilinin Japonca olarak doğru şekilde ayarlanıp ayarlanmadığını kontrol edeceğiz. Uzak Doğu dil kimliğini almak için aşağıdaki kodu kullanın:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Kod, Uzak Doğu dil kimliğinin Japonca ile eşleşip eşleşmediğini kontrol eder. Sonuca göre ilgili mesajı görüntüler.

### Aspose.Words for .NET kullanarak Japoncayı Düzenleme Dilleri Olarak Ekleme için örnek kaynak kodu

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Belge yüklenirken kullanılacak dil tercihlerini ayarlayın.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

