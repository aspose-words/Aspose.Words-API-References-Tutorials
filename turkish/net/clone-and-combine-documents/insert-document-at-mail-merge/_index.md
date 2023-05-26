---
title: Adres Mektup Birleştirmede Belge Ekle
linktitle: Adres Mektup Birleştirmede Belge Ekle
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words for .NET'i kullanarak adres-mektup birleştirme sırasında diğerine nasıl belge ekleyeceğinizi öğrenin.
type: docs
weight: 10
url: /tr/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

Bu eğitimde, Aspose.Words for .NET'in Adres Mektup Birleştirme Sırasında Belge Ekle özelliğini kullanarak adres mektup birleştirme sırasında başka bir belgeye nasıl belge ekleyeceğinizi göstereceğiz. Kaynak kodunu anlamak ve belge ekleme işlemini gerçekleştirmek için aşağıdaki adımları izleyin.

## 1. Adım: Ana belgenin yüklenmesi

Başlamak için belgeleriniz için dizini belirtin ve ana belgeyi bir Belge nesnesine yükleyin. İşte nasıl:

```csharp
// Belgeler dizinine giden yol.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 2. Adım: Adres Mektup Birleştirmeyi Yapılandırın

Şimdi adres mektup birleştirmeyi yapılandıralım ve başka bir belgeye belge eklemek için alan birleştirme geri aramasını belirleyelim. İşte nasıl:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## 3. Adım: Adres Mektup Birleştirmeyi Çalıştırma

Birleştirme alanlarının adlarını ve karşılık gelen verileri sağlayarak adres mektup birleştirmeyi çalıştıracağız. İşte nasıl:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Aspose.Words for .NET kullanarak Adres Mektup Birleştirmede Belge Ekleme için örnek kaynak kodu

Aspose.Words for .NET'in Adres Mektup Birleştirmede Belge Ekle özelliğinin tam kaynak kodu burada:

```csharp

	// Belgeler dizininin yolu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

	mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
	//Ana belgenin içinde "Belge_1" adlı bir birleştirme alanı vardır.
	// Bu alan için karşılık gelen veriler, belgeye giden tam nitelikli bir yol içerir.
	// Bu alana girilmelidir.
	mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

	mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");

```

Bu kodla, Aspose.Words for .NET kullanarak adres mektup birleştirme sırasında başka bir belgeye belge ekleyebileceksiniz. Ortaya çıkan belge yeni bir adla kaydedilecek



