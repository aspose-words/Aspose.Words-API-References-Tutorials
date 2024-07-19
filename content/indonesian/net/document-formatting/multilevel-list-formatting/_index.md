---
title: Pemformatan Daftar Bertingkat Dalam Dokumen Word
linktitle: Pemformatan Daftar Bertingkat Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menguasai pemformatan daftar bertingkat di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami. Sempurnakan struktur dokumen dengan mudah.
type: docs
weight: 10
url: /id/net/document-formatting/multilevel-list-formatting/
---
## Perkenalan

Jika Anda seorang pengembang yang ingin mengotomatiskan pembuatan dan pemformatan dokumen Word, Aspose.Words untuk .NET adalah terobosan baru. Hari ini, kita akan mendalami bagaimana Anda bisa menguasai pemformatan daftar bertingkat menggunakan perpustakaan canggih ini. Baik Anda membuat dokumen terstruktur, menguraikan laporan, atau membuat dokumentasi teknis, daftar bertingkat dapat meningkatkan keterbacaan dan pengorganisasian konten Anda.

## Prasyarat

Sebelum kita masuk ke detail seluk beluknya, pastikan Anda memiliki semua yang Anda perlukan untuk mengikuti tutorial ini.

1. Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan. Visual Studio adalah pilihan yang bagus.
2.  Aspose.Words for .NET: Unduh dan instal perpustakaan Aspose.Words for .NET. Kamu bisa mendapatkannya[Di Sini](https://releases.aspose.com/words/net/).
3.  Lisensi: Dapatkan lisensi sementara jika Anda tidak memiliki lisensi penuh. Mendapatkan[Di Sini](https://purchase.aspose.com/temporary-license/).
4. Pengetahuan Dasar C#: Keakraban dengan kerangka C# dan .NET akan bermanfaat.

## Impor Namespace

Untuk menggunakan Aspose.Words untuk .NET di proyek Anda, Anda harus mengimpor namespace yang diperlukan. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
```

## Langkah 1: Inisialisasi Dokumen dan Pembuat Anda

Hal pertama yang pertama, mari buat dokumen Word baru dan inisialisasi DocumentBuilder. Kelas DocumentBuilder menyediakan metode untuk menyisipkan konten ke dalam dokumen.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Terapkan Penomoran Default

 Untuk memulai dengan daftar bernomor, Anda menggunakan`ApplyNumberDefault` metode. Ini mengatur format daftar bernomor default.

```csharp
builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

 Di baris ini,`ApplyNumberDefault` memulai daftar bernomor, dan`Writeln` menambahkan item ke daftar.

## Langkah 3: Indentasi untuk Sublevel

 Selanjutnya, untuk membuat sublevel dalam daftar Anda, Anda menggunakan`ListIndent` metode. Metode ini mengindentasi item daftar, menjadikannya sublevel dari item sebelumnya.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");
```

Cuplikan kode ini mengindentasi item, membuat daftar tingkat kedua.

## Langkah 4: Indentasi Lebih Lanjut untuk Level yang Lebih Dalam

Anda dapat terus membuat indentasi untuk membuat level yang lebih dalam dalam daftar Anda. Di sini, kita akan membuat level ketiga.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");
```

Sekarang Anda memiliki daftar tingkat ketiga di bawah "Item 2.2".

## Langkah 5: Berusaha Kembali ke Tingkat yang Lebih Tinggi

 Untuk kembali ke level yang lebih tinggi, gunakan`ListOutdent` metode. Ini memindahkan item kembali ke tingkat daftar sebelumnya.

```csharp
builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");
```

Hal ini membawa "Item 2.3" kembali ke tingkat kedua.

## Langkah 6: Hapus Penomoran

Setelah selesai dengan daftar, Anda dapat menghapus penomoran untuk melanjutkan dengan teks biasa atau jenis pemformatan lainnya.

```csharp
builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");
builder.ListFormat.RemoveNumbers();
```

Cuplikan kode ini melengkapi daftar dan menghentikan penomoran.

## Langkah 7: Simpan Dokumen Anda

Terakhir, simpan dokumen ke direktori yang Anda inginkan.

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

Ini menyimpan dokumen Anda yang diformat dengan indah dengan daftar bertingkat.

## Kesimpulan

Dan itu dia! Anda telah berhasil membuat daftar bertingkat di dokumen Word menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memungkinkan Anda mengotomatiskan tugas pemformatan dokumen yang rumit dengan mudah. Ingat, menguasai alat-alat ini tidak hanya menghemat waktu tetapi juga memastikan konsistensi dan profesionalisme dalam proses pembuatan dokumen Anda.

## FAQ

### Bisakah saya menyesuaikan gaya penomoran daftar?
 Ya, Aspose.Words untuk .NET memungkinkan Anda menyesuaikan gaya penomoran daftar menggunakan`ListTemplate` kelas.

### Bagaimana cara menambahkan poin-poin, bukan angka?
 Anda dapat menerapkan poin-poin dengan menggunakan`ApplyBulletDefault` metode sebagai gantinya`ApplyNumberDefault`.

### Apakah mungkin untuk melanjutkan penomoran dari daftar sebelumnya?
 Ya, Anda dapat melanjutkan penomoran dengan menggunakan`ListFormat.List` properti untuk ditautkan ke daftar yang ada.

### Bagaimana cara mengubah tingkat indentasi secara dinamis?
 Anda dapat mengubah tingkat indentasi secara dinamis dengan menggunakan`ListIndent`Dan`ListOutdent` metode sesuai kebutuhan.

### Bisakah saya membuat daftar bertingkat dalam format dokumen lain seperti PDF?
Ya, Aspose.Words mendukung penyimpanan dokumen dalam berbagai format termasuk PDF, mempertahankan formatnya.
