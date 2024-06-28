---
title: Tampilkan Sembunyikan Bookmark Di Dokumen Word
linktitle: Tampilkan Sembunyikan Bookmark Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menampilkan atau menyembunyikan bookmark tertentu di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/show-hide-bookmarks/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Tampilkan Sembunyikan Bookmark di pustaka Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menampilkan atau menyembunyikan bookmark tertentu di dokumen Word.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Memuat dokumen

 Kami menggunakan`Document` kelas untuk memuat dokumen yang ada dari file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Langkah 2: Tampilkan atau sembunyikan bookmark tertentu

 Kami menggunakan`ShowHideBookmarkedContent` berfungsi untuk menampilkan atau menyembunyikan penanda tertentu dalam dokumen. Fungsi ini mengambil parameter dokumen, nama bookmark, dan boolean untuk menunjukkan apakah akan menampilkan atau menyembunyikan bookmark:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Langkah 3: Menyimpan dokumen yang dimodifikasi

 Kami menggunakan`Save` metode untuk menyimpan dokumen yang dimodifikasi ke file:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Contoh kode sumber untuk Tampilkan Sembunyikan Bookmark menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk menunjukkan menampilkan atau menyembunyikan bookmark tertentu menggunakan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### Kode sumber ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fitur Tampilkan Sembunyikan Bookmark Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk menampilkan atau menyembunyikan bookmark tertentu dalam dokumen.

### FAQ untuk menampilkan sembunyikan bookmark di dokumen Word

#### T: Dapatkah saya menampilkan atau menyembunyikan beberapa penanda dalam dokumen yang sama?

J: Ya, Anda dapat menampilkan atau menyembunyikan beberapa penanda dalam dokumen yang sama dengan mengulangi langkah 2 dan 3 untuk setiap penanda yang ingin Anda proses.

#### T: Apakah kode yang diberikan berfungsi dengan format dokumen Word lainnya, seperti .doc atau .docm?

A: Ya, kode yang diberikan berfungsi dengan berbagai format dokumen Word yang didukung oleh Aspose.Words, seperti .doc dan .docm. Pastikan untuk menggunakan nama file dan jalur yang benar saat memuat dan menyimpan dokumen.

#### T: Bagaimana cara menampilkan kembali bookmark tersembunyi?

 J: Untuk menampilkan kembali bookmark tersembunyi, Anda perlu menggunakan yang sama`ShowHideBookmarkedContent` fungsi meneruskan nilai`true` untuk parameter boolean yang menunjukkan apakah akan menampilkan atau menyembunyikan bookmark.

#### T: Dapatkah saya menggunakan ketentuan untuk menampilkan atau menyembunyikan bookmark berdasarkan nilai bidang gabungan dalam dokumen?

 J: Ya, Anda dapat menggunakan kondisi dan menggabungkan nilai bidang untuk menentukan apakah bookmark harus ditampilkan atau disembunyikan. Anda dapat menyesuaikan kodenya`ShowHideBookmarkedContent` berfungsi dengan memperhatikan kondisi dan nilai yang sesuai.

#### T: Bagaimana cara menghapus penanda di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk menghapus bookmark di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`RemoveBookmarks` metode`Document` kelas. Berikut ini contoh kodenya:

```csharp
doc.RemoveBookmarks("BookmarkName");
```