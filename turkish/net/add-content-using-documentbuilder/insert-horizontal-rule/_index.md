---
title: Word Belgesine Yatay Kural Ekleme
linktitle: Word Belgesine Yatay Kural Ekleme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine yatay kuralları nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
Bu kapsamlı örnekte, Aspose.Words for .NET kullanarak bir Word belgesine nasıl yatay bir kural ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, görsel ayırma ve düzenleme için belgelerinize yatay kurallar ekleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Bir Yatay Kural Ekleyin
Ardından, açıklayıcı bir metin eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın ve ardından yatay bir kural ekleyin:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## 3. Adım: Belgeyi Kaydedin
Yatay kuralı ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Aspose.Words for .NET kullanarak Yatay Kural Ekleme için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yatay bir kural eklemek için eksiksiz kaynak kodu burada:
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
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine yatay bir kuralın nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık belgelerinizi yatay kurallar kullanarak görsel olarak ayırabilir ve düzenleyebilirsiniz.

### Word belgesine yatay kural eklemek için SSS

#### S: Yatay kuralın görünümünü özelleştirebilir miyim?

C: Evet, kesinlikle! Aspose.Words for .NET, yatay kuralın görünümünü özelleştirmek için çeşitli özellikler sağlar. Belgenizin estetiğine uyması için genişliğini, yüksekliğini, hizalamasını, rengini ve gölgelemesini ayarlayabilirsiniz.

#### S: Tek bir belgeye birden çok yatay kural ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET'i kullanarak bir Word belgesine gerektiği kadar yatay kural ekleyebilirsiniz. Birden çok görsel ara veya bölüm ayırıcı eklemek için ekleme işlemini tekrarlamanız yeterlidir.

#### S: Yatay kurallar, PDF gibi diğer dosya biçimleriyle uyumlu mudur?

C: Evet, Aspose.Words for .NET kullanılarak eklenen yatay kurallar, DOCX ve PDF dahil olmak üzere çeşitli dosya biçimleriyle uyumludur. Bu, yatay kuralları korurken belgelerinizi farklı biçimlerde dışa aktarabileceğiniz anlamına gelir.

#### S: Belgedeki belirli konumlara programlı olarak yatay bir kural ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET, yatay kuralı programlı olarak belge içindeki belirli konumlara yerleştirmenize olanak tanır. Yerleşimini, belgenizin içeriğine ve yapısına göre kontrol edebilirsiniz.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mu?

C: Evet, Aspose.Words for .NET çok yönlüdür ve hem masaüstü hem de web uygulamalarında kullanılabilir. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kitaplığı zahmetsizce entegre edebilirsiniz.