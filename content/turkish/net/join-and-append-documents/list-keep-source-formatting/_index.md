---
title: Liste Kaynak Formatını Koru
linktitle: Liste Kaynak Formatını Koru
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken liste formatını nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/list-keep-source-formatting/
---

Bu eğitim, Aspose.Words for .NET'in Kaynak Biçimlendirmesini Listele özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, listelerin kaynak formatını korurken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kuruldu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla yükleyebilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## Adım 1: Belge Dizinlerini Başlatın

 Öncelikle belge dizininizin yolunu ayarlamanız gerekir. Değerini değiştirin`dataDir` belgelerinizin bulunduğu yola göre değişkendir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak ve Hedef Belgelerini Yükleyin

 Daha sonra Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. Dosya adlarını güncelleyin`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Adım 3: Kaynak Belgeyi Sürekli Akışa Ayarlayın

 Kaynak belgedeki içeriğin hedef belgeye eklendiğinde sürekli olarak akmasını sağlamak için`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting`parametresi, ekleme işlemi sırasında listelerin formatı da dahil olmak üzere kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 5: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Kaynak Biçimlendirmesini Listele özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Aspose.Words for .NET kullanılarak Liste Saklama Kaynak Formatlaması için örnek kaynak kodu 

Aspose.Words for .NET kullanan C#'taki Kaynak Biçimlendirmeyi Listele özelliğinin tam kaynak kodu:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Belgenin içeriğini sürekli akacak şekilde ekleyin.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Listeyi Koru Kaynak Formatlama özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgenin liste formatı korunarak birleştirilmiş içeriği içerecektir.