---
title: Aspose.Words for Java'da Belgeleri Klonlamak ve Birleştirmek
linktitle: Belgeleri Klonlamak ve Birleştirmek
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da belgeleri nasıl kopyalayıp birleştireceğinizi öğrenin. Kaynak kodu örnekleriyle adım adım kılavuz.
type: docs
weight: 27
url: /tr/java/document-manipulation/cloning-and-combining-documents/
---

## Aspose.Words for Java'da Belgeleri Klonlama ve Birleştirmeye Giriş

Bu eğitimde Aspose.Words for Java kullanarak belgelerin nasıl kopyalanıp birleştirileceğini inceleyeceğiz. Bir belgenin kopyalanması, değiştirme noktalarına belge eklenmesi, yer imleri ve adres-mektup birleştirme işlemleri dahil olmak üzere çeşitli senaryoları ele alacağız.

## Adım 1: Bir Belgeyi Klonlamak

 Aspose.Words for Java'da bir belgeyi kopyalamak için şunu kullanabilirsiniz:`deepClone()` yöntem. İşte basit bir örnek:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

Bu kod orijinal belgenin derin bir kopyasını oluşturacak ve onu yeni bir dosya olarak kaydedecektir.

## Adım 2: Belgeleri Değiştirme Noktalarına Ekleme

Belgeleri başka bir belgedeki belirli değiştirme noktalarına ekleyebilirsiniz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 Bu örnekte, bir kullanıyoruz`FindReplaceOptions` değiştirme için bir geri arama işleyicisi belirtmek için nesne.`InsertDocumentAtReplaceHandler` class ekleme mantığını yönetir.

## 3. Adım: Belgeleri Yer İmlerine Ekleme

Bir belgeyi başka bir belgedeki belirli bir yer imine eklemek için aşağıdaki kodu kullanabilirsiniz:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 Burada yer imini ada göre buluruz ve kullanırız.`insertDocument` içeriğini ekleme yöntemi`subDoc` belgeyi yer imi konumunda.

## Adım 4: Adres Mektup Birleştirme Sırasında Belgeleri Ekleme

Aspose.Words for Java'da adres-mektup birleştirme işlemi sırasında belge ekleyebilirsiniz. İşte nasıl:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 Bu örnekte, aşağıdakileri kullanarak alan birleştirme geri çağrısını ayarladık:`InsertDocumentAtMailMergeHandler` "Belge_1" alanı tarafından belirtilen belgenin eklenmesini işleyecek sınıf.

## Çözüm

Aspose.Words for Java'da belgeleri klonlamak ve birleştirmek çeşitli teknikler kullanılarak gerçekleştirilebilir. Bir belgeyi kopyalamanız, değiştirme noktalarına, yer imlerine veya adres-mektup birleştirme sırasında içerik eklemeniz gerekip gerekmediğine bakılmaksızın Aspose.Words, belgeleri sorunsuz bir şekilde işlemek için güçlü özellikler sağlar.

## SSS'ler

### Aspose.Words for Java'da bir belgeyi nasıl kopyalarım?

 Aspose.Words for Java'da bir belgeyi aşağıdaki komutu kullanarak kopyalayabilirsiniz:`deepClone()` yöntem. İşte bir örnek:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### Bir belgeyi yer imine nasıl ekleyebilirim?

 Aspose.Words for Java'da bir yer imine belge eklemek için yer imini ada göre bulabilir ve ardından`insertDocument` İçeriği ekleme yöntemi. İşte bir örnek:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### Aspose.Words for Java'da adres-mektup birleştirme sırasında belgeleri nasıl eklerim?

Aspose.Words for Java'da adres-mektup birleştirme sırasında bir alan birleştirme geri çağrısı ayarlayıp eklenecek belgeyi belirterek belge ekleyebilirsiniz. İşte bir örnek:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 Bu örnekte,`InsertDocumentAtMailMergeHandler`sınıfı, adres-mektup birleştirme sırasında "DocumentField" için ekleme mantığını yönetir.