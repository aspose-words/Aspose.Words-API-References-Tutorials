---
title: Hedef Stillerini Kullan
linktitle: Hedef Stillerini Kullan
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak hedef belge stillerini uygularken Word belgelerini nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/use-destination-styles/
---

Bu eğitim, Aspose.Words for .NET'in Use Destination Styles özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, hedef belgenin stillerini uygularken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Kaynak Belgeyi Hedef Stillerle Ekleyin

 Hedef belgenin stillerini uygularken kaynak belgeyi hedef belgeye eklemek için`AppendDocument` yöntemi`Document` ile sınıf`ImportFormatMode.UseDestinationStyles` parametre.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 4. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Hedef Stillerini Kullan özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Aspose.Words for .NET kullanarak Use Destination Styles için örnek kaynak kodu

Aspose.Words for .NET kullanan C# dilinde "Hedef Stillerini Kullan" özelliğinin tam kaynak kodu burada:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hedef belgenin stillerini kullanarak kaynak belgeyi ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Use Destination Styles özelliğini başarıyla uyguladınız. Nihai belge, uygulanan hedef belge stilleriyle birleştirilmiş içeriği içerecektir.