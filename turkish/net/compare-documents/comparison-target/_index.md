---
title: Karşılaştırma Hedefi
linktitle: Karşılaştırma Hedefi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'in belgeleri karşılaştırmanıza ve yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanıyan hedef karşılaştırma özelliğini öğrenin.
type: docs
weight: 10
url: /tr/net/compare-documents/comparison-target/
---

Aşağıda, Aspose.Words for .NET'in karşılaştırma hedefi işlevini kullanan C# kaynak kodunu adım adım açıklayan bir kılavuz bulunmaktadır.

## 1. Adım: Giriş

Aspose.Words for .NET'in hedef karşılaştırma özelliği, iki belgeyi karşılaştırmanıza ve hedef belgede yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanır. Bu, bir belgenin farklı sürümleri arasında yapılan değişiklikleri izlemek için yararlı olabilir.

## 2. Adım: Ortamı ayarlama

Başlamadan önce, geliştirme ortamınızı Aspose.Words for .NET ile çalışacak şekilde ayarlamanız gerekir. Aspose.Words kitaplığının kurulu olduğundan ve kodu yerleştirmek için uygun bir C# projesine sahip olduğunuzdan emin olun.

## 3. Adım: Gerekli Montajları Ekleyin

Aspose.Words for .NET'in karşılaştırma hedefi özelliğini kullanmak için gerekli montajları projenize eklemelisiniz. Projenizde Aspose.Words'a uygun referansların bulunduğundan emin olun.

```csharp
using Aspose.Words;
```

## Adım 4: Belge Başlatma

Bu adımda, karşılaştırma için iki belgeyi başlatacağız. Kaynak belgenin adının yanı sıra belgelerinizin bulunduğu dizin yolunu da belirtmelisiniz.

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Karşılaştırılacak belge A'nın başlatılması.
Document docA = new Document(dataDir + "DocumentA.docx");

// B belgesinin aynı kopyasını oluşturmak için A belgesini kopyalayın.
Document docB = docA.Clone();
```

## 5. Adım: Karşılaştırma Seçeneklerini Yapılandırma

Bu adımda, karşılaştırma davranışını belirtmek için karşılaştırma seçeneklerini yapılandıracağız. Seçenekler, Microsoft Word'ün "Belgeleri Karşılaştır" iletişim kutusundaki "Değişiklikleri göster" seçeneği olan karşılaştırma hedefinin yanı sıra biçimlendirmeyi yok sayma özelliğini içerir.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## 6. Adım: Belge Karşılaştırması

Şimdi belgeleri karşılaştıracağız ve sonucu yeni bir belgede oluşturacağız.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 bu`Compare` yöntem, belge A'yı belge B ile karşılaştırır ve değişiklikleri belge A'ya kaydeder. Referans için kullanıcı adını ve karşılaştırma tarihini belirtebilirsiniz.

### Aspose.Words for .NET kullanan Karşılaştırma Hedefi için örnek kaynak kodu


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Microsoft Word'ün "Belgeleri Karşılaştır" iletişim kutusundaki "Değişiklikleri göster" seçeneğiyle ilgilidir.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Çözüm

Bu yazıda, Aspose.Words for .NET'in diff hedef özelliğini inceledik. Bu özellik, iki belgeyi karşılaştırmanıza ve yapılan değişiklikleri içeren yeni bir belge oluşturmanıza olanak tanır. Belgelerinizin farklı sürümleri arasındaki değişiklikleri izlemek için bu bilgiyi kullanabilirsiniz.

