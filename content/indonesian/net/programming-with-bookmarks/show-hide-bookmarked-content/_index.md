---
title: Tampilkan Sembunyikan Konten yang Ditandai di Dokumen Word
linktitle: Tampilkan Sembunyikan Konten yang Ditandai di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menampilkan atau menyembunyikan konten bookmark di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Tampilkan Sembunyikan Konten yang Ditandai di pustaka Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menampilkan atau menyembunyikan konten bookmark di dokumen Word berdasarkan kondisi tertentu saat menggabungkan data.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Mendapatkan bookmark

 Kami menggunakan`Bookmarks` properti rentang dokumen untuk mendapatkan bookmark spesifik tempat kita ingin menampilkan atau menyembunyikan konten:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Langkah 2: Memasukkan bidang gabungan

 Kami menggunakan pembuat dokumen`DocumentBuilder` untuk menyisipkan bidang gabungan yang diperlukan. Bidang gabungan ini akan menetapkan kondisi untuk menampilkan atau menyembunyikan konten bookmark bergantung pada nilainya`showHide` variabel:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Langkah 3: Memindahkan konten bookmark

Kami menelusuri isi bookmark dan memindahkannya sehingga muncul

isse sebelum bookmark. Ini akan mengontrol menampilkan atau menyembunyikan konten berdasarkan kondisi yang ditentukan:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Langkah 4: Memindahkan sisa konten bookmark

Kami memindahkan sisa konten penanda setelah penanda, menggunakan simpul akhir penanda sebagai titik penyisipan:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Langkah 5: Melakukan penggabungan

 Kami menggunakan`Execute` metode dokumen`s `Menggabungkan surat` object to execute the merge using the bookmark name and the value of the `variabel showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Contoh kode sumber untuk Tampilkan Sembunyikan Konten yang Ditandai menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode Sumber untuk menunjukkan menampilkan atau menyembunyikan konten bookmark menggunakan Aspose.Words untuk .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "benar" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fitur Tampilkan Sembunyikan Konten yang Ditandai Aspose.Words untuk .NET. Kami telah mengikuti panduan langkah demi langkah untuk menampilkan atau menyembunyikan konten bookmark berdasarkan kondisi tertentu saat menggabungkan data.

### FAQ untuk menampilkan sembunyikan konten yang ditandai di dokumen Word

#### T: Dapatkah saya menggunakan ketentuan yang sama untuk beberapa bookmark dalam dokumen yang sama?

J: Ya, Anda dapat menggunakan ketentuan yang sama untuk beberapa penanda dalam dokumen yang sama. Ulangi saja langkah 2-5 untuk setiap bookmark, sesuaikan nama bookmark dan nilai opsionalnya`showhide` variabel sesuai kebutuhan.

#### T: Bagaimana cara menambahkan ketentuan lainnya untuk menampilkan atau menyembunyikan konten bookmark?

 J: Untuk menambahkan kondisi lainnya, Anda dapat menggunakan operator logika seperti`AND` Dan`OR` dalam kode untuk menyisipkan kolom gabungan pada langkah 2. Edit ketentuan dalam kode berikut untuk menambahkan ketentuan tambahan :

```csharp
builder. Write("\" = \"true\" ");
```

#### T: Bagaimana cara menghapus penanda di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk menghapus bookmark di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Remove` metode dari`Bookmarks` kumpulan rentang dokumen. Berikut ini contoh kode untuk menghapus bookmark tertentu:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### T: Apakah perpustakaan Aspose.Words gratis?

 J: Pustaka Aspose.Words adalah pustaka komersial dan memerlukan lisensi yang valid untuk digunakan dalam proyek Anda. Anda dapat memeriksanya[Aspose.Words untuk referensi .NET API](https://reference.aspose.com/words/net/) untuk mempelajari lebih lanjut tentang opsi lisensi dan harga.

#### T: Apakah ada perpustakaan lain yang tersedia untuk Pemrosesan Kata dengan dokumen Word di .NET?

J: Ya, ada perpustakaan lain yang tersedia untuk Pemrosesan Kata dengan dokumen Word di .NET, seperti Open XML SDK dan GemBox.Document. Anda dapat menjelajahi perpustakaan ini sebagai alternatif Aspose.Words berdasarkan kebutuhan dan preferensi spesifik Anda.