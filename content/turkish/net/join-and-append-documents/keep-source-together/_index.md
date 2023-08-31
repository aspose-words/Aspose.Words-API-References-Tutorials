---
title: Kaynağı Bir Arada Tutun
linktitle: Kaynağı Bir Arada Tutun
second_title: Aspose.Words Belge İşleme API'si
description: Kaynak içeriği hedef belgeyle bir arada tutarken Word belgelerini birleştirmek ve eklemek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-together/
---

Bu eğitim Aspose.Words for .NET'in Kaynağı Birlikte Tut özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgenin içeriğini hedef belgenin içeriğiyle bir arada tutarken birden çok Word belgesini birleştirmenize ve eklemenize olanak tanır. 

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kuruldu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla yükleyebilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## Adım 1: Belge Dizinlerini Başlatın

 Öncelikle belge dizininizin yolunu ayarlamanız gerekir. Değerini değiştirin`dataDir`belgelerinizin bulunduğu yola göre değişkendir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak ve Hedef Belgelerini Yükleyin

 Daha sonra Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. Dosya adlarını güncelleyin`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Adım 3: Kaynak Belgeyi, Hedef Belgenin İçeriğinden Sonra Görünecek Şekilde Ayarlayın

 Kaynak belgenin, hedef belgenin içeriğinden hemen sonra görüntülenmesini sağlamak için,`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Adım 4: Kaynak Belge için "Sonrakiyle Tut" Paragraf Biçimlendirmesini Ayarlayın

 Kaynak belgedeki paragrafları bir arada tutmak için belgedeki her paragrafta yinelenebilir ve`KeepWithNext` mülkiyet`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 6: Son Belgeyi Kaydedin

Son olarak, birleştirilmiş belgeyi "Kaynağı Bir Arada Tut" özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Aspose.Words for .NET kullanarak Keep Source Together için örnek kaynak kodu 

Aspose.Words for .NET kullanan C#'taki "Kaynağı Bir Arada Tut" özelliğinin tam kaynak kodu:


```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Kaynak belgeyi, hedef belgenin içeriğinden hemen sonra görünecek şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Kaynağı Bir Arada Tut özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgedeki paragrafların bir arada tutulduğu birleştirilmiş içeriği içerecektir.