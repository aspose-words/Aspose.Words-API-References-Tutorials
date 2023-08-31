---
title: Yazı Tipi Klasörlerini Öncelikli Olarak Ayarla
linktitle: Yazı Tipi Klasörlerini Öncelikli Olarak Ayarla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini öncelikli olarak ayarlamaya yönelik adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-with-priority/
---

Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini öncelikli olarak ayarlamanız için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sunacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak belgelerinizi işlerken özel arama önceliğine sahip birden fazla yazı tipi klasörünü nasıl belirleyeceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle belgeler dizininizin yolunu ayarlamanız gerekir. Bu, düzenlenmiş işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELERİNİZ DİZİNİ"ni uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yazı tipi klasörlerini öncelikli olarak ayarlayın
 Daha sonra yazı tipi klasörlerini öncelikli olarak ayarlayabilirsiniz.`FontSettings` sınıf ve`SetFontsSources()`yöntem. Örneklerini kullanarak birden fazla yazı tipi kaynağı belirtebilirsiniz.`SystemFontSource` Ve`FolderFontSource`. Bu örnekte iki yazı tipi kaynağı tanımladık: varsayılan sistem yazı tipi kaynağı ve önceliği 1 olan özel yazı tipi klasörü.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## 3. Adım: Oluşturulacak belgeyi yükleyin
 Artık oluşturulacak belgeyi kullanarak yükleyebilirsiniz.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 4. Adım: İşlenen belgeyi kaydedin
 Son olarak, oluşturulan belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Aspose.Words for .NET kullanarak Yazı Tipleri Klasörlerini Öncelikli Ayarlama için örnek kaynak kodu 
```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Çözüm
Bu eğitimde, Aspose.Words for .NET kullanarak bir belgeyi işlerken yazı tipi klasörlerini öncelikli olarak nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi oluştururken özel arama önceliğine sahip birden fazla yazı tipi klasörünü kolayca belirtebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tipi kaynaklarını kontrol edebilir ve özelleştirebilirsiniz.

### SSS'ler

#### S: Aspose.Words'te yazı tipi klasörlerini öncelikli olarak nasıl ayarlayabilirim?

 C: Aspose.Words'te yazı tipi klasörlerini öncelikli olarak ayarlamak için`SetFontsFoldersWithPriority` yöntemi`Fonts` yazı tipi klasörü konumlarını ve öncelik sırasını belirterek sınıf.

#### S: Bir yazı tipi farklı önceliğe sahip birden fazla klasörde mevcutsa ne olur?

C: Bir yazı tipi farklı önceliğe sahip birden fazla klasörde mevcutsa Aspose.Words, belgeleri işlerken klasördeki en yüksek öncelikli sürümü kullanacaktır.

#### S: Aspose.Words'te aynı önceliğe sahip birden fazla yazı tipi klasörü belirtebilir miyim?

C: Evet, Aspose.Words'te aynı önceliğe sahip birden fazla yazı tipi klasörü belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tiplerini ararken hepsini eşit öncelikli olarak değerlendirecektir.

#### S: Aspose.Words'te öncelikli olarak tanımlanan yazı tipi klasörlerini nasıl kontrol edebilirim?

 C: Aspose.Words'te öncelikli olarak tanımlanan yazı tipi klasörlerini kontrol etmek için`GetFolders` yöntemi`Fonts` Öncelik sıraları da dahil olmak üzere yapılandırılmış yazı tipi klasörlerinin listesini almak için class.

#### S: Aspose.Words'te yazı tipi klasörlerini öncelikli olarak ayarlamanın faydası nedir?

C: Aspose.Words'te yazı tipi klasörlerini öncelikli olarak ayarlamak, Word belgelerinizdeki yazı tiplerinin arama sırasını kontrol etmenize olanak tanır. Bu, istediğiniz yazı tiplerinin kullanıldığından emin olmanıza ve istenmeyen yazı tipi değiştirme sorunlarından kaçınmanıza yardımcı olur.