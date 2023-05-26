---
title: Liste Saklama Kaynağı Biçimlendirmesi
linktitle: Liste Saklama Kaynağı Biçimlendirmesi
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken liste biçimlendirmesini nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/list-keep-source-formatting/
---

Bu eğitim, Aspose.Words for .NET'in List Keep Source Formatting özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, listelerin kaynak biçimlendirmesini korurken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Kaynak Belgeyi Sürekli Akışa Ayarlayın

 Kaynak belgedeki içeriğin hedef belgeye eklendiğinde sürekli olarak akmasını sağlamak için,`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting`parametresi, ekleme işlemi sırasında listelerin biçimlendirmesi de dahil olmak üzere kaynak biçimlendirmesinin korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Liste Saklama Kaynağı Biçimlendirme özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Aspose.Words for .NET kullanan List Keep Source Formatting için örnek kaynak kodu 

Aspose.Words for .NET kullanan C# dilinde List Keep Source Formatting özelliğinin tam kaynak kodu burada:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Sürekli akması için belgenin içeriğini ekleyin.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak List Keep Source Formatting özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgenin liste biçimlendirmesi korunarak birleştirilmiş içeriği içerecektir.