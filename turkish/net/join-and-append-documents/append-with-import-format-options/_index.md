---
title: İçe Aktarma Biçimi Seçenekleriyle Ekle
linktitle: İçe Aktarma Biçimi Seçenekleriyle Ekle
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak içe aktarma formatı seçenekleriyle bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/append-with-import-format-options/
---

Bu öğretici, içe aktarma biçimi seçenekleriyle bir belgenin içeriğini diğerine eklemek için Aspose.Words for .NET'in nasıl kullanılacağını açıklar. Sağlanan kaynak kodu, kaynak ve hedef belgelerin nasıl açılacağını, içe aktarma biçimi seçeneklerinin nasıl belirleneceğini ve kaynak belgenin hedef belgeye nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. adresinden indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu bir belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 kullanarak kaynak ve hedef belgeleri açın.`Document` sınıf oluşturucu Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. Adım: İçe aktarma biçimi seçeneklerini belirtin

 örneğini oluşturun`ImportFormatOptions` içe aktarma biçimi seçeneklerini belirtmek için sınıf. Bu örnekte,`KeepSourceNumbering` özelliği, hedef belgeyle çakışma olması durumunda kaynak belgedeki numaralandırmanın kullanılmasını sağlar.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 4. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument`kaynak belgeyi eklemek için hedef belgenin yöntemi. Geçmek`ImportFormatMode.UseDestinationStyles` hedef belgenin stillerini ve biçimlendirmesini kullanmak için ikinci parametre olarak.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Bu, Aspose.Words for .NET kullanılarak içe aktarma biçimi seçenekleriyle bir belgeye ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanan Append With Import Format Options için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Kaynak ve hedef belgelerde numaralandırma çakışırsa,
	// daha sonra kaynak belgeden numaralandırma kullanılacaktır.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```