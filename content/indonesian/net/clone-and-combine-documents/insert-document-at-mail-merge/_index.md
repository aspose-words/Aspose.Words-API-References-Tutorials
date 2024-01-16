---
title: Sisipkan Dokumen Pada Mail Merge
linktitle: Sisipkan Dokumen Pada Mail Merge
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dokumen ke dokumen lain selama penggabungan surat menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara menyisipkan dokumen ke dalam dokumen lain selama penggabungan surat menggunakan fitur Sisipkan Dokumen Selama Penggabungan Surat di Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan melakukan penyisipan dokumen.

## Langkah 1: Memuat dokumen utama

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen utama ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Langkah 2: Konfigurasikan Gabungan Surat

Sekarang mari kita konfigurasikan gabungan surat dan tentukan bidang panggilan balik gabungan untuk menyisipkan dokumen ke dalam dokumen lain. Begini caranya:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Langkah 3: Menjalankan Mail Merge

Kami akan menjalankan gabungan surat dengan memberikan nama bidang gabungan dan data terkait. Begini caranya:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Contoh kode sumber untuk Sisipkan Dokumen Pada Gabungan Surat menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fitur Sisipkan Dokumen di Mail Merge Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// Dokumen utama memiliki bidang gabungan yang disebut "Dokumen_1".
// Data terkait untuk bidang ini berisi jalur yang sepenuhnya memenuhi syarat ke dokumen.
// Itu harus dimasukkan ke bidang ini.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Dengan kode ini Anda akan dapat menyisipkan dokumen ke dalam dokumen lain selama penggabungan surat menggunakan Aspose.Words untuk .NET. Dokumen yang dihasilkan akan disimpan dengan nama baru


## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara menyisipkan dokumen ke dalam dokumen lain selama penggabungan surat menggunakan fitur Sisipkan Dokumen Selama Penggabungan Surat di Aspose.Words untuk .NET. Dengan mengonfigurasi gabungan surat dan menyediakan data yang diperlukan, Anda dapat menyusun dokumen secara dinamis dengan menggabungkan berbagai templat atau bagian dokumen. Aspose.Words untuk .NET menyediakan cara yang fleksibel dan canggih untuk mengelola skenario pembuatan dokumen yang kompleks, menjadikannya alat yang berharga untuk mengotomatiskan tugas pembuatan dan manipulasi dokumen.

### FAQ

#### Q: Apa tujuan menyisipkan dokumen ke dalam dokumen lain saat mail merge?

J: Memasukkan dokumen ke dalam dokumen lain selama penggabungan surat memungkinkan Anda menggabungkan templat atau bagian dokumen yang berbeda secara dinamis berdasarkan data yang disediakan selama proses penggabungan. Fitur ini sangat berguna ketika Anda ingin menyusun dokumen kompleks dengan menggabungkan berbagai templat atau bagian yang telah ditentukan sebelumnya menjadi dokumen akhir.

#### T: Bagaimana cara menyisipkan dokumen ke dokumen lain selama penggabungan surat menggunakan Aspose.Words untuk .NET?

J: Untuk menyisipkan dokumen ke dalam dokumen lain selama penggabungan surat menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:
1. Muat dokumen utama yang akan dijadikan dasar ke dalam objek Dokumen.
2. Konfigurasikan gabungan surat dan tentukan panggilan balik gabungan bidang untuk menangani penyisipan dokumen.
3. Jalankan gabungan surat dengan nama bidang gabungan dan data terkait (jalur ke dokumen yang akan disisipkan).

#### T: Bagaimana cara menyesuaikan perilaku penyisipan selama penggabungan surat?

J: Untuk menyesuaikan perilaku penyisipan selama penggabungan surat, Anda dapat mengimplementasikan FieldMergingCallback kustom dengan mewarisi antarmuka IFieldMergingCallback. Ini memungkinkan Anda mengontrol cara dokumen disisipkan dan digabungkan berdasarkan kebutuhan spesifik Anda.

#### T: Dapatkah saya menyisipkan banyak dokumen selama penggabungan surat?

J: Ya, Anda dapat menyisipkan beberapa dokumen selama penggabungan surat dengan menyediakan data yang sesuai untuk setiap bidang gabungan. Untuk setiap bidang gabungan yang memerlukan penyisipan dokumen, tentukan jalur ke dokumen terkait sebagai data.


