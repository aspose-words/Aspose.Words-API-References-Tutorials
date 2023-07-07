---
title: Değiştirme Sırasında Belge Ekle
linktitle: Değiştirme Sırasında Belge Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET kullanarak değiştirme sırasında nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-replace/
---

Bu öğreticide, Aspose.Words for .NET'in Insert Document When Changeing özelliğini kullanarak değiştirirken bir belgeyi başka bir belgeye nasıl ekleyeceğinizi size göstereceğiz. Kaynak kodunu anlamak ve belge ekleme işlemini gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Ana belgenin yüklenmesi

Başlamak için belgeleriniz için dizini belirtin ve ana belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. Adım: Arama ve değiştirme seçeneklerini yapılandırın

Şimdi bir belgeyi başka bir belgeye eklemek için arama yönünü ve geri aramayı değiştir'i belirterek bul ve değiştir seçeneklerini yapılandıracağız. İşte nasıl:

```csharp
// Arama ve değiştirme seçeneklerini yapılandırın.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 3. Adım: Değiştirme yöntemini çağırma

Şimdi, yapılandırılmış seçenekleri kullanarak belirtilen metni bulup boş bir dizeyle değiştirmek için replace yöntemini çağıracağız. İşte nasıl:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Aspose.Words for .NET kullanarak Insert Document At Change için örnek kaynak kodu

Aspose.Words for .NET'i değiştirirken Belge Ekle özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Bul ve değiştir seçeneklerini ayarlayın.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// replace yöntemini çağırın.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```