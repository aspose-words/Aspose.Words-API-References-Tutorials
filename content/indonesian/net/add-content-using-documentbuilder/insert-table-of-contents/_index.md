---
title: Sisipkan Daftar Isi Dalam Dokumen Word
linktitle: Sisipkan Daftar Isi Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan daftar isi dalam dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Dalam tutorial komprehensif ini, Anda akan mempelajari cara menyisipkan daftar isi ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat membuat daftar isi dengan judul dan nomor halaman yang sesuai.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan inisialisasi objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Masukkan Daftar Isi
Selanjutnya, gunakan metode InsertTableOfContents dari kelas DocumentBuilder untuk menyisipkan daftar isi. Tentukan opsi pemformatan yang diperlukan dalam metode ini:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Langkah 3: Tambahkan Konten Dokumen
Setelah memasukkan daftar isi, tambahkan isi dokumen sebenarnya. Atur gaya judul yang sesuai menggunakan StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Langkah 4: Perbarui Daftar Isi
Daftar isi yang baru disisipkan pada awalnya akan kosong. Untuk mengisinya, perbarui bidang dalam dokumen:

```csharp
doc.UpdateFields();
```

## Langkah 5: Simpan Dokumen
Setelah memasukkan daftar isi dan memperbarui kolom, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Contoh Source Code Sisipkan Daftar Isi menggunakan Aspose.Words for .NET
Berikut source code lengkap untuk menyisipkan daftar isi menggunakan Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inisialisasi DocumentBuilder dengan objek Dokumen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan daftar isia
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Mulai konten dokumen sebenarnya di halaman kedua.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Daftar isi yang baru disisipkan pada awalnya akan kosong.
// Itu perlu diisi dengan memperbarui bidang dalam dokumen.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara menyisipkan daftar isi ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan memanfaatkan kode sumber yang disediakan, kini Anda dapat membuat daftar isi dengan judul dan nomor halaman yang sesuai untuk dokumen Anda.

### FAQ untuk menyisipkan daftar isi dalam dokumen word

#### Q: Bisakah saya menyesuaikan tampilan daftar isi?

 J: Ya, Anda dapat menyesuaikan tampilan daftar isi dengan memodifikasi opsi pemformatan yang ditentukan dalam`InsertTableOfContents` metode. Parameternya memungkinkan Anda mengontrol nomor halaman, indentasi, dan gaya lainnya.

#### Q: Bagaimana jika saya ingin memasukkan tingkatan judul tertentu dalam daftar isi?

 A: Anda dapat menentukan tingkat judul yang diinginkan untuk dimasukkan ke dalam daftar isi dengan menyesuaikan nilai di dalamnya`InsertTableOfContents` metode. Misalnya menggunakan`"\\o \"1-3\""` akan mencakup pos tingkat 1 hingga 3.

#### Q: Bisakah saya memperbarui daftar isi secara otomatis jika saya melakukan perubahan pada isi dokumen?

 A: Ya, Anda dapat memperbarui daftar isi secara otomatis dengan memanggil`UpdateFields` metode pada dokumen. Ini akan memastikan bahwa setiap perubahan yang dilakukan pada konten dokumen, seperti menambah atau menghapus judul, tercermin dalam daftar isi.

#### T: Bagaimana cara menata tingkat judul di daftar isi secara berbeda?

 J: Anda dapat mengatur gaya tingkat judul secara berbeda dengan menggunakan gaya paragraf berbeda untuk setiap tingkat judul. Dengan menugaskan berbeda`StyleIdentifier` nilai-nilai ke`ParagraphFormat` dari`DocumentBuilder`, Anda dapat membuat gaya berbeda untuk setiap tingkat judul.

#### Q: Apakah mungkin untuk menambahkan format tambahan pada judul di daftar isi?

 J: Ya, Anda dapat menambahkan pemformatan tambahan pada judul di daftar isi, seperti gaya font, warna, atau properti lainnya. Dengan menyesuaikan`Font` properti dari`DocumentBuilder`, Anda dapat menerapkan pemformatan khusus pada judul.