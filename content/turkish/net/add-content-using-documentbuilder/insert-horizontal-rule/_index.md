---
title: Word Belgesine Yatay Cetvel Ekleme
linktitle: Word Belgesine Yatay Cetvel Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine yatay kuralların nasıl eklendiğini öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
Bu kapsamlı örnekte, Aspose.Words for .NET'i kullanarak bir Word belgesine nasıl yatay kural ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda belgelerinize görsel ayırma ve düzenleme için yatay kurallar ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Adım 2: Yatay Kural Ekleyin
Daha sonra, açıklayıcı bir metin eklemek ve ardından yatay bir kural eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## 3. Adım: Belgeyi Kaydedin
Yatay kuralı ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Aspose.Words for .NET kullanarak Yatay Kural Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yatay kural eklemeye yönelik kaynak kodun tamamı burada:
Yatay kurallar, bölümleri bölmek, görsel aralar oluşturmak veya önemli bilgileri vurgulamak gibi çeşitli senaryolar için kullanışlıdır.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine nasıl yatay kural ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve verilen kaynak kodunu kullanarak artık belgelerinizi yatay kurallar kullanarak görsel olarak ayırabilir ve düzenleyebilirsiniz.

### Word belgesine yatay kural eklemeyle ilgili SSS

#### S: Yatay kuralın görünümünü özelleştirebilir miyim?

C: Evet, kesinlikle! Aspose.Words for .NET yatay kuralın görünümünü özelleştirmek için çeşitli özellikler sağlar. Belgenizin estetiğine uyacak şekilde genişliğini, yüksekliğini, hizalamasını, rengini ve gölgesini ayarlayabilirsiniz.

#### S: Tek bir belgeye birden fazla yatay kural ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine gerektiği kadar yatay kural ekleyebilirsiniz. Birden fazla görsel ara veya bölüm bölücü eklemek için ekleme işlemini tekrarlamanız yeterlidir.

#### S: Yatay kurallar PDF gibi diğer dosya formatlarıyla uyumlu mudur?

C: Evet, Aspose.Words for .NET kullanılarak eklenen yatay kurallar, DOCX ve PDF dahil çeşitli dosya formatlarıyla uyumludur. Bu, yatay kuralları koruyarak belgelerinizi farklı formatlarda dışa aktarabileceğiniz anlamına gelir.

#### S: Belgedeki belirli konumlara programlı olarak yatay bir kural ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET, yatay kuralı programlı olarak belge içindeki belirli konumlara konumlandırmanıza olanak tanır. Belgenizin içeriğine ve yapısına göre yerleşimini kontrol edebilirsiniz.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mudur?

C: Evet, Aspose.Words for .NET çok yönlüdür ve hem masaüstü hem de web uygulamalarında kullanılabilir. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kütüphaneyi zahmetsizce entegre edebilirsiniz.