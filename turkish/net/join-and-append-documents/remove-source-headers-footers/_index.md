---
title: Kaynak Başlıklarını Alt Bilgilerini Kaldır
linktitle: Kaynak Başlıklarını Alt Bilgilerini Kaldır
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken üst bilgileri ve alt bilgileri nasıl kaldıracağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/remove-source-headers-footers/
---

Bu eğitim, Aspose.Words for .NET'in Kaynak Başlıklarını Alt Bilgilerini Kaldır özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgeden üst bilgileri ve alt bilgileri kaldırırken Word belgelerini birleştirip eklemenize olanak tanır.

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

## 3. Adım: Kaynak Belge Bölümlerinden Üstbilgileri ve Altbilgileri Kaldırma

 Kaynak belgedeki her bölümden üstbilgileri ve altbilgileri kaldırmak için bölümler arasında yineleme yapabilirsiniz.`foreach` döngü ve çağrı`ClearHeadersFooters` yöntem.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 4. Adım: HeadersFooters için "LinkToPrevious" Ayarını Devre Dışı Bırakın

Kaynak belgeden üst bilgileri ve alt bilgileri temizledikten sonra bile, "LinkToPrevious" ayarının`HeadersFooters` hala ayarlanabilir. Bu davranıştan kaçınmak için, açıkça olarak ayarlamanız gerekir.`false` ilk bölüm için`HeadersFooters` mülk.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Kaynak Üstbilgileri Altbilgileri Kaldır özelliği etkinleştirilerek kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Aspose.Words for .NET kullanarak Kaynak Başlıklarını Alt Bilgilerini Kaldırmak için örnek kaynak kodu 

Aspose.Words for .NET kullanan C# dilindeki "Kaynak Başlıklarını Alt Bilgilerini Kaldır" özelliğinin tam kaynak kodu burada:


```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Kaynak belgedeki bölümlerin her birindeki üstbilgileri ve altbilgileri kaldırın.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Üstbilgiler ve altbilgiler kaynak belgeden temizlendikten sonra bile "LinkToPrevious" ayarı
	// HeadersFooters için hala ayarlanabilir. Bu, üstbilgilerin ve altbilgilerin hedeften devam etmesine neden olur
	// belge. Bu davranıştan kaçınmak için bu değer false olarak ayarlanmalıdır.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Bu kadar! Aspose.Words for .NET'i kullanarak Kaynak Başlıklarını Alt Bilgilerini Kaldır özelliğini başarıyla uyguladınız. Nihai belge, kaynak belgeden kaldırılan üstbilgiler ve altbilgiler ile birleştirilmiş içeriği içerecektir.