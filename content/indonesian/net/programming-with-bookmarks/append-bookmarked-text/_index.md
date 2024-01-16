---
title: Tambahkan Teks yang Ditandai Dalam Dokumen Word
linktitle: Tambahkan Teks yang Ditandai Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan teks dari penanda di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/append-bookmarked-text/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Tambahkan Teks yang Ditandai di perpustakaan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menambahkan teks yang terdapat dalam penanda tertentu dari dokumen Word ke dokumen lain.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Mendapatkan Paragraf Dari Bookmark

 Sebelum kita mulai menambahkan teks bookmark, kita perlu mendapatkan paragraf yang berisi awal dan akhir bookmark. Hal ini dapat dilakukan dengan mengakses`BookmarkStart` Dan`BookmarkEnd` properti penanda:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Langkah 2: Periksa Paragraf Induk

Kami memeriksa apakah paragraf awal dan akhir memiliki induk yang valid, yaitu apakah paragraf tersebut benar-benar termasuk dalam sebuah paragraf. Jika tidak, kami membuat pengecualian:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Langkah 3: Periksa Induk Paragraf

Kami memeriksa apakah paragraf awal dan akhir memiliki induk yang sama. Jika tidak, itu berarti paragraf tersebut tidak terdapat dalam bagian atau dokumen yang sama, dan kami memberikan pengecualian:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Langkah 4: Salin paragraf

Kami mengulangi node (paragraf) dari paragraf awal hingga paragraf akhir. Untuk setiap node, kami membuat salinan dan mengimpornya ke dalam konteks dokumen tujuan:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Contoh kode sumber untuk Menambahkan Teks yang Ditandai menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk mendemonstrasikan penambahan teks dari bookmark menggunakan Aspose.Words untuk .NET:

```csharp

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

```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Tambahkan Teks yang Ditandai Aspose.Words untuk .NET. Kami telah mengikuti panduan langkah demi langkah untuk mendapatkan paragraf dari bookmark, memverifikasi induk, dan menyalin paragraf ke dokumen lain.

### FAQ untuk menambahkan teks yang ditandai di dokumen Word

#### Q1: Apa saja prasyarat untuk menggunakan fitur "Tambahkan teks dengan bookmark" di Aspose.Words untuk .NET?

J: Untuk menggunakan fungsi "Tambahkan teks dengan bookmark" di Aspose.Words untuk .NET, Anda harus memiliki pengetahuan dasar bahasa C#. Anda juga memerlukan lingkungan pengembangan .NET dengan perpustakaan Aspose.Words terinstal.

#### Q2: Bagaimana cara mendapatkan paragraf yang berisi awal dan akhir penanda di dokumen Word?

J: Untuk mendapatkan paragraf yang berisi awal dan akhir penanda di dokumen Word, Anda dapat mengakses`BookmarkStart` Dan`BookmarkEnd` properti penanda. Berikut ini contoh kodenya:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: Apa yang terjadi jika paragraf awal dan akhir tidak memiliki induk yang sah?

J: Jika paragraf awal dan akhir tidak memiliki induk yang valid, artinya paragraf tersebut sebenarnya bukan paragraf, pengecualian akan diberikan. Situasi ini tidak dapat dikelola saat ini.
