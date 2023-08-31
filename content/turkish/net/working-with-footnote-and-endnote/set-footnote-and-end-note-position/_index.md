---
title: Dipnot ve Son Not Konumunu Ayarlama
linktitle: Dipnot ve Son Not Konumunu Ayarlama
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerinde dipnotların ve sonnotların konumunu nasıl ayarlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Bu adım adım eğitimde, bir Word belgesindeki dipnotların ve son notların konumunu ayarlamak için Aspose.Words for .NET'i nasıl kullanacağınız konusunda size rehberlik edeceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinizde nasıl uygulayacağınızı göstereceğiz.

 Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve kurulu olduğundan emin olun. Henüz yapmadıysanız, kitaplığı şuradan indirip yükleyin.[Aspose.Releases]https://releases.aspose.com/words/net/.

## Adım 1: Belge Nesnesini Başlatma

 İlk olarak, başlat`Document` kaynak belgenizin yolunu sağlayarak nesneyi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Adım 2: Dipnot ve Sonnot Konumunu Ayarlama

 Daha sonra şuraya erişin:`FootnoteOptions` Ve`EndnoteOptions` Dipnotların ve son notların konumunu ayarlamak için belgenin özellikleri. Bu örnekte dipnotların konumunu metnin altında, son notların konumunu ise bölümün sonunda olacak şekilde ayarladık:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Adım 3: Belgeyi Kaydetme

Son olarak değiştirilen belgeyi kaydedin:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak bir Word belgesindeki dipnotların ve sonnotların konumunu başarıyla ayarladınız.

### Aspose.Words for .NET kullanarak Dipnot ve Sonnot Konumunu Ayarlama için örnek kaynak kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Bu kodu kendi projelerinizde kullanmaktan ve özel gereksinimlerinize göre değiştirmekten çekinmeyin.

### SSS'ler

#### S: Aspose.Words'te dipnotları ve son notları nasıl konumlandırabilirim?

 C: Aspose.Words'te dipnotları ve son notları konumlandırmak için`FootnoteOptions` sınıf ve`Position` mülk. Bu özelliği istediğiniz herhangi bir değere ayarlayabilirsiniz.`BottomOfPage` (sayfanın altında) veya`EndOfSection`(bölümün sonunda).

#### S: Belgenin her sayfası veya bölümü için dipnotların ve son notların konumunu özelleştirmek mümkün müdür?

C: Evet, belgenin her sayfası veya bölümü için dipnotların ve son notların konumunu özelleştirmek mümkündür. Dipnotlar ve sonnotlar için belirli konumları tanımlamak amacıyla Aspose.Words bölüm ve sayfa işleme yöntemlerini kullanabilirsiniz.

#### S: Bir belgeden dipnotları veya son notları nasıl kaldırabilirim?

 C: Aspose.Words'te bir belgeden dipnotları veya son notları kaldırmak için aşağıdakiler gibi uygun yöntemleri kullanabilirsiniz:`RemoveAllFootnotes` tüm dipnotları kaldırmak için veya`RemoveAllEndnotes` tüm son notları kaldırmak için. Bu işlemleri yaptıktan sonra belgeyi kaydettiğinizden emin olun.

#### S: Dipnotlar ve son notlar sayfa kenar boşluklarının dışına yerleştirilebilir mi?

Hayır, varsayılan olarak dipnotlar ve son notlar Aspose.Words'de sayfa kenar boşluklarının dışına yerleştirilemez. Ancak gerekirse dipnotlara ve son notlara daha fazla alan sağlamak için belgenin kenar boşluklarını ayarlayabilirsiniz.

#### S: Dipnotlar ve son notlar belirli yazı tipi veya biçimlendirme stilleriyle özelleştirilebilir mi?

C: Evet, Aspose.Words'te dipnotları ve son notları belirli yazı tipi veya formatlama stilleriyle özelleştirebilirsiniz. Yazı tipi stilleri, renkleri, yazı tipi boyutları vb. dipnotları ve son notları uygulamak için mevcut yöntemleri ve özellikleri kullanabilirsiniz.