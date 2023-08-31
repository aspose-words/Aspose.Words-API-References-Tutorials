---
title: Basit Belge Ekleme
linktitle: Basit Belge Ekleme
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini korunmuş formatla nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/simple-append-document/
---

Bu eğitim, Aspose.Words for .NET'in Basit Belge Ekleme özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, Word belgelerini ek seçenek olmadan birleştirmenize ve eklemenize olanak tanır.

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

## Adım 3: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 4: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Basit Belge Ekle özelliğiyle kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Aspose.Words for .NET kullanan Basit Ekleme Belgesi için örnek kaynak kodu

Aspose.Words for .NET kullanarak C#'taki "Basit Belge Ekleme" özelliğinin tam kaynak kodu:

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hiçbir ekstra seçenek kullanmadan kaynak belgeyi hedef belgeye ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Basit Belge Ekleme özelliğini başarıyla uyguladınız. Nihai belge, kaynak formatı korunarak birleştirilmiş içeriği içerecektir.