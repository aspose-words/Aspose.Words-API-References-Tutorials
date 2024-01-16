---
title: Revize Edilmiş Sürüme Erişim
linktitle: Revize Edilmiş Sürüme Erişim
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET ile bir Word belgesinin gözden geçirilmiş versiyonuna erişin.
type: docs
weight: 10
url: /tr/net/working-with-revisions/access-revised-version/
---

Bu adım adım kılavuzda, Aspose.Words for .NET kullanarak bir Word belgesinin revize edilmiş sürümüne nasıl erişeceğinizi göstereceğiz. Size kaynak kodunun tamamını sağlayacağız ve işaretleme çıktısını nasıl biçimlendireceğinizi göstereceğiz.

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

Daha sonra, belgede bulunan düzeltmeler arasında geçiş yapacağız ve liste öğesi olan paragraflara ilişkin belirli bilgileri görüntüleyeceğiz.

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

### Aspose.Words for .NET kullanılarak Revize Edilmiş Sürüme Erişim için örnek kaynak kodu

Aspose.Words for .NET kullanarak bir belgenin revize edilmiş versiyonuna erişmek için tam kaynak kodu:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Belgenin revize edilmiş sürümüne geçin.
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

Bu eğitimde Aspose.Words for .NET kullanarak bir Word belgesinin revize edilmiş versiyonuna nasıl erişeceğimizi öğrendik. Belgeyi yükleyerek, revize edilmiş sürüme giderek ve revizyonlara göz atarak, liste öğesi olan paragraflara ilişkin özel bilgiler elde edebildik. Aspose.Words for .NET, incelemelere erişim de dahil olmak üzere Word belgelerini yönetmek için güçlü özellikler sunar. Artık bu bilgiyi Aspose.Words for .NET kullanarak kendi Word belgelerinizin revize edilmiş versiyonuna erişmek için kullanabilirsiniz.

### SSS'ler

#### S: Revizyonları olan bir belgeyi Aspose.Words for .NET'e nasıl yüklerim?

 C: Kullan`Document`Revizyonları içeren bir dosyadan belge yüklemek için Aspose.Words for .NET sınıfı. Tam belge yolunu belirtebilirsiniz.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### S: Aspose.Words for .NET'te bir belgenin revize edilmiş versiyonuna nasıl erişebilirim?

 C: Kullan`RevisionsView` mülkiyeti`Document` belgenin revize edilmiş sürümüne erişme nesnesi. Değerini ayarlayabilirsiniz`RevisionsView`mülkiyet`RevisionsView.Final` revizyonlar olmadan son sürümü göstermek için.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### S: Aspose.Words for .NET'te belge revizyonlarına nasıl göz atabilirim?

 C: Bir`foreach` Belgede mevcut revizyonlar arasında yineleme yapmak için döngü. Şunu kullanabilirsiniz:`Revisions` mülkiyeti`Document` Belgenin tüm revizyonlarının bir koleksiyonunu almak için itiraz edin.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Her revizyonu burada işleyin
}
```

#### S: Aspose.Words for .NET'te bir paragrafın liste öğesi olup olmadığı nasıl kontrol edilir?

 C: Kullan`IsListItem` mülkiyeti`Paragraph` Bir paragrafın bir liste öğesi olup olmadığını kontrol etmek için nesne.`IsListItem` mülk iadeleri`true` paragraf bir liste öğesi ise, aksi halde şunu döndürür:`false`.

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