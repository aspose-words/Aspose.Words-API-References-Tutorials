---
title: Ekle Yorum Kaldır Yanıtla
linktitle: Ekle Yorum Kaldır Yanıtla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerine yorum yanıtlarını nasıl ekleyeceğinizi ve kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-comments/add-remove-comment-reply/
---

Bu kapsamlı eğitimde, Aspose.Words for .NET kullanarak bir Word belgesine yorum yanıtlarını nasıl ekleyeceğinizi ve kaldıracağınızı öğreneceksiniz. Süreç boyunca size rehberlik edeceğiz ve size gerekli C# kod parçacıklarını sağlayacağız. Bu kılavuzun sonunda, yorum yanıtlarını yönetebilecek ve gereksinimlerinize göre özelleştirebileceksiniz.

## Önkoşullar
Başlamadan önce, aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Aspose.Words for .NET kitaplığı sisteminizde yüklü.

## 1. Adım: Belgeyi Yükleyin
Başlamak için, açıklamaları içeren belgeyi Document sınıfını kullanarak yükleyin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## 2. Adım: Yoruma Erişin ve Yanıtları Yönetin
Ardından, NodeType.Comment parametresiyle GetChild yöntemini kullanarak belgeden yoruma erişin:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Yorumdan bir yanıtı kaldırmak için RemoveReply yöntemini kullanın ve istenen yanıt dizinini sağlayın:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Yoruma yeni bir yanıt eklemek için AddReply yöntemini kullanın ve yazar adını, yazarın baş harflerini, tarih ve saati ve yanıt metnini sağlayın:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## 3. Adım: Belgeyi Kaydedin
Yorum yanıtlarını ekledikten veya çıkardıktan sonra, Document sınıfının Save yöntemini kullanarak belgeyi bir dosyaya kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Aspose.Words for .NET kullanarak Yorum Yanıtları Ekleme ve Kaldırma için Örnek Kaynak Kodu
Aspose.Words for .NET kullanarak yorum yanıtları eklemek ve kaldırmak için eksiksiz kaynak kodu burada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Çözüm
Tebrikler! Aspose.Words for .NET kullanarak bir Word belgesine yorum yanıtlarını nasıl ekleyeceğinizi ve kaldıracağınızı başarıyla öğrendiniz. Adım adım kılavuzu izleyerek ve sağlanan kaynak kodu kullanarak, artık yorum yanıtlarını yönetebilir ve gereksinimlerinize göre özelleştirebilirsiniz.

Yorum yanıtları, bir belge içinde işbirlikçi tartışmalara ve geri bildirime izin verir. Belgelerinizde işbirliğini ve iletişimi geliştirmek için farklı yanıt yazarları, baş harfleri, tarihler ve metinlerle denemeler yapın.