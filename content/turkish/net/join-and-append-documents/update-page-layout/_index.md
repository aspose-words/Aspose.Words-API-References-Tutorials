---
title: Sayfa Düzenini Güncelle
linktitle: Sayfa Düzenini Güncelle
second_title: Aspose.Words Belge İşleme API'si
description: Aspose.Words for .NET kullanarak Word belgelerini birleştirirken ve eklerken sayfa düzenini nasıl güncelleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/update-page-layout/
---

Bu eğitim Aspose.Words for .NET'in Sayfa Düzenini Güncelle özelliğini kullanma sürecinde size rehberlik edecektir. Bu özellik, Word belgelerini birleştirirken ve eklerken sayfa düzeninin doğru şekilde güncellenmesini sağlar.

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

## 3. Adım: Hedef Belgenin Sayfa Düzenini Güncelleyin

 Kaynak belgeyi eklemeden önce sayfa düzeninin doğru şekilde güncellendiğinden emin olmak için`UpdatePageLayout` Hedef belgedeki yöntem.

```csharp
dstDoc.UpdatePageLayout();
```

## Adım 4: Kaynak Belgeyi Hedef Belgeye Ekleme

 Artık kaynak belgeyi hedef belgeye aşağıdaki komutu kullanarak ekleyebilirsiniz:`AppendDocument` yöntemi`Document` sınıf.`ImportFormatMode.KeepSourceFormatting` parametresi ekleme işlemi sırasında kaynak formatının korunmasını sağlar.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5. Adım: Sayfa Düzenini Tekrar Güncelleyin

 Kaynak belgeyi ekledikten sonra aramanız gerekir.`UpdatePageLayout`Ekleme işleminden sonra yapılan değişikliklerin oluşturulan çıktıya yansıtıldığından emin olmak için hedef belgedeki yöntemi tekrar kullanın.

```csharp
dstDoc.UpdatePageLayout();
```

## Adım 6: Son Belgeyi Kaydedin

 Son olarak, birleştirilmiş belgeyi, Sayfa Düzenini Güncelle özelliği etkinleştirilmiş olarak kaydedin.`Save` yöntemi`Document` sınıf.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Aspose.Words for .NET kullanarak Sayfa Düzenini Güncelleme için örnek kaynak kodu

Aspose.Words for .NET kullanarak C#'taki "Sayfa Düzenini Güncelle" özelliğinin tam kaynak kodu:

```csharp
	// Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hedef belge PDF'ye, resme vb. dönüştürülürse.
	// veya UpdatePageLayout kaynak belgeden önce çağrılır. Eklidir,
	// bu durumda daha sonra yapılan değişiklikler oluşturulan çıktıya yansıtılmayacaktır
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Değişikliklerin oluşturulan çıktıya güncellenmesi için UpdatePageLayout'un tekrar çağrılması gerekir.
	// Tekrar çağrılmazsa, eklenen belge bir sonraki işlemenin çıktısında görünmeyecektir.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Bu kadar! Aspose.Words for .NET'i kullanarak Sayfa Düzenini Güncelle özelliğini başarıyla uyguladınız. Nihai belge, sayfa düzeninin doğru şekilde güncellendiği birleştirilmiş içeriği içerecektir.