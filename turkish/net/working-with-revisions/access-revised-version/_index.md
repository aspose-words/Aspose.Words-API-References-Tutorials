---
title: Gözden Geçirilmiş Sürüme Erişim
linktitle: Gözden Geçirilmiş Sürüme Erişim
second_title: Aspose.Words for .NET API Referansı
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


