---
title: Ekle Yorumu Kaldır Yanıtla
linktitle: Ekle Yorumu Kaldır Yanıtla
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde yorum yanıtlarını nasıl ekleyip kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/add-remove-comment-reply/
---

Bu kapsamlı eğitimde, Aspose.Words for .NET'i kullanarak bir Word belgesine yorum yanıtlarını nasıl ekleyip kaldıracağınızı öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda yorum yanıtlarını yönetebilecek ve bunları gereksinimlerinize göre özelleştirebileceksiniz.

## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kütüphanesi sisteminizde kuruludur.

## 1. Adım: Belgeyi Yükleyin
Başlamak için, yorumları içeren belgeyi Document sınıfını kullanarak yükleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 2. Adım: Yoruma Erişin ve Yanıtları Yönetin
Daha sonra, NodeType.Comment parametresiyle GetChild yöntemini kullanarak belgedeki açıklamaya erişin:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Yorumdan bir yanıtı kaldırmak için RemoveReply yöntemini kullanın ve istediğiniz yanıt dizinini sağlayın:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Yoruma yeni bir yanıt eklemek için AddReply yöntemini kullanın ve yazarın adını, yazarın adının baş harflerini, tarih ve saati ve yanıt metnini sağlayın:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 3. Adım: Belgeyi Kaydedin
Yorum yanıtlarını ekledikten veya kaldırdıktan sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Aspose.Words for .NET kullanarak Yorum Yanıtları Eklemek ve Kaldırmak için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yorum yanıtlarını eklemek ve kaldırmak için tam kaynak kodu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET'i kullanarak bir Word belgesine yorum yanıtlarını nasıl ekleyip kaldıracağınızı başarıyla öğrendiniz. Adım adım kılavuzu takip ederek ve sağlanan kaynak kodunu kullanarak artık yorum yanıtlarını yönetebilir ve bunları gereksinimlerinize göre özelleştirebilirsiniz.

Yorum yanıtları, bir belge içinde işbirlikçi tartışmalara ve geri bildirime olanak tanır. Belgelerinizde işbirliğini ve iletişimi geliştirmek için farklı yanıt yazarlarını, baş harflerini, tarihlerini ve metinlerini deneyin.

### SSS'ler

#### S: Aspose.Words for .NET'e nasıl yorum ekleyebilirim?

 C: Aspose.Words for .NET'e yorum eklemek için`Comment.AddComment` Yorumun metnini ve bunu belgede nereye eklemek istediğinizi belirten yöntem.

#### S: Aspose.Words for .NET'te bir yorumu nasıl kaldırabilirim?

 C: Aspose.Words for .NET'te bir yorumu kaldırmak için şu komutu kullanabilirsiniz:`Comment.Remove` belirten yöntem`Comment` Kaldırmak istediğiniz nesneyi seçin.

#### S: Aspose.Words for .NET'te bir yorumu yanıtlayabilir miyim?

 C: Evet, Aspose.Words for .NET'te bir yorumu aşağıdaki komutu kullanarak yanıtlayabilirsiniz:`Comment.AddReply` Yanıt metnini ve bunu belgede nereye eklemek istediğinizi belirten yöntem.

#### S: Aspose.Words for .NET'te mevcut yorumlara nasıl erişebilirim?

 C: Aspose.Words for .NET'teki mevcut yorumlara şu komutu kullanarak erişebilirsiniz:`CommentCollection` mülkiyeti`Document`nesne. Bu, belgede bulunan tüm yorumlara göz atmanıza olanak tanır.

#### S: Aspose.Words for .NET'te yorum metnini düzenleyebilir miyim?

 C: Evet, Aspose.Words for .NET'te bir yorumun metnini şu adrese erişerek düzenleyebilirsiniz:`Comment.Text` karşılık gelen mülk`Comment` nesneyi seçin ve metni gerektiği gibi değiştirin.