---
title: Jangan Simpan Gambar Bullet
linktitle: Jangan Simpan Gambar Bullet
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menonaktifkan penyimpanan poin gambar di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Poin gambar adalah fitur yang umum digunakan di dokumen Word untuk menambahkan poin khusus. Namun, dalam beberapa kasus mungkin perlu menonaktifkan registrasi poin gambar saat memanipulasi dokumen menggunakan Perpustakaan Aspose.Words untuk .NET. Dalam panduan langkah demi langkah ini, kami akan menjelaskan cara menggunakan kode sumber Aspose.Words C# untuk .NET untuk menonaktifkan penyimpanan poin gambar menggunakan opsi penyimpanan DocSaveOptions.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan yang kuat untuk membuat, mengedit, mengonversi, dan melindungi dokumen Word di berbagai platform termasuk .NET. Ia menawarkan banyak fitur untuk memanipulasi dokumen, seperti menyisipkan teks, mengubah format, menambahkan bagian, dan banyak lagi.

## Langkah 1: Mengatur Direktori Dokumen

Langkah pertama adalah menentukan direktori tempat dokumen Anda berada. Anda harus menentukan jalur direktori lengkap. Misalnya :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Memuat Dokumen dengan Image Bullets

Selanjutnya, Anda perlu memuat dokumen dengan poin gambar. Gunakan kelas Dokumen untuk memuat dokumen dari file. Misalnya :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Dalam contoh ini kita memuat dokumen dari file "Image bullet points.docx"

  terletak di direktori dokumen.

## Langkah 3: Konfigurasikan opsi perekaman

Sekarang mari kita konfigurasikan opsi penyimpanan untuk dokumen kita. Gunakan kelas DocSaveOptions untuk menentukan pengaturan penyimpanan. Misalnya :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Dalam contoh ini, kita membuat objek DocSaveOptions baru dan menyetel properti SavePictureBullet ke false untuk menonaktifkan penyimpanan poin gambar.

## Langkah 4: Aktifkan Fitur "Jangan Simpan Gambar Bullet".

Untuk mengaktifkan fitur "Jangan Simpan Gambar Bullet", kami telah mengonfigurasi opsi penyimpanan dengan SavePictureBullet disetel ke false. Hal ini memastikan bahwa poin gambar tidak disimpan dalam dokumen akhir.

## Langkah 5: Simpan dokumen

Terakhir, Anda dapat menyimpan dokumen menggunakan metode Simpan dari kelas Dokumen. Tentukan path lengkap ke file dan nama file yang diinginkan. Misalnya :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Pastikan untuk mengganti "dataDir" dengan jalur direktori ke dokumen Anda.

## Contoh kode sumber untuk opsi penyimpanan DocSaveOptions dengan fungsionalitas "Jangan Simpan Gambar Bullet" menggunakan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen dengan poin gambar
Document doc = new Document(dataDir + "Image bullet points.docx");

// Konfigurasikan opsi penyimpanan dengan fitur "Jangan Simpan Gambar Bullet".
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Simpan dokumen dengan opsi yang ditentukan
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Kesimpulan

Dalam panduan ini, kami membahas cara menonaktifkan penyimpanan poin gambar dalam dokumen menggunakan perpustakaan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi C# Anda. Menonaktifkan penyimpanan poin gambar dapat berguna dalam beberapa situasi untuk mempertahankan struktur dan format dokumen tanpa menyimpan poin gambar.