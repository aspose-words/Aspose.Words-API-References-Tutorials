---
title: Yazı Tipleri Klasörünü Ayarla
linktitle: Yazı Tipleri Klasörünü Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te yazı tipi dizinini nasıl ayarlayacağınızı ve belgelerinizde kullanılan yazı tiplerinin kullanılabilirliğini nasıl sağlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folder/
---
Bu öğreticide, size Aspose.Words for .NET'te yazı tipi dizinini nasıl ayarlayacağınızı göstereceğiz. Word belgenizde kullanılan yazı tiplerini içeren dizini nasıl belirleyeceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
 Dizin yolunu Word belgenizin konumuna ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yazı tipi dizinini ayarlayın
 örneğini oluşturun`FontSettings` sınıflandırın ve kullanın`SetFontsFolder` yazı tiplerini içeren dizini belirtme yöntemi. Yer değiştirmek`"Fonts"` gerçek yazı dizini adı ile.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## 3. Adım: Belgeyi yazı tipi ayarlarıyla yükleyin
 Kullan`LoadOptions` yazı tipi ayarlarını belirtmek için sınıf`FontSettings` seçenek. Daha sonra`Document` Bu seçenekleri kullanarak belgeyi yüklemek için sınıf.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Aspose.Words for .NET kullanan Set Fonts Folder için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Çözüm
Tebrikler! Artık Aspose.Words for .NET'te yazı tipi dizinini nasıl ayarlayacağınızı biliyorsunuz. Belgenizde kullanılan yazı tiplerinin kullanılabilirliğini sağlamak ve yazı tiplerinin görüntülenmesinde tutarlılık sağlamak için bu özelliği kullanabilirsiniz.

### SSS

#### S: Aspose.Words'te özel bir yazı tipi klasörünü nasıl ayarlayabilirim?

 C: Aspose.Words'te özel bir yazı tipi klasörü ayarlamak için`FontsFolder` sınıf ve`SetFontsFolders` yazı tiplerinizi içeren klasörün yolunu belirten yöntem.

#### S: Aspose.Words'te birden çok yazı tipi klasörü ayarlayabilir miyim?

 C: Evet, Aspose.Words'te birden fazla yazı tipi klasörü ayarlayabilirsiniz.`SetFontsFolders` yöntemi, kullanmak istediğiniz farklı yazı tipi klasörlerinin yolları ile birden çok kez.

#### S: Belgede kullanılan bir yazı tipi tanımlı yazı tipi klasörlerinde yoksa ne olur?

C: Belgede kullanılan bir yazı tipi Aspose.Words'ta tanımlanan yazı tipi klasörlerinde yoksa, bunun yerine yedek bir yazı tipi kullanılacaktır. Bu, orijinal yazı tipi mevcut olmasa bile belgedeki metnin her zaman doğru görüntülenmesini sağlar.

#### S: Aspose.Words'te tanımlanan yazı tipi klasörlerinin sistemde yüklü olan yazı tiplerine göre önceliği var mı?

C: Evet, Aspose.Words'ta tanımlanan yazı tipi klasörleri, sistemde yüklü olan yazı tiplerine göre önceliklidir. Bu, hem tanımlı yazı tipi klasörlerinde hem de sistem yazı tiplerinde aynı ada sahip bir yazı tipi varsa, Word belgeleri işlenirken yazı tipi klasöründeki sürümün kullanılacağı anlamına gelir.