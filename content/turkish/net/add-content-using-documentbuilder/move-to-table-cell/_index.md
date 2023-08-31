---
title: Word Belgesinde Tablo Hücresine Taşı
linktitle: Word Belgesinde Tablo Hücresine Taşı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'in word belgesi özelliğinde Tablo Hücresine Taşı özelliğini kullanmayla ilgili adım adım kılavuz
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-table-cell/
---
Bu örnekte, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in word belgesinde Tablo Hücresine Taşı özelliğini nasıl kullanacağınızı adım adım anlatacağız. Bu özellik, bir Word belgesindeki tablonun içindeki belirli hücrelerde gezinmenize ve bunları değiştirmenize olanak tanır. Bu işlevselliği uygulamanıza entegre etmek için aşağıdaki adımları izleyin.

## 1. Adım: Tabloyu içeren belgeyi yükleyin

Öncelikle hücreyi taşımak istediğimiz tablonun bulunduğu belgeyi yüklememiz gerekiyor. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Bu kod belirtilen belgeyi yükler ("MyDir + "Tables.docx ile değiştirin)"" belgenizin tabloyu içeren gerçek yolu ile birlikte).

## Adım 2: DocumentBuilder'ı belirli bir tablo hücresine taşıyın

Daha sonra DocumentBuilder'ı belirli bir tablo hücresine taşıyacağız. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Bu kod, mevcut belgeden bir DocumentBuilder oluşturur ve ardından imleci DocumentBuilder'dan belirtilen tablo hücresine taşır. Son olarak DocumentBuilder'ın işlevini kullanarak bu hücreye içerik ekler.`Write()` yöntem.

## 3. Adım: Sonucu kontrol edin

Artık tablo hücresine taşımanın başarılı olduğunu doğrulayabilirsiniz. Bu adımı gerçekleştirmek için aşağıdaki kodu kullanın:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Bu kod, belirtilen hücrenin gerçekten de DocumentBuilder'ın geçerli hücresi olduğunu doğrular. Ayrıca DocumentBuilder tarafından eklenen içeriğin tablo hücresine doğru şekilde kaydedildiğini de doğrular.

Bu kadar ! Artık sağlanan kaynak kodunu kullanarak Aspose.Words for .NET'in tablo hücresine taşıma işlevini nasıl kullanacağınızı anladınız. Artık bu işlevselliği kendi uygulamanıza entegre edebilir ve Word belgelerindeki belirli tablo hücrelerini değiştirebilirsiniz.


### Aspose.Words for .NET kullanarak bir tablo hücresine geçmek için örnek kaynak kodu


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Oluşturucuyu ilk tablonun 3. satırının 4. hücresine taşıyın.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Çözüm

Bu örnekte Aspose.Words for .NET'in Tablo Hücresine Taşı özelliğini inceledik. Tablo içeren bir belgenin nasıl yükleneceğini, DocumentBuilder'ı belirli bir tablo hücresine nasıl taşıyacağımızı ve bu hücreye içerik eklemeyi öğrendik. Bu özellik, geliştiricilere Aspose.Words for .NET kullanarak Word belge tablolarındaki belirli hücrelerde programlı olarak gezinmek ve bunları değiştirmek için güçlü araçlar sağlar. Dinamik Word belgesi işleme ve tablo içerik yönetimi için uygulamanıza değerli bir katkı olabilir.

### Word belgesinde tablo hücresine geçişle ilgili SSS'ler

#### S: Aspose.Words for .NET'teki Tablo Hücresine Taşı özelliğinin amacı nedir?

C: Aspose.Words for .NET'teki Tablo Hücresine Taşı özelliği, geliştiricilerin bir Word belgesindeki tablo içindeki belirli hücrelere programlı olarak gitmesine ve bunları değiştirmesine olanak tanır. Belirli bir hücreye içerik ekleme, değiştirme veya silme olanağı sağlar.

#### S: DocumentBuilder'ı bir Word belgesindeki belirli bir tablo hücresine nasıl taşıyabilirim?

C: DocumentBuilder'ı bir Word belgesindeki belirli bir tablo hücresine taşımak için DocumentBuilder sınıfının MoveToCell yöntemini kullanabilirsiniz. Bu yöntem, tablodaki hedef satırın ve hücrenin indekslerini parametre olarak alır ve imleci o hücrenin başına yerleştirir.

#### S: Tablo Hücresine Taşı özelliğini kullanarak belirli bir tablo hücresine taşındıktan sonra içerik ekleyebilir veya içeriği değiştirebilir miyim?

C: Evet, DocumentBuilder, MoveToCell kullanılarak istenen tablo hücresine konumlandırıldığında, bu hücrenin içeriğini eklemek veya değiştirmek için DocumentBuilder sınıfının Write, Writeln veya InsertHtml gibi çeşitli yöntemlerini kullanabilirsiniz.

#### S: Tablo hücresine taşımanın başarılı olduğunu nasıl doğrulayabilirim?

C: DocumentBuilder imlecinin konumunu kontrol ederek tablo hücresine başarılı bir şekilde taşındığını doğrulayabilirsiniz. Örneğin, DocumentBuilder'ın geçerli düğümünü, taşımayı planladığınız hücreyle karşılaştırabilir ve DocumentBuilder tarafından eklenen içeriğin tablo hücresine doğru şekilde kaydedildiğini doğrulayabilirsiniz.