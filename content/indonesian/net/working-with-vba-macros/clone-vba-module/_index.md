---
title: Mengkloning Modul Vba dari Dokumen Word
linktitle: Mengkloning Modul Vba dari Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mengkloning modul VBA dari dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-vba-macros/clone-vba-module/
---

Dalam tutorial ini, kami akan memberi tahu Anda cara mengkloning modul VBA dari dokumen Word dengan makro menggunakan perpustakaan Aspose.Words untuk .NET. Mengkloning modul VBA memungkinkan Anda menggunakan kembali atau menyalin kode VBA dari satu dokumen sumber ke dokumen lain. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda
- Dokumen Word yang berisi proyek VBA dengan modul yang ingin Anda tiru

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen sumber
Selanjutnya, kita akan memuat dokumen sumber Word, yang berisi proyek VBA dan modul yang ingin kita kloning.

```csharp
// Muat dokumen sumber
Document doc = new Document(dataDir + "VBA project.docm");
```

## Langkah 3: Buat dokumen baru dengan proyek VBA dan klon modulnya
Kami akan membuat dokumen baru dengan proyek VBA kosong dan mengkloning modul yang ditentukan dari dokumen sumber.

```csharp
// Buat dokumen baru dengan proyek VBA kosong
Document destDoc = new Document { VbaProject = new VbaProject() };

// Kloning modulnya
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Langkah 4: Simpan dokumen tujuan
Terakhir, kami akan menyimpan dokumen tujuan dengan modul VBA yang dikloning ke sebuah file.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Contoh kode sumber untuk Modul Clone Vba menggunakan Aspose.Words untuk .NET 
```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mengkloning modul VBA dari dokumen Word dengan makro menggunakan Aspose.Words untuk .NET. Mengkloning modul VBA memungkinkan Anda dengan mudah menggunakan kembali kode VBA dari satu dokumen sumber di dokumen lain. Jangan ragu untuk menggunakan fitur ini untuk mengatur dan mengelola makro Anda di berbagai dokumen.

### FAQ

#### T: Apa yang dimaksud dengan menduplikasi modul VBA?

J: Menduplikasi modul VBA terdiri dari menyalin modul yang berisi kode VBA dari dokumen sumber Word ke dokumen lain. Ini memungkinkan Anda untuk menggunakan kembali kode VBA dalam konteks berbeda atau membagikannya dengan dokumen lain.

#### T: Apa saja prasyarat untuk mengkloning modul VBA dari dokumen Word?

J: Sebelum Anda dapat mengkloning modul VBA dari dokumen Word, Anda harus memiliki pengetahuan tentang bahasa pemrograman C#. Anda juga perlu menginstal perpustakaan Aspose.Words untuk .NET di proyek Anda. Selain itu, Anda memerlukan dokumen Word yang berisi proyek VBA dengan modul yang ingin Anda tiru.

#### Q: Bagaimana cara mengatur direktori dokumen dalam kode?

 A: Dalam kode yang diberikan, Anda perlu mengganti.`"YOUR DOCUMENTS DIRECTORY"` dengan jalur yang sesuai ke direktori tempat dokumen Word Anda yang berisi proyek VBA berada.

#### Q: Bagaimana cara menyimpan dokumen tujuan dengan modul VBA yang dikloning?

 A: Untuk menyimpan dokumen tujuan dengan modul VBA yang dikloning, Anda dapat menggunakan`Save` metode`Document` kelas dengan menentukan jalur tujuan dan nama file yang diinginkan.