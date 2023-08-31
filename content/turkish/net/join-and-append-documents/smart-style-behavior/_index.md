---
title: Akıllı Stil Davranışı
linktitle: Akıllı Stil Davranışı
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken akıllı stil davranışını nasıl koruyacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/smart-style-behavior/
---

Bu eğitim, Aspose.Words for .NET'in Akıllı Stil Davranışı özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, akıllı stil davranışını korurken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Hedef Belgeye Sayfa Sonu Ekleme

 Eklenen içeriğin hedef belgede yeni bir sayfada görünmesini sağlamak için, bir sayfa sonu ekleyebilirsiniz.`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 4. Adım: Akıllı Stil Davranışı Seçeneklerini Ayarlayın

 Ekleme işlemi sırasında akıllı stil davranışını etkinleştirmek için bir örnek oluşturmanız gerekir:`ImportFormatOptions` ve ayarlayın`SmartStyleBehavior` mülkiyet`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`InsertDocument` yöntemi`DocumentBuilder` sınıf. Kullan`ImportFormatMode.UseDestinationStyles` parametreyi girin ve iletin`ImportFormatOptions` Akıllı stil davranışını sürdürmek için nesne.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Adım 6: Son Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Akıllı Stil Davranışı özelliği etkinleştirilmiş olarak`Save` yöntemi`Document` sınıf.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Aspose.Words for .NET kullanan Smart Style Behavior için örnek kaynak kodu

Aspose.Words for .NET kullanan C#'taki "Akıllı Stil Davranışı" özelliğinin tam kaynak kodu:
 
```csharp
	//Belge dizininizin yolu
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

Bu kadar! Aspose.Words for .NET'i kullanarak Smart Style Behavior özelliğini başarıyla uyguladınız. Nihai belge, akıllı stil davranışı korunan birleştirilmiş içeriği içerecektir.