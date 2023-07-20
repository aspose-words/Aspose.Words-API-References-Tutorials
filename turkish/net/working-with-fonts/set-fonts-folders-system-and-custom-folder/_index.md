---
title: Yazı Tipleri Klasör Sistemini ve Özel Klasörü Ayarla
linktitle: Yazı Tipleri Klasör Sistemini ve Özel Klasörü Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken sistem ve özel yazı tipi klasörlerini ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi işlerken sistem yazı tipi klasörlerini ve özel bir klasörü ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, belgelerinizi Aspose.Words for .NET kullanarak işlerken kullanmak için sistem klasörü ve özel bir klasör dahil olmak üzere birden çok yazı tipi klasörünü nasıl belirteceğinizi öğreneceksiniz.

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

## 3. Adım: Sistem ve özel yazı tipi klasörlerini ayarlayın
 Artık sistem yazı tipi klasörlerini ve özel bir klasörü kullanarak ayarlayabilirsiniz.`FontSettings` sınıf ve`SetFontsSources()` yöntem. Öncelikle, kullanarak ortama bağlı yazı tipi kaynaklarının listesini almanız gerekir.`GetFontsSources()` ve bir listede saklayın. Ardından, yeni bir örnek oluşturabilirsiniz.`FolderFontSource` yazı tiplerinizi içeren özel klasörün yolunu belirterek. Bu örneği mevcut yazı tipi kaynakları listesine ekleyin. Son olarak, kullan`SetFontsSources()` Yazı tipi kaynaklarını yeni listeyle güncellemek için.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## 4. Adım: Yazı Tipi Ayarlarını Uygulayın
 Ardından, kullanarak yazı tipi ayarlarını belgenize uygulamanız gerekir.`FontSettings` mülkiyeti`Document` sınıf.

```csharp
doc.FontSettings = fontSettings;
```

## 5. Adım: Oluşturulan belgeyi kaydedin
Son olarak, işlenen belgeyi şu şekilde bir dosyaya kaydedebilirsiniz:

   kullanmak`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Aspose.Words for .NET kullanan Set Fonts Folders System ve Custom Folder için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Varsayılan olarak aranan ortama bağlı yazı tipi kaynakları dizisini alın.
// Örneğin bu, Windows makinelerinde bir "Windows\Fonts\" kaynağı içerecektir.
// Yazı tipi girişlerini eklemeyi veya kaldırmayı çok daha kolay hale getirmek için bu diziyi yeni bir Listeye ekliyoruz.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aspose.Words'e yazı tiplerini aşağıdaki klasörde arama talimatı verecek yeni bir klasör kaynağı ekleyin.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Yazı tiplerimizi içeren özel klasörü mevcut yazı tipi kaynakları listesine ekleyin.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken sistem yazı tipi klasörlerini ve özel bir klasörü nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi işlerken kullanmak üzere sistem klasörü ve özel bir klasör dahil olmak üzere birden çok yazı tipi klasörünü kolayca belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle, belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.

### SSS

#### S: Aspose.Words'ta sistem yazı tipi klasörlerini nasıl ayarlayabilirim?

C: Aspose.Words'te sistem yazı tipi klasörlerini ayarlamak için herhangi bir şey yapmanız gerekmez. Aspose.Words, işletim sisteminizde yüklü olan sistem yazı tiplerini otomatik olarak kullanır.

#### S: Aspose.Words'ta özel yazı tipi klasörlerini nasıl ayarlayabilirim?

 A: Aspose.Words'te özel yazı tipi klasörlerini ayarlamak için`SetFontsFolders` yöntemi`Fonts` özel yazı tipi klasörlerinin konumlarını belirten sınıf.

#### S: Aspose.Words'ta birden fazla özel yazı tipi klasörü belirtebilir miyim?

 C: Evet, Aspose.Words'te birden fazla özel yazı tipi klasörü belirtebilirsiniz.`SetFontsFolders` yöntemi`Fonts` klasör konumlarının bir listesini içeren sınıf.

#### S: Aspose.Words'te tanımlanan yazı tipi klasörlerini nasıl kontrol edebilirim?

 Aspose.Words'te tanımlanan yazı tipi klasörlerini kontrol etmek için`GetFolders` yöntemi`Fonts` Yapılandırılan yazı tipi klasörlerinin listesini almak için sınıf.

#### S: Özel klasör yazı tipleri, Aspose.Words'ta sistem yazı tiplerine göre öncelikli midir?

C: Evet, özel klasör yazı tiplerinin Aspose.Words'ta sistem yazı tiplerine göre önceliği vardır. Hem özel klasörlerde hem de sistem yazı tiplerinde bir yazı tipi varsa, Aspose.Words özel klasördeki sürümü kullanacaktır.