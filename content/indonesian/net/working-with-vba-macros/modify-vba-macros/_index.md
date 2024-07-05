---
title: Ubah Makro Vba Dari Dokumen Word
linktitle: Ubah Makro Vba Dari Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mengedit makro VBA dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-vba-macros/modify-vba-macros/
---
Dalam tutorial ini, kami akan menjelaskan cara memodifikasi makro VBA pada dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Mengedit makro VBA memungkinkan Anda memperbarui kode VBA yang ada di dokumen Word Anda. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda
- Dokumen Word berisi makro VBA yang ingin Anda modifikasi

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang berisi makro VBA
Selanjutnya kita akan memuat dokumen Word yang berisi makro VBA yang ingin kita modifikasi.

```csharp
// Muat dokumen yang berisi makro VBA
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Langkah 3: Ubah kode sumber makro
 Kami sekarang akan memodifikasi kode sumber makro pertama proyek VBA. Ganti`newSourceCode` variabel dengan kode sumber baru yang ingin Anda gunakan.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Langkah 4: Simpan dokumen yang dimodifikasi
Terakhir, kami akan menyimpan dokumen yang dimodifikasi dengan makro VBA yang diperbarui ke sebuah file.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Contoh kode sumber untuk Memodifikasi Makro Vba menggunakan Aspose.Words untuk .NET
 
```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mengedit makro VBA di dokumen Word menggunakan Aspose.Words untuk .NET. Mengedit makro VBA memungkinkan Anda memperbarui kode VBA yang ada di dokumen Anda untuk melakukan perubahan atau peningkatan. Jangan ragu untuk menggunakan fitur ini untuk lebih menyesuaikan dan mengotomatiskan dokumen Word Anda.

### FAQ

#### T: Apa yang dimaksud dengan makro VBA di dokumen Word?

J: Makro VBA di dokumen Word adalah bagian kode yang bisa dijalankan untuk melakukan tindakan tertentu di dokumen. Makro VBA memungkinkan Anda mengotomatiskan tugas, menambahkan fungsionalitas khusus, dan berinteraksi dengan konten dokumen.

#### T: Apa saja prasyarat untuk mengedit makro VBA di dokumen Word?

J: Sebelum Anda bisa mengedit makro VBA di dokumen Word, Anda harus memiliki pengetahuan tentang bahasa pemrograman C#. Anda juga perlu menginstal perpustakaan Aspose.Words untuk .NET di proyek Anda. Selain itu, Anda memerlukan dokumen Word yang berisi makro VBA yang ingin Anda modifikasi.

#### Q: Bagaimana cara mengatur direktori dokumen dalam kode?

 A : Pada kode yang diberikan harus anda ganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur yang sesuai ke direktori tempat dokumen Word Anda yang berisi makro VBA berada.

#### T: Bagaimana cara menentukan kode sumber makro baru yang akan diubah?

 A: Untuk menentukan kode sumber baru dari makro yang ingin Anda modifikasi, Anda dapat menggunakan`SourceCode` milik yang bersangkutan`VbaModule` objek dengan menugaskannya string karakter yang berisi kode VBA baru.

#### T: Bisakah saya mengedit beberapa makro VBA dalam satu dokumen Word sekaligus?

 J: Ya, Anda dapat memodifikasi beberapa makro VBA dalam dokumen Word dengan menggunakan loop atau langsung mengakses makro yang sesuai`VbaModule` objek di`Modules` koleksi`VbaProject` obyek. Hal ini memungkinkan Anda memperbarui beberapa makro VBA secara bersamaan dalam satu operasi.