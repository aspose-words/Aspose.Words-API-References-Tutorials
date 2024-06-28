---
title: Hedef Stillerini Kullan
linktitle: Hedef Stillerini Kullan
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET'i kullanarak hedef belge stillerini uygularken Word belgelerini nasıl birleştireceğinizi ve ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/use-destination-styles/
---

Bu eğitim Aspose.Words for .NET'in Hedef Stillerini Kullan özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, hedef belgenin stillerini uygularken Word belgelerini birleştirmenize ve eklemenize olanak tanır.

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

## 3. Adım: Kaynak Belgeyi Hedef Stilleriyle Ekleme

 Hedef belgenin stillerini uygularken kaynak belgeyi hedef belgeye eklemek için`AppendDocument` yöntemi`Document` ile sınıf`ImportFormatMode.UseDestinationStyles` parametreler.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Adım 4: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi, Hedef Stillerini Kullan özelliği etkinleştirilerek kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Aspose.Words for .NET kullanarak Hedef Stilleri Kullanmak için örnek kaynak kodu

Aspose.Words for .NET kullanarak C#'taki "Hedef Stillerini Kullan" özelliğinin tam kaynak kodunu burada bulabilirsiniz:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hedef belgenin stillerini kullanarak kaynak belgeyi ekleyin.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Hedef Stillerini Kullan özelliğini başarıyla uyguladınız. Nihai belge, uygulanan hedef belgenin stilleri ile birleştirilmiş içeriği içerecektir.