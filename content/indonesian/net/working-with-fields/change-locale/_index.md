---
title: Ubah Lokal
linktitle: Ubah Lokal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah lokal untuk pemformatan tanggal dan angka di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/change-locale/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses mengubah lokal di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengubah lokal, Anda dapat mengontrol format tanggal dan angka selama operasi gabungan surat. Kami akan memberi Anda kode sumber C# yang diperlukan dan petunjuk langkah demi langkah untuk mencapai hal ini.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen dan DocumentBuilder
Untuk memulai, buat sebuah instance dari kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Bidang
Selanjutnya, masukkan bidang gabungan ke dalam dokumen menggunakan metode SisipkanField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Dalam kode di atas, kita menyisipkan kolom gabungan bernama "Tanggal" ke dalam dokumen.

## Langkah 3: Ubah Lokal
Untuk mengubah lokal format tanggal dan angka, Anda dapat mengubah budaya thread saat ini. Dalam contoh ini, kita akan menyetel lokal ke Jerman ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Dalam kode di atas, kita menyimpan budaya saat ini dan kemudian mengatur budaya thread saat ini ke bahasa Jerman.

## Langkah 4: Lakukan Penggabungan Surat
Lakukan operasi gabungan surat dan berikan nilai tanggal untuk bidang "Tanggal":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

Dalam cuplikan kode ini, kami menjalankan operasi gabungan surat dan memberikan tanggal saat ini sebagai nilai untuk bidang "Tanggal".

## Langkah 5: Kembalikan Lokal Asli
Setelah gabungan surat selesai, kembalikan budaya asli untuk thread:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Pada kode di atas, kami mengembalikan budaya asli thread.

## Langkah 6: Simpan Dokumen
Simpan dokumen yang dimodifikasi ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Contoh Source Code untuk Mengubah Lokal menggunakan Aspose.Words for .NET
Berikut kode sumber lengkap untuk mengubah lokal di dokumen Word menggunakan Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengubah lokal di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda kini dapat mengontrol format tanggal dan angka selama operasi gabungan surat. Sesuaikan lokal sesuai dengan kebutuhan Anda untuk memastikan pemformatan yang akurat dan konsisten dalam dokumen Anda.

### FAQ

#### T: Apakah Aspose.Words kompatibel dengan versi Microsoft Word yang berbeda?

J: Ya, Aspose.Words kompatibel dengan berbagai versi Microsoft Word termasuk Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, dan Word 2019.

#### T: Apakah Aspose.Words mendukung struktur bidang yang kompleks?

J: Tentu saja! Aspose.Words menawarkan dukungan ekstensif untuk struktur bidang yang kompleks, termasuk bidang bertumpuk, penghitungan, dan ekspresi kondisional. Anda dapat menggunakan API canggih ini untuk bekerja dengan semua jenis struktur bidang.

#### T: Apakah Aspose.Words mendukung operasi pembaruan lapangan?

J: Ya, Aspose.Words memungkinkan Anda memperbarui bidang sesuai jadwal. Anda dapat dengan mudah memperbarui nilai bidang, menyegarkan perhitungan, dan melakukan operasi terkait bidang lainnya menggunakan API.

#### T: Apakah mungkin untuk mengonversi kolom menjadi teks biasa menggunakan Aspose.Words?

J: Tentu saja! Aspose.Words menyediakan metode untuk mengubah bidang menjadi teks biasa. Ini dapat berguna ketika Anda perlu mengekstraksi konten tanpa pemformatan atau fungsionalitas terkait bidang apa pun.

#### T: Apakah mungkin membuat dokumen Word dengan bidang dinamis menggunakan Aspose.Words?

J: Tentu saja! Aspose.Words menawarkan fungsionalitas yang kuat untuk menghasilkan dokumen Word dengan bidang dinamis. Anda dapat membuat templat dengan bidang yang telah ditentukan sebelumnya dan mengisinya dengan data secara dinamis, memberikan solusi yang fleksibel dan efisien untuk pembuatan dokumen.