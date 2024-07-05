---
title: Yazı Tipleri Klasörlerinin Varsayılan Örneğini Ayarla
linktitle: Yazı Tipleri Klasörlerinin Varsayılan Örneğini Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi oluştururken varsayılan yazı tipi klasörünü ayarlamaya yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-default-instance/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi oluştururken varsayılan yazı tipi klasörünü ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak belgelerinizi işlerken kullanılacak varsayılan yazı tipi klasörünü nasıl ayarlayacağınızı öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Varsayılan yazı tipi klasörünü ayarlayın
 Daha sonra varsayılan yazı tipi klasörünü kullanarak ayarlayabilirsiniz.`FontSettings.DefaultInstance` sınıf ve`SetFontsFolder()`yöntem. Varsayılan klasör olarak kullanmak istediğiniz yazı tipleri klasörünün yolunu belirtin.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## 3. Adım: Oluşturulacak belgeyi yükleyin
 Artık oluşturulacak belgeyi kullanarak yükleyebilirsiniz.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4. Adım: İşlenen belgeyi kaydedin
 Son olarak, oluşturulan belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Aspose.Words for .NET kullanarak Yazı Tipi Klasörlerinin Varsayılan Örneğini Ayarlama için örnek kaynak kodu 

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Çözüm
Bu eğitimde Aspose.Words for .NET kullanarak bir belgeyi oluştururken varsayılan yazı tipi klasörünü nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi oluştururken varsayılan klasör olarak hangi yazı tipi klasörünün kullanılacağını kolayca belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.

### SSS'ler

#### S: Aspose.Words'te varsayılan yazı tipi klasörlerini nasıl ayarlayabilirim?

 C: Aspose.Words'te varsayılan yazı tipi klasörlerini ayarlamak için`Fonts` sınıf ve`SetFontsFolders` özel yazı tipi klasörü konumlarını belirtme yöntemi.

#### S: Varsayılan yazı tipi klasörlerini ayarlamak Aspose.Words ile işlenen tüm Word belgelerini etkiler mi?

C: Evet, varsayılan yazı tipi klasörlerinin ayarlanması Aspose.Words ile işlenen tüm Word belgelerini etkiler. Varsayılan yazı tipi klasörlerini ayarladıktan sonra Aspose.Words, tüm belgelerdeki yazı tiplerini aramak için bu konumları kullanacaktır.

#### S: Aspose.Words'te birden fazla varsayılan yazı tipi klasörü ayarlayabilir miyim?

 C: Evet, Aspose.Words'te birden fazla varsayılan yazı tipi klasörü ayarlayabilirsiniz. Özel yazı tipi klasörlerinin konumlarını kullanarak belirtmeniz yeterlidir.`SetFontsFolders` yöntemi`Fonts` sınıf.

#### S: Aspose.Words'te halihazırda ayarlanmış olan varsayılan yazı tipi klasörlerini nasıl kontrol edebilirim?

 C: Aspose.Words'te halihazırda tanımlanmış olan varsayılan yazı tipi klasörlerini kontrol etmek için`GetFolders` yöntemi`Fonts` Yapılandırılmış yazı tipi klasörlerinin konumlarını almak için sınıf.

#### S: Varsayılan yazı tipi klasörlerini ayarlamak, Word belgelerimde özel yazı tipleri kullanmama olanak tanır mı?

C: Evet, varsayılan yazı tipi klasörlerini ayarlayarak Word belgelerinizde özel yazı tipleri kullanabilirsiniz. Yazı tiplerini belirtilen klasörlere yerleştirmeniz yeterli; Aspose.Words, belgeleri oluştururken veya düzenlerken bunları kullanacaktır.