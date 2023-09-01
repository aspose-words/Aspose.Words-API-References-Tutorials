---
title: İçe Aktarma Formatı Seçenekleri ile Ekle
linktitle: İçe Aktarma Formatı Seçenekleri ile Ekle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak içe aktarma formatı seçenekleriyle bir belgeyi nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/append-with-import-format-options/
---

Bu eğitimde Aspose.Words for .NET'in, içe aktarma formatı seçenekleriyle bir belgenin içeriğini diğerine eklemek için nasıl kullanılacağı açıklanmaktadır. Sağlanan kaynak kodu, kaynak ve hedef belgelerin nasıl açılacağını, içe aktarma formatı seçeneklerinin nasıl belirleneceğini ve kaynak belgenin hedef belgeye nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin bulunduğu belge dizini yolu.

## 2. Adım: Kaynak ve hedef belgeleri açın

 Kaynak ve hedef belgeleri kullanarak açın.`Document` sınıf yapıcısı. Yer değiştirmek`"YOUR DOCUMENT DIRECTORY"` belge dizininizin gerçek yolu ile.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. Adım: İçe aktarma biçimi seçeneklerini belirtin

 Bir örneğini oluşturun`ImportFormatOptions` İçe aktarma biçimi seçeneklerini belirtmek için sınıf. Bu örnekte, şunu kullanıyoruz:`KeepSourceNumbering` Hedef belgeyle çakışmalar olması durumunda kaynak belgedeki numaralandırmanın kullanılmasını sağlayan özellik.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## 4. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument` Kaynak belgenin ekleneceği hedef belgenin yöntemi. Geçmek`ImportFormatMode.UseDestinationStyles` Hedef belgenin stillerini ve biçimlendirmesini kullanmak için ikinci parametre olarak.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 5. Adım: Hedef belgeyi kaydedin

 Son olarak, değiştirilen hedef belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Bu, Aspose.Words for .NET kullanarak içe aktarma formatı seçenekleriyle bir belgenin eklenmesi uygulamasını tamamlar.

### Aspose.Words for .NET kullanan İçe Aktarma Formatı Seçenekleriyle Ekleme için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Kaynak ve hedef belgelerdeki numaralandırmanın çakışması durumunda,
	// daha sonra kaynak belgedeki numaralandırma kullanılacaktır.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```