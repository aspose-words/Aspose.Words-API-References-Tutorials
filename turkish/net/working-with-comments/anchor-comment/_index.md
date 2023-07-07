---
title: Çapa Yorumu
linktitle: Çapa Yorumu
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerindeki belirli metinlere yorum yanıtlarını nasıl tutturacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/anchor-comment/
---

Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki belirli bir metne yorum yanıtlarını nasıl tutturacağınızı öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, yorumları belgelerinizdeki belirli metinlerle ilişkilendirebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge Oluşturun ve Metin Ekleyin
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve istediğiniz metni ekleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## 2. Adım: Bir Yorum Oluşturun ve Yorum Aralığı Ekleyin
Ardından, bir yorum oluşturun ve bunu CommentRangeStart ve CommentRangeEnd nesnelerini kullanarak belirli bir metinle ilişkilendirin:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## 3. Adım: Belgeyi Kaydedin
Yorumu belirli bir metne sabitledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Aspose.Words for .NET kullanarak Anchor Comment Reply için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak bir yorum yanıtını sabitlemek için eksiksiz kaynak kodu burada:

```csharp
// Belgenin bir örneğini oluşturun.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Üç Çalıştır nesnesi oluşturun.
//İlk ikisi biraz metin çalıştırırken, üçüncüsü bir Yorum çalıştırır.

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Run nesnelerinin her birinin ilişkili bir CommentRangeStart ve CommentRangeEnd nesnesi vardır.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### SSS

#### S: Aspose.Words for .NET'te yorum çapası nedir?

Y: Aspose.Words for .NET'te, bir yorum bağlantısı, bir yorumu bir belgedeki belirli bir konuma bağlayan bir işaretleyicidir.

#### S: Bir Aspose.Words for .NET belgesine nasıl yorum çapası ekleyebilirim?

C: Bir Aspose.Words for .NET belgesine yorum bağlantısı eklemek için eğitimde bahsedilen adımları izleyin.

#### S: Aspose.Words for .NET'te mevcut bir yorum bağlantısına nasıl erişebilirim?

 C: Aspose.Words for .NET'te varolan bir yorum bağlantısına şu şekilde erişebilirsiniz:`Comment.Anchor` mülk.

#### S: Aspose.Words for .NET'te bir yorum çapası ekleyebilir miyim?

 C: Evet, Aspose.Words for .NET'te bir yorum bağlantısını kaldırabilirsiniz.`Comment.Remove` yöntem.

#### S: Aspose.Words for .NET'te bir yorum bağlantısına bağlı bir yorumun metnini nasıl düzenleyebilirim?

C: Aspose.Words for .NET'te bir yorum bağlantısına bağlı bir yorumun metnini değiştirmek için şuraya erişebilirsiniz:`Comment.Text` karşılık gelen özellik`Comment` nesne ve metni gerektiği gibi değiştirin.

