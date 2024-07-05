---
title: Wilayah yang Dapat Diedit Tidak Terbatas di Dokumen Word
linktitle: Wilayah yang Dapat Diedit Tidak Terbatas di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat area yang dapat diedit tanpa batas di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-protection/unrestricted-editable-regions/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur area yang dapat diedit tidak terbatas di Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menentukan area dalam dokumen Word di mana konten dapat diedit tanpa batasan, meskipun bagian dokumen lainnya bersifat baca-saja. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen dan mengatur proteksi

Mulailah dengan memuat dokumen yang ada:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Lindungi dokumen dengan mengatur jenis perlindungan read-only dan kata sandi

## Langkah 2: Membuat area yang dapat diedit

Mulailah dengan membuat area yang dapat diedit menggunakan objek EditableRangeStart dan EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Objek EditableRange dibuat untuk EditableRangeStart yang baru saja kita buat.
EditableRange editableRange = edRangeStart.EditableRange;

// Letakkan sesuatu di dalam rentang yang dapat diedit.
builder.Writeln("Paragraph inside first editable range");

// Rentang yang dapat diedit terbentuk dengan baik jika memiliki awal dan akhir.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Langkah 3: Tambahkan konten di luar area yang dapat diedit

Anda dapat menambahkan konten di luar area yang dapat diedit, yang akan tetap hanya dapat dibaca:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Langkah 4: Simpan dokumen

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen dengan area yang dapat diedit.

### Contoh kode sumber untuk Wilayah yang Dapat Diedit Tidak Terbatas menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk area yang dapat diedit tanpa batas menggunakan Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Unggah dokumen dan jadikan sebagai hanya-baca.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Mulai rentang yang dapat diedit.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Objek EditableRange dibuat untuk EditableRangeStart yang baru saja kita buat.
EditableRange editableRange = edRangeStart.EditableRange;

// Letakkan sesuatu di dalam rentang yang dapat diedit.
builder.Writeln("Paragraph inside first editable range");

// Rentang yang dapat diedit terbentuk dengan baik jika memiliki awal dan akhir.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah membuat area yang dapat diedit tanpa batas di dokumen Word Anda dengan Aspose.Words untuk .NET.

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara membuat wilayah yang dapat diedit tanpa batas di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat menentukan area tertentu dalam dokumen tempat pengguna dapat dengan bebas mengedit konten sambil menjaga bagian dokumen lainnya hanya dapat dibaca. Aspose.Words untuk .NET menawarkan fitur canggih untuk perlindungan dan penyesuaian dokumen, memberi Anda kendali atas kemampuan pengeditan dokumen Word Anda.

### FAQ untuk wilayah yang dapat diedit tanpa batas di dokumen Word

#### T: Apa saja wilayah yang dapat diedit tanpa batas di Aspose.Words untuk .NET?

J: Wilayah yang dapat diedit tidak dibatasi di Aspose.Words untuk .NET adalah area dalam dokumen Word di mana konten dapat diedit tanpa batasan apa pun, meskipun bagian dokumen lainnya disetel sebagai hanya-baca. Wilayah ini menyediakan cara untuk menentukan bagian tertentu dari dokumen yang dapat diubah oleh pengguna sambil mempertahankan perlindungan dokumen secara keseluruhan.

#### T: Bagaimana cara membuat wilayah yang dapat diedit tanpa batas menggunakan Aspose.Words untuk .NET?

J: Untuk membuat wilayah yang dapat diedit tanpa batas di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Muat dokumen yang ada menggunakan`Document` kelas.
2.  Atur perlindungan dokumen ke hanya-baca menggunakan`Protect` metode`Document` obyek.
3.  Menggunakan`DocumentBuilder` kelas untuk membuat rentang yang dapat diedit dengan menambahkan`EditableRangeStart` objek dan sebuah`EditableRangeEnd` obyek.
4.  Tambahkan konten dalam rentang yang dapat diedit menggunakan`DocumentBuilder`.
5.  Simpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` obyek.

#### T: Dapatkah saya memiliki beberapa wilayah yang dapat diedit tanpa batas dalam satu dokumen Word?

J: Ya, Anda dapat memiliki beberapa wilayah yang dapat diedit tanpa batas dalam dokumen Word. Untuk mencapai hal ini, Anda dapat membuat beberapa set`EditableRangeStart` Dan`EditableRangeEnd` objek menggunakan`DocumentBuilder` kelas. Setiap kumpulan objek akan menentukan wilayah terpisah yang dapat diedit di mana pengguna dapat mengubah konten tanpa batasan apa pun.

#### T: Bisakah saya menyatukan wilayah yang dapat diedit satu sama lain?

 J: Tidak, Anda tidak dapat menyatukan wilayah yang dapat diedit satu sama lain menggunakan Aspose.Words untuk .NET. Setiap wilayah yang dapat diedit ditentukan oleh`EditableRangeStart` Dan`EditableRangeEnd` pasangan harus independen dan tidak tumpang tindih atau bersarang di wilayah lain yang dapat diedit. Wilayah bertingkat yang dapat diedit tidak didukung.

#### T: Dapatkah saya menghapus perlindungan hanya-baca dari dokumen dalam wilayah yang dapat diedit?

J: Tidak, Anda tidak dapat menghapus perlindungan hanya-baca dari dokumen dalam wilayah yang dapat diedit. Perlindungan hanya-baca diterapkan ke seluruh dokumen, dan tidak dapat dihapus secara selektif dalam wilayah tertentu yang dapat diedit. Tujuan dari wilayah yang dapat diedit adalah untuk memungkinkan modifikasi konten sekaligus menjaga keseluruhan dokumen hanya dapat dibaca.