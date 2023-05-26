---
title: Bağlantı Başlıkları Alt Bilgiler
linktitle: Bağlantı Başlıkları Alt Bilgiler
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken üst bilgileri ve alt bilgileri nasıl bağlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/link-headers-footers/
---

Bu eğitim, Aspose.Words for .NET'in Bağlantı Başlıkları Alt Bilgiler özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgenin üstbilgilerini ve altbilgilerini hedef belgedeki önceki bölüme bağlarken birden çok Word belgesini birleştirip eklemenize olanak tanır.

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

## 3. Adım: Eklenen Belgeyi Yeni Bir Sayfada Görünecek Şekilde Ayarlayın

Kaynak belgedeki içeriğin hedef belgede yeni bir sayfada görünmesini sağlamak için,`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 4. Adım: Üstbilgileri ve Altbilgileri Önceki Bölüme Bağlayın

 Kaynak belgenin üstbilgilerini ve altbilgilerini hedef belgedeki bir önceki bölüme bağlamak için`LinkToPrevious` yöntemi`HeadersFooters` Toplamak. geçerek`true` parametre olarak, kaynak belgedeki mevcut üst bilgileri veya alt bilgileri geçersiz kılarsınız.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi bağlantılı üstbilgiler ve altbilgilerle birlikte kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Aspose.Words for .NET kullanan Bağlantı Üstbilgileri Altbilgileri için örnek kaynak kodu 

Aspose.Words for .NET kullanan C# dilindeki "Üstbilgileri Altbilgileri Bağla" özelliğinin tam kaynak kodu burada:


```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Eklenen belgeyi yeni bir sayfada görünecek şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Kaynak belgedeki üst bilgileri ve alt bilgileri önceki bölüme bağlayın.
	// Bu, kaynak belgede zaten bulunan üst bilgileri veya alt bilgileri geçersiz kılar.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Bağlantı Başlıkları Alt Bilgiler özelliğini başarıyla uyguladınız. Nihai belge, hedef belgedeki önceki bölüme bağlı kaynak belgedeki üstbilgiler ve altbilgilerle birleştirilmiş içeriği içerecektir.