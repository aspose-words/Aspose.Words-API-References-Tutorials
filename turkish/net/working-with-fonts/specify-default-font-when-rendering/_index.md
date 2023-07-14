---
title: İşleme Sırasında Varsayılan Yazı Tipini Belirtin
linktitle: İşleme Sırasında Varsayılan Yazı Tipini Belirtin
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken varsayılan yazı tipini belirlemek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/specify-default-font-when-rendering/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken varsayılan yazı tipini belirlemeniz için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda belgelerinizi Aspose.Words for .NET kullanarak işlerken kullanılacak bir varsayılan yazı tipini nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenen işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Oluşturulacak belgeyi yükleyin
 Ardından, kullanarak işlenecek belgeyi yüklemeniz gerekir.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: Varsayılan yazı tipini ayarlayın
 Artık, örneğini oluşturarak, işleme sırasında kullanılacak varsayılan yazı tipini belirtebilirsiniz.`FontSettings` sınıf ve ayar`DefaultFontName`mülkiyeti`DefaultFontSubstitution` itiraz etmek`DefaultFontSubstitution` nesne`SubstitutionSettings` ile ilgili`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## 4. Adım: Oluşturulan belgeyi kaydedin
 Son olarak, işlenen belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Aspose.Words for .NET kullanarak Oluştururken Varsayılan Yazı Tipini Belirt için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
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
Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi işlerken varsayılan yazı tipini nasıl belirleyeceğimizi öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi işlerken kullanmak üzere varsayılan bir yazı tipini kolayca ayarlayabilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle, belgelerinizin işlenmesini özel ihtiyaçlarınıza göre kontrol edebilir ve özelleştirebilirsiniz.

### SSS

#### S: Aspose.Words'ta PDF'ye dönüştürürken varsayılan bir yazı tipini nasıl belirleyebilirim?

 C: Aspose.Words'te PDF'ye dönüştürürken bir varsayılan yazı tipi belirtmek için`PdfOptions`sınıflandırın ve ayarlayın`DefaultFontName` özelliğini istediğiniz yazı tipinin adına ekleyin.

#### S: PDF'ye dönüştürürken varsayılan yazı tipi yoksa ne olur?

Y: PDF'ye dönüştürürken belirtilen varsayılan yazı tipi mevcut değilse Aspose.Words, dönüştürülen belgedeki metni görüntülemek için yedek bir yazı tipi kullanır. Bu, orijinal yazı tipinden görünüşte küçük bir farka neden olabilir.

#### S: DOCX veya HTML gibi diğer çıktı biçimleri için varsayılan bir yazı tipi belirtebilir miyim?

C: Evet, uygun dönüştürme seçeneklerini kullanarak ve her biçim için karşılık gelen özelliği ayarlayarak DOCX veya HTML gibi diğer çıktı biçimleri için varsayılan bir yazı tipi belirtebilirsiniz.

#### S: Aspose.Words'te belirtilen varsayılan yazı tipini nasıl kontrol edebilirim?

 C: Aspose.Words'te belirtilen varsayılan yazı tipini kontrol etmek için`DefaultFontName`mülkiyeti`PdfOptions` sınıflandırın ve yapılandırılan yazı tipinin adını alın.

#### S: Belgenin her bölümü için farklı bir varsayılan yazı tipi belirlemek mümkün müdür?

C: Evet, her bölüme özel biçimlendirme seçeneklerini kullanarak belgenin her bölümü için farklı bir varsayılan yazı tipi belirlemek mümkündür. Ancak bu, Aspose.Words özelliklerini kullanarak belgenin daha gelişmiş şekilde işlenmesini gerektirecektir.