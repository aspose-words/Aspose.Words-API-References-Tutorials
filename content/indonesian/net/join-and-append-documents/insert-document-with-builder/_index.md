---
title: Sisipkan Dokumen Dengan Pembuat
linktitle: Sisipkan Dokumen Dengan Pembuat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan dua dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah untuk menyisipkan dokumen dengan DocumentBuilder dan mempertahankan pemformatan.
type: docs
weight: 10
url: /id/net/join-and-append-documents/insert-document-with-builder/
---
## Perkenalan

Jadi, Anda memiliki dua dokumen Word, dan Anda ingin menggabungkannya menjadi satu. Anda mungkin berpikir, "Apakah ada cara mudah untuk melakukan ini secara terprogram?" Sangat! Hari ini, saya akan memandu Anda melalui proses memasukkan satu dokumen ke dokumen lain menggunakan perpustakaan Aspose.Words untuk .NET. Metode ini sangat berguna, terutama ketika Anda berurusan dengan dokumen berukuran besar atau perlu mengotomatiskan prosesnya. Mari selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda perlukan:

1.  Aspose.Words untuk .NET: Jika Anda belum melakukannya, Anda dapat mendownloadnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Pastikan Anda telah menginstal Visual Studio atau IDE lain yang sesuai.
3. Pengetahuan Dasar tentang C#: Sedikit keakraban dengan C# akan sangat bermanfaat.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan untuk mengakses fungsi perpustakaan Aspose.Words. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Sekarang kita sudah memiliki prasyaratnya, mari kita uraikan prosesnya langkah demi langkah.

## Langkah 1: Menyiapkan Direktori Dokumen Anda

Sebelum kita mulai membuat kode, Anda perlu menyetel jalur ke direktori dokumen Anda. Di sinilah dokumen sumber dan tujuan Anda disimpan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya di mana dokumen Anda berada. Ini akan membantu program menemukan file Anda dengan mudah.

## Langkah 2: Memuat Dokumen Sumber dan Tujuan

Selanjutnya, kita perlu memuat dokumen yang ingin kita kerjakan. Dalam contoh ini, kita memiliki dokumen sumber dan dokumen tujuan.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Di sini, kami menggunakan`Document` kelas dari perpustakaan Aspose.Words untuk memuat dokumen kita. Pastikan nama file cocok dengan yang ada di direktori Anda.

## Langkah 3: Membuat Objek DocumentBuilder

 Itu`DocumentBuilder` class adalah alat yang ampuh di perpustakaan Aspose.Words. Ini memungkinkan kita menavigasi dan memanipulasi dokumen.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 Pada langkah ini, kami telah membuat a`DocumentBuilder` objek untuk dokumen tujuan kita. Ini akan membantu kami memasukkan konten ke dalam dokumen.

## Langkah 4: Pindah ke Akhir Dokumen

Kita perlu memindahkan kursor pembuat ke akhir dokumen tujuan sebelum memasukkan dokumen sumber.

```csharp
builder.MoveToDocumentEnd();
```

Hal ini memastikan bahwa dokumen sumber disisipkan di akhir dokumen tujuan.

## Langkah 5: Memasukkan Page Break

Agar semuanya tetap rapi, mari tambahkan hentian halaman sebelum menyisipkan dokumen sumber. Ini akan memulai konten dokumen sumber di halaman baru.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Hentian halaman memastikan bahwa konten dokumen sumber dimulai pada halaman baru, membuat dokumen gabungan terlihat profesional.

## Langkah 6: Memasukkan Dokumen Sumber

Sekarang sampai pada bagian yang menarik—memasukkan dokumen sumber ke dalam dokumen tujuan.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 Menggunakan`InsertDocument` metodenya, kita dapat memasukkan seluruh dokumen sumber ke dalam dokumen tujuan. Itu`ImportFormatMode.KeepSourceFormatting` memastikan bahwa format dokumen sumber dipertahankan.

## Langkah 7: Menyimpan Dokumen yang Digabung

Terakhir, mari simpan dokumen yang digabungkan. Ini akan menggabungkan dokumen sumber dan tujuan menjadi satu file.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Dengan menyimpan dokumen tersebut, kita menyelesaikan proses penggabungan kedua dokumen tersebut. Dokumen baru Anda sekarang sudah siap dan disimpan di direktori yang ditentukan.

## Kesimpulan

Dan itu dia! Anda telah berhasil menyisipkan satu dokumen ke dokumen lain menggunakan Aspose.Words untuk .NET. Metode ini tidak hanya efisien tetapi juga menjaga format kedua dokumen, memastikan penggabungan yang mulus. Baik Anda sedang mengerjakan proyek satu kali atau perlu mengotomatiskan pemrosesan dokumen, Aspose.Words untuk .NET siap membantu Anda.

## FAQ

### Apa itu Aspose.Words untuk .NET?  
Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, mengedit, mengonversi, dan memanipulasi dokumen Word secara terprogram.

### Bisakah saya menyimpan format dokumen sumber?  
 Ya, dengan menggunakan`ImportFormatMode.KeepSourceFormatting`, pemformatan dokumen sumber dipertahankan saat disisipkan ke dalam dokumen tujuan.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words untuk .NET?  
 Ya, Aspose.Words untuk .NET memerlukan lisensi untuk fungsionalitas penuh. Anda bisa mendapatkan[izin sementara](https://purchase.aspose.com/temporary-license/) untuk evaluasi.

### Bisakah saya mengotomatiskan proses ini?  
Sangat! Metode yang dijelaskan dapat dimasukkan ke dalam aplikasi yang lebih besar untuk mengotomatisasi tugas pemrosesan dokumen.

### Di mana saya dapat menemukan lebih banyak sumber daya dan dukungan?  
Untuk informasi lebih lanjut, Anda dapat memeriksa[dokumentasi](https://reference.aspose.com/words/net/) , atau kunjungi[forum dukungan](https://forum.aspose.com/c/words/8) untuk bantuan.