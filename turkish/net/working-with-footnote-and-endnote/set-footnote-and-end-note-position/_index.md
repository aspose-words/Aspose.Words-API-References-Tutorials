---
title: Dipnot ve Son Not Konumunu Ayarla
linktitle: Dipnot ve Son Not Konumunu Ayarla
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerinde dipnotların ve son notların konumunu nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Bu adım adım öğreticide, bir Word belgesindeki dipnotların ve son notların konumunu ayarlamak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve ayarlanmış olduğundan emin olun. Henüz yapmadıysanız, kitaplığı resmi web sitesinden indirip yükleyin.

## 1. Adım: Belge Nesnesini Başlatma

 İlk olarak,`Document` kaynak belgenizin yolunu sağlayarak itiraz edin:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Adım 2: Dipnot ve Son Not Konumunu Ayarlama

 Ardından, şuraya erişin:`FootnoteOptions` Ve`EndnoteOptions`Dipnotların ve son notların konumunu ayarlamak için belgenin özellikleri. Bu örnekte, dipnotların konumunu metnin altında ve son notların konumunu bölümün sonunda olacak şekilde ayarladık:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## 3. Adım: Belgeyi Kaydetme

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Bu kadar! Aspose.Words for .NET kullanarak bir Word belgesindeki dipnotların ve son notların konumunu başarıyla ayarladınız.

### Aspose.Words for .NET kullanarak Dipnot ve Sonnot Konumunu Ayarlamak için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Bu kodu kendi projelerinizde kullanmaktan çekinmeyin ve özel gereksinimlerinize göre değiştirin.
