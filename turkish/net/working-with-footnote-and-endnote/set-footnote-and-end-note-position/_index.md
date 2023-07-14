---
title: Dipnot ve Son Not Konumunu Ayarla
linktitle: Dipnot ve Son Not Konumunu Ayarla
second_title: Aspose.Words Belge İşleme API'sı
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

 Ardından, şuraya erişin:`FootnoteOptions` Ve`EndnoteOptions` Dipnotların ve son notların konumunu ayarlamak için belgenin özellikleri. Bu örnekte, dipnotların konumunu metnin altında ve son notların konumunu bölümün sonunda olacak şekilde ayarladık:

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

### SSS

#### S: Aspose.Words'te dipnotları ve son notları nasıl konumlandırabilirim?

 A: Aspose.Words'te dipnotları ve son notları konumlandırmak için`FootnoteOptions` sınıf ve`Position` mülk. Bu özelliği istediğiniz herhangi bir değere ayarlayabilirsiniz, örneğin`BottomOfPage` (sayfanın altında) veya`EndOfSection`(bölümün sonunda).

#### S: Belgenin her sayfası veya bölümü için dipnotların ve son notların konumunu özelleştirmek mümkün müdür?

C: Evet, belgenin her sayfası veya bölümü için dipnotların ve son notların konumunu özelleştirmek mümkündür. Dipnotlar ve son notlar için belirli konumları tanımlamak için Aspose.Words bölüm ve sayfa işleme yöntemlerini kullanabilirsiniz.

#### S: Bir belgeden dipnotları veya son notları nasıl kaldırırım?

 C: Aspose.Words'te bir belgeden dipnotları veya son notları kaldırmak için aşağıdakiler gibi uygun yöntemleri kullanabilirsiniz:`RemoveAllFootnotes` tüm dipnotları kaldırmak için veya`RemoveAllEndnotes` tüm son notları kaldırmak için. Bu işlemleri yaptıktan sonra belgeyi kaydettiğinizden emin olun.

#### S: Dipnotlar ve son notlar sayfa kenar boşluklarının dışına yerleştirilebilir mi?

Hayır, varsayılan olarak dipnotlar ve son notlar Aspose.Words'te sayfa kenar boşluklarının dışına yerleştirilemez. Ancak, gerekirse dipnotlar ve son notlar için daha fazla alan sağlamak üzere belge kenar boşluklarını ayarlayabilirsiniz.

#### S: Dipnotlar ve son notlar belirli yazı tipi veya biçimlendirme stilleriyle özelleştirilebilir mi?

C: Evet, Aspose.Words'ta dipnotları ve son notları belirli yazı tipi veya biçimlendirme stilleriyle özelleştirebilirsiniz. Yazı tipi stilleri, renkleri, yazı tipi boyutları vb. Dipnotları ve son notları uygulamak için mevcut yöntemleri ve özellikleri kullanabilirsiniz.