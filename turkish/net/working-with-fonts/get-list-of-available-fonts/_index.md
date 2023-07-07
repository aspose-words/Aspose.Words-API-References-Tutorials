---
title: Kullanılabilir Yazı Tiplerinin Listesini Alın
linktitle: Kullanılabilir Yazı Tiplerinin Listesini Alın
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET'te bulunan yazı tiplerinin listesini nasıl alacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-list-of-available-fonts/
---
Bu öğreticide, Aspose.Words for .NET'te bulunan yazı tiplerinin listesini nasıl alacağınızı açıklayacağız. Kullanılabilir yazı tiplerinin listesi, belgelerinizde hangi yazı tiplerini kullanabileceğinizi bilmenizi sağlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

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

## 2. Adım: Yazı tipi kaynaklarını yapılandırın
 Ardından, bir örneğini oluşturacağız`FontSettings` ve kullanarak mevcut yazı tipi kaynaklarını edinin.`GetFontsSources()` yöntem. Fontları içeren bir klasör belirterek yeni bir font kaynağı da ekleyeceğiz.

```csharp
// Yazı tipi kaynaklarını yapılandırma
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Yeni bir yazı tipi kaynağı ekleyin
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## 3. Adım: Kullanılabilir yazı tiplerinin listesini alın
 Şimdi kullanarak mevcut yazı tiplerine göz atacağız.`GetAvailableFonts()` yöntemi ilk güncellenen yazı tipi kaynağında.

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


### Aspose.Words for .NET kullanarak Kullanılabilir Yazı Tiplerinin Listesini Al için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Aspose.Words'e yazı tiplerini aşağıdaki klasörde arama talimatı verecek yeni bir klasör kaynağı ekleyin.
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
Bu öğreticide, Aspose.Words for .NET'te bulunan yazı tiplerinin listesini nasıl alacağımızı gördük. Bu, belgelerinizde hangi yazı tiplerini kullanabileceğinizi bilmenizi sağlar. İhtiyaçlarınıza uygun yazı tiplerini seçmek için bu özelliği kullanmaktan çekinmeyin.

### SSS

#### S: Aspose.Words'ta bulunan yazı tiplerinin listesini nasıl alabilirim?

 C: Aspose.Words'te bulunan yazı tiplerinin listesini almak için`FontsProvider` sınıf ve`GetAvailableFonts` yöntem. Bu yöntem, sisteminizde yüklü olan tüm yazı tiplerinin bir listesini döndürür.

#### S: Aspose.Words'te mevcut yazı tiplerinin listesini belirli kriterlere göre filtreleyebilir miyim?

C: Evet, Aspose.Words'ta bulunan yazı tiplerinin listesini belirli kriterler kullanarak filtreleyebilirsiniz. Örneğin, yazı tiplerini aileye, stile veya dile göre filtreleyebilirsiniz.

#### S: Word belgelerimde bulunan yazı tiplerinin listesini nasıl kullanabilirim?

 A: Word belgelerinizde bulunan yazı tiplerinin listesini kullanmak için, listeye göz atabilir ve programın yöntemlerini ve özelliklerini kullanarak uygun yazı tiplerini seçebilirsiniz.`FontSettings` Aspose.Words'te sınıf.