---
title: Kaynak biçimlendirmesini koruyun
linktitle: Kaynak biçimlendirmesini koruyun
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak orijinal formatı koruyarak kaynak belgeyi hedef belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-formatting/
---

Bu eğitimde Aspose.Words for .NET kullanılarak kaynak belgenin orijinal formatı korunarak bir kaynak belgenin hedef belgeye nasıl ekleneceği gösterilmektedir.

## 1. Adım: Projeyi ayarlayın

Aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

-  Aspose.Words for .NET kütüphanesi kuruldu. Şuradan indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ adresine gidin veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin kaydedileceği belge dizini yolu.

## 2. Adım: Hedef ve kaynak belgeleri oluşturun

 Örneklerini oluştur`Document` Hedef ve kaynak belgeler için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 3. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument` Kaynak belgenin ekleneceği hedef belgenin yöntemi. Geçmek`ImportFormatMode.KeepSourceFormatting`Kaynak belgenin orijinal formatını korumak için içe aktarma formatı modu olarak.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 4. Adım: Değiştirilen belgeyi kaydedin

 Değiştirilen belgeyi kullanarak kaydedin.`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Bu, Aspose.Words for .NET kullanarak orijinal formatı korurken, kaynak belgenin hedef belgeye eklenmesi uygulamasını tamamlıyor.

### Aspose.Words for .NET kullanarak Kaynak Formatını Koru için örnek kaynak kodu 

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Kaynak belgeyi hedef belgeye ekleyin.
	// Kaynak belgeyi içe aktarırken orijinal biçimlendirmesini korumak için biçimlendirme moduna geçin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```