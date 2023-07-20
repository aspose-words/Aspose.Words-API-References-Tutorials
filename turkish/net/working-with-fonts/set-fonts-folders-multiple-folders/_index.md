---
title: Font Klasörlerini Birden Fazla Klasör Olarak Ayarla
linktitle: Font Klasörlerini Birden Fazla Klasör Olarak Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken birden fazla yazı tipi klasörü ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken birden fazla yazı tipi klasörü ayarlamak için adım adım size yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, belgelerinizi Aspose.Words for .NET kullanarak işlerken kullanılacak birden çok yazı tipi klasörünü nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenen işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Oluşturulacak belgeyi yükleyin
 Ardından, belgeyi kullanarak işlenecek belgeyi yükleyebilirsiniz.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Yazı Tipi Klasörlerini Ayarlayın
 Artık kullanarak birden fazla yazı tipi klasörü ayarlayabilirsiniz.`FontSettings` sınıf ve`SetFontsFolders()` yöntem. Bir dizide kullanmak istediğiniz yazı tipi klasörlerinin yollarını belirleyebilirsiniz. Bu örnekte, iki yazı tipi klasörü belirledik: "C:\MyFonts\" ve "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 4. Adım: Yazı Tipi Ayarlarını Uygulayın
 Ardından, kullanarak yazı tipi ayarlarını belgenize uygulamanız gerekir.`FontSettings` mülkiyeti`Document` sınıf.

```csharp
doc.FontSettings = fontSettings;
```

## 5. Adım: Oluşturulan belgeyi kaydedin
 Son olarak, işlenen belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Aspose.Words for .NET kullanan Set Fonts Folders Multiple Folders için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Bu ayarın, varsayılan olarak aranmakta olan tüm varsayılan yazı tipi kaynaklarını geçersiz kılacağını unutmayın. Şimdi sadece bu klasörler aranacak
// yazı tipleri oluşturulurken veya gömülürken yazı tipleri. Sistem yazı tipi kaynaklarını korurken fazladan bir yazı tipi kaynağı eklemek için hem FontSettings.GetFontSources hem de
// Bunun yerine FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken birden fazla yazı tipi klasörünün nasıl ayarlanacağını öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi işlerken kullanmak üzere birden çok yazı tipi klasörünü kolayca belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle, belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.

### SSS

#### S: Aspose.Words'ta birden çok yazı tipi klasörünü nasıl ayarlayabilirim?

 C: Aspose.Words'te birden çok yazı tipi klasörü ayarlamak için`SetFontsFolders` yöntemi`Fonts` özel yazı tipi klasörü konumlarının bir listesini sağlayan sınıf.

#### S: Birden fazla yazı tipi klasörü ayarlamak Aspose.Words ile işlenen tüm belgeleri etkiler mi?

C: Evet, birden fazla yazı tipi klasörü ayarlamak Aspose.Words ile işlenen tüm belgeleri etkiler. Yazı tipi klasörlerini tanımladıktan sonra, Aspose.Words tüm belgelerde yazı tiplerini aramak için bu konumları kullanacaktır.

#### S: Aspose.Words'te kaç tane yazı tipi klasörü tanımlayabilirim?

C: Aspose.Words'te gerektiği kadar çok sayıda yazı tipi klasörü tanımlayabilirsiniz. Tanımlayabileceğiniz yazı tipi klasörlerinin sayısında belirli bir sınır yoktur.

#### S: Aspose.Words'te tanımlanan yazı tipi klasörlerini nasıl kontrol edebilirim?

 C: Aspose.Words'te tanımlanan yazı tipi klasörlerini kontrol etmek için`GetFolders` yöntemi`Fonts` Yapılandırılan yazı tipi klasörlerinin konumlarını almak için sınıf.

#### S: Yazı tipi klasörlerinin belirli yazı tiplerini içermesi gerekiyor mu?

C: Evet, yazı tipi klasörleri, Word belgelerinizde kullanmak istediğiniz yazı tiplerini içermelidir. Aspose.Words, belgeleri işlerken belirtilen klasörlerdeki yazı tiplerini arayacaktır.