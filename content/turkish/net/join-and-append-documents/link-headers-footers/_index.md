---
title: Bağlantı Başlıkları Altbilgileri
linktitle: Bağlantı Başlıkları Altbilgileri
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken üstbilgileri ve altbilgileri nasıl bağlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/link-headers-footers/
---

Bu eğitim, Aspose.Words for .NET'in Bağlantı Başlıkları Altbilgileri özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, kaynak belgenin üstbilgilerini ve altbilgilerini hedef belgedeki önceki bölüme bağlarken birden çok Word belgesini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Eklenen Belgeyi Yeni Sayfada Görünecek Şekilde Ayarlayın

 Kaynak belgedeki içeriğin hedef belgedeki yeni bir sayfada görünmesini sağlamak için`SectionStart` kaynak belgedeki ilk bölümün özelliği`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Adım 4: Üstbilgileri ve Altbilgileri Önceki Bölüme Bağlayın

 Kaynak belgenin üstbilgilerini ve altbilgilerini hedef belgedeki önceki bölüme bağlamak için`LinkToPrevious` yöntemi`HeadersFooters` Toplamak. Geçerek`true` parametre olarak kaynak belgedeki mevcut üstbilgileri veya altbilgileri geçersiz kılarsınız.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Adım 5: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Adım 6: Son Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi bağlantılı üstbilgiler ve altbilgilerle birlikte şunu kullanarak kaydedin:`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Aspose.Words for .NET kullanan Bağlantı Başlıkları Altbilgileri için örnek kaynak kodu 

Aspose.Words for .NET kullanan C#'taki "Bağlantı Başlıkları Altbilgileri" özelliğinin tam kaynak kodu:


```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Eklenen belgeyi yeni sayfada görünecek şekilde ayarlayın.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Kaynak belgedeki üstbilgileri ve altbilgileri önceki bölüme bağlayın.
	// Bu, kaynak belgede zaten bulunan tüm üstbilgileri veya altbilgileri geçersiz kılacaktır.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Bağlantı Başlıkları Altbilgileri özelliğini başarıyla uyguladınız. Nihai belge, hedef belgedeki önceki bölüme bağlanan kaynak belgedeki üstbilgiler ve altbilgilerle birleştirilmiş içeriği içerecektir.