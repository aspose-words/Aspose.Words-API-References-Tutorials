---
title: Dil İçin Heceleme Sözlüğünü Yükle
linktitle: Dil İçin Heceleme Sözlüğünü Yükle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'te belirli bir dil için heceleme sözlüğünü nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Bu adım adım eğitimde, size belirli bir dil için heceleme sözlüğünü Aspose.Words for .NET'e nasıl yükleyeceğinizi göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## 1. Adım: Belgeyi yükleme

İlk olarak, belgenizi belirtilen dizinden yükleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2. Adım: Tireleme sözlüğünü yükleme

Ardından, heceleme sözlüğü dosyasına bir akış açın ve onu istenen dil için kaydedin. Bu örnekte, İsviçre Almancası (de-CH) için bir sözlük yüklüyoruz:

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Veri dizininizde uygun sözlük dosyasının bulunduğundan emin olun.

## 3. Adım: Değiştirilen belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Bu yüzden ! Aspose.Words for .NET'te belirli bir dil için heceleme sözlüğünü başarıyla yüklediniz.

### Aspose.Words for .NET kullanan bir dil için heceleme sözlüğü yükleme örneği kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.

### SSS

#### S: Aspose.Words'ta belirli bir dil için heceleme sözlüğü nasıl yüklenir?

 C: Aspose.Words'te belirli bir dil için bir heceleme sözlüğü yüklemek için`Hyphenation` sınıf ve`LoadDictionary()` yöntem. örneğini oluşturun`Hyphenation` sınıf ve çağrı`LoadDictionary()` İstenen dil için heceleme sözlüğü dosyasının yolunu belirten yöntem. Bu, heceleme sözlüğünü Aspose.Words'a yükleyecektir.

#### S: Farklı diller için heceleme sözlüğü dosyalarını nerede bulabilirim?

A: Çeşitli çevrimiçi kaynaklarda farklı diller için heceleme sözlük dosyaları bulabilirsiniz. Bu dosyalar genellikle XML veya TEX biçimindedir. Farklı diller için açık kaynaklı heceleme sözlüklerini, dilbilim projelerine ayrılmış web sitelerinde veya kaynak kodu havuzlarında bulabilirsiniz.

#### S: Yüklenen hece sözlüğünü Aspose.Words'teki bir belgeye nasıl uygulayabilirim?

 C: Yüklenen heceleme sözlüğünü Aspose.Words'teki bir belgeye uygulamak için, belgedeki sözcükleri yinelemeniz ve`Hyphenate()` yöntemi`Hyphenation` kelimelerin hecelemesini elde etmek için sınıf. Daha sonra, örneğin heceler arasına kısa çizgiler ekleyerek hecelenmiş sözcükleri gerektiği gibi biçimlendirebilirsiniz.

#### S: Aspose.Words'ta heceleme için hangi diller destekleniyor?

Y: Aspose.Words, İngilizce, Fransızca, İspanyolca, Almanca, İtalyanca, Felemenkçe, Rusça, Portekizce, İsveççe, Norveççe, Danca, Fince, Lehçe, Çekçe ve çok daha fazlası dahil olmak üzere birçok dil için hecelemeyi destekler. Heceleme için desteklenen dillerin tam listesi için Aspose.Words belgelerine bakın.