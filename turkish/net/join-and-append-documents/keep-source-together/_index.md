---
title: Kaynağı Bir Arada Tutun
linktitle: Kaynağı Bir Arada Tutun
second_title: Aspose.Words for .NET API Referansı
description: Kaynak içeriği hedef belgeyle bir arada tutarken Word belgelerini birleştirmek ve eklemek için Aspose.Words for .NET'i nasıl kullanacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-together/
---

Bu eğitim, Aspose.Words for .NET'in Kaynağı Birlikte Tut özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgenin içeriğini hedef belgenin içeriğiyle bir arada tutarken birden çok Word belgesini birleştirip eklemenize olanak tanır. 

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kurulu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla kurabilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## 1. Adım: Belge Dizinlerini Başlatın

 Öncelikle, belge dizininize giden yolu ayarlamanız gerekir. değerini değiştir`dataDir` belgelerinizin bulunduğu yola değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak ve Hedef Belgeleri Yükleyin

 Ardından, Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. içindeki dosya adlarını güncelleyin.`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. Adım: Kaynak Belgeyi Hedef Belgenin İçeriğinden Sonra Görünecek Şekilde Ayarlayın

 Kaynak belgenin, hedef belgenin içeriğinden hemen sonra görünmesini sağlamak için,`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. Adım: Kaynak Belge için "Sonrakiyle Devam Et" Paragraf Biçimlendirmesini Ayarlayın

 Kaynak belgedeki paragrafları bir arada tutmak için belgedeki her paragrafı yineleyebilir ve`KeepWithNext` mülkiyet`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi "Kaynağı Bir Arada Tut" özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Aspose.Words for .NET kullanarak Keep Source Together için örnek kaynak kodu 

Aspose.Words for .NET kullanan C# dilindeki "Kaynağı Bir Arada Tut" özelliğinin tam kaynak kodu burada:


```csharp
	// Belge dizininizin yolu
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

Bu kadar! Aspose.Words for .NET'i kullanarak Keep Source Together özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgedeki paragrafların bir arada tutulduğu birleştirilmiş içeriği içerecektir.