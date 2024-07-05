---
title: Dillerin Tireli Kelimeleri
linktitle: Dillerin Tireli Kelimeleri
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak Word belgelerinde farklı dillerdeki kelimeleri nasıl tireleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-hyphenation/hyphenate-words-of-languages/
---

Bu adım adım eğitimde, Aspose.Words for .NET kullanarak Word belgelerinde farklı dillerdeki kelimeleri nasıl tireleyeceğiniz konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## Adım 1: Belge Nesnesini Başlatma

 İlk olarak, başlat`Document` farklı dillerde metin içeren kaynak belgenizin yolunu belirterek nesneyi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Adım 2: Tireleme Sözlüklerini Kaydetme

Daha sonra, işlemek istediğiniz farklı dillere ait tireleme sözlüklerini kaydedin. Bu örnekte Amerikan İngilizcesi ve İsviçre Almancası için sözlükleri kaydediyoruz:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Veri dizininizde uygun sözlük dosyalarının bulunduğundan emin olun.

## 3. Adım: Kelimeleri tireleme yoluyla işleme

Artık farklı dillerdeki kelimeleri işlemek için tireleme özelliklerini kullanabilirsiniz. Farklı yöntemler kullanabilirsiniz`Document` veya`DocumentBuilder` özel ihtiyaçlarınıza bağlı olarak.

```csharp
// Örnek: DocumentBuilder'ın Tireleme yöntemini kullanma
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## 4. Adım: Belgeyi kaydedin

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Bu yüzden ! Aspose.Words for .NET'i kullanarak bir Word belgesinde farklı dillerdeki kelimeleri tireleyerek başarılı bir şekilde işlediniz.

### Aspose.Words for .NET kullanarak sözcük tireleme için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel ihtiyaçlarınıza uyacak şekilde değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words ile belirli bir dildeki bir kelimeyi nasıl heceleyebilirim?

 C: Aspose.Words ile belirli bir dildeki bir kelimeyi hecelemek için`Hyphenation` sınıf ve`Hyphenate()` yöntem. Bir örneğini oluşturun`Hyphenation` İstenilen dili belirten sınıfı seçin, ardından`Hyphenate()` Kelimeyi argüman olarak hecelemek için geçirme yöntemi. Bu size belirtilen dildeki kelimenin hecelerini verecektir.

#### S: Aspose.Words'te heceleme dilini belirlemek için hangi dil kodlarını kullanmalıyım?

C: Aspose.Words'te heceleme dilini belirlemek için uygun dil kodlarını kullanmalısınız. Örneğin, İngilizce için "en", Fransızca için "fr", İspanyolca için "es", Almanca için "de" vb. kullanabilirsiniz. Desteklenen dil kodlarının tam listesi için Aspose.Words belgelerine bakın.

#### S: Aspose.Words'te heceleme tüm dillerde çalışıyor mu?

C: Aspose.Words'te heceleme, dile özgü heceleme kurallarına bağlıdır. Aspose.Words çok çeşitli dilleri desteklese de, bazı diller desteklenmeyebilir veya bunlar için heceleme mevcut olmayabilir. Heceleme için hangi dillerin desteklendiğini öğrenmek için Aspose.Words belgelerine bakın.