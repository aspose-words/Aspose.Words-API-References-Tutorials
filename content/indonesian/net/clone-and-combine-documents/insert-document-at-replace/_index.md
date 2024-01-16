---
title: Sisipkan Dokumen Saat Ganti
linktitle: Sisipkan Dokumen Saat Ganti
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dokumen pengganti menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/clone-and-combine-documents/insert-document-at-replace/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara menyisipkan dokumen ke dokumen lain saat mengganti menggunakan fitur Sisipkan Dokumen Saat Mengganti dari Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan melakukan penyisipan dokumen.

## Langkah 1: Memuat dokumen utama

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen utama ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Langkah 2: Konfigurasikan opsi pencarian dan penggantian

Sekarang kita akan mengkonfigurasi opsi temukan dan ganti dengan menentukan arah pencarian dan panggilan balik ganti untuk memasukkan dokumen ke dokumen lain. Begini caranya:

```csharp
// Konfigurasikan opsi pencarian dan penggantian.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Langkah 3: Memanggil metode penggantian

Kami sekarang akan memanggil metode ganti untuk menemukan dan mengganti teks yang ditentukan dengan string kosong, menggunakan opsi yang dikonfigurasi. Begini caranya:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Contoh kode sumber untuk Sisipkan Dokumen Saat Ganti menggunakan Aspose.Words untuk .NET

Berikut source code lengkap fitur Insert Document saat mengganti Aspose.Words for .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Atur opsi temukan dan ganti.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Panggil metode penggantian.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi cara menyisipkan dokumen ke dokumen lain selama penggantian menggunakan fitur Sisipkan Dokumen Saat Mengganti dari Aspose.Words untuk .NET. Dengan mengonfigurasi opsi temukan dan ganti serta menyediakan data yang diperlukan, Anda dapat menyusun dokumen secara dinamis dengan mengganti placeholder tertentu dengan konten templat atau bagian dokumen lainnya. Aspose.Words untuk .NET menawarkan cara yang ampuh dan fleksibel untuk mengelola tugas manipulasi dokumen yang kompleks, menjadikannya alat yang berharga untuk mengotomatisasi pembuatan dokumen dan skenario penyisipan konten.

### FAQ

#### Q: Apa tujuan menyisipkan suatu dokumen ke dalam dokumen lain pada saat penggantian?

J: Memasukkan dokumen ke dalam dokumen lain selama penggantian memungkinkan Anda mengganti placeholder tertentu secara dinamis dengan konten dokumen terpisah. Fitur ini sangat berguna ketika Anda ingin menyusun dokumen yang lebih besar dengan menggabungkan berbagai templat atau bagian dokumen yang telah ditentukan sebelumnya ke dalam placeholder tertentu.

#### T: Bagaimana cara menyisipkan dokumen ke dokumen lain selama penggantian menggunakan Aspose.Words untuk .NET?

A: Untuk menyisipkan dokumen ke dalam dokumen lain saat penggantian menggunakan Aspose.Words for .NET, ikuti langkah-langkah berikut:
1. Muat dokumen utama yang berisi placeholder ke dalam objek Dokumen.
2. Konfigurasikan opsi temukan dan ganti, termasuk arah pencarian dan ganti panggilan balik untuk menangani penyisipan dokumen.
3. Panggil metode ganti dengan pola pencarian yang sesuai, ganti placeholder dengan string kosong, menggunakan opsi yang dikonfigurasi.

#### T: Dapatkah saya menyesuaikan perilaku penyisipan selama penggantian?

J: Ya, Anda dapat menyesuaikan perilaku penyisipan selama penggantian dengan menerapkan ReplacingCallback khusus. Dengan mewarisi antarmuka IReplacingCallback, Anda dapat mengontrol cara dokumen disisipkan dan digabungkan berdasarkan kebutuhan spesifik Anda saat mengganti placeholder.

#### T: Bisakah saya mengganti beberapa placeholder dengan dokumen berbeda?

J: Ya, Anda dapat mengganti beberapa placeholder dengan dokumen berbeda dengan menentukan pola pencarian yang sesuai untuk setiap placeholder dan menyediakan dokumen terkait yang akan disisipkan.