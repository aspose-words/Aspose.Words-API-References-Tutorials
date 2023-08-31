---
title: Gözden Geçirilmiş Sürüme Erişim
linktitle: Gözden Geçirilmiş Sürüme Erişim
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesinin gözden geçirilmiş versiyonuna erişin.
type: docs
weight: 10
url: /tr/net/working-with-revisions/access-revised-version/
---

Bu adım adım kılavuzda, size Aspose.Words for .NET kullanarak bir Word belgesinin revize edilmiş versiyonuna nasıl erişeceğinizi göstereceğiz. Size tam kaynak kodunu sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

## 1. Adım: Belgeyi yükleme

İlk adım, revizyonları içeren belgeyi yüklemektir.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## 2. Adım: Gözden geçirilmiş sürüme erişin

Şimdi belgenin revize edilmiş versiyonuna geçeceğiz.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## 3. Adım: Düzeltmelere göz atın

Ardından, belgede bulunan revizyonları gözden geçireceğiz ve liste öğeleri olan paragraflar için belirli bilgileri göstereceğiz.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Aspose.Words for .NET kullanan Revize Edilmiş Sürüme Erişim için örnek kaynak kodu

Aspose.Words for .NET kullanan bir belgenin gözden geçirilmiş versiyonuna erişmek için eksiksiz kaynak kodu burada:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Belgenin gözden geçirilmiş sürümüne geçin.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Çözüm

Bu eğitimde, Aspose.Words for .NET kullanarak bir Word belgesinin revize edilmiş versiyonuna nasıl erişeceğimizi öğrendik. Belgeyi yükleyerek, gözden geçirilmiş sürüme giderek ve düzeltmelere göz atarak, liste öğeleri olan paragraflar için belirli bilgiler elde edebildik. Aspose.Words for .NET, incelemelere erişim de dahil olmak üzere Word belgelerini işlemek için güçlü özellikler sunar. Artık bu bilgiyi Aspose.Words for .NET kullanarak kendi Word belgelerinizin revize edilmiş versiyonuna erişmek için kullanabilirsiniz.

### SSS

#### S: Revizyonlu bir belgeyi Aspose.Words for .NET'e nasıl yüklerim?

 C: Şunu kullanın:`Document`revizyonlar içeren bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirleyebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir belgenin revize edilmiş versiyonuna nasıl erişebilirim?

 C: Şunu kullanın:`RevisionsView` mülkiyeti`Document` Belgenin revize edilmiş versiyonuna erişmek için itiraz edin. değerini ayarlayabilirsiniz.`RevisionsView` mülkiyet`RevisionsView.Final` revizyonlar olmadan son versiyonu göstermek için.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### S: Aspose.Words for .NET'te belge revizyonlarına nasıl göz atabilirim?

 C: Bir kullanın`foreach` belgede bulunan revizyonları yinelemek için döngü. kullanabilirsiniz`Revisions` mülkiyeti`Document` belgenin tüm revizyonlarının bir koleksiyonunu almak için nesne.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Her revizyonu burada işleyin
}
```

#### S: Aspose.Words for .NET'te bir paragrafın bir liste öğesi olup olmadığı nasıl kontrol edilir?

 C: Şunu kullanın:`IsListItem` mülkiyeti`Paragraph` paragrafın bir liste öğesi olup olmadığını kontrol etmek için nesne. bu`IsListItem` mülkiyet iadeleri`true` paragraf bir liste öğesiyse, aksi halde döndürür`false`.

```csharp
if (paragraph.IsListItem)
{
     // Paragraf bir liste öğesidir
}
else
{
     // Paragraf bir liste öğesi değil
}
```