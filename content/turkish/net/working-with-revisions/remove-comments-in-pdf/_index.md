---
title: Pdf Dosyasındaki Yorumları Kaldır
linktitle: Pdf Dosyasındaki Yorumları Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile PDF dosyasındaki yorumları kaldırın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/remove-comments-in-pdf/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir PDF dosyasındaki yorumları nasıl kaldıracağınızı anlatacağız. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, yorumları içeren belgeyi yüklemektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: PDF'deki yorumları gizleyin

PDF'yi oluştururken yorumları gizlemek için düzen seçeneğini yapılandıracağız.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 3. Adım: Belgeyi PDF olarak kaydedin

Son olarak yorumları silerek belgeyi PDF formatında kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown çıktı formatları

Çıktı, okunabilirliği artırmak için işaretleme biçiminde biçimlendirilebilir. Örneğin :

```markdown
- Comments are hidden in the generated PDF.
```

### Aspose.Words for .NET kullanarak PDF'teki Yorumları Kaldırmak için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir PDF dosyasındaki yorumları kaldırmak için gereken kaynak kodun tamamı burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// PDF'deki yorumları gizleyin.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Çözüm

Bu eğitimde Aspose.Words for .NET kullanarak bir PDF dosyasındaki yorumları nasıl kaldıracağımızı öğrendik. Uygun düzen seçeneklerini kullanarak PDF'yi oluştururken yorumları gizlemeyi başardık. Aspose.Words for .NET, Word dosyalarını işlemek ve bunları PDF dahil farklı formatlara dönüştürmek için büyük esneklik sunar. Aspose.Words for .NET'i kullanarak artık bu bilgiyi kendi PDF dosyalarınızdaki yorumları kaldırmak için uygulayabilirsiniz.

### PDF dosyasındaki yorumları kaldırmak için SSS

#### S: Aspose.Words for .NET'e belge nasıl yüklenir?

 C: Kullan`Document` Bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirtebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET ile oluşturulan PDF'lerdeki yorumlar nasıl gizlenir?

 C: Kullan`CommentDisplayMode` mülkiyeti`LayoutOptions` PDF oluşturulurken yorumların nasıl görüntüleneceğini yapılandırmak için nesne. Yorumları gizlemek için bu özelliği şu şekilde ayarlayın:`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### S: Aspose.Words for .NET ile belgeyi PDF olarak nasıl kaydedebilirim?

 C: Kullan`Save` yöntemi`Document` Belgeyi PDF formatında kaydetmek için nesne. PDF dosyasının tam yolunu belirtin.

```csharp
doc.Save("path/to/the/file.pdf");
```