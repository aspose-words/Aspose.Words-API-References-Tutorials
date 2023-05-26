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