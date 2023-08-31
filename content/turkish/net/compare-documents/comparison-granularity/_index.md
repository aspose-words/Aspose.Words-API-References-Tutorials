---
title: Word Belgesinde Karşılaştırma Ayrıntı Düzeyi
linktitle: Word Belgesinde Karşılaştırma Ayrıntı Düzeyi
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in, dokümanların karakter karakter karşılaştırılmasına ve yapılan değişikliklerin raporlanmasına olanak tanıyan word belgesindeki Granülerliği Karşılaştırma özelliğini öğrenin.
type: docs
weight: 10
url: /tr/net/compare-documents/comparison-granularity/
---
Burada, Aspose.Words for .NET'in word belgesinde Ayrıntı Düzeyini Karşılaştır özelliğini kullanan C# kaynak kodunu açıklayan adım adım bir kılavuz bulunmaktadır.

## Adım 1: Giriş

Aspose.Words for .NET'in Ayrıntı Düzeyini Karşılaştır özelliği, belgeleri karakter düzeyinde karşılaştırmanıza olanak tanır. Bu, her karakterin karşılaştırılacağı ve değişikliklerin buna göre raporlanacağı anlamına gelir.

## 2. Adım: Ortamı ayarlama

Başlamadan önce geliştirme ortamınızı Aspose.Words for .NET ile çalışacak şekilde ayarlamanız gerekir. Aspose.Words kütüphanesinin kurulu olduğundan ve kodu gömmek için uygun bir C# projesine sahip olduğunuzdan emin olun.

## Adım 3: Gerekli Montajları Ekleyin

Aspose.Words for .NET'in Granülariteyi Karşılaştır özelliğini kullanmak için gerekli derlemeleri projenize eklemeniz gerekir. Projenizde Aspose.Words'e doğru referansların bulunduğundan emin olun.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Adım 4: Belge Oluşturma

Bu adımda DocumentBuilder sınıfını kullanarak iki belge oluşturacağız. Bu belgeler karşılaştırma için kullanılacaktır.

```csharp
// A belgesini oluşturun.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// B belgesini oluşturun.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Adım 5: Karşılaştırma Seçeneklerini Yapılandırma

Bu adımda, karşılaştırma ayrıntı düzeyini belirlemek için karşılaştırma seçeneklerini yapılandıracağız. Burada karakter düzeyinde ayrıntı düzeyi kullanacağız.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Adım 6: Belge Karşılaştırması

Şimdi Document sınıfının Compare yöntemini kullanarak belgeleri karşılaştıralım. Değişiklikler A belgesine kaydedilecektir.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

`Compare` yöntem, A belgesini B belgesiyle karşılaştırır ve değişiklikleri A belgesine kaydeder. Referans için yazarın adını ve karşılaştırma tarihini belirtebilirsiniz.

## Çözüm

Bu yazıda Aspose.Words for .NET'in Granülerliği Karşılaştır özelliğini inceledik. Bu özellik, belgeleri karakter düzeyinde karşılaştırmanıza ve değişiklikleri raporlamanıza olanak tanır. Bu bilgiyi projelerinizde ayrıntılı belge karşılaştırmaları yapmak için kullanabilirsiniz.

### Aspose.Words for .NET kullanarak Karşılaştırma Ayrıntı Düzeyi için örnek kaynak kodu

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Çözüm

Bu eğitimde Aspose.Words for .NET'in Karşılaştırma Parça Boyutu özelliğini inceledik. Bu özellik, belgeleri karşılaştırırken ayrıntı düzeyini belirtmenize olanak tanır. Farklı ayrıntı düzeyleri seçerek, özel gereksinimlerinize bağlı olarak karakter, sözcük veya blok düzeyinde ayrıntılı karşılaştırmalar gerçekleştirebilirsiniz. Aspose.Words for .NET, esnek ve güçlü bir belge karşılaştırma özelliği sunarak, farklı ayrıntı düzeylerine sahip belgelerdeki farklılıkları tanımlamayı kolaylaştırır.

### SSS'ler

#### S: Aspose.Words for .NET'te Karşılaştırma Ayrıntı Düzeyini kullanmanın amacı nedir?

C: Aspose.Words for .NET'teki Karşılaştırma Ayrıntı Düzeyi, belgeleri karşılaştırırken ayrıntı düzeyini belirtmenize olanak tanır. Bu özellik sayesinde, belgeleri karakter düzeyi, sözcük düzeyi ve hatta blok düzeyi gibi farklı düzeylerde karşılaştırabilirsiniz. Her ayrıntı düzeyi, karşılaştırma sonuçlarında farklı düzeyde ayrıntı sağlar.

#### S: Aspose.Words for .NET'te Karşılaştırma Ayrıntı Düzeyini nasıl kullanırım?

C: Aspose.Words for .NET'te Karşılaştırma Ayrıntı Düzeyini kullanmak için şu adımları izleyin:
1. Aspose.Words kütüphanesiyle geliştirme ortamınızı kurun.
2. Aspose.Words'e başvurarak gerekli derlemeleri projenize ekleyin.
3.  Karşılaştırmak istediğiniz belgeleri kullanarak oluşturun.`DocumentBuilder` sınıf.
4.  Karşılaştırma seçeneklerini bir`CompareOptions` nesneyi ayarlama ve`Granularity` özelliği istenilen seviyeye getirin (örn.`Granularity.CharLevel` karakter düzeyinde karşılaştırma için).
5.  Kullan`Compare` yöntemi bir belge üzerinde, diğer belgeyi aktararak ve`CompareOptions` parametre olarak nesne. Bu yöntem, belgeleri belirtilen ayrıntı düzeyine göre karşılaştıracak ve değişiklikleri ilk belgeye kaydedecektir.

#### S: Aspose.Words for .NET'te Karşılaştırma Ayrıntı Düzeyinin mevcut seviyeleri nelerdir?

C: Aspose.Words for .NET üç düzeyde Karşılaştırma Parçalılığı sağlar:
- `Granularity.CharLevel`: Belgeleri karakter düzeyinde karşılaştırır.
- `Granularity.WordLevel`: Belgeleri kelime düzeyinde karşılaştırır.
- `Granularity.BlockLevel`: Belgeleri blok düzeyinde karşılaştırır.

#### S: Karşılaştırma sonuçlarını karakter düzeyinde ayrıntı düzeyiyle nasıl yorumlayabilirim?

C: Karakter düzeyinde ayrıntı düzeyiyle, karşılaştırılan belgelerdeki her karakter, farklılıklar açısından analiz edilir. Karşılaştırma sonuçları, eklemeler, silmeler ve değişiklikler de dahil olmak üzere bireysel karakter düzeyindeki değişiklikleri gösterecektir.