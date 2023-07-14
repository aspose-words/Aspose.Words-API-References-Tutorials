---
title: Klonlama Belgesi
linktitle: Klonlama Belgesi
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir Word belgesini nasıl kopyalayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/cloning-document/
---

Bu eğitimde size Aspose.Words for .NET'in klon özelliğini kullanarak bir Word belgesini nasıl klonlayacağınızı anlatacağız. Kaynak kodunu anlamak ve mevcut bir belgenin tam bir kopyasını oluşturmak için aşağıdaki adımları izleyin.

## 1. Adım: Belgeyi yükleme

Başlamak için belge dizininizi belirtin ve mevcut belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## 2. Adım: Belgeyi klonlayın

Şimdi tam bir kopyasını oluşturarak belgeyi klonlayacağız. İşte nasıl:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Aspose.Words for .NET kullanarak Belge Kopyalamak için örnek kaynak kodu

.NET için Aspose.Words belge klonlama özelliğinin tam kaynak kodu burada:

```csharp
// Belgeler dizininin yolu.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Bu kodla, Aspose.Words for .NET kullanarak Word belgesini kopyalayabileceksiniz. Belgenin tam kopyası yeni bir dosya adı altında kaydedilecektir.

