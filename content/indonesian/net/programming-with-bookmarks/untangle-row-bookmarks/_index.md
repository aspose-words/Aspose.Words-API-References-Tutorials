---
title: Menguraikan Penanda Baris Dalam Dokumen Word
linktitle: Menguraikan Penanda Baris Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menguraikan penanda baris bersarang di dokumen Word untuk menghapus baris tertentu tanpa memengaruhi penanda lainnya.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Dalam artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Untangle Row Bookmarks di pustaka Aspose.Words untuk .NET. Fungsi ini memungkinkan untuk meletakkan ujung penanda garis pada baris yang sama dengan awal penanda.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Memuat dokumen

 Kami menggunakan`Document` kelas untuk memuat dokumen yang ada dari file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Langkah 2: Mengurai Penanda Garis

 Kami menggunakan`Untangle` berfungsi untuk mengurai bookmark dari baris. Fungsi ini melakukan tugas khusus untuk meletakkan ujung baris penanda pada baris yang sama dengan permulaan penanda:

```csharp
Untangle(doc);
```

## Langkah 3: Hapus baris demi bookmark

 Kami menggunakan`DeleteRowByBookmark` berfungsi untuk menghapus baris tertentu berdasarkan penandanya:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Langkah 4: Periksa integritas bookmark lainnya

Kami memverifikasi bahwa bookmark lainnya tidak rusak dengan memeriksa apakah bagian akhir bookmark masih ada:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Contoh kode sumber untuk Untangle Row Bookmarks menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk menguraikan bookmark dari baris menggunakan Aspose.Words untuk .NET:


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Ini melakukan tugas khusus untuk meletakkan ujung penanda baris ke dalam baris yang sama dengan awal penanda.
	Untangle(doc);

	// Sekarang kita dapat dengan mudah menghapus baris berdasarkan penanda tanpa merusak penanda baris lainnya.
	DeleteRowByBookmark(doc, "ROW2");

	// Ini hanya untuk memastikan bahwa bookmark lainnya tidak rusak.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Menguraikan kode sumber
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Dapatkan baris induk dari node akhir bookmark dan bookmark.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Jika kedua baris ditemukan baik-baik saja, dan awal dan akhir penanda berada di baris yang berdekatan,
                // pindahkan simpul akhir penanda ke akhir paragraf terakhir di sel terakhir baris atas.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### Kode sumber DeleteRowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fitur Untangle Row Bookmarks dari Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk menguraikan penanda baris dan menghapus baris tertentu tanpa merusak penanda lainnya.

### FAQ untuk menguraikan bookmark baris di dokumen Word

#### T: Apakah Unscramble Row Bookmarks hanya berfungsi dengan bookmark baris dalam tabel?

A: Ya, fitur Untangle Row Bookmarks dirancang khusus untuk mengurai baris bookmark yang ada di tabel. Fungsi ini dapat digunakan untuk memproses penanda baris dalam array dan memastikan bahwa ujung penanda berada di baris yang sama dengan awal penanda.

#### T: Apakah fungsi Unscramble Line Bookmarks mengubah konten dokumen asli?

J: Ya, fungsi Uraikan penanda baris memodifikasi dokumen asli dengan menggerakkan ujung penanda baris untuk menempatkannya pada baris yang sama dengan awal penanda. Pastikan untuk menyimpan salinan cadangan dokumen sebelum menerapkan fitur ini.

#### T: Bagaimana cara mengidentifikasi penanda garis di dokumen Word saya?

J: Penanda baris biasanya digunakan dalam tabel untuk menandai bagian tertentu. Anda dapat mengidentifikasi penanda baris dengan menelusuri penanda di dokumen dan memeriksa apakah penanda berada di baris tabel.

#### T: Apakah mungkin untuk mengurai penanda baris pada tabel yang tidak bersebelahan?

J: Fungsi Untangle Row Bookmarks seperti yang disajikan dalam artikel ini dirancang untuk menguraikan bookmark baris di tabel yang berdekatan. Untuk menguraikan penanda baris dalam tabel yang tidak berdekatan, penyesuaian tambahan pada kode mungkin diperlukan tergantung pada struktur dokumen.

#### T: Manipulasi apa lagi yang dapat saya lakukan pada penanda baris setelah diurai?

A: Setelah penanda garis terurai, Anda dapat melakukan berbagai manipulasi sesuai kebutuhan. Ini mungkin termasuk mengedit, menghapus, atau menambahkan konten ke baris yang ditandai. Pastikan untuk menangani penanda garis dengan hati-hati untuk menghindari dampak yang tidak diinginkan pada sisa dokumen.