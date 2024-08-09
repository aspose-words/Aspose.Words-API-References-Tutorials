---
title: Mulai Ulang Daftar Di Setiap Bagian
linktitle: Mulai Ulang Daftar Di Setiap Bagian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memulai ulang daftar di setiap bagian dalam dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami yang terperinci untuk mengelola daftar secara efektif.
type: docs
weight: 10
url: /id/net/working-with-list/restart-list-at-each-section/
---
## Perkenalan

Membuat dokumen yang terstruktur dan terorganisir dengan baik terkadang terasa seperti memecahkan teka-teki yang rumit. Salah satu bagian dari teka-teki itu adalah mengelola daftar secara efektif, terutama ketika Anda ingin daftar tersebut dimulai ulang di setiap bagian. Dengan Aspose.Words untuk .NET, Anda dapat melakukannya dengan lancar. Mari selami bagaimana Anda bisa memulai ulang daftar di setiap bagian dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET: Unduh dan instal versi terbaru dari[Asumsikan Rilis](https://releases.aspose.com/words/net/) halaman.
2. Lingkungan .NET: Siapkan lingkungan pengembangan Anda dengan .NET terinstal.
3. Pemahaman Dasar C#: Disarankan untuk menguasai bahasa pemrograman C#.
4.  Lisensi Aspose: Anda dapat memilih a[izin sementara](https://purchase.aspose.com/temporary-license/) jika Anda tidak memilikinya.

## Impor Namespace

Sebelum menulis kode, pastikan Anda mengimpor namespace yang diperlukan:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

Sekarang, mari kita bagi prosesnya menjadi beberapa langkah agar mudah diikuti.

## Langkah 1: Inisialisasi Dokumen

Pertama, Anda harus membuat instance dokumen baru.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Tambahkan Daftar Bernomor

Selanjutnya, tambahkan daftar bernomor ke dokumen. Daftar ini akan mengikuti format penomoran default.

```csharp
doc.Lists.Add(ListTemplate.NumberDefault);
```

## Langkah 3: Akses Daftar dan Atur Properti Restart

Ambil daftar yang baru saja Anda buat dan atur`IsRestartAtEachSection`properti ke`true`. Hal ini memastikan daftar dimulai ulang penomorannya pada setiap bagian baru.

```csharp
List list = doc.Lists[0];
list.IsRestartAtEachSection = true;
```

## Langkah 4: Buat Pembuat Dokumen dan Kaitkan Daftarnya

 Buat sebuah`DocumentBuilder` untuk menyisipkan konten ke dalam dokumen dan mengaitkannya dengan daftar.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;
```

## Langkah 5: Tambahkan Item Daftar dan Sisipkan Hentian Bagian

Sekarang, tambahkan item ke daftar. Untuk mengilustrasikan fungsionalitas mulai ulang, kami akan menyisipkan hentian bagian setelah sejumlah item tertentu.

```csharp
for (int i = 1; i < 45; i++)
{
    builder.Writeln($"List item {i}");

    if (i == 15)
        builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

## Langkah 6: Simpan Dokumen

Terakhir, simpan dokumen dengan opsi yang sesuai untuk memastikan kepatuhan.

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };
doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah memulai ulang daftar di setiap bagian dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET. Fitur ini sangat berguna untuk membuat dokumen terstruktur dengan baik yang memerlukan bagian terpisah dengan penomoran daftarnya sendiri. Dengan Aspose.Words, menangani tugas-tugas seperti itu menjadi mudah, memungkinkan Anda fokus pada pembuatan konten berkualitas tinggi.

## FAQ

### Bisakah saya memulai ulang daftar di setiap bagian untuk tipe daftar yang berbeda?
Ya, Aspose.Words untuk .NET memungkinkan Anda memulai ulang berbagai tipe daftar, termasuk daftar poin dan nomor.

### Bagaimana jika saya ingin menyesuaikan format penomoran?
 Anda dapat menyesuaikan format penomoran dengan memodifikasi`ListTemplate` properti saat membuat daftar.

### Apakah ada batasan jumlah item dalam daftar?
Tidak, tidak ada batasan khusus mengenai jumlah item yang dapat Anda miliki dalam daftar menggunakan Aspose.Words untuk .NET.

### Bisakah saya menggunakan fitur ini dalam format dokumen lain seperti PDF?
Ya, Anda dapat menggunakan Aspose.Words untuk mengonversi dokumen Word ke format lain seperti PDF dengan tetap mempertahankan struktur daftar.

### Bagaimana saya bisa mendapatkan uji coba gratis Aspose.Words untuk .NET?
 Anda bisa mendapatkan uji coba gratis dari[Asumsikan Rilis](https://releases.aspose.com/) halaman.