---
title: Sisipkan Tabel Dari Html
linktitle: Sisipkan Tabel Dari Html
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan tabel dari HTML ke dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/insert-table-from-html/
---

Dalam tutorial ini, kita akan mempelajari cara menyisipkan tabel ke dalam dokumen Word dari HTML menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menyisipkan tabel dari HTML ke dalam dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat dokumen dan menginisialisasi pembuat dokumen
Untuk memulai Pemrosesan Kata dengan dokumen dan pembuat dokumen, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen
Document doc = new Document();

// Inisialisasi pembuat dokumen
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Memasukkan tabel dari HTML
Selanjutnya kita akan memasukkan tabel tersebut ke dalam dokumen menggunakan kode HTML. Gunakan kode berikut:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Di sini kita menggunakan`InsertHtml` metode pembuat dokumen untuk memasukkan HTML yang berisi tabel. HTML yang ditentukan membuat tabel dengan dua baris dan dua sel di setiap baris. Anda dapat menyesuaikan isi tabel dengan memodifikasi kode HTML sesuai kebutuhan Anda.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan tabel yang disisipkan dari HTML. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Sisipkan Tabel Dari Html menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Perhatikan bahwa AutoFitSettings tidak berlaku untuk tabel yang disisipkan dari HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyisipkan tabel ke dalam dokumen Word dari HTML menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat menyisipkan tabel dari HTML ke dalam dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda mengonversi dan mengimpor data tabel dari sumber HTML ke dokumen Word Anda.
