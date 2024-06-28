---
title: Bağlantı Yorumu
linktitle: Bağlantı Yorumu
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak yorum yanıtlarını Word belgelerindeki belirli metne nasıl bağlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/anchor-comment/
---

Bu kapsamlı eğitimde, Aspose.Words for .NET kullanarak yorum yanıtlarını bir Word belgesindeki belirli bir metne nasıl bağlayacağınızı öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda yorumları belgelerinizdeki belirli metinlerle ilişkilendirebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

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

## 2. Adım: Yorum Oluşturun ve Yorum Aralığı Ekleyin
Ardından, bir yorum oluşturun ve CommentRangeStart ve CommentRangeEnd nesnelerini kullanarak bunu belirli bir metinle ilişkilendirin:

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
Yorumu belirli bir metne bağladıktan sonra, Document sınıfının Kaydet yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Bağlantı Yorumu için Örnek Kaynak Kodu Aspose.Words for .NET kullanarak yanıtlama
Aspose.Words for .NET kullanarak bir yorum yanıtını sabitlemek için gereken kaynak kodun tamamı burada:

```csharp
// Belgenin bir örneğini oluşturun.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Üç Çalıştırma nesnesi oluşturun.
//İlk ikisi bir metin çalıştırırken üçüncüsü bir Yorum çalıştırır

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

### SSS'ler

#### S: Aspose.Words for .NET'te yorum bağlantısı nedir?

C: Aspose.Words for .NET'te yorum bağlantısı, bir yorumu belgedeki belirli bir konuma bağlayan bir işaretleyicidir.

#### S: Aspose.Words for .NET belgesine nasıl yorum bağlantısı ekleyebilirim?

C: Aspose.Words for .NET belgesine yorum bağlantısı eklemek için eğitimde belirtilen adımları izleyin.

#### S: Aspose.Words for .NET'te mevcut bir yorum bağlantısına nasıl erişebilirim?

 C: Aspose.Words for .NET'te mevcut bir yorum bağlantısına aşağıdaki komutu kullanarak erişebilirsiniz:`Comment.Anchor` mülk.

#### S: Aspose.Words for .NET'te bir yorum bağlantısını destekleyebilir miyim?

 C: Evet, Aspose.Words for .NET'teki bir yorum bağlantısını aşağıdaki komutu kullanarak kaldırabilirsiniz:`Comment.Remove` yöntem.

#### S: Aspose.Words for .NET'te bir yorum bağlantısına bağlı bir yorumun metnini nasıl düzenleyebilirim?

C: Aspose.Words for .NET'te bir yorum bağlantısına bağlı yorumun metnini değiştirmek için`Comment.Text` karşılık gelen mülk`Comment` nesneyi seçin ve metni gerektiği gibi değiştirin.

