---
title: Word Belgesinde Karşılaştırma Hedefi
linktitle: Word Belgesinde Karşılaştırma Hedefi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in belgeleri karşılaştırmanıza ve yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanıyan word belgesindeki hedef karşılaştırma özelliğini öğrenin.
type: docs
weight: 10
url: /tr/net/compare-documents/comparison-target/
---
Aşağıda Aspose.Words for .NET'in word belgesi işlevselliğindeki karşılaştırma hedefini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## Adım 1: Giriş

Aspose.Words for .NET'in hedefi karşılaştırma özelliği, iki belgeyi karşılaştırmanıza ve hedef belgede yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanır. Bu, bir belgenin farklı sürümleri arasında yapılan değişiklikleri izlemek için yararlı olabilir.

## 2. Adım: Ortamı ayarlama

Başlamadan önce geliştirme ortamınızı Aspose.Words for .NET ile çalışacak şekilde ayarlamanız gerekir. Aspose.Words kütüphanesinin kurulu olduğundan ve kodu gömmek için uygun bir C# projesine sahip olduğunuzdan emin olun.

## Adım 3: Gerekli Montajları Ekleyin

Aspose.Words for .NET'in karşılaştırma hedefi özelliğini kullanmak için gerekli derlemeleri projenize eklemelisiniz. Projenizde Aspose.Words'e doğru referansların bulunduğundan emin olun.

```csharp
using Aspose.Words;
```

## Adım 4: Belge Başlatma

Bu adımda karşılaştırma için iki belgeyi başlatacağız. Kaynak belgenin adının yanı sıra belgelerinizin bulunduğu dizin yolunu da belirtmeniz gerekir.

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Karşılaştırma için A belgesinin başlatılması.
Document docA = new Document(dataDir + "DocumentA.docx");

// B belgesinin aynı kopyasını oluşturmak için A belgesini kopyalayın.
Document docB = docA.Clone();
```

## Adım 5: Karşılaştırma Seçeneklerini Yapılandırma

Bu adımda karşılaştırmanın davranışını belirtmek için karşılaştırma seçeneklerini yapılandıracağız. Seçenekler arasında biçimlendirmeyi göz ardı etme özelliğinin yanı sıra, Microsoft Word'ün "Belgeleri Karşılaştır" iletişim kutusundaki "Değişiklikleri göster" seçeneği olan karşılaştırma hedefi de bulunur.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Adım 6: Belge Karşılaştırması

Şimdi belgeleri karşılaştırıp sonucu yeni bir belgede oluşturacağız.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

`Compare`yöntemi, A belgesini B belgesiyle karşılaştırır ve değişiklikleri A belgesine kaydeder. Referans için kullanıcı adını ve karşılaştırma tarihini belirleyebilirsiniz.

### Aspose.Words for .NET kullanan Karşılaştırma Hedefi için örnek kaynak kodu


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// "Belgeleri Karşılaştır" iletişim kutusundaki Microsoft Word "Değişiklikleri göster" seçeneğiyle ilgilidir.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Çözüm

Bu yazıda Aspose.Words for .NET'in fark hedefi özelliğini inceledik. Bu özellik, iki belgeyi karşılaştırmanıza ve yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanır. Bu bilgiyi belgelerinizin farklı sürümleri arasındaki değişiklikleri izlemek için kullanabilirsiniz.

### SSS'ler

#### S: Aspose.Words for .NET'te Karşılaştırma Hedefini kullanmanın amacı nedir?

C: Aspose.Words for .NET'teki Karşılaştırma Hedefi, iki belgeyi karşılaştırmanıza ve hedef belgede yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanır. Bu özellik, bir belgenin farklı sürümleri arasında yapılan değişiklikleri izlemek ve farklılıkları ayrı bir belgede görselleştirmek için kullanışlıdır.

#### S: Aspose.Words for .NET'te Karşılaştırma Hedefini nasıl kullanırım?

C: Aspose.Words for .NET'te Karşılaştırma Hedefini kullanmak için şu adımları izleyin:
1. Aspose.Words kütüphanesiyle geliştirme ortamınızı kurun.
2. Aspose.Words'e başvurarak gerekli derlemeleri projenize ekleyin.
3.  Karşılaştırmak istediğiniz belgeleri kullanarak başlatın.`Document` sınıf veya`DocumentBuilder` sınıf.
4.  Karşılaştırma seçeneklerini bir`CompareOptions` gibi nesne ve ayar özellikleri`IgnoreFormatting` Ve`Target` (Örneğin,`ComparisonTargetType.New` karşılaştırma hedefi için).
5.  Kullan`Compare` yöntemi bir belge üzerinde, diğer belgeyi aktararak ve`CompareOptions` parametre olarak nesne. Bu yöntem belgeleri karşılaştıracak ve değişiklikleri ilk belgeye kaydedecektir.

####  Soru: Programın amacı nedir?`Target` property in the `CompareOptions` class?

 C:`Target` içindeki mülk`CompareOptions` class, Microsoft Word'ün "Belgeleri Karşılaştır" iletişim kutusundaki "Değişiklikleri göster" seçeneğine benzeyen karşılaştırma hedefini belirtmenize olanak tanır. Hedef şu şekilde ayarlanabilir:`ComparisonTargetType.New` yeni bir belgedeki değişiklikleri göstermek için,`ComparisonTargetType.Current` Geçerli belgedeki değişiklikleri göstermek için veya`ComparisonTargetType.Formatting` yalnızca biçimlendirme değişikliklerini göstermek için.