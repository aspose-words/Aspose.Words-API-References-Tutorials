---
title: Japoncayı Düzenleme Dilleri Olarak Ekleyin
linktitle: Japoncayı Düzenleme Dilleri Olarak Ekleyin
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile Japonca'yı düzenleme dili olarak eklemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Bu öğreticide, Aspose.Words for .NET ile bir düzenleme dili olarak Japonca eklemenin işlevselliğini anlamanız ve uygulamanız için sizi adım adım yönlendireceğiz. Bu özellik, bir belge yüklerken dil tercihlerini ayarlamanıza ve düzenleme dili olarak Japonca eklemenize olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda Japonca eklemek istediğimiz ve varsayılan bir düzenleme dili içermeyen Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
LoadOptions loadOptions = new LoadOptions();

// Belge yüklenirken kullanılacak dil tercihlerini ayarlayın.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## 3. Adım: Varsayılan dili kontrol etme

Belgeyi yükledikten sonra, varsayılan düzenleme dilinin doğru bir şekilde Japonca olarak ayarlanıp ayarlanmadığını kontrol edeceğiz. Uzak Doğu dil kimliğini almak için aşağıdaki kodu kullanın:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

Kod, Uzak Doğu dil kimliğinin Japonca ile eşleşip eşleşmediğini kontrol eder. Sonuca göre ilgili mesajı görüntüler.

### Aspose.Words for .NET kullanarak Düzenleme Dilleri Olarak Japonca Ekleme için örnek kaynak kodu

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

