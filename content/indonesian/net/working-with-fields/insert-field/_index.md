---
title: Sisipkan Bidang
linktitle: Sisipkan Bidang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara Menyisipkan bidang ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET. Personalisasikan dokumen Anda dengan bidang dinamis.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-field/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Sisipkan Bidang" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Dokumen dan DocumentBuilder

Kita mulai dengan membuat dokumen baru dan menginisialisasi DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Memasukkan bidang

 Kami menggunakan`InsertField()` metode DocumentBuilder untuk menyisipkan bidang ke dalam dokumen. Dalam contoh ini, kami menyisipkan kolom gabungan (MERGEFIELD) dengan nama kolom "MyFieldName" dan format penggabungan.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Contoh kode sumber untuk menyisipkan kolom dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Masukkan bidang.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

Dalam contoh ini, kami membuat dokumen baru, menginisialisasi DocumentBuilder, lalu menyisipkan kolom gabungan dengan nama kolom "MyFieldName" dan format penggabungan. Dokumen tersebut kemudian disimpan dengan nama file tertentu.

Ini menyimpulkan panduan kami tentang penggunaan fitur "Sisipkan Bidang" dengan Aspose.Words untuk .NET.

### FAQ

#### T: Apa yang dimaksud dengan bidang di Word?

J: Bidang di Word adalah elemen yang memungkinkan Anda menyisipkan dan memanipulasi data dinamis dalam dokumen. Dapat digunakan untuk menampilkan informasi variabel seperti tanggal, nomor halaman, tabel, rumus matematika, dll.

#### T: Bagaimana cara menyisipkan bidang dalam dokumen Word?

A: Untuk menyisipkan field di dokumen Word, Anda dapat mengikuti langkah-langkah berikut:

1. Tempatkan kursor Anda di tempat Anda ingin menyisipkan bidang.
2. Buka tab "Sisipkan" di pita.
3. Klik tombol "Bidang" di grup "Teks" untuk membuka kotak dialog bidang.
4. Pilih jenis bidang yang ingin Anda sisipkan dari daftar drop-down.
5. Konfigurasikan opsi bidang sesuai kebutuhan.
6. Klik tombol "OK" untuk memasukkan bidang tersebut ke dalam dokumen Anda.

#### T: Apa saja tipe bidang yang umum digunakan di Word?

J: Word menawarkan beragam tipe bidang yang bisa Anda gunakan dalam dokumen Anda. Berikut adalah beberapa jenis bidang yang umum digunakan:

- Tanggal dan waktu: menampilkan tanggal dan waktu saat ini.
- Nomor halaman: menampilkan nomor halaman saat ini.
- Daftar isi: secara otomatis menghasilkan daftar isi berdasarkan gaya judul Anda.
- Perhitungan: melakukan perhitungan matematis menggunakan rumus.
- Teks Pengisi: Menghasilkan teks acak untuk mengisi dokumen Anda.

#### T: Bisakah saya mengkustomisasi tampilan bidang di Word?

J: Ya, Anda bisa mengkustomisasi tampilan bidang di Word dengan menggunakan opsi pemformatan yang tersedia. Misalnya, Anda dapat mengubah font, ukuran, warna, dan gaya teks dalam suatu bidang. Anda juga dapat menerapkan efek pemformatan seperti huruf tebal, miring, dan garis bawah.
  