---
title: Oluşturucuyla Belge Ekle
linktitle: Oluşturucuyla Belge Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak bir belgeyi başka bir belgenin sonuna nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/insert-document-with-builder/
---

 Bu eğitimde Aspose.Words for .NET kullanılarak bir belgenin başka bir belgeye nasıl ekleneceği açıklanmaktadır.`DocumentBuilder` sınıf. Sağlanan kaynak kodu, kaynak formatını korurken bir belgenin başka bir belgenin sonuna nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 Kaynak ve hedef belgeleri kullanarak açın.`Document` sınıf yapıcısı. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: DocumentBuilder'ı başlatın

 Yeni bir örneğini oluşturun`DocumentBuilder` sınıfa girin ve hedef belgeyi parametre olarak iletin.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Adım 4: DocumentBuilder'ı konumlandırın

Taşı`DocumentBuilder` kullanarak belgenin sonuna kadar`MoveToDocumentEnd` yöntem. Mevcut içeriği eklenen belgeden ayırmak için sayfa sonu ekleyin.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 5. Adım: Kaynak belgeyi ekleyin

 Kullan`InsertDocument` yöntemi`DocumentBuilder` Kaynak belgeyi hedef belgeye eklemek için sınıf. İçe aktarma formatı modunu şu şekilde ayarlayın:`ImportFormatMode.KeepSourceFormatting` kaynak biçimlendirmesini korumak için.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 6: Değiştirilen belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Bu, Aspose.Words for .NET kullanarak bir belgenin başka bir belgeye eklenmesi işlemini tamamlar.

### Aspose.Words for .NET kullanarak Insert Document With Builder için örnek kaynak kodu 

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