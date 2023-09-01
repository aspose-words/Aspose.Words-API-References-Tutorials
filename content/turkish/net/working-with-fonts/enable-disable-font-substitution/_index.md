---
title: Yazı Tipi Değiştirmeyi Devre Dışı Bırakmayı Etkinleştir
linktitle: Yazı Tipi Değiştirmeyi Devre Dışı Bırakmayı Etkinleştir
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde Aspose.Words for .NET ile bir Word belgesinde yazı tipi değiştirmeyi nasıl etkinleştireceğinizi veya devre dışı bırakacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/enable-disable-font-substitution/
---
Bu eğitimde, bir Word belgesini .NET için Aspose.Words kütüphanesini kullanarak oluştururken yazı tipi değiştirmeyi nasıl etkinleştireceğiniz veya devre dışı bırakacağınız konusunda size yol göstereceğiz. Yazı tipi değiştirmeyi etkinleştirmek veya devre dışı bırakmak, eksik yazı tiplerinin otomatik olarak varsayılan yazı tipiyle değiştirilip değiştirilmeyeceğini denetlemenize olanak tanır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

## Önkoşullar
Başlamadan önce aşağıdaki öğelere sahip olduğunuzdan emin olun:
- C# programlama dili hakkında çalışma bilgisi
- .NET için Aspose.Words kütüphanesi projenizde yüklü
- Yazı tipi değişikliğiyle veya yazı tipi değişikliği olmadan oluşturmak istediğiniz bir Word belgesi

## 1. Adım: Belge dizinini tanımlayın
 Öncelikle, Word belgenizin konumuna giden dizin yolunu ayarlamanız gerekir. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` uygun yol ile kodda.

```csharp
// Belgeler dizininizin yolu
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Belgeyi yükleyin ve yazı tipi ayarlarını yapılandırın
 Daha sonra, oluşturmak istediğiniz Word belgesini yükleyeceğiz ve örneğini oluşturacağız.`FontSettings` Yazı tipi ayarlarını yönetmek için sınıf. Yazı tipi adını belirterek varsayılan yazı tipi geçersiz kılmayı ayarlayacağız.`DefaultFontName` ve yazı tipi bilgilerini geçersiz kılmayı şununla devre dışı bırakın:`Enabled` ayarlanır`false`.

```csharp
// Belgeyi yükleyin
Document doc = new Document(dataDir + "Rendering.docx");

// Yazı tipi ayarlarını yapılandırma
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Yazı tipi ayarlarını belgeye uygulama
doc.FontSettings = fontSettings;
```

## 3. Adım: İşlenen belgeyi kaydedin
Son olarak, tanımlanmış yazı tipi geçersiz kılma ayarlarına uyacak şekilde oluşturulan belgeyi kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Aspose.Words for .NET kullanarak Yazı Tipi Değiştirmeyi Etkinleştirme ve Devre Dışı Bırakma için örnek kaynak kodu 

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
Bu eğitimde, bir Word belgesini Aspose.Words for .NET ile oluştururken yazı tipi değiştirmeyi nasıl etkinleştirip devre dışı bırakacağımızı gördük. Yazı tipi değişimini kontrol ederek, oluşturulan belgelerinizde eksik yazı tiplerinin nasıl ele alınacağını etkileyebilirsiniz. Word belgelerinizdeki yazı tiplerinin yönetimini özelleştirmek için bu özelliği kullanmaktan çekinmeyin.

### SSS'ler

#### S: Aspose.Words ile bir Word belgesinde yazı tipi değiştirmeyi nasıl etkinleştirebilirim?

C: Aspose.Words ile bir Word belgesinde yazı tipi değişimini etkinleştirmek için gerekli yazı tipleri mevcut olmadığında kullanılacak ikame yazı tiplerini belirlemek için API'yi kullanabilirsiniz. Bu, orijinal yazı tipleri olmasa bile tutarlı metin görselleştirmesi sağlayacaktır.

#### S: Aspose.Words ile bir Word belgesinde yazı tipi değiştirmeyi devre dışı bırakmak mümkün müdür?

C: Evet, Aspose.Words ile Word belgesinde yazı tipi değiştirmeyi devre dışı bırakabilirsiniz. API'yi kullanarak, Word'ün gerekli yazı tiplerini diğer yazı tipleriyle değiştirmesini önleyebilirsiniz; bu, metnin orijinal görünümünü korur.

#### S: Bir Word belgesinde değişiklik sırasında gerekli yazı tipleri eksik olduğunda ne olur?

C: Bir Word belgesinde değişiklik sırasında gerekli yazı tipleri eksik olduğunda Aspose.Words bu sorunu tespit edebilir ve size düzeltmeniz için seçenekler sunabilir. Eksik yazı tiplerini alternatif yazı tipleriyle değiştirmeyi veya eksik yazı tiplerini belgeye dahil ederek doğru görüntülemeyi seçebilirsiniz.

#### S: Bir Word belgesindeki yazı tiplerini Aspose.Words ile değiştirirken eksik yazı tiplerini nasıl halledebilirim?

C: Bir Word belgesinde Aspose.Words ile değiştirirken eksik yazı tiplerini ele almak için, eksik yazı tiplerini tespit etmek ve çözünürlük seçenekleri sunmak amacıyla API'yi kullanabilirsiniz. İhtiyaçlarınıza bağlı olarak, eksik yazı tiplerini alternatif yazı tipleriyle değiştirmeyi veya eksik yazı tiplerini belgeye dahil etmeyi seçebilirsiniz.

#### S: Bir Word belgesinde yazı tipi değişimini denetlemek önemli midir?

C: Evet, metnin görsel bütünlüğünü korumak için bir Word belgesinde yazı tipi değişimini kontrol etmek önemlidir. Yazı tipi değiştirmeyi etkinleştirmek veya devre dışı bırakmak için Aspose.Words'ü kullanarak gerekli yazı tiplerinin kullanılmasını sağlayabilir ve eksik veya değiştirilmiş yazı tiplerinden kaynaklanan sorunları önleyebilirsiniz.