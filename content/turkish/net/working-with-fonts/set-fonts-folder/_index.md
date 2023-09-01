---
title: Yazı Tipleri Klasörünü Ayarla
linktitle: Yazı Tipleri Klasörünü Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te yazı tipi dizinini nasıl ayarlayacağınızı ve belgelerinizde kullanılan yazı tiplerinin kullanılabilirliğinden nasıl emin olacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folder/
---
Bu eğitimde size Aspose.Words for .NET'te yazı tipi dizinini nasıl ayarlayacağınızı göstereceğiz. Word belgenizde kullanılan yazı tiplerini içeren dizini nasıl belirleyeceğinizi öğreneceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü

## 1. Adım: Belge dizinini tanımlayın
 Dizin yolunu Word belgenizin konumuna ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yazı tipi dizinini ayarlayın
 Bir örneğini oluşturun`FontSettings` sınıf ve kullanın`SetFontsFolder` Yazı tiplerini içeren dizini belirtme yöntemi. Yer değiştirmek`"Fonts"` gerçek yazı tipi dizininin adı ile.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## 3. Adım: Belgeyi yazı tipi ayarlarıyla yükleyin
 Kullan`LoadOptions` yazı tipi ayarlarını belirtmek için sınıf`FontSettings` seçenek. Daha sonra şunu kullanın:`Document` Bu seçenekleri kullanarak belgeyi yüklemek için sınıf.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Aspose.Words for .NET kullanarak Yazı Tiplerini Ayarla Klasörü için örnek kaynak kodu 

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
Tebrikler! Artık Aspose.Words for .NET'te font dizinini nasıl ayarlayacağınızı biliyorsunuz. Belgenizde kullanılan yazı tiplerinin kullanılabilirliğini sağlamak ve yazı tiplerinin görüntülenmesinde tutarlılığı sağlamak için bu özelliği kullanabilirsiniz.

### SSS'ler

#### S: Aspose.Words'te özel bir yazı tipi klasörünü nasıl ayarlayabilirim?

 C: Aspose.Words'te özel bir yazı tipi klasörü oluşturmak için`FontsFolder` sınıf ve`SetFontsFolders` yazı tiplerinizi içeren klasörün yolunu belirten yöntem.

#### S: Aspose.Words'te birden fazla yazı tipi klasörü ayarlayabilir miyim?

 C: Evet, Aspose.Words'te birden fazla yazı tipi klasörü ayarlayabilirsiniz.`SetFontsFolders` Kullanmak istediğiniz farklı yazı tipi klasörlerinin yollarını kullanarak yöntemi birden çok kez kullanın.

#### S: Belgede kullanılan bir yazı tipi, tanımlanan yazı tipi klasörlerinde mevcut değilse ne olur?

C: Belgede kullanılan bir yazı tipi Aspose.Words'te tanımlanan yazı tipi klasörlerinde bulunmuyorsa onun yerine başka bir yazı tipi kullanılacaktır. Bu, orijinal yazı tipi mevcut olmasa bile belgedeki metnin her zaman doğru şekilde görüntülenmesini sağlar.

#### S: Aspose.Words'te tanımlanan font klasörlerinin sistemde yüklü olan fontlara göre önceliği var mı?

C: Evet, Aspose.Words'te tanımlanan font klasörleri, sistemde yüklü olan fontlara göre önceliklidir. Bu, hem tanımlı yazı tipi klasörlerinde hem de sistem yazı tiplerinde aynı ada sahip bir yazı tipinin mevcut olması durumunda, Word belgeleri işlenirken yazı tipi klasöründeki sürümün kullanılacağı anlamına gelir.