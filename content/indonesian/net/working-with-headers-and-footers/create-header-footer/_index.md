---
title: Buat Header Footer
linktitle: Buat Header Footer
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat header dan footer di dokumen Word Anda dengan Aspose.Words untuk .NET. Sesuaikan header dan footer untuk setiap halaman.
type: docs
weight: 10
url: /id/net/working-with-headers-and-footers/create-header-footer/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# berikut untuk membuat header dan footer menggunakan Aspose.Words untuk fungsionalitas .NET. Pastikan Anda telah menyertakan perpustakaan Aspose.Words di proyek Anda sebelum menggunakan kode ini.

## Langkah 1: Tetapkan jalur direktori dokumen

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Pastikan untuk menentukan jalur yang benar ke direktori dokumen Anda tempat dokumen yang diedit akan disimpan.

## Langkah 2: Buat dokumen dan pembuat dokumen

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di sini kita membuat sebuah instance dari`Document` kelas dan sebuah instance dari`DocumentBuilder` kelas yang memungkinkan kita memanipulasi dokumen dan menambahkan elemen.

## Langkah 3: Tetapkan parameter halaman dan header pertama

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Tentukan apakah kita ingin header/footer halaman pertama berbeda dengan halaman lainnya.
// Anda juga dapat menggunakan properti PageSetup.OddAndEvenPagesHeaderFooter untuk menentukan
// header/footer yang berbeda untuk halaman ganjil dan genap.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Kami mengatur parameter halaman, termasuk jarak header, dan kemudian berpindah ke header utama (`HeaderPrimary`). Kami menggunakan pembuat dokumen untuk menambahkan teks dan memformat header.

## Langkah 4: Sisipkan gambar dan teks di header utama

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Kami menggunakan pembuat dokumen untuk menyisipkan gambar di sudut kiri atas header utama, lalu kami menambahkan beberapa teks rata kanan.

## Langkah 5: Sisipkan tabel di footer utama

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Langkah 6: Tambahkan halaman baru dan atur header/footer

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Bagian ini tidak memerlukan header/footer yang berbeda untuk halaman pertama, kita hanya memerlukan satu halaman judul dalam dokumen,
//dan header/footer untuk halaman ini telah ditentukan di bagian sebelumnya.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Bagian ini menampilkan header/footer dari bagian sebelumnya secara default, panggil currentSection.HeadersFooters.LinkToPrevious(false) untuk memutus tautan ini,
// lebar halaman berbeda untuk bagian baru, jadi kita perlu mengatur lebar sel yang berbeda untuk tabel footer.
currentSection.HeadersFooters.LinkToPrevious(false);

// Jika kita ingin menggunakan header/footer yang sudah ada untuk bagian ini,
//namun dengan sedikit perubahan, mungkin masuk akal untuk menyalin header/footer
// dari bagian sebelumnya dan terapkan perubahan yang diperlukan sesuai keinginan kita.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Simpan dokumennya
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Kami menambahkan hentian halaman dan hentian bagian untuk membuat halaman baru di mana header/footer utama akan terlihat. Kami mengatur parameter untuk bagian baru, lalu kami menggunakan`CopyHeadersFootersFromPreviousSection` metode untuk menyalin header/footer dari bagian sebelumnya. Terakhir, kami mengatur lebar sel yang sesuai untuk tabel footer utama dan menyimpan dokumen.

### Contoh kode sumber untuk membuat header dan footer dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Tentukan apakah kita ingin header/footer halaman pertama berbeda dengan halaman lainnya.
// Anda juga dapat menggunakan properti PageSetup.OddAndEvenPagesHeaderFooter untuk menentukan
// header/footer yang berbeda untuk halaman ganjil dan genap.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Sisipkan gambar yang diposisikan ke sudut atas/kiri header.
// Jarak dari tepi atas/kiri halaman diatur ke 10 poin.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Kami menggunakan tabel dengan dua sel untuk membuat satu bagian teks per baris (dengan penomoran halaman).
// Untuk disejajarkan ke kiri, dan bagian teks lainnya (dengan hak cipta) disejajarkan ke kanan.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Ia menggunakan bidang PAGE dan NUMPAGES untuk menghitung secara otomatis nomor halaman saat ini dan banyak halaman.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Buat hentian halaman untuk membuat halaman kedua di mana header/footer utama akan terlihat.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Bagian ini tidak memerlukan header/footer halaman pertama yang berbeda, kami hanya memerlukan satu halaman judul dalam dokumen,
//dan header/footer untuk halaman ini telah ditentukan di bagian sebelumnya.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Bagian ini menampilkan header/footer dari bagian sebelumnya
// secara default panggil currentSection.HeadersFooters.LinkToPrevious(false) untuk membatalkan lebar halaman ini
// berbeda untuk bagian baru, dan oleh karena itu kita perlu mengatur lebar sel yang berbeda untuk tabel footer.
currentSection.HeadersFooters.LinkToPrevious(false);

// Jika kita ingin menggunakan set header/footer yang sudah ada untuk bagian ini.
// Namun dengan sedikit modifikasi, mungkin lebih baik menyalin header/footer
// dari bagian sebelumnya dan terapkan modifikasi yang diperlukan sesuai keinginan kita.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### FAQ

#### T: Bagaimana cara menambahkan header ke dokumen saya di Aspose.Words?

 A: Untuk menambahkan header ke dokumen Anda di Aspose.Words, Anda dapat menggunakan`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` metode. Metode ini menambahkan judul utama ke bagian pertama dokumen Anda.

#### T: Bagaimana cara menambahkan footer ke dokumen saya di Aspose.Words?

 A: Untuk menambahkan footer ke dokumen Anda di Aspose.Words, Anda dapat menggunakan`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`metode. Metode ini menambahkan footer utama ke bagian pertama dokumen Anda.

#### T: Bagaimana cara menambahkan teks ke header atau footer saya di Aspose.Words?

 A: Untuk menambahkan teks ke header atau footer Anda di Aspose.Words, Anda dapat menggunakan`HeaderFooter.Paragraphs` properti untuk mendapatkan kumpulan paragraf header atau footer, lalu tambahkan paragraf yang berisi teks Anda ke koleksi ini menggunakan`ParagraphCollection.Add` metode.

#### T: Bisakah saya mengkustomisasi konten header atau footer dengan gambar dan nomor halaman di Aspose.Words?

 A: Ya, Anda dapat menyesuaikan konten header atau footer dengan gambar dan nomor halaman di Aspose.Words. Anda dapat menggunakan objek seperti`Shape` untuk menambahkan gambar dan objek seperti`Field` untuk menambahkan nomor halaman ke header atau footer Anda.

#### T: Bisakah saya mengubah font, ukuran dan warna teks di header atau footer saya di Aspose.Words?

 A: Ya, Anda dapat mengubah font, ukuran dan warna teks di header atau footer Anda di Aspose.Words. Anda dapat mengakses properti pemformatan teks seperti`Font` untuk mengubah font,`Size` untuk menyesuaikan ukuran, dan`Color`untuk mengatur warna teks.