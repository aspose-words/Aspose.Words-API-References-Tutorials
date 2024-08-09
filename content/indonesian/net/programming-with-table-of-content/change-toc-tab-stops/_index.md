---
title: Ubah Toc Tab Stop di Dokumen Word
linktitle: Ubah Toc Tab Stop di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah perhentian tab TOC di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah ini akan membantu Anda membuat Daftar Isi yang terlihat profesional.
type: docs
weight: 10
url: /id/net/programming-with-table-of-content/change-toc-tab-stops/
---
## Perkenalan

Pernah bertanya-tanya bagaimana cara meramaikan Daftar Isi (TOC) di dokumen Word Anda? Mungkin Anda ingin tab stop tersebut sejajar sempurna untuk sentuhan profesional. Anda berada di tempat yang tepat! Hari ini, kami mendalami cara mengubah perhentian tab TOC menggunakan Aspose.Words untuk .NET. Tetaplah di sini, dan saya berjanji Anda akan menyelesaikannya dengan semua pengetahuan untuk membuat TOC Anda terlihat menarik dan rapi.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words untuk .NET: Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE apa pun yang kompatibel dengan C#.
3. Dokumen Word: Khususnya, dokumen yang berisi TOC.

Punya semua itu? Luar biasa! Ayo berguling.

## Impor Namespace

Hal pertama yang pertama, Anda harus mengimpor namespace yang diperlukan. Ini seperti mengemas peralatan Anda sebelum memulai sebuah proyek.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Mari kita bagi proses ini menjadi langkah-langkah sederhana dan mudah dicerna. Kita akan memuat dokumen, memodifikasi perhentian tab TOC, dan menyimpan dokumen yang diperbarui.

## Langkah 1: Muat Dokumen

Mengapa? Kita perlu mengakses dokumen Word yang berisi TOC yang ingin kita modifikasi.

Bagaimana? Berikut cuplikan kode sederhana untuk Anda mulai:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen yang berisi daftar isi
Document doc = new Document(dataDir + "Table of contents.docx");
```

Bayangkan dokumen Anda seperti kue, dan kami akan menambahkan sedikit lapisan gula. Langkah pertama adalah mengeluarkan kue itu dari kotaknya.

## Langkah 2: Identifikasi Paragraf Daftar Isi

Mengapa? Kita perlu menunjukkan dengan tepat paragraf-paragraf yang membentuk TOC. 

Bagaimana? Ulangi paragraf dan periksa gayanya:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // Paragraf TOC ditemukan
    }
}
```

Anggap saja seperti memindai kerumunan untuk menemukan teman Anda. Di sini, kami mencari paragraf dengan gaya entri TOC.

## Langkah 3: Ubah Tab Stop

Mengapa? Di sinilah keajaiban terjadi. Mengubah perhentian tab membuat TOC Anda terlihat lebih bersih.

Bagaimana? Hapus tab stop yang ada dan tambahkan yang baru pada posisi yang diubah:

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

Ini seperti menyesuaikan furnitur di ruang tamu Anda hingga terasa pas. Kami mengubah perhentian tab tersebut untuk kesempurnaan.

## Langkah 4: Simpan Dokumen yang Dimodifikasi

Mengapa? Untuk memastikan semua kerja keras Anda disimpan dan dapat dilihat atau dibagikan.

Bagaimana? Simpan dokumen dengan nama baru agar aslinya tetap utuh:

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Dan voila! TOC Anda sekarang memiliki tab berhenti tepat di tempat yang Anda inginkan.

## Kesimpulan

Mengubah perhentian tab TOC di dokumen Word menggunakan Aspose.Words untuk .NET sangatlah mudah setelah Anda menguraikannya. Dengan memuat dokumen Anda, mengidentifikasi paragraf TOC, memodifikasi tab stop, dan menyimpan dokumen, Anda dapat memperoleh tampilan yang halus dan profesional. Ingat, latihan membuat sempurna, jadi teruslah bereksperimen dengan posisi tab stop yang berbeda untuk mendapatkan tata letak persis yang Anda inginkan.

## FAQ

### Bisakah saya mengubah perhentian tab untuk level TOC yang berbeda secara terpisah?
Ya kamu bisa! Cukup periksa setiap level TOC tertentu (Toc1, Toc2, dll.) dan sesuaikan.

### Bagaimana jika dokumen saya memiliki beberapa TOC?
Kode memindai semua paragraf bergaya TOC, sehingga akan mengubah semua TOC yang ada dalam dokumen.

### Apakah mungkin untuk menambahkan beberapa tab stop di entri TOC?
 Sangat! Anda dapat menambahkan perhentian tab sebanyak yang diperlukan dengan menyesuaikan`para.ParagraphFormat.TabStops` koleksi.

### Bisakah saya mengubah perataan tab stop dan gaya pemimpin?
Ya, Anda dapat menentukan perataan dan gaya pemimpin yang berbeda saat menambahkan perhentian tab baru.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words untuk .NET?
 Ya, Anda memerlukan lisensi yang valid untuk menggunakan Aspose.Words untuk .NET di luar masa uji coba. Anda bisa mendapatkan[izin sementara](https://purchase.aspose.com/temporary-license/) atau[beli satu](https://purchase.aspose.com/buy).