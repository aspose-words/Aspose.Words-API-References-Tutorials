---
title: Pindahkan Node Dalam Dokumen yang Dilacak
linktitle: Pindahkan Node Dalam Dokumen yang Dilacak
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memindahkan node dalam dokumen Word yang dilacak menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami yang terperinci. Sempurna untuk pengembang.
type: docs
weight: 10
url: /id/net/working-with-revisions/move-node-in-tracked-document/
---
## Perkenalan

Hai, Aspose. Penggemar kata-kata! Jika Anda pernah perlu memindahkan simpul di dokumen Word sambil melacak revisi, Anda berada di tempat yang tepat. Hari ini, kita akan mempelajari cara mencapai hal ini menggunakan Aspose.Words untuk .NET. Anda tidak hanya akan mempelajari proses langkah demi langkah, namun Anda juga akan mempelajari beberapa tip dan trik untuk membuat manipulasi dokumen Anda lancar dan efisien.

## Prasyarat

Sebelum kita mengotori beberapa kode, pastikan Anda memiliki semua yang Anda butuhkan:

-  Aspose.Words untuk .NET: Unduh[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan .NET: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET yang kompatibel.
- Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang C#.

Punya segalanya? Besar! Mari beralih ke namespace yang perlu kita impor.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan. Ini penting untuk bekerja dengan Aspose.Words dan menangani node dokumen.

```csharp
using Aspose.Words;
using System;
```

Baiklah, mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola. Setiap langkah akan dijelaskan secara rinci untuk memastikan Anda memahami apa yang terjadi di setiap titik.

## Langkah 1: Inisialisasi Dokumen

 Untuk memulai, kita perlu menginisialisasi dokumen baru dan menggunakan a`DocumentBuilder` untuk menambahkan beberapa paragraf.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Menambahkan beberapa paragraf
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");

// Periksa jumlah paragraf awal
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Langkah 2: Mulai Lacak Revisi

Selanjutnya, kita perlu mulai melacak revisi. Ini penting karena memungkinkan kita melihat perubahan yang dilakukan pada dokumen.

```csharp
// Mulai lacak revisi
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Langkah 3: Pindahkan Node

Sekarang sampai pada bagian inti dari tugas kita: memindahkan node dari satu lokasi ke lokasi lain. Kami akan memindahkan paragraf ketiga dan menempatkannya sebelum paragraf pertama.

```csharp
// Tentukan node yang akan dipindahkan dan jangkauan akhirnya
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];

// Pindahkan node dalam rentang yang ditentukan
while (node != endNode)
{
    Node nextNode = node.NextSibling;
    body.InsertBefore(node, referenceNode);
    node = nextNode;
}
```

## Langkah 4: Hentikan Pelacakan Revisi

Setelah kita memindahkan node, kita harus berhenti melacak revisi.

```csharp
// Berhenti melacak revisi
doc.StopTrackRevisions();
```

## Langkah 5: Simpan Dokumen

Terakhir, mari simpan dokumen kita yang telah dimodifikasi ke direktori yang ditentukan.

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");

// Keluarkan jumlah paragraf terakhir
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
```

## Kesimpulan

Dan itu dia! Anda telah berhasil memindahkan simpul dalam dokumen yang dilacak menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memudahkan manipulasi dokumen Word secara terprogram. Baik Anda membuat, mengedit, atau melacak perubahan, Aspose.Words siap membantu Anda. Jadi, silakan dan cobalah. Selamat membuat kode!

## FAQ

### Apa itu Aspose.Words untuk .NET?

Aspose.Words for .NET adalah perpustakaan kelas untuk bekerja dengan dokumen Word secara terprogram. Hal ini memungkinkan pengembang untuk membuat, mengedit, mengkonversi, dan mencetak dokumen Word dalam aplikasi .NET.

### Bagaimana cara melacak revisi dalam dokumen Word menggunakan Aspose.Words?

 Untuk melacak revisi, gunakan`StartTrackRevisions` metode pada`Document` obyek. Ini akan mengaktifkan pelacakan revisi, menunjukkan perubahan apa pun yang dilakukan pada dokumen.

### Bisakah saya memindahkan banyak node di Aspose.Words?

Ya, Anda dapat memindahkan banyak node dengan mengulanginya dan menggunakan metode seperti`InsertBefore` atau`InsertAfter` untuk menempatkannya di lokasi yang diinginkan.

### Bagaimana cara berhenti melacak revisi di Aspose.Words?

 Gunakan`StopTrackRevisions` metode pada`Document` keberatan untuk berhenti melacak revisi.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?

 Anda dapat menemukan dokumentasi terperinci[Di Sini](https://reference.aspose.com/words/net/).