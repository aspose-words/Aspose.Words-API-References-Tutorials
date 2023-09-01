---
title: True Type Yazı Tipleri Klasörünü Ayarla
linktitle: True Type Yazı Tipleri Klasörünü Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi oluştururken gerçek tip yazı tipleri klasörünü ayarlamaya yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-true-type-fonts-folder/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi işlerken doğru tip yazı tipleri klasörünü ayarlamanız için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak belgelerinizi işlerken kullanılacak True Type yazı tiplerini içeren özel bir klasörü nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Oluşturulacak belgeyi yükleyin
 Daha sonra, belgeyi kullanarak oluşturulacak belgeyi yüklemeniz gerekir.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: True Type Yazı Tipleri Klasörünü Ayarlayın
Artık, bir örneğini oluşturarak oluşturma sırasında kullanılacak gerçek tip yazı tiplerinin klasörünü belirtebilirsiniz.`FontSettings` sınıf ve kullanımı`SetFontsFolder()` yazı tipleri klasörünü ayarlama yöntemi. True Type yazı tiplerinizi içeren özel bir klasör belirtebilirsiniz. İkinci parametre`SetFontsFolder()` belirtilen klasörün alt klasörlerinde de arama yapmak isteyip istemediğinizi belirtir.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## 4. Adım: İşlenen belgeyi kaydedin
 Son olarak, oluşturulan belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Aspose.Words for .NET kullanarak Set True Type Fonts Klasörü için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Bu ayarın, varsayılan olarak aranan tüm varsayılan yazı tipi kaynaklarını geçersiz kılacağını unutmayın. Artık yalnızca bu klasörler aranacak
// Yazı tiplerini oluştururken veya gömerken kullanılan yazı tipleri. Sistem yazı tipi kaynaklarını korurken fazladan bir yazı tipi kaynağı eklemek için hem FontSettings.GetFontSources hem de kullanın.
// Bunun yerine FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Yazı tipi ayarlarını belirleme
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir belgeyi oluştururken true type fonts klasörünü nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek belgelerinizi oluştururken kullanılacak True Type yazı tiplerini içeren özel bir klasörü kolayca belirtebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tiplerini kontrol edebilir ve özelleştirebilirsiniz.

### SSS'ler

#### S: Aspose.Words'te TrueType yazı tipleri klasörünü nasıl yapılandırabilirim?

 C: Aspose.Words'te TrueType yazı tipleri klasörünü yapılandırmak için`SetTrueTypeFontsFolder` yöntemi`Fonts` TrueType yazı tiplerini içeren klasörün konumunu belirten sınıf.

#### S: Hangi tür yazı tipleri TrueType yazı tipleri olarak kabul edilir?

C: TrueType yazı tipleri popüler bir yazı tipi biçimidir. Genellikle Word belgelerinde kullanılırlar ve .ttf veya .ttc dosya uzantısına sahiptirler.

#### S: Aspose.Words'te birden fazla TrueType yazı tipi klasörü belirtebilir miyim?

C: Evet, Aspose.Words'te birden fazla TrueType yazı tipi klasörü belirleyebilirsiniz.`SetTrueTypeFontsFolder` yöntemi`Fonts` klasör konumlarının listesini içeren sınıf.

#### S: Aspose.Words'te yapılandırılan TrueType yazı tipleri klasörünü nasıl kontrol edebilirim?

 C: Aspose.Words'te yapılandırılmış TrueType Fonts klasörünü kontrol etmek için`GetTrueTypeFontsFolder` yöntemi`Fonts` Yapılandırılmış TrueType Yazı Tipleri klasörünün konumunu almak için sınıf.

#### S: Aspose.Words'te TrueType yazı tipleri klasörünü yapılandırmak neden önemlidir?

C: Aspose.Words'te TrueType yazı tipleri klasörünü ayarlamak önemlidir çünkü Aspose.Words'ün Word belgelerini işlerken gereken yazı tiplerini bulmasına yardımcı olur. Bu, farklı sistemlerde bile belge formatı ve görünümünde tutarlılık sağlar.