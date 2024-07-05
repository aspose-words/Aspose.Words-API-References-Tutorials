---
title: Ubah Toc Tab Stop di Dokumen Word
linktitle: Ubah Toc Tab Stop di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah tab daftar isi di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words untuk .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi dokumen Word dalam aplikasi C#. Di antara fungsi yang ditawarkan oleh Aspose.Words, terdapat kemungkinan untuk mengubah tab yang digunakan dalam daftar isi dokumen Word. Dalam panduan ini, kami akan menunjukkan cara menggunakan kode sumber C# Aspose.Words untuk .NET untuk mengubah tab di daftar isi dokumen.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami pustaka Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan populer yang membuat Pemrosesan Kata dengan dokumen Word menjadi mudah dan efisien. Ia menawarkan berbagai fitur untuk membuat, mengedit, dan memanipulasi dokumen Word, termasuk mengubah tab daftar isi.

## Memuat dokumen yang berisi daftar isi

Langkah pertama adalah memuat dokumen Word yang berisi daftar isi yang ingin Anda modifikasi. Gunakan kelas Dokumen untuk memuat dokumen dari file sumber. Berikut ini contohnya:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Dalam contoh ini, kita memuat dokumen "Daftar Isi.docx" yang terletak di direktori dokumen.

## Mengubah tab di daftar isi

Setelah dokumen dimuat, kami memeriksa setiap paragraf dokumen dan memeriksa apakah dokumen tersebut diformat menggunakan gaya hasil Daftar Isi (TOC). Jika sudah, kita modifikasi tab yang digunakan untuk menyelaraskan nomor halaman. Begini caranya:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

Dalam contoh ini, kami menggunakan loop untuk mengulang setiap paragraf dalam dokumen. Kami kemudian memeriksa apakah paragraf diformat menggunakan gaya Hasil Daftar Isi (TOC). Jika demikian, kita mengakses tab pertama yang digunakan dalam paragraf ini dan memodifikasinya dengan menghapus tab lama dan menambahkan tab baru dengan posisi yang dimodifikasi.

## Simpan dokumen yang dimodifikasi

Setelah Anda membuat perubahan yang diperlukan pada tab di daftar isi, Anda dapat menyimpan dokumen yang dimodifikasi menggunakan metode Simpan dari kelas Dokumen. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Dalam contoh ini, kami menyimpan dokumen yang dimodifikasi sebagai "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Contoh kode sumber untuk fitur "Edit Tab Daftar Isi" dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen yang berisi daftar isi
Document doc = new Document(dataDir + "Table of contents.docx");

// Ubah tab daftar isi
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Kesimpulan

Dalam panduan ini, kami telah membahas cara menggunakan Aspose.Words untuk .NET untuk mengubah tab di daftar isi dokumen Word menggunakan kode sumber C# yang disediakan. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menyesuaikan tab daftar isi di dokumen Word Anda di aplikasi C# Anda. Aspose.Words menawarkan fleksibilitas dan kemampuan luar biasa untuk bekerja dengan gaya dan format dokumen Anda, memungkinkan Anda membuat dokumen Word yang menarik dan profesional.

### FAQ untuk mengubah tab berhenti di dokumen Word

#### T: Apa tujuan fungsionalitas "Ubah Penghentian Tab Toc di Dokumen Word" di Aspose.Words untuk .NET?

J: Fungsionalitas "Ubah Perhentian Tab Toc di Dokumen Word" di Aspose.Words untuk .NET memungkinkan Anda mengubah perhentian tab yang digunakan dalam daftar isi dokumen Word. Ini memungkinkan Anda untuk menyesuaikan perataan dan posisi nomor halaman dan judul terkait dalam daftar isi.

#### T: Apa itu Aspose.Words untuk .NET?

J: Aspose.Words for .NET adalah perpustakaan canggih yang dirancang untuk Pemrosesan Kata dengan dokumen Word di aplikasi .NET. Ini menyediakan fitur komprehensif untuk membuat, mengedit, memanipulasi, dan mengonversi dokumen Word secara terprogram menggunakan C# atau bahasa .NET lainnya.

#### T: Bagaimana cara memuat dokumen Word yang berisi daftar isi menggunakan Aspose.Words untuk .NET?

 J: Untuk memuat dokumen Word yang berisi daftar isi menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Document` kelas dan konstruktornya. Dengan menyediakan jalur file dokumen, Anda dapat memuatnya ke dalam a`Document` obyek. Berikut ini contohnya:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Cuplikan kode ini memuat dokumen "Daftar Isi.docx" yang terletak di direktori yang ditentukan.

#### T: Bagaimana cara mengubah tab yang digunakan dalam daftar isi menggunakan Aspose.Words untuk .NET?

 J: Setelah dokumen dimuat, Anda dapat mengulangi setiap paragraf dokumen dan memeriksa apakah dokumen tersebut diformat menggunakan gaya hasil Daftar Isi (TOC). Jika paragraf diformat sebagai gaya TOC, Anda dapat memodifikasi tab yang digunakan untuk menyelaraskan nomor halaman. Di Aspose.Words untuk .NET, Anda dapat mengakses`ParagraphFormat` properti setiap paragraf untuk mengambil dan memodifikasi tab stop. Berikut ini contohnya:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Dalam kode ini, perulangan mengulangi setiap paragraf dalam dokumen. Jika sebuah paragraf memiliki gaya TOC, paragraf tersebut mengakses perhentian tab pertama yang digunakan dalam paragraf tersebut, menghapusnya, dan menambahkan perhentian tab baru dengan posisi yang diubah.

#### T: Bisakah saya mengubah tab untuk beberapa level di daftar isi menggunakan Aspose.Words untuk .NET?

A: Ya, Anda dapat mengubah tab untuk beberapa tingkatan di daftar isi menggunakan Aspose.Words untuk .NET. Dengan mengulangi setiap paragraf dan memeriksa gaya TOC, Anda dapat memodifikasi tab untuk setiap level satu per satu. Anda dapat mengakses tingkat daftar isi yang diinginkan dan menyesuaikan perhentian tab.

#### T: Bagaimana cara menyimpan dokumen yang dimodifikasi setelah mengubah tab di daftar isi menggunakan Aspose.Words untuk .NET?

 A: Setelah melakukan perubahan yang diperlukan pada tab di daftar isi, Anda dapat menyimpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` kelas. Berikan jalur file dan nama yang diinginkan untuk dokumen keluaran sebagai parameter ke`Save` metode. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Kode ini menyimpan dokumen yang dimodifikasi sebagai "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### T: Bisakah saya mengkustomisasi aspek lain dari daftar isi menggunakan Aspose.Words untuk .NET?

J: Ya, dengan Aspose.Words for .NET, Anda dapat menyesuaikan berbagai aspek daftar isi. Selain mengubah tab, Anda dapat mengubah gaya font, ukuran, perataan, dan properti pemformatan lainnya dari entri daftar isi dan nomor halaman. Selain itu, Anda dapat menyesuaikan indentasi, spasi, dan format judul terkait.

#### Q:. Bisakah saya mengubah perataan tab dan karakter pemimpin untuk daftar isi menggunakan Aspose.Words untuk .NET?

A: Ya, Anda dapat mengubah perataan tab dan karakter pemimpin untuk daftar isi menggunakan Aspose.Words untuk .NET. Dengan mengakses perhentian tab dan menyesuaikan properti perataan dan pemimpinnya, Anda dapat mengontrol perataan dan tampilan visual nomor halaman dan judul terkait di daftar isi.

#### T: Apakah Aspose.Words untuk .NET mendukung perubahan gaya dan pemformatan lain di dokumen Word?

J: Ya, Aspose.Words untuk .NET menyediakan dukungan ekstensif untuk mengubah berbagai gaya dan pemformatan dalam dokumen Word. Ini memungkinkan Anda mengubah gaya untuk berbagai elemen seperti paragraf, judul, tabel, daftar, dan banyak lagi. Anda dapat mengubah font, warna, perataan, lekukan, spasi, dan aspek pemformatan lainnya sesuai kebutuhan Anda.

#### T: Bisakah saya mengubah tab di daftar isi dokumen Word yang sudah ada menggunakan Aspose.Words untuk .NET?

J: Ya, Anda dapat memodifikasi tab di daftar isi dokumen Word yang sudah ada menggunakan Aspose.Words untuk .NET. Dengan memuat dokumen, mengulangi paragraf, dan membuat perubahan yang diperlukan pada perhentian tab, Anda dapat memperbarui tab di daftar isi. Terakhir, simpan dokumen untuk menerapkan modifikasi.