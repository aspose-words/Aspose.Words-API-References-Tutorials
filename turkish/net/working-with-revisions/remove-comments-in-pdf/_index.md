---
title: Pdf'deki Yorumları Kaldır
linktitle: Pdf'deki Yorumları Kaldır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET ile bir PDF dosyasındaki yorumları kaldırın.
type: docs
weight: 10
url: /tr/net/working-with-revisions/remove-comments-in-pdf/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir PDF dosyasındaki yorumları nasıl kaldıracağınızı anlatacağız. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, yorumları içeren belgeyi yüklemektir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. Adım: PDF'deki yorumları gizleyin

PDF oluştururken yorumları gizlemek için düzen seçeneğini yapılandıracağız.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 3. Adım: Belgeyi PDF olarak kaydedin

Son olarak yorumları silerek belgeyi PDF formatında kaydedeceğiz.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown çıktı formatları

Çıktı, okunabilirliği artırmak için işaretlemede biçimlendirilebilir. Örneğin :

```markdown
- Comments are hidden in the generated PDF.
```

### Aspose.Words for .NET kullanarak Pdf'deki Yorumları Kaldır için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir PDF dosyasındaki yorumları kaldırmak için eksiksiz kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Revisions.docx");

	// PDF'deki yorumları gizleyin.
	doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

	doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");

```