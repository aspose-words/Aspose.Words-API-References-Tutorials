---
title: Dapatkan Jenis Kata Revisi
linktitle: Dapatkan Jenis Kata Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendapatkan revisi jenis kata dalam dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah ini membantu Anda menangani revisi dokumen secara efisien.
type: docs
weight: 10
url: /id/net/working-with-revisions/get-revision-types/
---
## Perkenalan

Pernahkah Anda tenggelam dalam lautan revisi dokumen, bertanya-tanya siapa yang memindahkan apa dan kapan? Anda tidak sendirian. Menangani revisi dokumen bisa menjadi tugas yang membosankan, terutama jika menangani dokumen yang luas. Tapi, jangan khawatir! Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah mengidentifikasi dan mengelola revisi ini. Dalam panduan ini, kami akan memandu Anda melalui proses langkah demi langkah tentang cara mendapatkan revisi jenis kata dalam dokumen Word menggunakan Aspose.Words untuk .NET. Jadi, kencangkan sabuk pengaman, dan mari selami!

## Prasyarat

Sebelum kita mengotori beberapa kode, ada beberapa hal yang Anda perlukan:

1.  Aspose.Words untuk .NET Library: Jika Anda belum melakukannya, unduh dari[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE lain yang kompatibel dengan .NET.
3. Pengetahuan Dasar C#: Pemahaman bahasa pemrograman C# akan bermanfaat.
4.  Dokumen Word dengan Revisi: Pastikan Anda memiliki a`.docx`file dengan perubahan terlacak untuk menguji kode.

## Impor Namespace

Untuk memulai, Anda harus mengimpor namespace yang diperlukan dalam proyek C# Anda. Ini akan memungkinkan Anda mengakses fungsionalitas yang disediakan oleh Aspose.Words untuk .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Mari kita bagi contoh ini menjadi beberapa langkah untuk pemahaman dan penerapan yang lebih baik.

## Langkah 1: Siapkan Direktori Dokumen Anda

Hal pertama yang pertama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda yang telah direvisi akan ditempatkan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke folder dokumen Anda.

## Langkah 2: Muat Dokumen Word Anda

Selanjutnya, Anda perlu memuat dokumen Word ke dalam proyek Anda. Dokumen ini harus memiliki revisi yang ingin Anda analisis.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Pastikan file tersebut`Revisions.docx` ada di direktori yang ditentukan.

## Langkah 3: Akses Koleksi Paragraf

Sekarang setelah dokumen Anda dimuat, Anda perlu mengakses paragraf di bagian pertama badan dokumen. Ini akan membantu Anda mengulangi setiap paragraf untuk memeriksa revisi.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Langkah 4: Ulangi Paragraf dan Periksa Revisi

Di sinilah keajaiban terjadi. Anda akan mengulangi setiap paragraf dan memeriksa apakah paragraf telah dipindahkan (dihapus atau disisipkan).

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Perulangan ini melewati setiap paragraf dan menggunakan`IsMoveFromRevision`Dan`IsMoveToRevision` properti untuk menentukan apakah paragraf dipindahkan (dihapus) atau dipindahkan (dimasukkan).

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, Anda dapat dengan mudah mengidentifikasi jenis revisi di dokumen Word Anda menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memudahkan penanganan revisi dokumen, memungkinkan Anda fokus pada tugas yang lebih penting. 

## FAQ

### Bisakah saya menggunakan Aspose.Words untuk .NET untuk melacak perubahan yang dibuat oleh pengguna tertentu?

Ya, Aspose.Words untuk .NET menyediakan fungsionalitas untuk mengakses detail revisi, termasuk pembuat perubahan.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?

 Sangat! Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Bagaimana cara menerapkan lisensi sementara untuk Aspose.Words untuk .NET?

 Anda dapat meminta dan menerapkan lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dokumentasi lebih rinci untuk Aspose.Words untuk .NET?

 Dokumentasi terperinci tersedia di[Asumsikan situs web](https://reference.aspose.com/words/net/).

### Bisakah saya menggunakan Aspose.Words untuk .NET dalam proyek non-komersial?

Ya, Aspose.Words untuk .NET dapat digunakan dalam proyek komersial dan non-komersial, namun pastikan untuk memeriksa persyaratan lisensi.