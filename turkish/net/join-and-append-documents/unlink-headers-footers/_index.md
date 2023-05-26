---
title: Üstbilgilerin Altbilgilerin Bağlantısını Kaldırma
linktitle: Üstbilgilerin Altbilgilerin Bağlantısını Kaldırma
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak üstbilgi ve altbilgi bağlantısını kaldırırken Word belgelerini nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/unlink-headers-footers/
---

Bu eğitim, Aspose.Words for .NET'in Unlink Headers Footers özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, üstbilgilerin ve altbilgilerin kaynak belgeden bağlantısını kaldırırken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Kaynak Belgedeki Üstbilgiler ve Altbilgilerin Bağlantısını Kaldırın

 Kaynak belgedeki üstbilgiler ve altbilgiler ile devam eden hedef belgenin üstbilgiler ve altbilgiler arasındaki bağlantıyı kaldırmak için,`LinkToPrevious` mülkiyeti`HeadersFooters` kaynak belgenin ilk bölümünde toplama`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Üstbilgilerin Altbilgilerin Bağlantısını Kaldır özelliği etkinleştirilerek kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Aspose.Words for .NET kullanan Unlink Headers Footers için örnek kaynak kodu

Aspose.Words for .NET kullanan C# dilindeki "Üstbilgilerin Altbilgilerin Bağlantısını Kaldır" özelliğinin tam kaynak kodu burada:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Bunu durdurmak için kaynak belgedeki üstbilgilerin ve altbilgilerin bağlantısını kaldırın.
	// hedef belgenin üstbilgileri ve altbilgilerine devam etmekten.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Başlıkların Altbilgilerin Bağlantısını Kaldır özelliğini başarıyla uyguladınız. Nihai belge, hedef belgeden bağlantısı kaldırılmış kaynak belgedeki üstbilgiler ve altbilgilerle birleştirilmiş içeriği içerecektir.