---
title: Yazı Tipi Ayarları Varsayılan Örnek
linktitle: Yazı Tipi Ayarları Varsayılan Örnek
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde, Aspose.Words for .NET ile bir Word belgesinde varsayılan yazı tipi ayarlarının nasıl yapılandırılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/font-settings-default-instance/
---

Bu eğitimde, .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesinde varsayılan yazı tipi ayarlarını nasıl yapılandıracağınız konusunda size yol göstereceğiz. Varsayılan yazı tipi ayarları, belgeleri yüklerken ve görüntülerken kullanılan yazı tipi kaynaklarını belirtmenize olanak tanır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, Word belgenizin konumuna giden dizin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Adım 2: Varsayılan Yazı Tipi Ayarlarını Yapılandırın
 Daha sonra, şunun bir örneğini oluşturacağız:`FontSettings` kullanarak`FontSettings.DefaultInstance`, ardından belgeleri yüklerken ve işlerken kullanılan yazı tipi kaynaklarını belirteceğiz. Bu örnekte bir sistem yazı tipi kaynağı ve bir klasör yazı tipi kaynağı kullanıyoruz.

```csharp
// Varsayılan yazı tipi ayarlarını yapılandırın
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 3. Adım: Yazı tipi ayarlarını içeren belgeyi yükleyin
 Şimdi belgeyi kullanarak yükleyeceğiz`LoadOptions` ve kullanılacak yazı tipi ayarlarını belirtme.

```csharp
// Belgeyi yazı tipi ayarlarıyla yükleyin
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Aspose.Words for .NET kullanan Yazı Tipi Ayarları Varsayılan Örneği için örnek kaynak kodu 
```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Çözüm
Bu eğitimde Aspose.Words for .NET ile bir Word belgesinde varsayılan yazı tipi ayarlarının nasıl yapılandırılacağını gördük. Belgeleri yüklerken ve oluştururken kullanılan yazı tipi kaynaklarını belirterek, yazı tiplerinin belgelerinizdeki görünümünü kontrol edebilirsiniz. Projelerinizdeki yazı tipi ayarlarını özelleştirmek için bu özelliği kullanmaktan çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te varsayılan yazı tipini nasıl ayarlayabilirim?

 C: Aspose.Words'te varsayılan yazı tipini ayarlamak için`FontSettings` sınıf ve`DefaultFontName` İstenilen yazı tipinin adını belirten özellik.

#### S: Aspose.Words'te varsayılan yazı tipi boyutunu belirtebilir miyim?

 C: Evet, Aspose.Words'te varsayılan yazı tipi boyutunu aşağıdaki komutu kullanarak belirtebilirsiniz:`DefaultFontSize` mülkiyeti`FontSettings` sınıf. İstediğiniz nokta boyutunu ayarlayabilirsiniz.

#### S: Aspose.Words'te varsayılan yazı tipi rengini ayarlamak mümkün mü?

 C: Evet, Aspose.Words'te varsayılan yazı tipi rengini aşağıdaki komutu kullanarak ayarlayabilirsiniz:`DefaultColor` mülkiyeti`FontSettings` sınıf. Rengi RGB değerlerini veya önceden tanımlanmış adları kullanarak belirleyebilirsiniz.

#### S: Varsayılan yazı tipi ayarları tüm belgelere uygulanır mı?

C: Evet, varsayılan yazı tipi ayarları, tek bir belge için belirli ayarlar yapılmadığı sürece Aspose.Words'te oluşturulan veya düzenlenen tüm belgelere uygulanır.