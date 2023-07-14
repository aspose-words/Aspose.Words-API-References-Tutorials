---
title: Yazı Tipi Ayarları Varsayılan Örneği
linktitle: Yazı Tipi Ayarları Varsayılan Örneği
second_title: Aspose.Words Belge İşleme API'sı
description: Bu eğitimde, Aspose.Words for .NET ile bir Word belgesinde varsayılan yazı tipi ayarlarının nasıl yapılandırılacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/font-settings-default-instance/
---

Bu öğreticide, .NET için Aspose.Words kitaplığı kullanılarak bir Word belgesinde varsayılan yazı tipi ayarlarının nasıl yapılandırılacağı konusunda size yol göstereceğiz. Varsayılan yazı tipi ayarları, belgeleri yüklerken ve işlerken kullanılan yazı tipi kaynaklarını belirtmenize olanak tanır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Varsayılan Yazı Tipi Ayarlarını Yapılandırın
 Ardından, bir örneğini oluşturacağız`FontSettings` kullanarak`FontSettings.DefaultInstance`, ve ardından belgeleri yüklerken ve işlerken kullanılan yazı tipi kaynaklarını belirteceğiz. Bu örnekte, bir sistem yazı tipi kaynağı ve bir klasör yazı tipi kaynağı kullanıyoruz.

```csharp
// Varsayılan yazı tipi ayarlarını yapılandırın
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## 3. Adım: Belgeyi yazı tipi ayarlarıyla yükleyin
 Şimdi kullanarak belgeyi yükleyeceğiz`LoadOptions` ve kullanılacak yazı tipi ayarlarını belirleme.

```csharp
// Belgeyi yazı tipi ayarlarıyla yükleyin
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Aspose.Words for .NET kullanan Yazı Tipi Ayarları Varsayılan Örneği için örnek kaynak kodu 
```csharp

//Belge dizininizin yolu
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
Bu eğitimde, Aspose.Words for .NET ile bir Word belgesinde varsayılan yazı tipi ayarlarının nasıl yapılandırılacağını gördük. Belgeleri yüklerken ve görüntülerken kullanılan yazı tipi kaynaklarını belirterek, belgelerinizdeki yazı tiplerinin görünümünü kontrol edebilirsiniz. Projelerinizde yazı tipi ayarlarını özelleştirmek için bu özelliği kullanmaktan çekinmeyin.

### SSS

#### S: Aspose.Words'ta varsayılan yazı tipini nasıl ayarlayabilirim?

 C: Aspose.Words'te varsayılan yazı tipini ayarlamak için`FontSettings` sınıf ve`DefaultFontName` istenen yazı tipinin adını belirten özellik.

#### S: Aspose.Words'te varsayılan yazı tipi boyutunu belirtebilir miyim?

 C: Evet, Aspose.Words'te varsayılan yazı tipi boyutunu şu şekilde belirleyebilirsiniz:`DefaultFontSize`mülkiyeti`FontSettings` sınıf. İstediğiniz nokta boyutunu ayarlayabilirsiniz.

#### S: Aspose.Words'te varsayılan yazı tipi rengini ayarlamak mümkün mü?

 C: Evet, Aspose.Words'te varsayılan yazı tipi rengini`DefaultColor`mülkiyeti`FontSettings` sınıf. Rengi, RGB değerlerini veya önceden tanımlanmış adları kullanarak belirleyebilirsiniz.

#### S: Varsayılan yazı tipi ayarları tüm belgeler için geçerli mi?

C: Evet, tek bir belge için özel ayarlar yapılmadığı sürece, varsayılan yazı tipi ayarları Aspose.Words'te oluşturulan veya düzenlenen tüm belgeler için geçerlidir.