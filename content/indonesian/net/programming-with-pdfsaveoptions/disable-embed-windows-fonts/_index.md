---
title: Kurangi Ukuran PDF dengan Menonaktifkan Font Tersemat
linktitle: Kurangi Ukuran PDF dengan Menonaktifkan Font Tersemat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Kurangi ukuran PDF dengan menonaktifkan font yang disematkan menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk mengoptimalkan dokumen Anda demi penyimpanan dan berbagi yang efisien.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---
## Perkenalan

Mengurangi ukuran file PDF sangat penting untuk penyimpanan yang efisien dan berbagi dengan cepat. Salah satu cara efektif untuk melakukannya adalah dengan menonaktifkan font yang disematkan, terutama ketika font standar sudah tersedia di sebagian besar sistem. Dalam tutorial ini, kita akan mempelajari cara memperkecil ukuran PDF dengan menonaktifkan font yang disematkan menggunakan Aspose.Words untuk .NET. Kami akan memandu setiap langkah untuk memastikan Anda dapat menerapkan ini dengan mudah di proyek Anda sendiri.

## Prasyarat

Sebelum mendalami kodenya, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET: Jika Anda belum melakukannya, unduh dan instal dari[Tautan unduhan](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan .NET: Visual Studio adalah pilihan yang populer.
- Contoh Dokumen Word: Siapkan file DOCX yang ingin Anda konversi ke PDF.

## Impor Namespace

Untuk memulai, pastikan Anda telah mengimpor namespace yang diperlukan ke proyek Anda. Ini memungkinkan Anda untuk mengakses kelas dan metode yang diperlukan untuk tugas kita.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dikelola. Setiap langkah akan memandu Anda menjalani tugas, memastikan Anda memahami apa yang terjadi di setiap titik.

## Langkah 1: Inisialisasi Dokumen Anda

Pertama, kita perlu memuat dokumen Word yang ingin Anda konversi ke PDF. Di sinilah perjalanan Anda dimulai.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Di Sini,`dataDir` adalah pengganti direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya.

## Langkah 2: Konfigurasikan Opsi Penyimpanan PDF

Selanjutnya, kami akan menyiapkan opsi penyimpanan PDF. Di sinilah kami menentukan bahwa kami tidak ingin menyematkan font standar Windows.

```csharp
// PDF keluaran akan disimpan tanpa menyematkan font windows standar.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone
};
```

 Dengan mengatur`FontEmbeddingMode` ke`EmbedNone`, kami menginstruksikan Aspose.Words untuk tidak menyertakan font ini dalam PDF, sehingga mengurangi ukuran file.

## Langkah 3: Simpan Dokumen sebagai PDF

Terakhir, kami menyimpan dokumen sebagai PDF menggunakan opsi penyimpanan yang dikonfigurasi. Inilah saatnya DOCX Anda berubah menjadi PDF ringkas.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur direktori Anda yang sebenarnya sekali lagi. PDF keluaran sekarang akan disimpan di direktori yang ditentukan tanpa font standar yang disematkan.

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda dapat mengurangi ukuran file PDF Anda secara signifikan. Menonaktifkan font yang disematkan adalah cara sederhana namun efektif untuk membuat dokumen Anda lebih ringan dan mudah dibagikan. Aspose.Words untuk .NET membuat proses ini lancar, memastikan Anda dapat mengoptimalkan file Anda dengan sedikit usaha.

## FAQ

### Mengapa saya harus menonaktifkan font yang tertanam dalam PDF?
Menonaktifkan font yang disematkan dapat secara signifikan mengurangi ukuran file PDF, menjadikannya lebih efisien untuk penyimpanan dan lebih cepat untuk dibagikan.

### Apakah PDF akan tetap ditampilkan dengan benar tanpa font yang disematkan?
Ya, selama fontnya standar dan tersedia di sistem tempat PDF dilihat, font tersebut akan ditampilkan dengan benar.

### Bisakah saya menyematkan font tertentu secara selektif saja ke dalam PDF?
Ya, Aspose.Words untuk .NET memungkinkan Anda menyesuaikan font mana yang disematkan, memberikan fleksibilitas dalam cara Anda mengurangi ukuran file.

### Apakah saya memerlukan Aspose.Words untuk .NET untuk menonaktifkan font yang disematkan di PDF?
Ya, Aspose.Words untuk .NET menyediakan fungsionalitas yang diperlukan untuk mengonfigurasi opsi penyematan font dalam PDF.

### Bagaimana cara mendapatkan dukungan jika saya mengalami masalah?
 Anda dapat mengunjungi[Forum dukungan](https://forum.aspose.com/c/words/8) untuk bantuan dengan masalah apa pun yang Anda temui.
