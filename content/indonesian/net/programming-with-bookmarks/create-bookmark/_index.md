---
title: Buat Bookmark Di Dokumen Word
linktitle: Buat Bookmark Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat bookmark di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang mendetail ini. Sempurna untuk navigasi dan pengorganisasian dokumen.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/create-bookmark/
---
## Perkenalan

Membuat bookmark di dokumen Word bisa menjadi terobosan baru, terutama ketika Anda ingin menavigasi dokumen berukuran besar dengan mudah. Hari ini, kita akan memandu proses pembuatan bookmark menggunakan Aspose.Words untuk .NET. Tutorial ini akan membawa Anda langkah demi langkah, memastikan Anda memahami setiap bagian prosesnya. Jadi, mari selami!

## Prasyarat

Sebelum kita mulai, Anda harus memiliki yang berikut ini:

1.  Aspose.Words untuk .NET Library: Unduh dan instal dari[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan .NET lainnya.
3. Pengetahuan Dasar C#: Pemahaman konsep dasar pemrograman C#.

## Impor Namespace

Untuk bekerja dengan Aspose.Words untuk .NET, Anda perlu mengimpor namespace yang diperlukan:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Dokumen dan DocumentBuilder

Inisialisasi Dokumen

Pertama, kita perlu membuat dokumen baru dan menginisialisasi`DocumentBuilder`. Ini adalah titik awal untuk menambahkan konten dan bookmark ke dokumen Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Penjelasan: Itu`Document` objek adalah kanvas Anda. Itu`DocumentBuilder` seperti pena Anda, yang memungkinkan Anda menulis konten dan membuat penanda di dokumen.

## Langkah 2: Buat Bookmark Utama

Memulai dan Mengakhiri Bookmark Utama

Untuk membuat bookmark, Anda perlu menentukan titik awal dan akhir. Di sini, kita akan membuat bookmark bernama "My Bookmark".

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");
```

 Penjelasan: Itu`StartBookmark` metode menandai awal bookmark, dan`Writeln` menambahkan teks di dalam bookmark.

## Langkah 3: Buat Bookmark Bersarang

Tambahkan Bookmark Bersarang di dalam Bookmark Utama

Anda dapat menyarangkan bookmark di dalam bookmark lainnya. Di sini, kami menambahkan "Bookmark Bersarang" di dalam "Bookmark Saya".

```csharp
builder.StartBookmark("Nested Bookmark");
builder.Writeln("Text inside a NestedBookmark.");
builder.EndBookmark("Nested Bookmark");
```

 Penjelasan: Penanda bersarang memungkinkan pengorganisasian konten yang lebih terstruktur dan hierarkis. Itu`EndBookmark` metode menutup bookmark saat ini.

## Langkah 4: Tambahkan Teks di Luar Bookmark Bersarang

Lanjutkan Menambahkan Konten

Setelah bookmark bersarang, kita dapat terus menambahkan lebih banyak konten di dalam bookmark utama.

```csharp
builder.Writeln("Text after Nested Bookmark.");
builder.EndBookmark("My Bookmark");
```

Penjelasan: Ini memastikan bahwa penanda utama mencakup penanda bersarang dan teks tambahan.

## Langkah 5: Konfigurasikan Opsi Penyimpanan PDF

Atur Opsi Penyimpanan PDF untuk Bookmark

Saat menyimpan dokumen sebagai PDF, kita dapat mengonfigurasi opsi untuk menyertakan bookmark.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);
```

 Penjelasan: Itu`PdfSaveOptions` kelas memungkinkan Anda menentukan bagaimana dokumen harus disimpan sebagai PDF. Itu`BookmarksOutlineLevels` properti mendefinisikan hierarki bookmark di PDF.

## Langkah 6: Simpan Dokumen

Simpan Dokumen sebagai PDF

Terakhir, simpan dokumen dengan opsi yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

 Penjelasan: Itu`Save` metode menyimpan dokumen dalam format dan lokasi yang ditentukan. PDF sekarang akan menyertakan bookmark yang kita buat.

## Kesimpulan

Membuat bookmark di dokumen Word menggunakan Aspose.Words untuk .NET sangatlah mudah dan sangat berguna untuk navigasi dan pengorganisasian dokumen. Baik Anda membuat laporan, membuat eBuku, atau mengelola dokumen berukuran besar, bookmark membuat hidup lebih mudah. Ikuti langkah-langkah yang diuraikan dalam tutorial ini, dan Anda akan memiliki PDF yang di-bookmark siap dalam waktu singkat.

## FAQ

### Bisakah saya membuat banyak bookmark pada level berbeda?

Sangat! Anda dapat membuat bookmark sebanyak yang diperlukan dan menentukan tingkat hierarkinya saat menyimpan dokumen sebagai PDF.

### Bagaimana cara memperbarui teks bookmark?

 Anda dapat menavigasi ke bookmark menggunakan`DocumentBuilder.MoveToBookmark` lalu perbarui teksnya.

### Apakah mungkin untuk menghapus bookmark?

 Ya, Anda dapat menghapus bookmark menggunakan`Bookmarks.Remove` metode dengan menentukan nama bookmark.

### Bisakah saya membuat bookmark dalam format lain selain PDF?

Ya, Aspose.Words mendukung bookmark dalam berbagai format, termasuk DOCX, HTML, dan EPUB.

### Bagaimana cara memastikan bookmark muncul dengan benar di PDF?

 Pastikan untuk mendefinisikan`BookmarksOutlineLevels` dengan benar di`PdfSaveOptions`. Ini memastikan penanda disertakan dalam kerangka PDF.