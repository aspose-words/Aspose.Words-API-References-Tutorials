---
title: Ulangi Baris Di Halaman Berikutnya
linktitle: Ulangi Baris Di Halaman Berikutnya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat dokumen Word dengan baris header tabel berulang menggunakan Aspose.Words untuk .NET. Ikuti panduan ini untuk memastikan dokumen profesional dan rapi.
type: docs
weight: 10
url: /id/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---
## Perkenalan

Membuat dokumen Word secara terprogram bisa menjadi tugas yang menakutkan, terutama ketika Anda perlu mempertahankan format di beberapa halaman. Pernahkah Anda mencoba membuat tabel di Word, hanya untuk menyadari bahwa baris header Anda tidak terulang di halaman berikutnya? Jangan takut! Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah memastikan bahwa header tabel Anda berulang di setiap halaman, memberikan tampilan profesional dan halus pada dokumen Anda. Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mencapai hal ini menggunakan contoh kode sederhana dan penjelasan mendetail. Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET: Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. .NET Framework diinstal pada mesin Anda.
3. Visual Studio atau IDE lain yang mendukung pengembangan .NET.
4. Pemahaman dasar pemrograman C#.

Pastikan Anda telah menginstal Aspose.Words untuk .NET dan menyiapkan lingkungan pengembangan Anda sebelum melanjutkan.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Tambahkan arahan penggunaan berikut di bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Namespace ini mencakup kelas dan metode yang diperlukan untuk memanipulasi dokumen dan tabel Word.

## Langkah 1: Inisialisasi Dokumen

 Pertama, mari buat dokumen Word baru dan a`DocumentBuilder` untuk membuat meja kita.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Kode ini menginisialisasi dokumen baru dan a`DocumentBuilder` objek, yang membantu dalam membangun struktur dokumen.

## Langkah 2: Mulai Tabel dan Tentukan Baris Header

Selanjutnya, kita akan memulai tabel dan menentukan baris header yang ingin kita ulangi di halaman berikutnya.

```csharp
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();

builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
```

 Di sini, kita memulai tabel baru, atur`HeadingFormat`properti ke`true` untuk menunjukkan bahwa baris tersebut adalah header, dan menentukan perataan dan lebar sel.

## Langkah 3: Tambahkan Baris Data ke Tabel

Sekarang, kita akan menambahkan beberapa baris data ke tabel kita. Baris-baris ini tidak akan terulang pada halaman berikutnya.

```csharp
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
    builder.InsertCell();
    builder.RowFormat.HeadingFormat = false;
    builder.Write("Column 1 Text");
    
    builder.InsertCell();
    builder.Write("Column 2 Text");
    builder.EndRow();
}
```

 Perulangan ini menyisipkan 50 baris data ke dalam tabel, dengan dua kolom di setiap baris. Itu`HeadingFormat` diatur ke`false` untuk baris ini, karena ini bukan baris header.

## Langkah 4: Simpan Dokumen

Terakhir, kami menyimpan dokumen ke direktori yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Ini menyimpan dokumen dengan nama tertentu di direktori dokumen Anda.

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, Anda dapat membuat dokumen Word dengan tabel yang memiliki baris header berulang di halaman berikutnya menggunakan Aspose.Words untuk .NET. Hal ini tidak hanya meningkatkan keterbacaan dokumen Anda tetapi juga memastikan tampilan yang konsisten dan profesional. Sekarang, silakan dan coba ini di proyek Anda!

## FAQ

### Bisakah saya menyesuaikan baris header lebih lanjut?
 Ya, Anda dapat menerapkan pemformatan tambahan pada baris header dengan memodifikasi properti`ParagraphFormat`, `RowFormat` , Dan`CellFormat`.

### Apakah mungkin menambahkan lebih banyak kolom ke tabel?
 Sangat! Anda dapat menambahkan kolom sebanyak yang diperlukan dengan menyisipkan lebih banyak sel di dalamnya`InsertCell` metode.

### Bagaimana saya bisa mengulangi baris lain di halaman berikutnya?
 Untuk membuat baris mana pun berulang, atur`RowFormat.HeadingFormat`properti ke`true` untuk baris tertentu itu.

### Bisakah saya menggunakan metode ini untuk tabel yang ada di dokumen?
 Ya, Anda dapat mengubah tabel yang ada dengan mengaksesnya melalui`Document` objek dan menerapkan format serupa.

### Opsi pemformatan tabel apa lagi yang tersedia di Aspose.Words untuk .NET?
 Aspose.Words untuk .NET menawarkan berbagai opsi pemformatan tabel, termasuk penggabungan sel, pengaturan batas, dan perataan tabel. Lihat[dokumentasi](https://reference.aspose.com/words/net/) untuk lebih jelasnya.