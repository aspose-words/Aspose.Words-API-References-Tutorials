---
title: Yorum ekle
linktitle: Yorum ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerine nasıl yorum ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/add-comments/
---

Bu kapsamlı eğitimde Aspose.Words for .NET kullanarak bir Word belgesine nasıl yorum ekleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda belgelerinize yorum ekleyebilecek ve bunların içeriğini özelleştirebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Yeni Bir Belge ve DocumentBuilder Oluşturun
Başlamak için Document sınıfını kullanarak yeni bir belge oluşturun ve bir DocumentBuilder nesnesini başlatın:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: Belgeye İçerik Ekleme
Daha sonra DocumentBuilder nesnesini kullanarak istediğiniz içeriği belgeye ekleyin. Bu örnekte bir miktar metin ekliyoruz:

```csharp
builder.Write("Some text is added.");
```

## 3. Adım: Yorum Oluşturun ve İçerik Ekleyin
Yorum eklemek için, Document nesnesini, yazarın adını, yazarın adının baş harflerini ve geçerli tarihi ileten Comment sınıfının bir örneğini oluşturun:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Ardından, yorumu geçerli paragrafa ekleyin:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Yoruma paragraf ve metin gibi içerikler ekleyin:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Adım 4: Belgeyi Kaydedin
Yorumu ve içeriğini ekledikten sonra, Document sınıfının Kaydet yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Aspose.Words for .NET kullanarak Yorum Eklemek için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yorum eklemeye yönelik kaynak kodun tamamı burada:

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
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine nasıl yorum ekleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak artık belgelerinize yorum ekleyebilir ve bunların içeriğini özelleştirebilirsiniz.

Yorumlar işbirliği yapmak, ek bilgi sağlamak veya bir belgede not almak için kullanışlıdır. Özel gereksinimlerinizi karşılamak için farklı yazar adları, baş harfleri ve yorum içerikleriyle denemeler yapın.

### SSS'ler

#### S: Aspose.Words for .NET belgesine nasıl yorum ekleyebilirim?

C: Aspose.Words for .NET belgesine yorum eklemek için eğitimde belirtilen adımları izlemeniz gerekir.

#### S: Aspose.Words for .NET'te yorum metnini formatlayabilir miyim?

C: Evet, Aspose.Words for .NET'te mevcut formatlama özelliklerini kullanarak yorum metnini formatlayabilirsiniz.

#### S: Bir belgede bulunan tüm yorumları nasıl alabilirim?

 C: Bir belgede sunulan tüm yorumları aşağıdaki komutu kullanarak alabilirsiniz:`Document.Comments` mülk.

#### S: Aspose.Words for .NET'te belirli bir yorumu silebilir miyim?

 C: Evet, Aspose.Words for .NET'te belirli bir yorumu aşağıdaki komutu kullanarak kaldırabilirsiniz:`Comment.Remove` yöntem.

#### S: Aspose.Words for .NET'te mevcut bir yorumun metnini nasıl değiştirebilirim?

 C: Aspose.Words for .NET'te mevcut bir yorumun metnini değiştirmek için`Comment.Text` karşılık gelen mülk`Comment` nesneyi seçin ve metni gerektiği gibi değiştirin.