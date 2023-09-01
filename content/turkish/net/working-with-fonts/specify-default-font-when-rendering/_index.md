---
title: İşleme Sırasında Varsayılan Yazı Tipini Belirtin
linktitle: İşleme Sırasında Varsayılan Yazı Tipini Belirtin
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi oluştururken varsayılan yazı tipini belirlemeye yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/specify-default-font-when-rendering/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi oluştururken varsayılan yazı tipini belirlemek için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak belgelerinizi işlerken kullanılacak varsayılan yazı tipini nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Oluşturulacak belgeyi yükleyin
 Daha sonra, belgeyi kullanarak oluşturulacak belgeyi yüklemeniz gerekir.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Varsayılan yazı tipini ayarlayın
 Artık, oluşturma sırasında kullanılacak varsayılan yazı tipini, örneğini oluşturarak belirleyebilirsiniz.`FontSettings` sınıf ve ayarlama`DefaultFontName` mülkiyeti`DefaultFontSubstitution` itiraz`DefaultFontSubstitution` nesne`SubstitutionSettings` ile ilgili`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 4. Adım: İşlenen belgeyi kaydedin
 Son olarak, oluşturulan belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Aspose.Words for .NET Kullanarak Oluştururken Varsayılan Yazı Tipini Belirleme için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Burada tanımlanan varsayılan yazı tipi oluşturma sırasında bulunamazsa
// bunun yerine makinedeki en yakın yazı tipi kullanılır.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir belgeyi oluştururken varsayılan yazı tipini nasıl belirleyeceğimizi öğrendik. Bu adım adım kılavuzu izleyerek belgelerinizi oluştururken kullanılacak varsayılan yazı tipini kolayca ayarlayabilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle belgelerinizin işlenmesini özel ihtiyaçlarınıza göre kontrol edebilir ve özelleştirebilirsiniz.

### SSS'ler

#### S: Aspose.Words'te PDF'ye dönüştürürken varsayılan yazı tipini nasıl belirleyebilirim?

 C: Aspose.Words'te PDF'ye dönüştürürken varsayılan yazı tipini belirlemek için`PdfOptions` sınıfı seçin ve ayarlayın`DefaultFontName` İstenilen yazı tipinin adının özelliğini kullanın.

#### S: PDF'ye dönüştürürken varsayılan yazı tipi kullanılamıyorsa ne olur?

C: PDF'ye dönüştürürken belirtilen varsayılan yazı tipi mevcut değilse Aspose.Words, dönüştürülen belgedeki metni görüntülemek için yedek bir yazı tipi kullanır. Bu, orijinal yazı tipinden görünümde küçük bir farklılığa neden olabilir.

#### S: DOCX veya HTML gibi diğer çıktı biçimleri için varsayılan bir yazı tipi belirtebilir miyim?

C: Evet, uygun dönüştürme seçeneklerini kullanarak ve her format için ilgili özelliği ayarlayarak DOCX veya HTML gibi diğer çıktı formatları için varsayılan bir yazı tipi belirleyebilirsiniz.

#### S: Aspose.Words'te belirtilen varsayılan yazı tipini nasıl kontrol edebilirim?

 C: Aspose.Words'te belirtilen varsayılan yazı tipini kontrol etmek için`DefaultFontName` mülkiyeti`PdfOptions` sınıfına gidin ve yapılandırılan yazı tipinin adını alın.

#### S: Belgenin her bölümü için farklı bir varsayılan yazı tipi belirlemek mümkün mü?

C: Evet, her bölüme özel biçimlendirme seçeneklerini kullanarak belgenin her bölümü için farklı bir varsayılan yazı tipi belirlemek mümkündür. Ancak bu, Aspose.Words özellikleri kullanılarak belgenin daha gelişmiş şekilde işlenmesini gerektirir.