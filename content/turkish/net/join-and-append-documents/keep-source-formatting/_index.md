---
title: Kaynak biçimlendirmesini koruyun
linktitle: Kaynak biçimlendirmesini koruyun
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak orijinal biçimlendirmeyi korurken bir kaynak belgeyi hedef belgeye nasıl ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/keep-source-formatting/
---

Bu eğitim, Aspose.Words for .NET kullanılarak kaynak belgenin orijinal biçimlendirmesi korunurken bir kaynak belgenin hedef belgeye nasıl ekleneceğini gösterir.

## 1. Adım: Projeyi kurun

Aşağıdaki ön koşullara sahip olduğunuzdan emin olun:

- Aspose.Words for .NET kitaplığı yüklendi. adresinden indirebilirsiniz[Aspose.Releases]https://releases.aspose.com/words/net/ veya yüklemek için NuGet paket yöneticisini kullanın.
- Kaynak ve hedef belgelerin kaydedileceği bir belge dizini yolu.

## 2. Adım: Hedef ve kaynak belgeleri oluşturun

 Örneklerini oluştur`Document` hedef ve kaynak belgeler için.

```csharp
// Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## 3. Adım: Kaynak belgeyi hedef belgeye ekleyin

 Kullan`AppendDocument`kaynak belgeyi eklemek için hedef belgenin yöntemi. Geçmek`ImportFormatMode.KeepSourceFormatting` kaynak belgenin orijinal biçimlendirmesini korumak için içe aktarma biçimi modu olarak.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 4. Adım: Değiştirilen belgeyi kaydedin

 Değiştirilen belgeyi şunu kullanarak kaydedin:`Save` yöntemi`Document` nesne.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Bu, Aspose.Words for .NET kullanarak orijinal biçimlendirmeyi korurken kaynak belgeyi hedef belgeye ekleme uygulamasını tamamlar.

### Aspose.Words for .NET kullanarak Kaynak Biçimlendirmesini Koru için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Kaynak belgeyi hedef belgeye ekleyin.
	// Kaynak belgeyi içe aktarırken orijinal biçimlendirmesini korumak için biçim modunu geçin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```