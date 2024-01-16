---
title: Konversi Bidang Dalam Tubuh
linktitle: Konversi Bidang Dalam Tubuh
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan Aspose.Words untuk .NET untuk mengonversi bidang Halaman menjadi teks di badan dokumen Word.
type: docs
weight: 10
url: /id/net/working-with-fields/convert-fields-in-body/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan fitur ConvertFieldsInBody dari Aspose.Words untuk .NET menggunakan kode sumber C# yang disediakan. Fitur ini memungkinkan Anda mengonversi bidang tertentu di badan dokumen menjadi teks biasa, sehingga dokumen Anda lebih mudah diproses. Ikuti langkah-langkah di bawah ini untuk menggunakan fitur ini secara efektif.

## Langkah 1: Prasyarat

Sebelum memulai, pastikan Anda telah menginstal Aspose.Words untuk .NET dan memiliki dokumen yang siap untuk diproses. Pastikan juga Anda memiliki jalur direktori ke dokumen Anda.

## Langkah 2: Muat dokumen

Mulailah dengan mendeklarasikan variabel untuk jalur ke direktori dokumen Anda, lalu gunakan variabel tersebut untuk menginisialisasi objek Dokumen dari dokumen yang ditentukan. Dalam contoh kita, dokumen tersebut disebut "Linked field.docx".

```csharp
// Jalur ke direktori dokumen Anda.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Langkah 3: Ubah Bidang Halaman menjadi Teks Biasa

 Sekarang dokumen sudah dimuat, kita dapat melanjutkan ke langkah konversi. Untuk mengonversi bidang halaman menjadi teks biasa di badan bagian pertama, Anda dapat menggunakan`Range.Fields` metode untuk mendapatkan semua bidang dalam rentang yang ditentukan, lalu memfilter jenis bidang`FieldType.FieldPage` . Kemudian Anda dapat menggunakan`ForEach` metode untuk mengulang setiap bidang dan memanggil`Unlink()` metode untuk mengubahnya menjadi teks biasa.

```csharp
// Berikan parameter yang sesuai untuk mengonversi bidang halaman menjadi teks biasa di isi bagian pertama.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Langkah 4: Simpan dokumen yang dimodifikasi

Setelah Anda mengonversi bidang halaman menjadi teks biasa, Anda dapat menyimpan dokumen yang dimodifikasi menggunakan`Save()` metode dan menentukan jalur dan nama file keluaran. Dalam contoh kami, kami menyimpannya sebagai "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Contoh kode sumber untuk mengonversi bidang di badan dengan Aspose.Words untuk .NET

Berikut adalah contoh kode sumber lengkap untuk mengonversi kolom menjadi isi menggunakan Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen Anda.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Linked fields.docx");

// Berikan parameter yang sesuai untuk mengonversi bidang halaman menjadi teks biasa di isi bagian pertama.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### FAQ

#### T: Apakah Aspose.Words kompatibel dengan versi Microsoft Word yang berbeda?

J: Ya, Aspose.Words kompatibel dengan berbagai versi Microsoft Word, termasuk Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, dan Word 2019.

#### T: Dapatkah Aspose.Words menangani struktur bidang yang kompleks?

J: Tentu saja! Aspose.Words memberikan dukungan ekstensif untuk struktur bidang yang kompleks, termasuk bidang bertumpuk, perhitungan, dan ekspresi kondisional. Anda dapat memanfaatkan API yang kuat untuk bekerja dengan semua jenis struktur bidang.

#### T: Apakah Aspose.Words mendukung operasi pembaruan lapangan?

J: Ya, Aspose.Words memungkinkan Anda memperbarui bidang secara terprogram. Anda dapat dengan mudah memperbarui nilai bidang, menyegarkan perhitungan, dan melakukan operasi terkait bidang lainnya menggunakan API.

#### T: Bisakah saya mengonversi kolom menjadi teks biasa menggunakan Aspose.Words?

J: Tentu saja! Aspose.Words menyediakan metode untuk mengubah bidang menjadi teks biasa. Ini dapat berguna ketika Anda perlu mengekstraksi konten tanpa format atau fungsi terkait bidang apa pun.

#### T: Apakah mungkin membuat dokumen Word dengan bidang dinamis menggunakan Aspose.Words?

J: Tentu saja! Aspose.Words menawarkan fitur canggih untuk menghasilkan dokumen Word dengan bidang dinamis. Anda dapat membuat templat dengan bidang yang telah ditentukan sebelumnya dan mengisinya dengan data secara dinamis, memberikan solusi pembuatan dokumen yang fleksibel dan efisien.