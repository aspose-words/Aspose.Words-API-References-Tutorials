---
title: Konversi Bidang Dalam Paragraf
linktitle: Konversi Bidang Dalam Paragraf
second_title: API Pemrosesan Dokumen Aspose.Words
description: Ubah bidang IF menjadi teks biasa dalam paragraf dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/convert-fields-in-paragraph/
---

Berikut adalah tutorial yang menunjukkan cara menggunakan fitur Konversi Bidang ke Paragraf dengan Aspose.Words untuk .NET. Kode ini mengonversi semua kolom tipe IF yang ditemukan di paragraf terakhir dokumen menjadi teks biasa. Ikuti langkah-langkah di bawah ini untuk memahami dan menjalankan kode ini.

Pastikan Anda telah menginstal Aspose.Words untuk .NET dan menyiapkan lingkungan pengembangan sebelum memulai.

## Langkah 1: Impor referensi

Untuk menggunakan Aspose.Words dalam proyek Anda, Anda perlu menambahkan referensi yang diperlukan. Pastikan Anda telah menambahkan referensi ke perpustakaan Aspose.Words di proyek Anda.

## Langkah 2: Memuat dokumen

Sebelum Anda dapat mengonversi bidang, Anda harus memuat dokumen yang berisi bidang yang akan dikonversi. Pastikan untuk menentukan jalur yang benar ke direktori yang berisi dokumen tersebut. Berikut cara mengunggah dokumen:

```csharp
//Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Mengubah bidang menjadi teks

Sekarang setelah dokumen dimuat, kita dapat melanjutkan dengan mengonversi kolom tipe menjadi teks biasa. Dalam contoh ini, kami hanya menargetkan bidang yang ada di paragraf terakhir dokumen. Berikut adalah kode yang melakukan konversi ini:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Kode ini menggunakan kombinasi metode LINQ untuk memfilter bidang di paragraf terakhir dokumen dan kemudian mengubahnya menjadi teks biasa dengan memanggil`Unlink()` metode.

## Langkah 4: Menyimpan dokumen yang dimodifikasi

 Setelah bidang dikonversi, Anda dapat menyimpan dokumen yang dimodifikasi. Menggunakan`Save()` metode untuk ini. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk cadangan.

### Contoh kode sumber untuk Konversi Bidang Dalam Paragraf menggunakan Aspose.Words untuk .NET

```csharp
//Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen.
Document doc = new Document(dataDir + "Linked fields.docx");

// Ubah bidang IF menjadi teks biasa di paragraf terakhir dokumen.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Simpan dokumen yang diubah.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### FAQ

#### T: Apa yang dimaksud dengan bidang konversi di Aspose.Words?

J: Bidang konversi di Aspose.Words adalah tipe bidang yang mengonversi nilai atau ekspresi ke format atau tipe data lain. Misalnya, Anda dapat menggunakan bidang konversi untuk mengonversi tanggal ke format tertentu, angka menjadi teks, atau melakukan jenis konversi lainnya.

#### T: Bagaimana cara menyisipkan bidang konversi dalam paragraf dengan Aspose.Words?

A: Untuk menyisipkan kolom konversi dalam paragraf dengan Aspose.Words, Anda dapat mengikuti langkah-langkah berikut:

1. Impor kelas Dokumen dari namespace Aspose.Words.
2. Buat instance Dokumen dengan memuat dokumen Anda yang sudah ada.
3. Dapatkan paragraf di mana Anda ingin menyisipkan bidang konversi.
4. Gunakan metode InsertField untuk menyisipkan bidang konversi dengan sintaks yang benar.

#### T: Format konversi apa yang didukung Aspose.Words?

J: Aspose.Words mendukung berbagai format konversi dalam bidang, termasuk format tanggal, format angka, format teks, format mata uang, format persentase, dan banyak lagi. Anda dapat memeriksa dokumentasi Aspose.Words untuk daftar lengkap format konversi yang tersedia.

#### T: Bagaimana cara memperbarui bidang konversi di dokumen Word dengan Aspose.Words?

J: Untuk memperbarui bidang konversi di dokumen Word dengan Aspose.Words, Anda dapat menggunakan metode UpdateFields. Metode ini mengulang dokumen dan memperbarui semua bidang, termasuk bidang konversi, menghitung ulang nilai berdasarkan data saat ini.