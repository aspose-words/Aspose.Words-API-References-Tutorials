---
title: Buat Proyek Vba di Dokumen Word
linktitle: Buat Proyek Vba di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara membuat proyek VBA di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-vba-macros/create-vba-project/
---

Dalam tutorial ini, kami akan memberi tahu Anda cara membuat proyek VBA di dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Membuat proyek VBA memungkinkan Anda menambahkan kode VBA khusus ke dokumen Word Anda. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buat dokumen dan proyek VBA baru
 Selanjutnya, kita akan membuat dokumen baru dengan membuat instance`Document` kelas dan proyek VBA kosong dengan membuat instance`VbaProject` kelas.

```csharp
// Buat dokumen baru
Document doc = new Document();

//Buat proyek VBA baru
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Langkah 3: Buat modul baru dan tentukan kode sumber makro.
 Kami akan membuat modul baru dengan membuat instance`VbaModule` kelas dan menentukan nama makro, jenis (modul prosedural) dan kode sumber.

```csharp
// Buat modul baru
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Tambahkan modul ke proyek VBA
doc.VbaProject.Modules.Add(module);
```

## Langkah 4: Simpan dokumen
Terakhir, kami akan menyimpan dokumen dengan proyek VBA yang dibuat dalam sebuah file.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Contoh kode sumber untuk Membuat Proyek Vba menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Buat modul baru dan tentukan kode sumber makro.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Tambahkan modul ke proyek VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara membuat proyek VBA di dokumen Word menggunakan Aspose.Words untuk .NET. Membuat proyek VBA memungkinkan Anda menambahkan dan menyesuaikan kode VBA di dokumen Word Anda. Jangan ragu untuk menggunakan fitur ini untuk mengotomatiskan tugas atau menambahkan fungsionalitas khusus ke dokumen Word Anda.

### FAQ

#### T: Apa yang dimaksud dengan proyek VBA di dokumen Word?

J: Proyek VBA dalam dokumen Word adalah kumpulan modul VBA yang berisi kode yang dapat digunakan untuk mengotomatiskan tugas, menambahkan fungsionalitas khusus, atau melakukan operasi tertentu dalam dokumen Word.

#### T: Apa saja prasyarat untuk membuat proyek VBA di dokumen Word?

J: Sebelum Anda dapat membuat proyek VBA di dokumen Word, Anda harus memiliki pengetahuan tentang bahasa pemrograman C#. Anda juga perlu menginstal perpustakaan Aspose.Words untuk .NET di proyek Anda.

#### Q: Bagaimana cara mengatur direktori dokumen dalam kode?

 A: Pada kode yang diberikan, Anda perlu menggantinya.`"YOUR DOCUMENTS DIRECTORY"` dengan jalur yang sesuai ke direktori tempat Anda ingin menyimpan dokumen Word Anda dengan proyek VBA.

#### T: Bagaimana cara menentukan kode sumber makro dalam modul VBA?

 A: Untuk menentukan kode sumber makro di modul VBA, Anda dapat menggunakan`SourceCode` properti dari`VbaModule` kelas dengan menugaskannya string karakter yang berisi kode VBA.

#### T: Bisakah saya menambahkan beberapa modul VBA ke proyek VBA di dokumen Word?

J: Ya, Anda dapat menambahkan beberapa modul VBA ke proyek VBA di dokumen Word dengan membuat beberapa modul`VbaModule` objek dan menambahkannya ke`Modules` koleksi`VbaProject` obyek. Hal ini memungkinkan Anda untuk mengatur kode VBA Anda ke dalam modul yang berbeda untuk pengelolaan dan penggunaan kembali yang lebih baik.