---
title: Word Belgesinde Tablo Hücresine Taşı
linktitle: Word Belgesinde Tablo Hücresine Taşı
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET'in word belgesi özelliğinde Tablo Hücresine Taşı'yı kullanmak için adım adım kılavuz
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-table-cell/
---
Bu örnekte, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in Word belgesinde Tablo Hücresine Taşı özelliğini adım adım nasıl kullanacağınızı göstereceğiz. Bu özellik, bir Word belgesindeki bir tablonun içindeki belirli hücrelerde gezinmenizi ve bu hücreleri değiştirmenizi sağlar. Bu işlevi uygulamanıza entegre etmek için aşağıdaki adımları izleyin.

## 1. Adım: Tabloyu içeren belgeyi yükleyin

Öncelikle hücreyi içine taşımak istediğimiz tabloyu içeren belgeyi yüklememiz gerekiyor. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Bu kod, belirtilen belgeyi yükler ("MyDir + "Tables.docx yerine"" tabloyu içeren belgenizin gerçek yolu ile).

## 2. Adım: DocumentBuilder'ı belirli bir tablo hücresine taşıyın

Ardından, DocumentBuilder'ı belirli bir tablo hücresine taşıyacağız. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Bu kod, mevcut belgeden bir DocumentBuilder oluşturur ve ardından imleci DocumentBuilder'dan belirtilen tablo hücresine taşır. Son olarak, DocumentBuilder'ı kullanarak o hücreye içerik ekler.`Write()` yöntem.

## 3. Adım: Sonucu kontrol edin

Artık tablo hücresine taşımanın başarılı olduğunu doğrulayabilirsiniz. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Bu kod, belirtilen hücrenin gerçekten DocumentBuilder'ın geçerli hücresi olduğunu doğrular. Ayrıca, DocumentBuilder tarafından eklenen içeriğin tablo hücresine doğru şekilde kaydedildiğini de doğrular.

Bu kadar ! Sağlanan kaynak kodunu kullanarak Aspose.Words for .NET'in tablo hücresine taşıma işlevini artık nasıl kullanacağınızı anladınız. Artık bu işlevi kendi uygulamanıza entegre edebilir ve Word belgelerindeki belirli tablo hücrelerini değiştirebilirsiniz.


### Aspose.Words for .NET kullanarak bir tablo hücresine geçmek için örnek kaynak kodu


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Oluşturucuyu ilk tablonun 3. satırındaki 4. hücreye taşıyın.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Çözüm

Bu örnekte Aspose.Words for .NET'in Tablo Hücresine Taşı özelliğini inceledik. Tablo içeren bir belgeyi yüklemeyi, DocumentBuilder'ı belirli bir tablo hücresine taşımayı ve bu hücreye içerik eklemeyi öğrendik. Bu özellik, geliştiricilere Aspose.Words for .NET kullanarak Word belge tablolarındaki belirli hücrelerde programlı olarak gezinmek ve bunları değiştirmek için güçlü araçlar sağlar. Dinamik Word belge işleme ve tablo içerik yönetimi uygulamanıza değerli bir katkı olabilir.

### Word belgesinde tablo hücresine geçiş için SSS

#### S: Aspose.Words for .NET'teki Tablo Hücresine Taşı özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Tablo Hücresine Taşı özelliği, geliştiricilerin bir Word belgesindeki bir tablo içindeki belirli hücrelere programlı olarak gitmesine ve bunlarda değişiklik yapmasına olanak tanır. Belirli bir hücreye içerik ekleme, değiştirme veya silme yeteneği sağlar.

#### S: DocumentBuilder'ı bir Word belgesindeki belirli bir tablo hücresine nasıl taşırım?

C: DocumentBuilder'ı bir Word belgesinde belirli bir tablo hücresine taşımak için DocumentBuilder sınıfının MoveToCell yöntemini kullanabilirsiniz. Bu yöntem tablodaki hedef satırın ve hücrenin indekslerini parametre olarak alır ve imleci o hücrenin başına yerleştirir.

#### S: Tablo Hücresine Taşı özelliğini kullanarak belirli bir tablo hücresine taşıdıktan sonra içerik ekleyebilir veya içeriği değiştirebilir miyim?

Y: Evet, DocumentBuilder MoveToCell kullanılarak istenen tablo hücresine yerleştirildikten sonra, o hücrenin içeriğini eklemek veya değiştirmek için DocumentBuilder sınıfının Write, Writeln veya InsertHtml gibi çeşitli yöntemlerini kullanabilirsiniz.

#### S: Tablo hücresine taşımanın başarılı olduğunu nasıl doğrulayabilirim?

A: DocumentBuilder'ın imlecinin konumunu kontrol ederek tablo hücresine başarılı taşımayı doğrulayabilirsiniz. Örneğin, DocumentBuilder'ın geçerli düğümünü taşımak istediğiniz hücreyle karşılaştırabilir ve DocumentBuilder tarafından eklenen içeriğin tablo hücresine doğru şekilde kaydedildiğini doğrulayabilirsiniz.