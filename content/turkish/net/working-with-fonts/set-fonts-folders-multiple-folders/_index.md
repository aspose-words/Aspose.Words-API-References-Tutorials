---
title: Yazı Tiplerini Ayarlama Klasörleri Birden Çok Klasör
linktitle: Yazı Tiplerini Ayarlama Klasörleri Birden Çok Klasör
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi oluştururken birden fazla yazı tipi klasörü ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi oluştururken birden fazla yazı tipi klasörü ayarlama işlemini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak belgelerinizi işlerken kullanılacak birden fazla yazı tipi klasörünü nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Oluşturulacak belgeyi yükleyin
 Daha sonra, oluşturulacak belgeyi kullanarak yükleyebilirsiniz.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Yazı Tipi Klasörlerini Ayarlayın
 Artık birden fazla yazı tipi klasörünü kullanarak ayarlayabilirsiniz.`FontSettings` sınıf ve`SetFontsFolders()` yöntem. Bir dizide kullanmak istediğiniz yazı tipi klasörlerinin yollarını belirtebilirsiniz. Bu örnekte iki yazı tipi klasörü belirledik: "C:\MyFonts\" ve "D:\Çeşitli\Fontlar\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## 4. Adım: Yazı Tipi Ayarlarını Uygulayın
 Daha sonra yazı tipi ayarlarını belgenize uygulamanız gerekir.`FontSettings` mülkiyeti`Document` sınıf.

```csharp
doc.FontSettings = fontSettings;
```

## 5. Adım: İşlenen belgeyi kaydedin
 Son olarak, oluşturulan belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Klasörlerini Birden Fazla Klasöre Ayarlama için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Bu ayarın, varsayılan olarak aranan tüm varsayılan yazı tipi kaynaklarını geçersiz kılacağını unutmayın. Artık yalnızca bu klasörler aranacak
// Yazı tiplerini oluştururken veya gömerken yazı tipleri. Sistem yazı tipi kaynaklarını korurken fazladan bir yazı tipi kaynağı eklemek için hem FontSettings.GetFontSources hem de kullanın.
// Bunun yerine FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir belgeyi oluştururken birden fazla yazı tipi klasörünün nasıl ayarlanacağını öğrendik. Bu adım adım kılavuzu izleyerek belgelerinizi oluştururken kullanılacak birden fazla yazı tipi klasörünü kolayca belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.

### SSS'ler

#### S: Aspose.Words'te birden fazla yazı tipi klasörünü nasıl ayarlayabilirim?

 C: Aspose.Words'te birden fazla yazı tipi klasörü ayarlamak için`SetFontsFolders` yöntemi`Fonts` özel yazı tipi klasörü konumlarının bir listesini sağlayan sınıf.

#### S: Birden fazla yazı tipi klasörü ayarlamak Aspose.Words ile işlenen tüm belgeleri etkiler mi?

C: Evet, birden fazla yazı tipi klasörü ayarlamak Aspose.Words ile işlenen tüm belgeleri etkiler. Yazı tipi klasörlerini tanımladıktan sonra Aspose.Words, tüm belgelerdeki yazı tiplerini aramak için bu konumları kullanacaktır.

#### S: Aspose.Words'te kaç tane font klasörü tanımlayabilirim?

C: Aspose.Words'te gerektiği kadar yazı tipi klasörü tanımlayabilirsiniz. Tanımlayabileceğiniz yazı tipi klasörlerinin sayısında belirli bir sınır yoktur.

#### S: Aspose.Words'te tanımlanan yazı tipi klasörlerini nasıl kontrol edebilirim?

 C: Aspose.Words'te tanımlanan yazı tipi klasörlerini kontrol etmek için`GetFolders` yöntemi`Fonts` Yapılandırılmış yazı tipi klasörlerinin konumlarını almak için sınıf.

#### S: Yazı tipi klasörlerinin belirli yazı tiplerini içermesi gerekiyor mu?

C: Evet, yazı tipi klasörleri Word belgelerinizde kullanmak istediğiniz yazı tiplerini içermelidir. Aspose.Words, belgeleri işlerken belirtilen klasörlerdeki yazı tiplerini arayacaktır.