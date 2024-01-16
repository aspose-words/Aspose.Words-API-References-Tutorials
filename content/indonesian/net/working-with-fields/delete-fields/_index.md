---
title: Hapus Bidang
linktitle: Hapus Bidang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menghapus bidang gabungan di dokumen Word Anda menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/delete-fields/
---

Untuk menjelaskan cara menggunakan fitur "Hapus Bidang" di Aspose. Words untuk .NET kami telah membuat panduan langkah demi langkah di bawah ini. 

Penting untuk mengikuti setiap langkah dengan cermat untuk mencapai hasil yang diinginkan. 

## Langkah 1: Membuat Dokumen Baru

Dalam cuplikan kode ini kita mulai dengan membuat dokumen kosong baru menggunakan baris berikut: 

```csharp
Document doc = new Document();
```

## Langkah 2: Hapus Gabungkan Bidang

 Untuk menghapus semua bidang gabungan yang ada dalam dokumen, kami menggunakan`DeleteFields()` fungsi. 

Hal ini sangat berguna jika Anda hanya ingin menyimpan konten statis dan menghapus informasi penggabungan apa pun. 

### Contoh Kode Sumber untuk Menghapus Bidang dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen yang ada.
Document doc = new Document(dataDir + "YourDocument.docx");

// Hapus bidang gabungan.
doc.MailMerge.DeleteFields();

// Simpan dokumen yang diubah.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 Dalam contoh kita, pertama-tama kita memuat dokumen yang sudah ada sebelum memanggil`DeleteFields()`. Terakhir kita simpan dokumen yang sudah dimodifikasi dengan nama file baru. 

Untuk menghapus bidang gabungan secara efektif dari dokumen menggunakan fitur "Hapus Bidang" Aspose.Words untuk .NET, ambil petunjuk dari contoh ini. 

Selalu ingat untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur direktori spesifik Anda. 

Panduan kami tentang penerapan fungsionalitas "Hapus Bidang" melalui Aspose.Words untuk .NET telah selesai.

### FAQ

#### T: Apa yang dimaksud dengan bidang di Aspose.Words?

J: Bidang di Aspose.Words adalah struktur dokumen yang mewakili teks yang dihasilkan secara otomatis atau nilai terhitung. Bidang digunakan untuk menampilkan informasi dinamis dalam dokumen, seperti nomor halaman, tanggal, bidang gabungan surat, dll.

#### T: Bagaimana cara menghapus bidang dalam dokumen Word dengan Aspose.Words?

A: Untuk menghapus field di dokumen Word dengan Aspose.Words, Anda dapat mengikuti langkah-langkah berikut:

1. Impor kelas Dokumen dari namespace Aspose.Words.
2. Buat instance Dokumen dengan memuat dokumen Anda yang sudah ada.
3. Gunakan metode HapusFields untuk menghapus semua bidang dari dokumen.

#### T: Bisakah saya menghapus kolom tertentu daripada menghapus semua kolom dari dokumen?

J: Ya, Anda dapat menghapus kolom tertentu daripada menghapus semua kolom dari dokumen. Untuk melakukan ini, Anda perlu mengakses setiap bidang satu per satu dan menggunakan metode Hapus untuk menghapusnya.

#### T: Bagaimana cara memeriksa apakah ada bidang di dokumen Word sebelum menghapusnya?

J: Untuk memeriksa apakah suatu bidang ada di dokumen Word sebelum menghapusnya, Anda dapat menggunakan metode Berisi dari kumpulan Bidang untuk menemukan bidang yang ditentukan. Metode ini mengembalikan nilai boolean yang menunjukkan apakah bidang tersebut ada atau tidak.

#### T: Apa dampak penghapusan suatu bidang pada dokumen lainnya?

J: Saat Anda menghapus bidang dalam dokumen Word, bidang tersebut akan dihapus dari dokumen dan teks yang dihasilkan atau nilai terhitung yang terkait dengan bidang tersebut akan dihapus. Hal ini dapat mempengaruhi tata letak dokumen, karena konten yang dihasilkan oleh bidang tersebut akan dihapus.