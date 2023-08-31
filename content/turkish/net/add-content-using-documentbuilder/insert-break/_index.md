---
title: Word Belgesine Ara Ekle
linktitle: Word Belgesine Ara Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerine nasıl sayfa sonları ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-break/
---
Bu kapsamlı örnekte, Aspose.Words for .NET'te InsertBreak yöntemini kullanarak bir Word belgesine nasıl sayfa sonları ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgenizdeki sayfa sonlarını kontrol edebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İçerik ve Sayfa Sonları Ekleyin
Ardından, belgeye içerik eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın. Sayfa sonu eklemek için, BreakType.PageBreak parametresiyle InsertBreak yöntemini kullanın:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## 3. Adım: Belgeyi Kaydedin
İçeriği ve sayfa sonlarını ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Aspose.Words for .NET kullanan Insert Break için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak sayfa sonları eklemek için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Kodu özel gereksinimlerinize göre ayarlamayı ve gerektiğinde ek işlevlerle geliştirmeyi unutmayın.


## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine sayfa sonları eklemeyi başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak, istenen konumlara sayfa sonları ekleyerek artık belgenizin sayfalandırmasını ve düzenini kontrol edebilirsiniz.

### SSS

#### S: Sayfa sonlarının yanı sıra farklı türde sonlar ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET, sayfa sonları, sütun sonları ve bölüm sonları dahil olmak üzere çeşitli türde sonları destekler. İstenen kesme türünü eklemek için InsertBreak yöntemini farklı BreakType parametreleriyle kullanabilirsiniz.

#### S: Belgenin belirli bölümlerine sayfa sonları ekleyebilir miyim?

C: Evet, belge içinde belirli konumlara sayfa sonları ekleyebilirsiniz. DocumentBuilder'ı kullanarak, belgenizin içeriğine ve yapısına göre sayfa sonlarının yerleşimini kontrol edebilirsiniz.

#### S: Belgeyi farklı dosya biçimlerinde kaydederken sayfa sonları korunacak mı?

C: Evet, belge DOCX, PDF veya RTF gibi farklı dosya formatlarında kaydedilirken Aspose.Words for .NET kullanılarak eklenen sayfa sonları korunur. Bu, farklı dosya biçimlerinde tutarlı sayfalandırma ve düzen sağlar.

#### S: Sayfa sonlarının görünümünü özelleştirebilir miyim?

C: Sayfa sonları belgenin kendisinde görünmez, ancak belgenin görünümünü kontrol etmek için sayfa sonlarından önce ve sonra içeriğin biçimlendirmesini ve düzenini ayarlayabilirsiniz.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mu?

C: Evet, Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun çok yönlü bir kitaplıktır. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kitaplığı zahmetsizce entegre edebilirsiniz.