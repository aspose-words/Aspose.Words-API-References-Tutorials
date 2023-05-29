---
title: İşaretleme Belgesini Oku
linktitle: İşaretleme Belgesini Oku
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET Adım adım kılavuz ile işaretleme belgesini nasıl okuyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-markdown/read-markdown-document/
---

Bu örnekte, bir Markdown belgesini Aspose.Words for .NET kullanarak nasıl okuyacağınızı göstereceğiz. Markdown, düz metni biçimlendirmek için kullanılan hafif bir biçimlendirme dilidir.

## 1. Adım: Markdown belgesini okuma

 İlk olarak, kullanacağız`Document` Markdown belgesini okumak için sınıf. Okunacak Markdown dosyasının yolunu belirtmemiz gerekiyor.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## 2. Adım: Başlık biçimlendirmesini kaldırın

Belgenin son paragrafındaki başlıktan biçimlendirmeyi kaldırabiliriz. Bu örnekte, paragrafa "Alıntı" stilini atıyoruz.

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## 3. Adım: Belgeyi kaydetme

Son olarak belgeyi istediğimiz formatta kaydedebiliriz.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### Aspose.Words for .NET ile bir Markdown belgesini okumak için örnek kaynak kodu


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");

// Son paragraftaki bir Alıntıdan Başlık biçimlendirmesini kaldıralım.
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

Tebrikler! Artık bir Markdown belgesini Aspose.Words for .NET ile nasıl okuyacağınızı öğrendiniz.

