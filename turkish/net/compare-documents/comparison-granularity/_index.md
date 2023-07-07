---
title: Karşılaştırma Ayrıntı Düzeyi
linktitle: Karşılaştırma Ayrıntı Düzeyi
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'in, belgelerin karakter karakter karşılaştırılmasına ve yapılan değişikliklerin raporlanmasına olanak tanıyan Karşılaştırma Tanecikliğini Öğrenin.
type: docs
weight: 10
url: /tr/net/compare-documents/comparison-granularity/
---
Aşağıda, Aspose.Words for .NET'in Granülariteyi Karşılaştır özelliğini kullanan C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır.

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

 bu`Compare`yöntem A belgesini B belgesiyle karşılaştırır ve değişiklikleri A belgesine kaydeder. Yazarın adını ve karşılaştırma tarihini referans olarak belirtebilirsiniz.

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
