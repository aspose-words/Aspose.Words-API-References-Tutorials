---
title: Kaynak Üstbilgileri Altbilgilerini Kaldır
linktitle: Kaynak Üstbilgileri Altbilgilerini Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken üstbilgileri ve altbilgileri nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/remove-source-headers-footers/
---

Bu eğitim, Aspose.Words for .NET'in Kaynak Üst Bilgilerini Kaldır Alt Bilgilerini Kaldırma özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgedeki üstbilgileri ve altbilgileri kaldırırken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

## Önkoşullar

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Aspose.Words for .NET kuruldu. Aspose web sitesinden indirebilir veya NuGet aracılığıyla yükleyebilirsiniz.
2. Visual Studio veya başka herhangi bir C# geliştirme ortamı.

## Adım 1: Belge Dizinlerini Başlatın

 Öncelikle belge dizininizin yolunu ayarlamanız gerekir. Değerini değiştirin`dataDir` belgelerinizin bulunduğu yola göre değişkendir.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Adım 2: Kaynak ve Hedef Belgelerini Yükleyin

Daha sonra Aspose.Words'ü kullanarak kaynak ve hedef belgeleri yüklemeniz gerekir.`Document` sınıf. Dosya adlarını güncelleyin`Document` belge adlarınıza göre yapıcı.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. Adım: Kaynak Belge Bölümlerinden Üstbilgileri ve Altbilgileri Kaldırma

 Kaynak belgedeki her bölümden üstbilgileri ve altbilgileri kaldırmak için, bir bölüm kullanarak bölümler arasında yineleme yapabilirsiniz.`foreach` döngü yapın ve çağırın`ClearHeadersFooters` yöntem.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Adım 4: HeadersFooters için "LinkToÖnceki" Ayarını Devre Dışı Bırakın

Kaynak belgedeki üstbilgileri ve altbilgileri temizledikten sonra bile "LinkToÖnceki" ayarının`HeadersFooters` hala ayarlanabilir. Bu davranışı önlemek için bunu açıkça ayarlamanız gerekir.`false` ilk bölüm için`HeadersFooters` mülk.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 6: Son Belgeyi Kaydedin

 Son olarak, birleştirilen belgeyi, Kaynak Üstbilgileri Altbilgilerini Kaldır özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Aspose.Words for .NET kullanarak Kaynak Üstbilgileri Altbilgilerini Kaldırmak için örnek kaynak kodu 

Aspose.Words for .NET kullanarak C#'taki "Kaynak Üst Bilgilerinin Alt Bilgilerini Kaldır" özelliğinin tam kaynak kodunu burada bulabilirsiniz:


```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Kaynak belgedeki bölümlerin her birinden üstbilgileri ve altbilgileri kaldırın.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Kaynak belgedeki üstbilgiler ve altbilgiler temizlendikten sonra bile "LinkToÖnceki" ayarı
	// HeadersFooters için hala ayarlanabilir. Bu, üstbilgilerin ve altbilgilerin hedeften devam etmesine neden olur
	// belge. Bu davranışı önlemek için bu değer false olarak ayarlanmalıdır.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Bu kadar! Aspose.Words for .NET'i kullanarak Kaynak Üst Bilgilerini Alt Bilgilerini Kaldır özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgeden kaldırılan üstbilgiler ve altbilgilerle birleştirilmiş içeriği içerecektir.