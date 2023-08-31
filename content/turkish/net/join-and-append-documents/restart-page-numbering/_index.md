---
title: Sayfa Numaralandırmayı Yeniden Başlat
linktitle: Sayfa Numaralandırmayı Yeniden Başlat
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken sayfa numaralandırmayı nasıl yeniden başlatacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/restart-page-numbering/
---

Bu eğitim Aspose.Words for .NET'in Sayfa Numaralandırmayı Yeniden Başlat özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgedeki sayfa numaralandırmayı yeniden başlatırken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Adım 3: Kaynak Belgeyi Sayfa Numaralandırmayı Yeniden Başlatacak Şekilde Ayarlayın

 Kaynak belgede sayfa numaralandırmayı yeniden başlatmak için`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.NewPage` ve ayarlayın`RestartPageNumbering` mülkiyet`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 5: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Sayfa Numaralandırmayı Yeniden Başlat özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Aspose.Words for .NET kullanarak Sayfa Numaralandırmayı Yeniden Başlatmak için örnek kaynak kodu

Aspose.Words for .NET kullanarak C#'taki "Sayfa Numaralandırmayı Yeniden Başlat" özelliğinin tam kaynak kodu:
 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Sayfa Numaralandırmayı Yeniden Başlat özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgede yeniden başlatılan sayfa numaralandırmasıyla birleştirilmiş içeriği içerecektir.