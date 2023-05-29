---
title: Tablo Hücresine Taşı
linktitle: Tablo Hücresine Taşı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'te Tablo Hücresine Taşı'yı kullanmak için adım adım kılavuz
type: docs
weight: 10
url: /tr/net/add-content-using-documentbuilder/move-to-table-cell/
---

Bu örnekte, sağlanan C# kaynak kodunu kullanarak Aspose.Words for .NET'in Tablo Hücresine Taşı özelliğini adım adım nasıl kullanacağınız konusunda size yol göstereceğiz. Bu özellik, bir Word belgesindeki bir tablonun içindeki belirli hücrelerde gezinmenizi ve bu hücreleri değiştirmenizi sağlar. Bu işlevi uygulamanıza entegre etmek için aşağıdaki adımları izleyin.

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
