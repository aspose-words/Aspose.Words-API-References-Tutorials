---
title: Üstbilgi Altbilgilerinin Bağlantısını Kaldır
linktitle: Üstbilgi Altbilgilerinin Bağlantısını Kaldır
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak üstbilgi ve altbilgilerin bağlantısını keserken Word belgelerini nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/unlink-headers-footers/
---

Bu eğitim, Aspose.Words for .NET'in Başlık Altbilgilerinin Bağlantısını Kaldır özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, üstbilgilerin ve altbilgilerin kaynak belgeyle bağlantısını keserken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Kaynak Belgedeki Üstbilgilerin ve Altbilgilerin Bağlantısını Kaldırma

 Kaynak belgedeki üstbilgi ve altbilgilerin, hedef belgenin üstbilgileri ve altbilgileriyle devam eden bağlantısını kaldırmak için,`LinkToPrevious` mülkiyeti`HeadersFooters` kaynak belgenin ilk bölümündeki toplama`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 5: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi, Üstbilgi Altbilgilerinin Bağlantısını Kaldır özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Aspose.Words for .NET kullanarak Üstbilgi Altbilgilerinin Bağlantısını Kaldırma için örnek kaynak kodu

Aspose.Words for .NET kullanarak C#'taki "Başlık Alt Bilgilerinin Bağlantısını Kaldır" özelliğinin tam kaynak kodunu burada bulabilirsiniz:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Bunu durdurmak için kaynak belgedeki üstbilgi ve altbilgilerin bağlantısını kaldırın
	// hedef belgenin üstbilgilerine ve altbilgilerine devam etmekten.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Üstbilgi Altbilgilerinin Bağlantısını Kaldır özelliğini başarıyla uyguladınız. Nihai belge, hedef belgeyle bağlantısı kaldırılmış kaynak belgedeki üstbilgi ve altbilgilerle birleştirilmiş içeriği içerecektir.