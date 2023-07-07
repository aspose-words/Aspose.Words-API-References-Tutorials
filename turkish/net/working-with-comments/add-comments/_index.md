---
title: Yorum ekle
linktitle: Yorum ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerine nasıl yorum ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/add-comments/
---

Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesine nasıl yorum ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, belgelerinize yorum ekleyebilecek ve içeriklerini özelleştirebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesi başlatın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye İçerik Ekleyin
Ardından, DocumentBuilder nesnesini kullanarak istenen içeriği belgeye ekleyin. Bu örnekte, biraz metin ekliyoruz:

```csharp
builder.Write("Some text is added.");
```

## 3. Adım: Bir Yorum Oluşturun ve İçerik Ekleyin
Yorum eklemek için, Document nesnesini, yazar adını, yazarın adının baş harflerini ve geçerli tarihi ileten bir Comment sınıfı örneği oluşturun:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Ardından, yorumu mevcut paragrafa ekleyin:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Yoruma paragraf ve metin gibi içerikler ekleyin:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## 4. Adım: Belgeyi Kaydedin
Yorumu ve içeriğini ekledikten sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Aspose.Words for .NET kullanarak Yorum Ekleme için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yorum eklemek için eksiksiz kaynak kodu burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine nasıl yorum ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak, artık belgelerinize yorum ekleyebilir ve içeriklerini özelleştirebilirsiniz.

Yorumlar, işbirliği yapmak, ek bilgi sağlamak veya bir belge içinde notlar almak için kullanışlıdır. Özel gereksinimlerinizi karşılamak için farklı yazar adları, baş harfler ve yorum içerikleri ile denemeler yapın.

### SSS

#### S: Bir Aspose.Words for .NET belgesine nasıl yorum ekleyebilirim?

C: Bir Aspose.Words for .NET belgesine yorum eklemek için eğitimde belirtilen adımları izlemeniz gerekir.

#### S: Yorum metnini Aspose.Words for .NET'te biçimlendirebilir miyim?

C: Evet, mevcut biçimlendirme özelliklerini kullanarak yorum metnini Aspose.Words for .NET'te biçimlendirebilirsiniz.

#### S: Bir belgede bulunan tüm yorumları nasıl alabilirim?

 C: Bir belgede bulunan tüm yorumları aşağıdakileri kullanarak alabilirsiniz.`Document.Comments` mülk.

#### S: Aspose.Words for .NET'te belirli bir yorumu silebilir miyim?

 C: Evet, Aspose.Words for .NET'te belirli bir yorumu kaldırabilirsiniz.`Comment.Remove` yöntem.

#### S: Aspose.Words for .NET'te mevcut bir yorumun metnini nasıl değiştirebilirim?

 C: Aspose.Words for .NET'te mevcut bir yorumun metnini değiştirmek için şuraya erişebilirsiniz:`Comment.Text` karşılık gelen özellik`Comment` nesne ve metni gerektiği gibi değiştirin.