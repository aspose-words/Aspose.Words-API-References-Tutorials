---
title: Word Belgesinde Karşılaştırma Ayrıntı Düzeyi
linktitle: Word Belgesinde Karşılaştırma Ayrıntı Düzeyi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'in, belgelerin karakter karakter karşılaştırılmasını ve yapılan değişikliklerin raporlanmasını sağlayan sözcük belgesi özelliğinde Tanecikliği Karşılaştırmayı Öğrenin.
type: docs
weight: 10
url: /tr/net/compare-documents/comparison-granularity/
---
Aşağıda, Aspose.Words for .NET'in word belgesinde Granülariteyi Karşılaştır özelliğini kullanan C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır.

## 1. Adım: Giriş

Aspose.Words for .NET'in Granülariteyi Karşılaştır özelliği, belgeleri karakter düzeyinde karşılaştırmanıza olanak tanır. Bu, her karakterin karşılaştırılacağı ve değişikliklerin buna göre raporlanacağı anlamına gelir.

## 2. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile çalışacak şekilde ayarlamanız gerekir. Aspose.Words kitaplığının kurulu olduğundan ve kodu yerleştirmek için uygun bir C# projesine sahip olduğunuzdan emin olun.

## 3. Adım: Gerekli Montajları Ekleyin

Aspose.Words for .NET'in Granülariteyi Karşılaştır özelliğini kullanmak için gerekli derlemeleri projenize eklemeniz gerekir. Projenizde Aspose.Words'a uygun referansların bulunduğundan emin olun.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## 4. Adım: Belge Oluşturma

Bu adımda, DocumentBuilder sınıfını kullanarak iki belge oluşturacağız. Bu belgeler karşılaştırma için kullanılacaktır.

```csharp
// A belgesini oluşturun.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Belge B oluşturun.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## 5. Adım: Karşılaştırma Seçeneklerini Yapılandırma

Bu adımda, karşılaştırma ayrıntı düzeyini belirtmek için karşılaştırma seçeneklerini yapılandıracağız. Burada karakter düzeyinde ayrıntı düzeyi kullanacağız.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## 6. Adım: Belge Karşılaştırması

Şimdi Document sınıfının Compare yöntemini kullanarak belgeleri karşılaştıralım. Değişiklikler belge A'ya kaydedilecektir.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 bu`Compare` yöntem A belgesini B belgesiyle karşılaştırır ve değişiklikleri A belgesine kaydeder. Yazarın adını ve karşılaştırma tarihini referans olarak belirtebilirsiniz.

## Çözüm

Bu makalede, Aspose.Words for .NET'in Granülariteyi Karşılaştır özelliğini inceledik. Bu özellik, belgeleri karakter düzeyinde karşılaştırmanıza ve değişiklikleri raporlamanıza olanak tanır. Bu bilgiyi, projelerinizde ayrıntılı belge karşılaştırmaları yapmak için kullanabilirsiniz.

### Aspose.Words for .NET kullanan Karşılaştırma Tanecikliliği için örnek kaynak kodu

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET'in Karşılaştırma Tanecikliği özelliğini inceledik. Bu özellik, belgeleri karşılaştırırken ayrıntı düzeyini belirlemenizi sağlar. Farklı ayrıntı düzeyleri seçerek, özel gereksinimlerinize bağlı olarak karakter, kelime veya blok düzeyinde ayrıntılı karşılaştırmalar yapabilirsiniz. Aspose.Words for .NET, esnek ve güçlü bir belge karşılaştırma yeteneği sunarak, değişen ayrıntı düzeyine sahip belgelerdeki farklılıkları tanımlamayı kolaylaştırır.

### SSS

#### S: Aspose.Words for .NET'te Comparison Granularity kullanmanın amacı nedir?

A: Aspose.Words for .NET'teki Karşılaştırma Tanecikliliği, belgeleri karşılaştırırken ayrıntı düzeyini belirtmenize olanak tanır. Bu özellikle, belgeleri karakter düzeyinde, kelime düzeyinde ve hatta blok düzeyinde gibi farklı düzeylerde karşılaştırabilirsiniz. Her ayrıntı düzeyi, karşılaştırma sonuçlarında farklı bir ayrıntı düzeyi sağlar.

#### S: Karşılaştırma Tanecikliliğini Aspose.Words for .NET'te nasıl kullanırım?

C: Aspose.Words for .NET'te Karşılaştırma Parçacıklarını kullanmak için şu adımları izleyin:
1. Aspose.Words kütüphanesi ile geliştirme ortamınızı kurun.
2. Aspose.Words'e başvurarak gerekli montajları projenize ekleyin.
3.  kullanarak karşılaştırmak istediğiniz belgeleri oluşturun.`DocumentBuilder` sınıf.
4.  Oluşturarak karşılaştırma seçeneklerini yapılandırın.`CompareOptions` nesne ve ayarlama`Granularity` özelliğini istenilen seviyeye getirin (örn.`Granularity.CharLevel` karakter düzeyinde karşılaştırma için).
5.  Kullan`Compare` yöntemi bir belge üzerinde, diğer belgeyi ve`CompareOptions` parametre olarak nesne. Bu yöntem, belgeleri belirtilen ayrıntı düzeyine göre karşılaştırır ve değişiklikleri ilk belgeye kaydeder.

#### S: Aspose.Words for .NET'te mevcut Karşılaştırma Tane Düzeyi seviyeleri nelerdir?

Y: Aspose.Words for .NET, üç düzeyde Karşılaştırma Ayrıntı Düzeyi sağlar:
- `Granularity.CharLevel`: Belgeleri karakter düzeyinde karşılaştırır.
- `Granularity.WordLevel`: Belgeleri kelime düzeyinde karşılaştırır.
- `Granularity.BlockLevel`: Belgeleri blok düzeyinde karşılaştırır.

#### S: Karşılaştırma sonuçlarını karakter düzeyinde ayrıntı düzeyiyle nasıl yorumlayabilirim?

C: Karakter düzeyinde ayrıntı düzeyiyle, karşılaştırılan belgelerdeki her karakter farklılıklar açısından analiz edilir. Karşılaştırma sonuçları, eklemeler, silmeler ve değişiklikler dahil olmak üzere bireysel karakter düzeyindeki değişiklikleri gösterecektir.