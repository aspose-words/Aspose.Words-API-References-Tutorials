---
title: Mengkloning dan Menggabungkan Dokumen di Aspose.Words untuk Java
linktitle: Kloning dan Penggabungan Dokumen
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara mengkloning dan menggabungkan dokumen di Aspose.Words untuk Java. Panduan langkah demi langkah dengan contoh kode sumber.
type: docs
weight: 27
url: /id/java/document-manipulation/cloning-and-combining-documents/
---

## Pengantar Kloning dan Menggabungkan Dokumen di Aspose.Words untuk Java

Dalam tutorial ini, kita akan mempelajari cara mengkloning dan menggabungkan dokumen menggunakan Aspose.Words untuk Java. Kami akan membahas berbagai skenario, termasuk mengkloning dokumen, menyisipkan dokumen pada titik penggantian, penanda, dan selama operasi penggabungan surat.

## Langkah 1: Mengkloning Dokumen

 Untuk mengkloning dokumen di Aspose.Words untuk Java, Anda dapat menggunakan`deepClone()` metode. Berikut ini contoh sederhananya:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

Kode ini akan membuat tiruan mendalam dari dokumen asli dan menyimpannya sebagai file baru.

## Langkah 2: Memasukkan Dokumen di Titik Pengganti

Anda dapat menyisipkan dokumen pada titik penggantian tertentu di dokumen lain. Inilah cara Anda melakukannya:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 Dalam contoh ini, kami menggunakan a`FindReplaceOptions` objek untuk menentukan penangan panggilan balik untuk penggantinya. Itu`InsertDocumentAtReplaceHandler` kelas menangani logika penyisipan.

## Langkah 3: Memasukkan Dokumen di Bookmark

Untuk menyisipkan dokumen pada bookmark tertentu di dokumen lain, Anda dapat menggunakan kode berikut:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 Di sini, kami menemukan bookmark berdasarkan nama dan menggunakan`insertDocument` metode untuk memasukkan konten`subDoc` dokumen di lokasi penanda.

## Langkah 4: Memasukkan Dokumen Selama Mail Merge

Anda dapat menyisipkan dokumen selama operasi penggabungan surat di Aspose.Words untuk Java. Begini caranya:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 Dalam contoh ini, kami menetapkan panggilan balik penggabungan bidang menggunakan`InsertDocumentAtMailMergeHandler` kelas untuk menangani penyisipan dokumen yang ditentukan oleh bidang "Dokumen_1".

## Kesimpulan

Mengkloning dan menggabungkan dokumen di Aspose.Words untuk Java dapat dilakukan dengan menggunakan berbagai teknik. Baik Anda perlu mengkloning dokumen, menyisipkan konten pada titik penggantian, penanda, atau selama penggabungan surat, Aspose.Words menyediakan fitur canggih untuk memanipulasi dokumen dengan lancar.

## FAQ

### Bagaimana cara mengkloning dokumen di Aspose.Words untuk Java?

 Anda dapat mengkloning dokumen di Aspose.Words untuk Java menggunakan`deepClone()` metode. Berikut ini contohnya:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### Bagaimana cara menyisipkan dokumen di bookmark?

 Untuk menyisipkan dokumen di bookmark di Aspose.Words untuk Java, Anda dapat menemukan bookmark berdasarkan nama lalu menggunakan`insertDocument` metode untuk memasukkan konten. Berikut ini contohnya:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### Bagaimana cara menyisipkan dokumen selama penggabungan surat di Aspose.Words untuk Java?

Anda dapat menyisipkan dokumen selama penggabungan surat di Aspose.Words untuk Java dengan mengatur panggilan balik penggabungan bidang dan menentukan dokumen yang akan disisipkan. Berikut ini contohnya:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 Dalam contoh ini,`InsertDocumentAtMailMergeHandler`kelas menangani logika penyisipan untuk "DocumentField" selama penggabungan surat.