---
title: Jaga Meja Bersama
linktitle: Jaga Meja Bersama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mencegah tabel terpecah antar halaman dalam dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan kami untuk memelihara dokumen yang profesional dan mudah dibaca.
type: docs
weight: 10
url: /id/net/programming-with-tables/keep-table-together/
---
## Perkenalan

Pernahkah Anda merasa frustrasi ketika tabel di dokumen Word Anda terbagi menjadi dua halaman? Ini seperti informasi yang Anda susun dengan cermat tiba-tiba memutuskan untuk berhenti di tengah jalan! Menyatukan tabel dalam satu halaman sangat penting agar mudah dibaca dan disajikan. Entah itu untuk laporan, proposal proyek, atau sekadar dokumen pribadi, pemisahan tabel bisa jadi cukup merepotkan. Beruntung bagi kami, Aspose.Words untuk .NET memiliki cara bagus untuk mengatasi masalah ini. Dalam tutorial ini, kami akan memandu langkah-langkah untuk menjaga tabel Anda tetap utuh dan terlihat tajam. Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET - Jika Anda belum menginstalnya, Anda dapat mendownloadnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. Dokumen Word dengan Tabel - Kita akan bekerja dengan contoh dokumen yang memiliki tabel yang mencakup beberapa halaman.
3. Pengetahuan Dasar C# - Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini akan memberi kita akses ke kelas dan metode yang kita perlukan dari Aspose.Words untuk .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang mudah dan mudah dicerna. Kita akan mulai dengan memuat dokumen kita dan diakhiri dengan menyimpan dokumen yang diperbarui di mana tabelnya tetap menyatu.

## Langkah 1: Muat Dokumen

 Untuk bekerja dengan dokumen Word, kita perlu memuatnya terlebih dahulu. Kami akan menggunakan`Document` kelas untuk ini.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Langkah 2: Akses Tabel

Selanjutnya, kita perlu mendapatkan meja yang ingin kita pertahankan. Kami akan berasumsi bahwa ini adalah tabel pertama dalam dokumen.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Langkah 3: Atur KeepWithNext untuk Paragraf

 Untuk mencegah tabel pecah antar halaman, kita perlu menyetel`KeepWithNext` properti untuk setiap paragraf dalam tabel, kecuali paragraf terakhir pada baris terakhir.

```csharp
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
    cell.EnsureMinimum();
    foreach (Paragraph para in cell.Paragraphs)
    {
        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }
}
```

## Langkah 4: Simpan Dokumen

Terakhir, kami menyimpan dokumen yang diperbarui. Ini akan menerapkan perubahan kami dan memastikan tabel tetap menyatu dalam satu halaman.

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, Anda dapat mencegah tabel terpecah menjadi beberapa halaman di dokumen Word Anda. Solusi sederhana namun efektif ini memastikan tabel Anda tetap rapi dan profesional, sehingga meningkatkan keterbacaan dokumen Anda. Aspose.Words untuk .NET membuat penanganan masalah pemformatan menjadi mudah, memungkinkan Anda fokus pada pembuatan konten yang hebat.

## FAQ

### Bisakah saya menyatukan beberapa tabel menggunakan metode ini?  
Ya, Anda bisa menerapkan logika yang sama ke beberapa tabel dengan mengulangi setiap tabel di dokumen Anda.

### Bagaimana jika meja saya terlalu besar untuk muat dalam satu halaman?  
Jika sebuah tabel terlalu besar untuk ditampung dalam satu halaman, tabel tersebut akan tetap tersebar di seluruh halaman. Metode ini memastikan tabel yang lebih kecil tetap utuh tanpa terpecah.

### Apakah ada cara untuk mengotomatiskan ini untuk semua tabel dalam dokumen?  
 Ya, Anda dapat mengulang semua tabel di dokumen Anda dan menerapkannya`KeepWithNext` properti untuk setiap paragraf.

### Apakah saya memerlukan lisensi berbayar untuk Aspose.Words untuk .NET?  
Anda dapat memulai dengan uji coba gratis dari[Di Sini](https://releases.aspose.com/), namun untuk fungsionalitas penuh, disarankan menggunakan lisensi berbayar.

### Bisakah saya menerapkan pemformatan lain pada tabel sambil tetap menyatukannya?  
Sangat! Anda dapat memformat tabel sesuai kebutuhan sambil memastikan tabel tetap menyatu dalam satu halaman.