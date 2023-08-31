---
title: Mevcut Yazı Tiplerinin Listesini Alın
linktitle: Mevcut Yazı Tiplerinin Listesini Alın
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde Aspose.Words for .NET'te bulunan yazı tiplerinin listesini nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-list-of-available-fonts/
---
Bu eğitimde Aspose.Words for .NET'te bulunan yazı tiplerinin listesini nasıl alacağınızı açıklayacağız. Kullanılabilir yazı tipleri listesi, belgelerinizde hangi yazı tiplerini kullanabileceğinizi bilmenizi sağlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

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

## 2. Adım: Yazı tipi kaynaklarını yapılandırın
 Daha sonra, şunun bir örneğini oluşturacağız:`FontSettings` ve mevcut yazı tipi kaynaklarını kullanarak`GetFontsSources()` yöntem. Fontları içeren bir klasör belirleyerek yeni bir font kaynağı da ekleyeceğiz.

```csharp
// Yazı tipi kaynaklarını yapılandırma
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Yeni bir yazı tipi kaynağı ekleme
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 3. Adım: Kullanılabilir yazı tiplerinin listesini alın
 Şimdi mevcut yazı tiplerine göz atacağız.`GetAvailableFonts()` İlk güncellenen yazı tipi kaynağındaki yöntem.

```csharp
// Kullanılabilir yazı tiplerinin listesini edinin
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Aspose.Words for .NET kullanarak Mevcut Yazı Tiplerinin Listesini Al için örnek kaynak kodu 

```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aspose.Words'e yazı tiplerini aşağıdaki klasörde araması talimatını verecek yeni bir klasör kaynağı ekleyin.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Yazı tiplerimizi içeren özel klasörü mevcut yazı tipi kaynakları listesine ekleyin.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Çözüm
Bu eğitimde Aspose.Words for .NET'te mevcut yazı tiplerinin listesinin nasıl alınacağını gördük. Bu, belgelerinizde hangi yazı tiplerini kullanabileceğinizi bilmenizi sağlar. İhtiyaçlarınıza uygun yazı tiplerini seçmek için bu özelliği kullanmaktan çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te bulunan yazı tiplerinin listesini nasıl alabilirim?

 C: Aspose.Words'te bulunan yazı tiplerinin listesine ulaşmak için`FontsProvider` sınıf ve`GetAvailableFonts` yöntem. Bu yöntem, sisteminizde yüklü olan tüm yazı tiplerinin bir listesini döndürecektir.

#### S: Aspose.Words'te mevcut yazı tiplerinin listesini belirli kriterlere göre filtreleyebilir miyim?

C: Evet, Aspose.Words'te bulunan yazı tiplerinin listesini belirli kriterleri kullanarak filtreleyebilirsiniz. Örneğin yazı tiplerini aileye, stile veya dile göre filtreleyebilirsiniz.

#### S: Word belgelerimde mevcut yazı tipleri listesini nasıl kullanabilirim?

 C: Word belgelerinizde bulunan yazı tipleri listesini kullanmak için listeye göz atabilir ve Word'ün yöntemlerini ve özelliklerini kullanarak uygun yazı tiplerini seçebilirsiniz.`FontSettings` Aspose.Words'deki sınıf.