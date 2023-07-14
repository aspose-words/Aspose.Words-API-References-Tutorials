---
title: Rusçayı Varsayılan Düzenleme Dili Olarak Ayarla
linktitle: Rusçayı Varsayılan Düzenleme Dili Olarak Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir belgenin varsayılan düzenleme dili olarak Rusça'yı ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

Bu eğitimde, Aspose.Words for .NET ile Rusça'yı varsayılan düzenleme dili olarak ayarlamak için C# kaynak kodunda size yol göstereceğiz. Bu özellik, bir belge yüklerken varsayılan dili ayarlamanıza olanak tanır.

## Adım 1: Proje Kurulumu

Başlamak için favori IDE'nizde yeni bir C# projesi oluşturun. Aspose.Words for .NET kitaplığına projenizde referans verildiğinden emin olun.

## 2. Adım: Belgeyi yükleme

Bu adımda, Rusça'yı varsayılan düzenleme dili olarak ayarlamak istediğimiz Word belgesini yükleyeceğiz. Belgeyi yüklemek için aşağıdaki kodu kullanın:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 Yer değiştirmek`"YOUR DOCUMENTS DIRECTORY"` belgenizin bulunduğu dizinin gerçek yolu ile.

## 3. Adım: Varsayılan dili kontrol etme

Belgeyi yükledikten sonra, varsayılan dilin doğru bir şekilde Rusça olarak ayarlanıp ayarlanmadığını kontrol edeceğiz. Varsayılan dil kimliğini almak için aşağıdaki kodu kullanın:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

Kod, dil kimliğinin Rusça ile eşleşip eşleşmediğini kontrol eder. Sonuca göre ilgili mesajı görüntüler.

### Aspose.Words for .NET kullanarak Rusça'yı Varsayılan Düzenleme Dili Olarak Ayarlamak için örnek kaynak kodu

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 bölümünde doğru belge yolunu belirttiğinizden emin olun.`dataDir` değişken.

Artık Aspose.Words for .NET kullanan bir belge için Rusça'yı varsayılan düzenleme dili olarak nasıl ayarlayacağınızı öğrendiniz. Adım kılavuzunu takip ederek