---
title: Builder ile Belge Ekle
linktitle: Builder ile Belge Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak başka bir belgenin sonuna nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/insert-document-with-builder/
---

 Bu eğitim, Aspose.Words for .NET'i kullanarak başka bir belgeye belge eklemek için nasıl kullanılacağını açıklar.`DocumentBuilder` sınıf. Sağlanan kaynak kodu, kaynak biçimlendirmesini koruyarak başka bir belgenin sonuna bir belgenin nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. Resmi Aspose web sitesinden indirebilir veya yüklemek için NuGet paket yöneticisini kullanabilirsiniz.
- Kaynak ve hedef belgelerin bulunduğu bir belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 kullanarak kaynak ve hedef belgeleri açın.`Document` sınıf oluşturucu Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: DocumentBuilder'ı Başlatın

 Yeni bir örneğini oluştur`DocumentBuilder` sınıflandırın ve hedef belgeyi bir parametre olarak iletin.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Adım 4: DocumentBuilder'ı Konumlandırın

 Taşı`DocumentBuilder` kullanarak belgenin sonuna`MoveToDocumentEnd` yöntem. Mevcut içeriği eklenen belgeden ayırmak için bir sayfa sonu ekleyin.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 5. Adım: Kaynak belgeyi ekleyin

 Kullan`InsertDocument` yöntemi`DocumentBuilder` kaynak belgeyi hedef belgeye eklemek için sınıf. İçe aktarma formatı modunu şu şekilde ayarlayın:`ImportFormatMode.KeepSourceFormatting` kaynak biçimlendirmesini korumak için.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. Adım: Değiştirilen belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Bu, Aspose.Words for .NET kullanılarak başka bir belgeye belge ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Document With Builder için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```