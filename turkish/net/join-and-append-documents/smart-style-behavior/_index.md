---
title: Akıllı Stil Davranışı
linktitle: Akıllı Stil Davranışı
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken akıllı stil davranışını nasıl sürdüreceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/smart-style-behavior/
---

Bu eğitim, Aspose.Words for .NET'in Akıllı Stil Davranışı özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, akıllı stil davranışını korurken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Hedef Belgeye Sayfa Sonu Ekleyin

 Eklenen içeriğin hedef belgede yeni bir sayfada görünmesini sağlamak için bir sayfa sonu ekleyebilirsiniz.`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 4. Adım: Akıllı Stil Davranış Seçeneklerini Ayarlayın

Ekleme işlemi sırasında akıllı stil davranışını etkinleştirmek için bir örnek oluşturmanız gerekir.`ImportFormatOptions` ve ayarla`SmartStyleBehavior` mülkiyet`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`InsertDocument` yöntemi`DocumentBuilder` sınıf. Kullan`ImportFormatMode.UseDestinationStyles` parametre ve geçmek`ImportFormatOptions` akıllı stil davranışını sürdürmek için nesne.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 6. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Akıllı Stil Davranışı özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Aspose.Words for .NET kullanan Smart Style Behavior için örnek kaynak kodu

Aspose.Words for .NET kullanan C# dilinde "Akıllı Stil Davranışı" özelliğinin tam kaynak kodu burada:
 
```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Smart Style Behavior özelliğini başarıyla uyguladınız. Nihai belge, korunan akıllı stil davranışıyla birleştirilmiş içeriği içerecektir.