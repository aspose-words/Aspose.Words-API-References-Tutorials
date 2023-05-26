---
title: Yorum Çözüldü ve Yanıtlar
linktitle: Yorum Çözüldü ve Yanıtlar
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerindeki yorumları ve yanıtlarını nasıl çözeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/comment-resolved-and-replies/
---

Bu kapsamlı öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki yorumları ve yanıtlarını nasıl çözümleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, yorum çözümlemesini yönetebilecek ve yorumların durumunu ve yanıtlarını güncelleyebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Belgeyi Yükleyin ve Yorumlara Erişin
Başlamak için, Document sınıfını kullanarak yorumları içeren belgeyi yükleyin ve yorumlar koleksiyonuna erişin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 2. Adım: Yorumları ve Yanıtlarını Çözün
Ardından, çözülmüş olarak işaretlemek için yorumları ve yanıtlarını yineleyin:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Yukarıdaki kodda, ana yoruma erişir ve yanıtlarını yineleriz. Üst yorum kimliğini ve çözüm durumunu alabiliriz. Ardından, çözümü belirtmek için her yorum yanıtının "Bitti" işaretini güncelliyoruz.

## 3. Adım: Belgeyi Kaydedin
Yorumları çözümledikten ve durumlarını güncelledikten sonra, değiştirilen belgeyi Document sınıfının Save yöntemini kullanarak bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Aspose.Words for .NET Kullanarak Yorumları ve Yanıtlarını Çözmek İçin Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yorumları ve yanıtlarını çözmek için eksiksiz kaynak kodu burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Kodu, belge dosyası yolu ve ek özelleştirme dahil olmak üzere özel gereksinimlerinize göre ayarlamayı unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesindeki yorumları ve yanıtlarını nasıl çözümleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak, artık yorum çözümlemesini yönetebilir ve yorumların durumunu ve yanıtlarını ihtiyaçlarınıza göre güncelleyebilirsiniz.

Yorum çözünürlüğü, bir belgedeki geri bildirimlerin izlenmesine ve yönetilmesine yardımcı olur. Belgelerinizdeki işbirliğini ve inceleme süreçlerini iyileştirmek için farklı yorum durumları ile denemeler yapın ve bunları özelleştirin.
