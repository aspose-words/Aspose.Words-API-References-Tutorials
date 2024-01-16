---
title: Bagian Tidak Terbatas Dalam Dokumen Word
linktitle: Bagian Tidak Terbatas Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan bagian yang tidak dibatasi dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-protection/unrestricted-section/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur bagian tidak terbatas Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menentukan bagian tertentu dalam dokumen Word yang tidak diproteksi, meskipun bagian dokumen lainnya diproteksi. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Bagian

Mulailah dengan membuat instance kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Tambahkan konten ke dokumen
Gunakan objek DocumentBuilder untuk menambahkan konten ke dokumen dan menyisipkan hentian bagian:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Langkah 3: Lindungi Dokumen dan Bagian

Perlindungan bagian hanya berfungsi ketika perlindungan dokumen diaktifkan dan hanya pengeditan di bidang formulir yang diperbolehkan. Anda dapat melindungi dokumen menggunakan metode Protect() pada objek Dokumen:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Pastikan untuk menentukan jenis perlindungan yang benar dan mengatur kata sandi yang diinginkan.

## Langkah 4: Menonaktifkan perlindungan untuk bagian tertentu

Secara default, semua bagian dilindungi, tetapi Anda dapat menonaktifkan perlindungan secara selektif untuk bagian tertentu menggunakan properti ProtectedForForms dari objek Bagian:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Dalam contoh ini, perlindungan dinonaktifkan untuk bagian pertama.

## Langkah 5: Simpan dokumen

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen dengan bagian yang tidak dibatasi.

### Contoh kode sumber untuk Bagian Tidak Terbatas menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk bagian tidak dibatasi menggunakan Aspose.Words untuk .NET:


```csharp

// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Sisipkan dua bagian dengan beberapa teks.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Perlindungan bagian hanya berfungsi ketika perlindungan dokumen diaktifkan dan hanya pengeditan di bidang formulir yang diperbolehkan.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Secara default, semua bagian dilindungi, tetapi kita dapat menonaktifkan perlindungan secara selektif.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Dengan mengikuti langkah-langkah ini, Anda akan dapat dengan mudah menentukan bagian yang tidak dibatasi dalam dokumen Word Anda dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur bagian tidak terbatas dari Aspose.Words untuk .NET, yang memungkinkan bagian tertentu dalam dokumen Word tetap tidak terlindungi sementara bagian dokumen lainnya dilindungi. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menentukan bagian dalam dokumen tempat pengguna dapat dengan bebas mengedit konten sambil menjaga perlindungan untuk bagian lainnya. Aspose.Words untuk .NET menawarkan kemampuan canggih untuk perlindungan dan penyesuaian dokumen, memberi Anda kendali atas izin pengeditan dalam dokumen Word Anda.

### FAQ untuk bagian tidak terbatas dalam dokumen Word

#### T: Apa saja bagian yang tidak dibatasi di Aspose.Words untuk .NET?

J: Bagian yang tidak dibatasi di Aspose.Words untuk .NET adalah bagian tertentu dalam dokumen Word yang tidak dilindungi, meskipun bagian dokumen lainnya dilindungi. Bagian ini memungkinkan pengguna untuk mengubah konten di dalamnya sambil menjaga perlindungan untuk bagian lain dari dokumen.

#### T: Bagaimana cara membuat bagian tidak dibatasi menggunakan Aspose.Words untuk .NET?

J: Untuk membuat bagian yang tidak dibatasi dalam dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat sebuah instance dari`Document` kelas dan a`DocumentBuilder` obyek.
2.  Menggunakan`DocumentBuilder` untuk menambahkan konten ke dokumen dan menyisipkan hentian bagian.
3.  Lindungi dokumen menggunakan`Protect` metode`Document` objek, menentukan jenis perlindungan dan kata sandi yang diinginkan.
4.  Nonaktifkan perlindungan untuk bagian tertentu dengan mengatur`ProtectedForForms` milik yang bersangkutan`Section` objek untuk`false`.
5. Simpan dokumen yang diubah.

#### T: Dapatkah saya memiliki beberapa bagian yang tidak dibatasi dalam dokumen Word?

 J: Ya, Anda dapat memiliki beberapa bagian yang tidak dibatasi dalam dokumen Word. Dengan menonaktifkan perlindungan secara selektif untuk bagian tertentu menggunakan`ProtectedForForms` properti dari`Section`objek, Anda dapat menentukan beberapa bagian di mana pengguna dapat dengan bebas memodifikasi konten sambil menjaga bagian lain tetap terlindungi.

#### Q4. Bisakah saya menghapus perlindungan dari bagian yang awalnya dilindungi?
 Ya, Anda dapat menghapus perlindungan dari bagian yang awalnya dilindungi dengan mengatur`ProtectedForForms` milik yang bersangkutan`Section` objek untuk`false`. Ini memungkinkan pengguna untuk mengedit konten dalam bagian tertentu tanpa batasan apa pun.

#### T: Tipe perlindungan apa yang bisa diterapkan pada dokumen Word?

J: Aspose.Words for .NET menyediakan berbagai jenis perlindungan yang dapat diterapkan pada dokumen Word, antara lain:
- Tanpa Perlindungan: Tidak ada perlindungan yang diterapkan.
- AllowOnlyRevisions: Pengguna hanya dapat melakukan revisi pada dokumen.
- AllowOnlyComments: Pengguna hanya dapat menambahkan komentar ke dokumen.
- AllowOnlyFormFields: Pengguna hanya dapat mengedit kolom formulir di dokumen.
- ReadOnly: Dokumen bersifat read-only, dan pengeditan tidak diperbolehkan.


