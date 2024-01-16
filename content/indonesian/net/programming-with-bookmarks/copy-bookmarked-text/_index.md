---
title: Salin Teks yang Ditandai Dalam Dokumen Word
linktitle: Salin Teks yang Ditandai Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyalin teks bookmark di dokumen Word ke dokumen lain menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/copy-bookmarked-text/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Salin Teks yang Ditandai di pustaka Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menyalin konten penanda tertentu dari dokumen sumber ke dokumen lain.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Memuat Dokumen Sumber

 Sebelum menyalin teks bookmark, kita perlu memuat dokumen sumber ke dalam a`Document` objek menggunakan jalur file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Langkah 2: Mendapatkan bookmark sumber

 Kami menggunakan`Bookmarks` properti rentang dokumen sumber untuk mendapatkan bookmark spesifik yang ingin kita salin:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Langkah 3: Membuat dokumen tujuan

Kami membuat dokumen baru yang akan berfungsi sebagai dokumen tujuan untuk menyalin konten bookmark:

```csharp
Document dstDoc = new Document();
```

## Langkah 4: Menentukan Lokasi Salin

Kami menentukan lokasi di mana kami ingin menambahkan teks yang disalin. Dalam contoh kita, kita menambahkan teks ke akhir isi bagian terakhir dokumen tujuan:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Langkah 5: Impor dan salin teks bookmark

 Kami menggunakan a`NodeImporter`objek untuk mengimpor dan menyalin teks bookmark dari dokumen sumber ke dokumen tujuan:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Contoh kode sumber untuk Menyalin Teks yang Ditandai menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk mendemonstrasikan penyalinan teks dari bookmark menggunakan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Ini adalah bookmark yang isinya ingin kita salin.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Kami akan menambahkan dokumen ini.
	Document dstDoc = new Document();

	// Katakanlah kita akan ditambahkan ke akhir badan bagian terakhir.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Jika Anda mengimpor beberapa kali tanpa satu konteks pun, ini akan menghasilkan banyak gaya yang tercipta.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### Tambahkan Kode Sumber BookmarkedText

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // Ini adalah paragraf yang berisi awal penanda.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // Ini adalah paragraf yang berisi akhir dari bookmark.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // Batasi diri kita pada skenario yang cukup sederhana.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // Kami ingin menyalin semua paragraf dari paragraf awal hingga (dan termasuk) paragraf akhir,
            // oleh karena itu simpul tempat kita berhenti adalah satu setelah paragraf akhir.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //Ini membuat salinan node saat ini dan mengimpornya (membuatnya valid) dalam konteksnya
                // dari dokumen tujuan. Mengimpor berarti menyesuaikan gaya dan pengidentifikasi daftar dengan benar.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Kesimpulan

Dalam artikel ini, kita menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Salin Teks yang Ditandai dari Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk menyalin konten penanda dari dokumen sumber ke dokumen lain.

### FAQ untuk menyalin teks yang diberi bookmark di dokumen Word

#### T: Apa saja persyaratan untuk menggunakan fitur "Salin teks dengan bookmark" di Aspose.Words untuk .NET?

J: Untuk menggunakan fitur "Salin teks dengan bookmark" di Aspose.Words untuk .NET, Anda harus memiliki pengetahuan dasar tentang bahasa C#. Anda juga memerlukan lingkungan pengembangan .NET dengan perpustakaan Aspose.Words terinstal.

#### T: Bagaimana cara memuat dokumen sumber ke Aspose.Words untuk .NET?

 J: Untuk memuat dokumen sumber di Aspose.Words untuk .NET, Anda dapat menggunakan`Document` kelas dengan menentukan jalur file dokumen. Berikut ini contoh kodenya:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### T: Bagaimana cara mendapatkan konten bookmark tertentu dalam dokumen sumber menggunakan Aspose.Words untuk .NET?

 J: Untuk mendapatkan konten bookmark tertentu dalam dokumen sumber menggunakan Aspose.Words untuk .NET, Anda dapat mengakses`Bookmarks` properti rentang dokumen sumber dan gunakan nama bookmark untuk mengambil bookmark tertentu. Berikut ini contoh kodenya:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### T: Bagaimana cara menentukan lokasi salinan teks bookmark di dokumen tujuan menggunakan Aspose.Words untuk .NET?

 J: Untuk menentukan di mana Anda ingin menambahkan teks bookmark yang disalin di dokumen tujuan menggunakan Aspose.Words untuk .NET, Anda dapat menavigasi ke isi bagian terakhir dokumen tujuan. Anda dapat menggunakan`LastSection` properti untuk mengakses bagian terakhir dan`Body` properti untuk mengakses isi bagian itu. Berikut ini contoh kodenya:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### T: Bagaimana cara mengimpor dan menyalin teks bookmark dari dokumen sumber ke dokumen tujuan menggunakan Aspose.Words untuk .NET?

 J: Untuk mengimpor dan menyalin teks bookmark dari dokumen sumber ke dokumen tujuan menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`NodeImporter` kelas yang menentukan dokumen sumber, dokumen tujuan, dan mode pemformatan yang akan disimpan. Kemudian Anda dapat menggunakan`AppendBookmarkedText` metode untuk menambahkan teks bookmark di dokumen tujuan. Berikut ini contoh kodenya:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### T: Bagaimana cara menyimpan dokumen tujuan setelah menyalin teks bookmark menggunakan Aspose.Words untuk .NET?

J: Untuk menyimpan dokumen tujuan setelah menyalin teks dari bookmark menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Save` metode`Document` objek yang menentukan jalur file tujuan. Berikut ini contoh kodenya:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```