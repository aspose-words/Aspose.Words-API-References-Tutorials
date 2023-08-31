---
title: Yorum Çözüldü ve Cevaplar
linktitle: Yorum Çözüldü ve Cevaplar
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerindeki yorumları ve yanıtlarını nasıl çözümleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/comment-resolved-and-replies/
---

Bu kapsamlı eğitimde, Aspose.Words for .NET kullanarak bir Word belgesindeki yorumları ve yanıtlarını nasıl çözümleyeceğinizi öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda yorum çözümlemesini yönetebilecek ve yorumların durumunu ve yanıtlarını güncelleyebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Belgeyi Yükleyin ve Yorumlara Erişin
Başlamak için, Document sınıfını kullanarak yorumları içeren belgeyi yükleyin ve yorumlar koleksiyonuna erişin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## 2. Adım: Yorumları ve Yanıtlarını Çözümleyin
Ardından, yorumları ve yanıtlarını yineleyerek çözümlendi olarak işaretleyin:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Yukarıdaki kodda ana yoruma erişiyoruz ve yanıtlarını yineliyoruz. Ana yorum kimliğini ve çözüm durumunu alabiliriz. Ardından, çözümü belirtmek için her yorum yanıtının "Bitti" işaretini güncelleriz.

## 3. Adım: Belgeyi Kaydedin
Yorumları çözümledikten ve durumlarını güncelledikten sonra, değiştirilen belgeyi Document sınıfının Save yöntemini kullanarak bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Aspose.Words for .NET Kullanarak Yorumları ve Yanıtlarını Çözümlemeye Yönelik Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yorumları ve yanıtlarını çözümlemeye yönelik kaynak kodun tamamı burada:

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
Kodu, belge dosya yolu ve ek özelleştirme dahil olmak üzere özel gereksinimlerinize göre ayarlamayı unutmayın.

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesindeki yorumları ve yanıtlarını nasıl çözümleyeceğinizi başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodunu kullanarak artık yorum çözümlemesini yönetebilir ve yorumların durumunu ve yanıtlarını gereksinimlerinize göre güncelleyebilirsiniz.

Yorum çözünürlüğü, bir belgedeki geri bildirimin izlenmesine ve yönetilmesine yardımcı olur. Farklı yorum durumlarını deneyin ve belgelerinizdeki işbirliğini ve inceleme süreçlerini geliştirmek için bunları özelleştirin.

### SSS'ler

#### S: Aspose.Words for .NET'te bir yorumu nasıl çözümleyebilirim?

 C: Aspose.Words for .NET'te bir yorumu çözümlemek için`Comment.Resolve` belirten yöntem`Comment` çözmek istediğiniz nesneyi seçin. Bu, yorumu çözümlendi olarak işaretleyecek ve son belgede gizleyecektir.

#### S: Aspose.Words for .NET'te çözümlenen bir yoruma nasıl yanıt eklerim?

 C: Son belgede çözümlenen yorumlar varsayılan olarak gizlense de, çözümlenen bir yoruma yine de yanıt ekleyebilirsiniz.`Comment.AddReply` Yanıt metnini ve onu nereye eklemek istediğinizi belirten yöntem.

#### S: Aspose.Words for .NET'te çözümlenen yorumları nasıl görüntüleyebilirim?

 C: Varsayılan olarak çözümlenen yorumlar son belgede gizlenir. Ancak bunları kullanarak gösterebilirsiniz.`CommentOptions.ShowResolvedComments` mülkiyeti`Document` nesne ve onu buna ayarlamak`true`.

#### S: Aspose.Words for .NET'te yanıtlar dahil tüm yorumları nasıl gizleyebilirim?

 C: Aspose.Words for .NET'te yanıtlar dahil tüm yorumları gizlemek için`CommentOptions.CommentDisplayMode` mülkiyeti`Document` nesneyi seçin ve buna ayarlayın`CommentDisplayMode.None`.

#### S: Aspose.Words for .NET'te çözümlenen bir yorumun metnini düzenleyebilir miyim?

 C: Evet, Aspose.Words for .NET'te çözümlenen bir yorumun metnini şu adrese erişerek düzenleyebilirsiniz:`Comment.Text` karşılık gelen mülk`Comment` nesneyi seçin ve metni gerektiği gibi değiştirin.