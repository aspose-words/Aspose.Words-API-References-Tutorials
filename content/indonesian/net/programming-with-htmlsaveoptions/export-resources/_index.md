---
title: Ekspor Sumber Daya
linktitle: Ekspor Sumber Daya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor sumber daya seperti CSS dan font sambil menyimpan dokumen Word sebagai HTML menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-resources/
---
## Perkenalan

Hai, rekan penggila teknologi! Jika Anda pernah merasa perlu mengonversi dokumen Word ke HTML, Anda berada di tempat yang tepat. Hari ini, kita menyelami dunia Aspose.Words yang menakjubkan untuk .NET. Pustaka canggih ini memudahkan Anda bekerja dengan dokumen Word secara terprogram. Dalam tutorial ini, kita akan memandu langkah-langkah untuk mengekspor sumber daya, seperti font dan CSS, saat menyimpan dokumen Word sebagai HTML menggunakan Aspose.Words untuk .NET. Bersiaplah untuk perjalanan yang menyenangkan dan informatif!

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki semua yang Anda perlukan untuk memulai. Berikut daftar periksa singkatnya:

1.  Visual Studio: Pastikan Anda telah menginstal Visual Studio di mesin Anda. Anda dapat mengunduhnya dari[Situs web Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words untuk .NET: Anda memerlukan perpustakaan Aspose.Words untuk .NET. Jika Anda belum mendapatkannya, dapatkan uji coba gratis dari[Asumsikan Rilis](https://releases.aspose.com/words/net/) atau membelinya dari[Asumsikan Toko](https://purchase.aspose.com/buy).
3. Pengetahuan Dasar tentang C#: Pemahaman mendasar tentang C# akan membantu Anda mengikuti contoh kode.

Punya semua itu? Besar! Mari beralih ke mengimpor namespace yang diperlukan.

## Impor Namespace

Untuk menggunakan Aspose.Words untuk .NET, Anda perlu menyertakan namespace yang relevan dalam proyek Anda. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Namespace ini sangat penting untuk mengakses kelas dan metode Aspose.Words yang akan kita gunakan dalam tutorial kita.

Mari kita uraikan proses mengekspor sumber daya saat menyimpan dokumen Word sebagai HTML. Kami akan melakukannya selangkah demi selangkah, sehingga mudah diikuti.

## Langkah 1: Siapkan Direktori Dokumen Anda

Hal pertama yang pertama, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda berada dan tempat file HTML akan disimpan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori Anda.

## Langkah 2: Muat Dokumen Word

 Selanjutnya, muat dokumen Word yang ingin Anda konversi ke HTML. Untuk tutorial ini, kita akan menggunakan dokumen bernama`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Baris kode ini memuat dokumen dari direktori yang ditentukan.

## Langkah 3: Konfigurasikan Opsi Penyimpanan HTML

Untuk mengekspor sumber daya seperti CSS dan font, Anda perlu mengonfigurasi`HtmlSaveOptions`. Langkah ini penting untuk memastikan keluaran HTML Anda terstruktur dengan baik dan mencakup sumber daya yang diperlukan.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://contoh.com/resources"
};
```

Mari kita uraikan fungsi masing-masing opsi:
- `CssStyleSheetType = CssStyleSheetType.External`: Opsi ini menentukan bahwa gaya CSS harus disimpan dalam stylesheet eksternal.
- `ExportFontResources = true`: Ini memungkinkan ekspor sumber daya font.
- `ResourceFolder = dataDir + "Resources"`: Menentukan folder lokal tempat sumber daya (seperti font dan file CSS) akan disimpan.
- `ResourceFolderAlias = "http://example.com/resources"`: Menetapkan alias untuk folder sumber daya, yang akan digunakan dalam file HTML.

## Langkah 4: Simpan Dokumen sebagai HTML

Dengan opsi penyimpanan yang dikonfigurasi, langkah terakhir adalah menyimpan dokumen sebagai file HTML. Inilah cara Anda melakukannya:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Baris kode ini menyimpan dokumen dalam format HTML, bersama dengan sumber daya yang diekspor.

## Kesimpulan

Dan itu dia! Anda telah berhasil mengekspor sumber daya sambil menyimpan dokumen Word sebagai HTML menggunakan Aspose.Words untuk .NET. Dengan perpustakaan canggih ini, menangani dokumen Word secara terprogram menjadi sangat mudah. Baik Anda sedang mengerjakan aplikasi web atau hanya perlu mengonversi dokumen untuk penggunaan offline, Aspose.Words siap membantu Anda.

## FAQ

### Bisakah saya mengekspor gambar beserta font dan CSS?
 Ya kamu bisa! Aspose.Words untuk .NET juga mendukung ekspor gambar. Pastikan untuk mengkonfigurasi`HtmlSaveOptions` demikian.

### Apakah ada cara untuk menyematkan CSS daripada menggunakan stylesheet eksternal?
 Sangat. Anda dapat mengatur`CssStyleSheetType` ke`CssStyleSheetType.Embedded` jika Anda lebih suka gaya yang disematkan.

### Bagaimana cara menyesuaikan nama file HTML keluaran?
 Anda dapat menentukan nama file apa pun yang Anda suka di`doc.Save` metode. Misalnya,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Apakah Aspose.Words mendukung format lain selain HTML?
 Ya, ini mendukung berbagai format termasuk PDF, DOCX, TXT, dan banyak lagi. Lihat[dokumentasi](https://reference.aspose.com/words/net/) untuk daftar lengkap.

### Di mana saya bisa mendapatkan lebih banyak dukungan dan sumber daya?
Untuk bantuan lebih lanjut, kunjungi[Forum Dukungan Aspose.Words](https://forum.aspose.com/c/words/8) . Anda juga dapat menemukan dokumentasi dan contoh terperinci di[Asumsikan situs web](https://reference.aspose.com/words/net/).