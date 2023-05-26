---
title: Sayfa Düzenini Güncelle
linktitle: Sayfa Düzenini Güncelle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken sayfa düzenini nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/update-page-layout/
---

Bu eğitim, Aspose.Words for .NET'in Sayfa Düzenini Güncelle özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, Word belgelerini birleştirirken ve eklerken sayfa düzeninin doğru şekilde güncellenmesini sağlar.

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

## 3. Adım: Hedef Belge için Sayfa Düzenini Güncelleyin

 Kaynak belgeyi eklemeden önce sayfa düzeninin doğru şekilde güncellendiğinden emin olmak için`UpdatePageLayout` Hedef belgedeki yöntem.

```csharp
dstDoc.UpdatePageLayout();
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleyin

 Artık, kaynak belgeyi hedef belgeye aşağıdakileri kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf. bu`ImportFormatMode.KeepSourceFormatting` parametresi, ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Sayfa Düzenini Tekrar Güncelleyin

 Kaynak belgeyi ekledikten sonra aramanız gerekir.`UpdatePageLayout`ekleme işleminden sonra yapılan herhangi bir değişikliğin işlenen çıktıya yansıtıldığından emin olmak için yöntemi hedef belgede tekrar kullanın.

```csharp
dstDoc.UpdatePageLayout();
```

## 6. Adım: Nihai Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi Sayfa Düzenini Güncelle özelliği etkinleştirilerek kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Aspose.Words for .NET kullanarak Sayfa Düzenini Güncellemek için örnek kaynak kodu

Aspose.Words for .NET kullanarak C# dilinde "Sayfa Düzenini Güncelle" özelliğinin tam kaynak kodu burada:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hedef belge PDF'ye dönüştürülürse, görüntü vb.
	// veya UpdatePageLayout, kaynak belgeden önce çağrılır. ekli,
	// daha sonra yapılan herhangi bir değişiklik, işlenen çıktıya yansıtılmayacaktır.
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Değişikliklerin işlenen çıktıya güncellenmesi için UpdatePageLayout'un yeniden çağrılması gerekir.
	// Tekrar çağrılmazsa, eklenen belge bir sonraki işlemenin çıktısında görünmez.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Sayfa Düzenini Güncelle özelliğini başarıyla uyguladınız. Nihai belge, doğru şekilde güncellenen sayfa düzeniyle birleştirilmiş içeriği içerecektir.