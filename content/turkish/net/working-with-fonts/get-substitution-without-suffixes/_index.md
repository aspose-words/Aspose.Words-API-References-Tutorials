---
title: Son Ekler Olmadan Değiştirme Alma
linktitle: Son Ekler Olmadan Değiştirme Alma
second_title: Aspose.Words Belge İşleme API'si
description: Bu eğitimde Aspose.Words for .NET ile bir Word belgesinde soneksiz geçersiz kılmaların nasıl alınacağını öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-fonts/get-substitution-without-suffixes/
---

Bu derste, .NET için Aspose.Words kütüphanesini kullanarak bir Word belgesinde sonekler olmadan geçersiz kılmaların nasıl alınacağını size göstereceğiz. Son ekleri olmayan değişiklikler, belgeleri görüntülerken veya yazdırırken yazı tipi değiştirme sorunlarını çözmek için kullanılır. .NET projenizdeki kodu anlamanıza ve uygulamanıza yardımcı olmak için sizi adım adım yönlendireceğiz.

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

## 2. Adım: Belgeyi yükleyin ve son ekleri olmayan değişiklikleri yapılandırın
 Daha sonra belgeyi kullanarak yükleyeceğiz.`Document` kullanarak soneksiz ikameleri sınıflandırın ve yapılandırın`DocumentSubstitutionWarnings` sınıf. Ayrıca yazı tiplerini içeren bir klasör belirleyerek bir yazı tipi kaynağı da ekleyeceğiz.

```csharp
// Belgeyi yükleyin ve son ekleri olmayan değişiklikleri yapılandırın
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## 3. Adım: Belgeyi kaydedin
Son olarak, son ek içermeyen geçersiz kılmaların uygulandığı belgeyi kaydedeceğiz.

```csharp
// Belgeyi kaydet
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Aspose.Words for .NET kullanarak Son Ekler Olmadan Değiştirme Al için örnek kaynak kodu 
```csharp

//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Çözüm
Bu eğitimde Aspose.Words for .NET ile bir Word belgesinde sonekler olmadan geçersiz kılmaların nasıl alınacağını gördük. Son ekleri olmayan değişiklikler, yazı tipi değiştirme sorunlarını çözmek için kullanışlıdır. Belgelerinizin görüntülenmesini ve yazdırılmasını iyileştirmek için bu özelliği kullanmaktan çekinmeyin.

### SSS'ler

#### S: Aspose.Words neden yazı tipi değişikliklerine son ekler ekliyor?

C: Aspose.Words, orijinal yazı tipleri ile değiştirilen yazı tipleri arasındaki çakışmaları önlemek için yazı tipi değiştirmelere son ekler ekler. Bu, belgeleri dönüştürürken ve değiştirirken maksimum uyumluluğun sağlanmasına yardımcı olur.

#### S: Aspose.Words'te son ekler olmadan yazı tipi değişikliklerini nasıl alabilirim?

 C: Aspose.Words'te son ekler olmadan yazı tipi değişikliklerini almak için şu komutu kullanabilirsiniz:`FontSubstitutionSettings` sınıf ve`RemoveSuffixes` mülk. Bu özelliği şu şekilde ayarlamak`true` eklenen sonekler olmadan yazı tipi değişikliklerini alır.

#### S: Aspose.Words'te yazı tipi değişikliklerine sonek eklemeyi devre dışı bırakmak mümkün mü?

C: Hayır, Aspose.Words'te yazı tipi değişikliklerine sonek eklemeyi devre dışı bırakmak mümkün değildir. Belge uyumluluğunu ve tutarlılığını sağlamak için son ekler varsayılan olarak eklenir.

#### S: Aspose.Words'te yazı tipi değişikliklerinde istenmeyen son ekleri nasıl filtreleyebilirim?

 C: Aspose.Words'te yazı tipi değişikliklerinde istenmeyen son ekleri filtrelemek için dize işleme tekniklerini kullanabilirsiniz.`Replace` veya`Substring` Eklemek istemediğiniz belirli son ekleri kaldırma yöntemleri.