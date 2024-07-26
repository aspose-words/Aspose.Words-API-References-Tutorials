---
title: Jenis Kontrol Pilihan Dalam Dokumen Word
linktitle: Jenis Kontrol Pilihan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang formulir kotak kombo di dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah ini untuk integrasi konten HTML yang lancar.
type: docs
weight: 10
url: /id/net/programming-with-htmlloadoptions/preferred-control-type/
---
## Perkenalan

kita menyelami tutorial menarik tentang cara bekerja dengan opsi pemuatan HTML di Aspose.Words untuk .NET, khususnya berfokus pada pengaturan jenis kontrol pilihan saat menyisipkan bidang formulir kotak kombo ke dalam dokumen Word. Panduan langkah demi langkah ini akan membantu Anda memahami cara memanipulasi dan merender konten HTML secara efektif dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita beralih ke kode, ada beberapa hal yang perlu Anda siapkan:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan, seperti Visual Studio.
3. Pengetahuan Dasar C#: Pemahaman mendasar tentang pemrograman C# diperlukan untuk mengikuti tutorial.
4. Konten HTML: Pengetahuan dasar tentang HTML sangat membantu karena kita akan bekerja dengan konten HTML dalam contoh ini.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk memulai:

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.Words;
using Aspose.Words.Loading;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah untuk memastikan kejelasan dan pemahaman.

## Langkah 1: Siapkan Konten HTML Anda

Pertama, kita perlu menentukan konten HTML yang ingin kita masukkan ke dalam dokumen Word. Berikut cuplikan HTML yang akan kami gunakan:

```csharp
const string html = @"
    <html>
        <select name='ComboBox' size='1'>
            <option value='val1'>item1</option>
            <option value='val2'></option>                        
        </select>
    </html>
";
```

HTML ini berisi kotak kombo sederhana dengan dua opsi. Kami akan memuat HTML ini ke dalam dokumen Word dan menentukan cara merendernya.

## Langkah 2: Tentukan Direktori Dokumen

Selanjutnya, tentukan direktori tempat dokumen Word Anda akan disimpan. Ini membantu dalam mengatur file Anda dan menjaga manajemen jalur tetap bersih.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan dokumen Word Anda.

## Langkah 3: Konfigurasikan Opsi Pemuatan HTML

 Di sini, kami mengonfigurasi opsi pemuatan HTML, khususnya berfokus pada`PreferredControlType`Properti. Ini menentukan bagaimana kotak kombo harus dirender dalam dokumen Word.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

 Dengan mengatur`PreferredControlType` ke`HtmlControlType.StructuredDocumentTag`, kami memastikan bahwa kotak kombo ditampilkan sebagai tag dokumen terstruktur (SDT) di dokumen Word.

## Langkah 4: Muat Konten HTML ke dalam Dokumen

Menggunakan opsi pemuatan yang dikonfigurasi, kami memuat konten HTML ke dalam dokumen Word baru.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

Di sini, kami mengonversi string HTML menjadi array byte dan memuatnya ke dalam dokumen menggunakan aliran memori. Hal ini memastikan bahwa konten HTML diinterpretasikan dan dirender dengan benar oleh Aspose.Words.

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang ditentukan dalam format DOCX.

```csharp
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

Ini menyimpan dokumen Word dengan kontrol kotak kombo yang diberikan di lokasi yang ditentukan.

## Kesimpulan

Dan itu dia! Kami telah berhasil menyisipkan bidang formulir kotak kombo ke dalam dokumen Word menggunakan Aspose.Words untuk .NET dengan memanfaatkan opsi pemuatan HTML. Panduan langkah demi langkah ini akan membantu Anda memahami proses dan menerapkannya pada proyek Anda. Baik Anda mengotomatiskan pembuatan dokumen atau memanipulasi konten HTML, Aspose.Words for .NET menyediakan alat canggih untuk mencapai tujuan Anda.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah pustaka manipulasi dokumen canggih yang memungkinkan pengembang membuat, mengedit, mengonversi, dan merender dokumen Word secara terprogram.

### Bisakah saya menggunakan tipe kontrol HTML lain dengan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET mendukung berbagai tipe kontrol HTML. Anda dapat mengkustomisasi bagaimana kontrol yang berbeda dirender dalam dokumen Word.

### Bagaimana cara menangani konten HTML yang kompleks di Aspose.Words untuk .NET?
 Aspose.Words for .NET memberikan dukungan komprehensif untuk HTML, termasuk elemen kompleks. Pastikan Anda mengonfigurasi`HtmlLoadOptions`tepat untuk menangani konten HTML spesifik Anda.

### Di mana saya dapat menemukan lebih banyak contoh dan dokumentasi?
 Anda dapat menemukan dokumentasi rinci dan contoh di[Halaman dokumentasi Aspose.Words untuk .NET](https://reference.aspose.com/words/net/).

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis dari[Asumsikan situs web](https://releases.aspose.com/).
