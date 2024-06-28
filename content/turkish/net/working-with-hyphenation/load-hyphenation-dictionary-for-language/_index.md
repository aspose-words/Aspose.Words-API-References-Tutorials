---
title: Dil İçin Tireleme Sözlüğünü Yükle
linktitle: Dil İçin Tireleme Sözlüğünü Yükle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'te belirli bir dil için tireleme sözlüğünü nasıl yükleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

Bu adım adım eğitimde, belirli bir dil için tireleme sözlüğünü Aspose.Words for .NET'e nasıl yükleyeceğinizi göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin:[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. Adım: Belgeyi yükleme

Öncelikle belgenizi belirtilen dizinden yükleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2. Adım: Tireleme sözlüğünü yükleme

Daha sonra, tireleme sözlüğü dosyasına bir akış açın ve bunu istediğiniz dil için kaydedin. Bu örnekte İsviçre Almancası (de-CH) için bir sözlük yüklüyoruz:

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Veri dizininizde uygun sözlük dosyasının bulunduğundan emin olun.

## 3. Adım: Değiştirilen belgeyi kaydedin

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Bu yüzden ! Aspose.Words for .NET'te belirli bir dil için tireleme sözlüğünü başarıyla yüklediniz.

### Aspose.Words for .NET kullanan bir dil için tireleme sözlüğü yüklemeye yönelik örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te belirli bir dil için heceleme sözlüğü nasıl yüklenir?

 C: Aspose.Words'e belirli bir dil için heceleme sözlüğü yüklemek için`Hyphenation` sınıf ve`LoadDictionary()` yöntem. Bir örneğini oluşturun`Hyphenation` sınıfa girin ve arayın`LoadDictionary()` İstenilen dil için heceleme sözlüğü dosyasının yolunu belirten yöntem. Bu, heceleme sözlüğünü Aspose.Words'e yükleyecektir.

#### S: Farklı diller için heceleme sözlüğü dosyalarını nerede bulabilirim?

C: Farklı diller için heceleme sözlüğü dosyalarını çeşitli çevrimiçi kaynaklarda bulabilirsiniz. Bu dosyalar genellikle XML veya TEX formatındadır. Farklı diller için açık kaynaklı heceleme sözlüklerini, dilbilim projelerine ayrılmış web sitelerinde veya kaynak kod depolarında bulabilirsiniz.

#### S: Yüklenen hece sözlüğünü Aspose.Words'teki bir belgeye nasıl uygulayabilirim?

C: Yüklenen heceleme sözlüğünü Aspose.Words'teki bir belgeye uygulamak için belgedeki kelimelerin üzerinde yineleme yapmanız ve`Hyphenate()` yöntemi`Hyphenation` Kelimelerin hecelemesini almak için sınıf. Daha sonra hecelenmiş sözcükleri gerektiği gibi biçimlendirebilirsiniz; örneğin hecelerin arasına kısa çizgi ekleyerek.

#### S: Aspose.Words'te heceleme için hangi diller destekleniyor?

C: Aspose.Words, İngilizce, Fransızca, İspanyolca, Almanca, İtalyanca, Felemenkçe, Rusça, Portekizce, İsveççe, Norveççe, Danca, Fince, Lehçe, Çekçe ve çok daha fazlası dahil olmak üzere birçok dilde hecelemeyi destekler. Heceleme için desteklenen dillerin tam listesi için Aspose.Words belgelerine bakın.