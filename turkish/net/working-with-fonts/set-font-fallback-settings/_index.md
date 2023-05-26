---
title: Yazı Tipi Yedek Ayarlarını Ayarlayın
linktitle: Yazı Tipi Yedek Ayarlarını Ayarlayın
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te yazı tipi değiştirme ayarlarını nasıl yapacağınızı ve Word belgelerinizde yazı tipi değiştirmeyi nasıl özelleştireceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-font-fallback-settings/
---
Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi değiştirme ayarlarını nasıl yapacağınızı göstereceğiz. Yazı tipi değiştirme ayarları, belirtilen yazı tipleri mevcut olmadığında kullanılacak değiştirme yazı tiplerini belirtmenize olanak tanır.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı

## 1. Adım: Belge dizinini tanımlayın
Dizin yolunu Word belgenizin konumuna ayarlayarak başlayın. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yazı tipi değiştirme ayarlarını yükleyin
 örneğini oluşturun`FontSettings` sınıflandırın ve kullanın`Load`yazı tipi geçersiz kılma ayarlarını bir XML dosyasından yükleme yöntemi. Belirtilen XML dosyası, kullanılacak yazı tipi değiştirme kurallarını içermelidir.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## 3. Adım: Yazı tipi değiştirme ayarlarını uygulayın
 Yazı tipi değiştirme ayarlarını belgeye atayarak belgeyle ilişkilendirin.`FontSettings` mülk.

```csharp
doc.FontSettings = fontSettings;
```

## 4. Adım: Belgeyi kaydedin
 kullanarak belgeyi kaydedin.`Save` yöntemi`Document` uygun yol ve dosya adıyla.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Aspose.Words for .NET kullanarak Font Fallback Ayarlarını Ayarlamak için örnek kaynak kodu 
```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir Word belgesinde yazı tipi değiştirme ayarlarını nasıl yapacağınızı öğrendiniz. Belirtilen yazı tipleri mevcut olmadığında bile belgenizin tutarlı görünmesini sağlamak için farklı yazı tipi değiştirme kurallarını deneyin.
