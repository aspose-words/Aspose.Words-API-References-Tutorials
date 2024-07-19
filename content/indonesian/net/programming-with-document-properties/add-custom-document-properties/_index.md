---
title: Tambahkan Properti Dokumen Kustom
linktitle: Tambahkan Properti Dokumen Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan properti dokumen kustom di file Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk menyempurnakan dokumen Anda dengan metadata tambahan.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/add-custom-document-properties/
---
## Perkenalan

Hai! Apakah Anda mendalami dunia Aspose.Words untuk .NET dan bertanya-tanya bagaimana cara menambahkan properti dokumen khusus ke file Word Anda? Nah, Anda datang ke tempat yang tepat! Properti khusus bisa sangat berguna untuk menyimpan metadata tambahan yang tidak tercakup dalam properti bawaan. Baik itu mengotorisasi dokumen, menambahkan nomor revisi, atau bahkan memasukkan tanggal tertentu, properti khusus siap membantu Anda. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menambahkan properti ini dengan lancar menggunakan Aspose.Words untuk .NET. Siap untuk memulai? Ayo selami!

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang Anda perlukan:

1.  Perpustakaan Aspose.Words untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Words untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: IDE seperti Visual Studio.
3. Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang C# dan .NET.
4.  Contoh Dokumen: Siapkan contoh dokumen Word, beri nama`Properties.docx`, yang akan Anda modifikasi.

## Impor Namespace

Sebelum kita dapat memulai coding, kita perlu mengimpor namespace yang diperlukan. Ini adalah langkah penting untuk memastikan bahwa kode Anda memiliki akses ke semua fungsi yang disediakan oleh Aspose.Words.

```csharp
using System;
using Aspose.Words;
```

## Langkah 1: Menyiapkan Jalur Dokumen

 Hal pertama yang pertama, kita perlu menyiapkan jalur ke dokumen kita. Disinilah kita akan menentukan lokasi kita`Properties.docx` mengajukan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Dalam cuplikan ini, ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda. Langkah ini penting karena memungkinkan program untuk mencari dan membuka file Word Anda.

## Langkah 2: Mengakses Properti Dokumen Kustom

Selanjutnya, mari akses properti dokumen kustom dari dokumen Word. Di sinilah semua metadata khusus Anda akan disimpan.

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
```

Dengan melakukan ini, kita dapat menangani kumpulan properti kustom, yang akan kita kerjakan pada langkah-langkah berikut.

## Langkah 3: Memeriksa Properti yang Ada

Sebelum menambahkan properti baru, ada baiknya untuk memeriksa apakah properti tertentu sudah ada. Hal ini untuk menghindari duplikasi yang tidak perlu.

```csharp
if (customDocumentProperties["Authorized"] != null) return;
```

Baris ini memeriksa apakah properti "Berwenang" sudah ada. Jika ya, program akan keluar dari metode ini lebih awal untuk mencegah penambahan properti duplikat.

## Langkah 4: Menambahkan Properti Boolean

Sekarang, mari tambahkan properti khusus pertama kita—nilai boolean untuk menunjukkan apakah dokumen tersebut diotorisasi.

```csharp
customDocumentProperties.Add("Authorized", true);
```

 Baris ini menambahkan properti khusus bernama "Resmi" dengan nilai`true`. Sederhana dan lugas!

## Langkah 5: Menambahkan Properti String

Selanjutnya, kita akan menambahkan properti khusus lainnya untuk menentukan siapa yang mengizinkan dokumen tersebut.

```csharp
customDocumentProperties.Add("Authorized By", "John Smith");
```

Di sini, kami menambahkan properti bernama "Diotorisasi Oleh" dengan nilai "John Smith". Jangan ragu untuk mengganti "John Smith" dengan nama lain yang Anda sukai.

## Langkah 6: Menambahkan Properti Tanggal

Mari tambahkan properti untuk menyimpan tanggal otorisasi. Ini membantu dalam melacak kapan dokumen tersebut diotorisasi.

```csharp
customDocumentProperties.Add("Authorized Date", DateTime.Today);
```

 Cuplikan ini menambahkan properti bernama "Tanggal Resmi" dengan tanggal saat ini sebagai nilainya. Itu`DateTime.Today`properti secara otomatis mengambil tanggal hari ini.

## Langkah 7: Menambahkan Nomor Revisi

Kita juga dapat menambahkan properti untuk melacak nomor revisi dokumen. Ini sangat berguna untuk kontrol versi.

```csharp
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
```

Di sini, kami menambahkan properti yang disebut "Revisi Resmi" dan menetapkan nomor revisi dokumen saat ini.

## Langkah 8: Menambahkan Properti Numerik

Terakhir, mari tambahkan properti numerik untuk menyimpan jumlah yang diotorisasi. Ini bisa berupa apa saja, mulai dari angka anggaran hingga jumlah transaksi.

```csharp
customDocumentProperties.Add("Authorized Amount", 123.45);
```

 Baris ini menambahkan properti bernama "Authorized Amount" dengan nilai`123.45`. Sekali lagi, jangan ragu untuk menggantinya dengan nomor apa pun yang sesuai dengan kebutuhan Anda.

## Kesimpulan

Dan itu dia! Anda telah berhasil menambahkan properti dokumen kustom ke dokumen Word menggunakan Aspose.Words untuk .NET. Properti ini bisa sangat berguna untuk menyimpan metadata tambahan yang spesifik untuk kebutuhan Anda. Baik Anda melacak detail otorisasi, nomor revisi, atau jumlah tertentu, properti khusus memberikan solusi yang fleksibel.

Ingat, kunci untuk menguasai Aspose.Words untuk .NET adalah latihan. Jadi, teruslah bereksperimen dengan berbagai properti dan lihat bagaimana properti tersebut dapat menyempurnakan dokumen Anda. Selamat membuat kode!

## FAQ

### Apa yang dimaksud dengan properti dokumen kustom?
Properti dokumen kustom adalah metadata yang bisa Anda tambahkan ke dokumen Word untuk menyimpan informasi tambahan yang tidak tercakup dalam properti bawaan.

### Bisakah saya menambahkan properti selain string dan angka?
Ya, Anda bisa menambahkan berbagai tipe properti, termasuk boolean, tanggal, dan bahkan objek khusus.

### Bagaimana cara mengakses properti ini di dokumen Word?
Properti kustom dapat diakses secara terprogram menggunakan Aspose.Words atau dilihat langsung di Word melalui properti dokumen.

### Apakah mungkin untuk mengedit atau menghapus properti khusus?
Ya, Anda dapat dengan mudah mengedit atau menghapus properti khusus menggunakan metode serupa yang disediakan oleh Aspose.Words.

### Bisakah properti khusus digunakan untuk memfilter dokumen?
Sangat! Properti khusus sangat baik untuk mengkategorikan dan memfilter dokumen berdasarkan metadata tertentu.
