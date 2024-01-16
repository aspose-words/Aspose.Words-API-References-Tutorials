---
title: Pemformatan Daftar Bertingkat Dalam Dokumen Word
linktitle: Pemformatan Daftar Bertingkat Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat daftar bertingkat dan menerapkan pemformatan khusus di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-formatting/multilevel-list-formatting/
---
Dalam tutorial ini, kami akan menunjukkan cara menggunakan pemformatan daftar bertingkat di fitur dokumen Word dengan Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerapkan perubahan.

## Langkah 1: Membuat dan mengonfigurasi dokumen

Untuk memulai, buat dokumen baru dan objek DocumentBuilder terkait. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Memformat daftar bertingkat

Kami sekarang akan menerapkan pemformatan daftar bertingkat menggunakan metode yang tersedia di objek DocumentBuilder. Begini caranya:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Langkah 3: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save` metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Contoh kode sumber untuk Pemformatan Daftar Bertingkat menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fitur pemformatan daftar bertingkat dengan Aspose.Words for .NET:


```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Dengan kode ini Anda akan dapat membuat daftar multi-level dan menerapkan pemformatan yang tepat untuk setiap level menggunakan Aspose.Words untuk .NET.


## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi proses pemanfaatan fitur pemformatan daftar bertingkat dalam dokumen Word dengan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat membuat daftar yang terorganisir dengan baik dengan berbagai tingkatan, sehingga meningkatkan struktur dan keterbacaan dokumen Anda.

### FAQ

#### T: Apa yang dimaksud dengan daftar bertingkat dalam dokumen Word?

J: Daftar bertingkat dalam dokumen Word adalah daftar hierarki yang memungkinkan Anda mengatur item ke dalam berbagai tingkat sub-item. Ini membantu menyajikan informasi secara terstruktur, sehingga memudahkan pembaca untuk memahami isinya.

#### T: Dapatkah saya menyesuaikan tampilan daftar bertingkat?

A: Ya, Anda dapat menyesuaikan tampilan daftar bertingkat di dokumen Word Anda. Dengan menerapkan gaya yang berbeda, seperti poin-poin, angka, atau huruf, dan menyesuaikan indentasi dan spasi, Anda dapat membuat daftar yang menarik dan terorganisir secara visual.

#### T: Apakah Aspose.Words untuk .NET mendukung opsi pemformatan daftar lainnya?

J: Ya, Aspose.Words untuk .NET menyediakan serangkaian fitur lengkap untuk pemformatan daftar. Ini mendukung berbagai tipe daftar, termasuk daftar berpoin, daftar bernomor, dan daftar bertingkat. Anda dapat memanipulasi format daftar, menambah atau menghapus item, dan menyesuaikan tampilannya.

#### T: Bisakah saya menggunakan Aspose.Words for .NET untuk bekerja dengan elemen dokumen lainnya?

J: Ya, Aspose.Words untuk .NET menawarkan kemampuan ekstensif untuk bekerja dengan berbagai elemen dokumen, seperti paragraf, tabel, gambar, dan lainnya. Ini memungkinkan Anda membuat, memodifikasi, dan mengonversi dokumen Word secara terprogram, menyederhanakan tugas pemrosesan dokumen.