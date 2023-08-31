---
title: Sayfa Numaralandırmayı Yeniden Başlat
linktitle: Sayfa Numaralandırmayı Yeniden Başlat
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken sayfa numaralandırmayı nasıl yeniden başlatacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/restart-page-numbering/
---

Bu eğitim, Aspose.Words for .NET'in Sayfa Numaralandırmayı Yeniden Başlat özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgede sayfa numaralandırmayı yeniden başlatırken Word belgelerini birleştirip eklemenize olanak tanır.

## Önkoşullar

Başlamadan önce, aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kurulu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla kurabilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## 1. Adım: Belge Dizinlerini Başlatın

 Öncelikle, belge dizininize giden yolu ayarlamanız gerekir. değerini değiştir`dataDir`belgelerinizin bulunduğu yola değişken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. Adım: Kaynak ve Hedef Belgeleri Yükleyin

 Ardından, Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. içindeki dosya adlarını güncelleyin.`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak Belgeyi Sayfa Numaralandırmayı Yeniden Başlatacak Şekilde Ayarlayın

 Kaynak belgede sayfa numaralandırmayı yeniden başlatmak için,`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.NewPage` ve ayarla`RestartPageNumbering` mülkiyet`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Sayfa Numaralandırmayı Yeniden Başlat özelliği etkinleştirilerek kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Aspose.Words for .NET kullanarak Sayfa Numaralandırmayı Yeniden Başlatmak için örnek kaynak kodu

Aspose.Words for .NET kullanılarak C#'ta "Sayfa Numaralandırmayı Yeniden Başlat" özelliğinin tam kaynak kodu burada:
 

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