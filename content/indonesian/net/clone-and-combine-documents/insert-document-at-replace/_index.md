---
title: Sisipkan Dokumen Saat Ganti
linktitle: Sisipkan Dokumen Saat Ganti
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan satu dokumen Word ke dokumen lain dengan lancar menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami yang terperinci. Sempurna untuk pengembang yang ingin menyederhanakan pemrosesan dokumen.
type: docs
weight: 10
url: /id/net/clone-and-combine-documents/insert-document-at-replace/
---
## Perkenalan

Hai, maestro dokumentasi! Pernahkah Anda menemukan diri Anda terlalu mendalami kode, mencoba mencari cara untuk menyisipkan satu dokumen Word ke dokumen Word lainnya dengan lancar? Jangan takut, karena hari ini kita akan mendalami dunia Aspose.Words untuk .NET agar tugas tersebut menjadi mudah. Kami akan membahas panduan langkah demi langkah yang terperinci tentang cara menggunakan perpustakaan canggih ini untuk menyisipkan dokumen pada titik tertentu selama operasi pencarian dan penggantian. Siap menjadi penyihir Aspose.Words? Mari kita mulai!

## Prasyarat

Sebelum kita beralih ke kode, ada beberapa hal yang perlu Anda siapkan:

-  Visual Studio: Pastikan Anda telah menginstal Visual Studio di mesin Anda. Jika Anda belum memilikinya, Anda dapat mengunduhnya dari[Di Sini](https://visualstudio.microsoft.com/).
-  Aspose.Words untuk .NET: Anda memerlukan perpustakaan Aspose.Words. Anda bisa mendapatkannya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).
- Pengetahuan Dasar C#: Pemahaman dasar tentang C# dan .NET akan membantu Anda mengikuti tutorial ini.

Baiklah, jika sudah tidak ada lagi, mari kita mengotori tangan kita dengan beberapa kode!

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Words. Ini seperti mengumpulkan semua alat Anda sebelum memulai sebuah proyek. Tambahkan ini menggunakan arahan di bagian atas file C# Anda:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Sekarang kita sudah memiliki prasyaratnya, mari kita bagi prosesnya menjadi langkah-langkah kecil. Setiap langkah sangat penting dan akan membawa kita lebih dekat ke tujuan kita.

## Langkah 1: Menyiapkan Direktori Dokumen

Pertama, kita perlu menentukan direktori tempat dokumen kita disimpan. Ini seperti menyiapkan panggung sebelum pertunjukan besar.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur ke direktori Anda. Di sinilah dokumen Anda akan hidup dan bernafas.

## Langkah 2: Muat Dokumen Utama

Selanjutnya, kita memuat dokumen utama yang ingin kita sisipkan dokumen lain. Anggaplah ini sebagai panggung utama kita di mana semua aksi akan terjadi.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Kode ini memuat dokumen utama dari direktori yang ditentukan.

## Langkah 3: Atur Opsi Temukan dan Ganti

Untuk menemukan lokasi spesifik di mana kita ingin menyisipkan dokumen, kita menggunakan fungsi temukan dan ganti. Ini seperti menggunakan peta untuk menemukan tempat yang tepat untuk tambahan baru kita.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Di sini, kita menyetel arah ke mundur dan menentukan penangan panggilan balik khusus yang akan kita tentukan selanjutnya.

## Langkah 4: Lakukan Operasi Penggantian

Sekarang, kami memberi tahu dokumen utama kami untuk mencari teks placeholder tertentu dan menggantinya dengan apa pun, sambil menggunakan panggilan balik khusus kami untuk menyisipkan dokumen lain.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Kode ini melakukan operasi temukan dan ganti, lalu menyimpan dokumen yang diperbarui.

## Langkah 5: Buat Penangan Panggilan Balik Penggantian Kustom

Penangan panggilan balik khusus kami adalah tempat keajaiban terjadi. Pengendali ini akan menentukan bagaimana penyisipan dokumen dilakukan selama operasi pencarian dan penggantian.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Sisipkan dokumen setelah paragraf yang berisi teks yang cocok.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Hapus paragraf dengan teks yang cocok.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Di sini, kita memuat dokumen yang akan disisipkan dan kemudian memanggil metode pembantu untuk melakukan penyisipan.

## Langkah 6: Tentukan Metode Sisipkan Dokumen

Bagian terakhir dari teka-teki kita adalah metode yang benar-benar menyisipkan dokumen di lokasi yang ditentukan.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Ulangi semua node tingkat blok di badan bagian,
		// lalu klon dan masukkan setiap node yang bukan paragraf kosong terakhir dari suatu bagian.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

Metode ini menangani impor node dari dokumen yang akan disisipkan dan menempatkannya di tempat yang tepat di dokumen utama.

## Kesimpulan

Dan itu dia! Panduan komprehensif untuk menyisipkan satu dokumen ke dokumen lain menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengotomatiskan tugas perakitan dan manipulasi dokumen. Baik Anda sedang membangun sistem manajemen dokumen atau hanya perlu menyederhanakan alur kerja pemrosesan dokumen Anda, Aspose.Words adalah sahabat karib Anda.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah perpustakaan yang kuat untuk memanipulasi dokumen Word secara terprogram. Ini memungkinkan Anda membuat, memodifikasi, mengonversi, dan memproses dokumen Word dengan mudah.

### Bisakah saya memasukkan banyak dokumen sekaligus?
Ya, Anda dapat memodifikasi pengendali panggilan balik untuk menangani beberapa penyisipan dengan mengulangi kumpulan dokumen.

### Apakah ada uji coba gratis yang tersedia?
 Sangat! Anda dapat mengunduh uji coba gratis dari[Di Sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.Words?
Anda bisa mendapatkan dukungan dengan mengunjungi[Aspose.Forum kata-kata](https://forum.aspose.com/c/words/8).

### Bisakah saya mempertahankan format dokumen yang disisipkan?
 Ya, itu`NodeImporter` kelas memungkinkan Anda menentukan bagaimana pemformatan ditangani saat mengimpor node dari satu dokumen ke dokumen lainnya.