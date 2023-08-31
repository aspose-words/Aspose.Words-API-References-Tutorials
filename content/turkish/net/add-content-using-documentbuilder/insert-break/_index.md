---
title: Word Belgesine Kesme Ekle
linktitle: Word Belgesine Kesme Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine sayfa sonlarını nasıl ekleyeceğinizi öğrenin. Adım adım rehber.
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/insert-break/
---
Bu kapsamlı örnekte, Aspose.Words for .NET'teki InsertBreak yöntemini kullanarak bir Word belgesine sayfa sonlarının nasıl ekleneceğini öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda belgenizdeki sayfa sonlarını kontrol edebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İçerik ve Sayfa Sonlarını Ekleme
Daha sonra belgeye içerik eklemek için DocumentBuilder sınıfının Writeln yöntemini kullanın. Sayfa sonu eklemek için InsertBreak yöntemini BreakType.PageBreak parametresiyle birlikte kullanın:

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

### Aspose.Words for .NET kullanarak Insert Break için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak sayfa sonları eklemek için tam kaynak kodunu burada bulabilirsiniz:

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
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine sayfa sonlarının nasıl ekleneceğini başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve verilen kaynak kodunu kullanarak, artık istediğiniz konumlara sayfa sonları ekleyerek belgenizin sayfalandırmasını ve düzenini kontrol edebilirsiniz.

### SSS'ler

#### S: Sayfa sonlarının yanı sıra farklı türde sonlar da ekleyebilir miyim?

C: Kesinlikle! Aspose.Words for .NET, sayfa sonları, sütun sonları ve bölüm sonları dahil olmak üzere çeşitli sonları destekler. İstediğiniz kesme türünü eklemek için InsertBreak yöntemini farklı BreakType parametreleriyle kullanabilirsiniz.

#### S: Belgenin belirli bölümlerine sayfa sonları ekleyebilir miyim?

C: Evet, belgenin belirli konumlarına sayfa sonları ekleyebilirsiniz. DocumentBuilder'ı kullanarak belgenizin içeriğine ve yapısına göre sayfa sonlarının yerleşimini kontrol edebilirsiniz.

#### S: Belgeyi farklı dosya formatlarında kaydederken sayfa sonları korunacak mı?

C: Evet, Aspose.Words for .NET kullanılarak eklenen sayfa sonları, belge DOCX, PDF veya RTF gibi farklı dosya formatlarında kaydedilirken korunur. Bu, farklı dosya formatlarında tutarlı sayfalandırma ve düzen sağlar.

#### S: Sayfa sonlarının görünümünü özelleştirebilir miyim?

C: Sayfa sonları belgenin kendisinde görünmez, ancak belgenin görünümünü kontrol etmek için içeriğin biçimlendirmesini ve düzenini sayfa sonlarından önce ve sonra ayarlayabilirsiniz.

#### S: Aspose.Words for .NET hem masaüstü hem de web uygulamaları için uygun mudur?

C: Evet, Aspose.Words for .NET hem masaüstü hem de web uygulamalarına uygun, çok yönlü bir kütüphanedir. İster bir Windows uygulaması ister web tabanlı bir sistem oluşturuyor olun, kütüphaneyi zahmetsizce entegre edebilirsiniz.