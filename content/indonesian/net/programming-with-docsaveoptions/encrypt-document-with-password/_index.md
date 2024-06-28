---
title: Enkripsi Dokumen Dengan Kata Sandi
linktitle: Enkripsi Dokumen Dengan Kata Sandi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengenkripsi dokumen dengan kata sandi menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Keamanan dokumen sangat penting ketika Pengolahan Kata dengan file dalam aplikasi C#. Dengan pustaka Aspose.Words untuk .NET, Anda dapat dengan mudah melindungi dokumen Anda dengan mengenkripsinya menggunakan kata sandi. Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan kode sumber Aspose.Words untuk .NET C# untuk mengenkripsi dokumen menggunakan opsi penyimpanan DocSaveOptions.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami pustaka Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan yang kuat untuk membuat, mengedit, mengonversi, dan melindungi dokumen Word di berbagai platform termasuk .NET. Ia menawarkan banyak fitur untuk memanipulasi dokumen, seperti menyisipkan teks, mengubah format, menambahkan bagian, dan banyak lagi.

## Langkah 1: Mendefinisikan direktori dokumen

Langkah pertama adalah mengatur direktori tempat Anda ingin menyimpan dokumen terenkripsi. Anda harus menentukan jalur direktori lengkap. Misalnya :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Membuat dan mengedit dokumen

Kemudian Anda dapat membuat dokumen dan menambahkan konten ke dalamnya. Gunakan kelas DocumentBuilder yang disediakan oleh Aspose.Words untuk membuat konten dokumen Anda. Misalnya :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

Dalam contoh ini, kita membuat dokumen kosong baru dan kemudian menggunakan DocumentBuilder untuk menulis teks "Halo Dunia!".

## Langkah 3: Konfigurasikan opsi perekaman

Sekarang mari kita konfigurasikan opsi penyimpanan untuk dokumen kita. Gunakan kelas DocSaveOptions untuk menentukan pengaturan penyimpanan. Misalnya :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

Dalam contoh ini, kita membuat objek DocSaveOptions baru dan mengatur properti Kata Sandi menjadi "kata sandi" untuk mengenkripsi dokumen dengan kata sandi ini.

## Langkah 4: Mengaktifkan Fitur "Enkripsi Dokumen Dengan Kata Sandi".

Kami telah mengonfigurasi opsi untuk

pendaftaran dengan kata sandi yang ditentukan, yang secara otomatis mengaktifkan fitur "Enkripsi Dokumen Dengan Kata Sandi". Hal ini memastikan bahwa dokumen dienkripsi dengan kata sandi yang ditentukan saat disimpan.

## Langkah 5: Menyimpan dokumen

Terakhir, Anda dapat menyimpan dokumen menggunakan metode Simpan dari kelas Dokumen. Tentukan path lengkap ke file dan nama file yang diinginkan. Misalnya :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Pastikan untuk mengganti "dataDir" dengan jalur direktori ke dokumen Anda.

### Contoh kode sumber untuk opsi penyimpanan DocSaveOptions dengan fungsionalitas "Enkripsi Dokumen Dengan Kata Sandi" menggunakan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Membuat dan mengedit dokumen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Konfigurasikan opsi penyimpanan dengan fitur "Enkripsi Dokumen Dengan Kata Sandi".
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Simpan dokumen dengan opsi yang ditentukan
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Kesimpulan

Dalam panduan ini, kami menjelaskan cara menggunakan pustaka Aspose.Words untuk .NET guna mengenkripsi dokumen dengan kata sandi menggunakan opsi penyimpanan DocSaveOptions. Dengan mengikuti langkah-langkah yang disediakan dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah menerapkan fungsi ini di aplikasi C# Anda. Mengenkripsi dokumen dengan kata sandi menjamin kerahasiaan dan keamanannya saat menanganinya.