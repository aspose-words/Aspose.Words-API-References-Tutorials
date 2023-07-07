---
title: Yazı Tipi Değiştirmeyi Devre Dışı Bırakmayı Etkinleştir
linktitle: Yazı Tipi Değiştirmeyi Devre Dışı Bırakmayı Etkinleştir
second_title: Aspose.Words for .NET API Referansı
description: Bu öğreticide, Aspose.Words for .NET ile bir Word belgesinde yazı tipi değiştirmeyi nasıl etkinleştireceğinizi veya devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/enable-disable-font-substitution/
---
Bu öğreticide, bir Word belgesini Aspose.Words .NET kitaplığı kullanarak işlerken yazı tipi değiştirmeyi nasıl etkinleştireceğiniz veya devre dışı bırakacağınız konusunda size yol göstereceğiz. Yazı tipi değiştirmeyi etkinleştirmek veya devre dışı bırakmak, eksik yazı tiplerinin otomatik olarak varsayılan bir yazı tipiyle değiştirilip değiştirilmeyeceğini kontrol etmenizi sağlar. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce, aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- Projenizde yüklü olan .NET için Aspose.Words kitaplığı
- Yazı tipi değiştirmeli veya değiştirmesiz işlemek istediğiniz bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, dizin yolunu Word belgenizin konumuna ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin ve yazı tipi ayarlarını yapılandırın
 Ardından, işlemek istediğiniz Word belgesini yükleyeceğiz ve örneğini oluşturacağız.`FontSettings` yazı tipi ayarlarını işlemek için sınıf. Yazı tipi adını belirterek varsayılan yazı tipi geçersiz kılmayı ayarlayacağız.`DefaultFontName` ve ile yazı tipi bilgilerini geçersiz kılmayı devre dışı bırakın`Enabled` ayarlanır`false`.

```csharp
//belgeyi yükle
Document doc = new Document(dataDir + "Rendering.docx");

// Yazı tipi ayarlarını yapılandırın
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Yazı tipi ayarlarını belgeye uygulama
doc.FontSettings = fontSettings;
```

## 3. Adım: Oluşturulan belgeyi kaydedin
Son olarak, tanımlanmış yazı tipi geçersiz kılma ayarlarına uyacak şekilde işlenmiş belgeyi kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Aspose.Words for .NET kullanarak Enable Disable Font Substitution için örnek kaynak kodu 

```csharp

// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Çözüm
Bu öğreticide, bir Word belgesini Aspose.Words for .NET ile işlerken yazı tipi değiştirmeyi nasıl etkinleştireceğimizi veya devre dışı bırakacağımızı gördük. Yazı tipi değiştirmeyi kontrol ederek, işlenmiş belgelerinizde eksik yazı tiplerinin nasıl işleneceğini etkileyebilirsiniz. Word belgelerinizdeki yazı tiplerinin yönetimini özelleştirmek için bu özelliği kullanmaktan çekinmeyin.

### SSS

#### S: Aspose.Words ile bir Word belgesinde yazı tipi değiştirmeyi nasıl etkinleştirebilirim?

C: Aspose.Words ile bir Word belgesinde yazı tipi değiştirmeyi etkinleştirmek için, gerekli yazı tipleri mevcut olmadığında kullanılacak değiştirme yazı tiplerini belirtmek için API'yi kullanabilirsiniz. Bu, orijinal yazı tipleri olmadan bile tutarlı metin görselleştirmesi sağlayacaktır.

#### S: Aspose.Words ile bir Word belgesinde yazı tipi değiştirmeyi devre dışı bırakmak mümkün mü?

C: Evet, Aspose.Words ile bir Word belgesinde yazı tipi değiştirmeyi devre dışı bırakabilirsiniz. API'yi kullanarak, Word'ün gerekli yazı tiplerini metnin orijinal görünümünü koruyan diğer yazı tipleriyle değiştirmesini engelleyebilirsiniz.

#### S: Bir Word belgesinde değiştirme sırasında gerekli yazı tipleri eksik olursa ne olur?

Y: Bir Word belgesinde değiştirme sırasında gerekli yazı tipleri eksik olduğunda, Aspose.Words bu sorunu algılayabilir ve düzeltmeniz için size seçenekler sağlayabilir. Eksik yazı tiplerini alternatif yazı tipleriyle değiştirmeyi seçebilir veya eksik yazı tiplerini belgeye dahil ederek doğru görüntülemeyi sağlayabilirsiniz.

#### S: Bir Word belgesinde Aspose.Words ile değiştirirken eksik yazı tiplerini nasıl halledebilirim?

C: Bir Word belgesinde Aspose.Words ile değiştirirken eksik yazı tiplerini işlemek için, API'yi kullanarak eksik yazı tiplerini tespit edebilir ve çözünürlük seçenekleri sunabilirsiniz. İhtiyaçlarınıza bağlı olarak, eksik yazı tiplerini alternatif yazı tipleriyle değiştirmeyi veya eksik yazı tiplerini belgeye dahil etmeyi seçebilirsiniz.

#### S: Bir Word belgesinde yazı tipi değiştirmeyi kontrol etmek önemli midir?

C: Evet, metnin görsel bütünlüğünü korumak için bir Word belgesinde yazı tipi değişimini kontrol etmek önemlidir. Yazı tipi değiştirmeyi etkinleştirmek veya devre dışı bırakmak için Aspose.Words'ü kullanarak, gerekli yazı tiplerinin kullanıldığından emin olabilir ve eksik veya değiştirilmiş yazı tipleriyle ilgili sorunlardan kaçınabilirsiniz.