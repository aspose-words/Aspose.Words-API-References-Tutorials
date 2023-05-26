---
title: Basit Belge Ekleme
linktitle: Basit Belge Ekleme
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini korunmuş biçimlendirmeyle nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/simple-append-document/
---

Bu eğitim, Aspose.Words for .NET'in Basit Belge Ekle özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, hiçbir ek seçenek olmadan Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 4. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Basit Belge Ekle özelliğiyle kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Aspose.Words for .NET kullanan Simple Append Document için örnek kaynak kodu

Aspose.Words for .NET kullanan C# dilinde "Basit Belge Ekleme" özelliğinin tam kaynak kodu burada:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hiçbir ekstra seçenek kullanmadan kaynak belgeyi hedef belgeye ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Basit Belge Ekle özelliğini başarıyla uyguladınız. Nihai belge, kaynak biçimlendirmesi korunarak birleştirilmiş içeriği içerecektir.