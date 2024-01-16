---
title: Ubah Kontrol Konten
linktitle: Ubah Kontrol Konten
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah teks, daftar dropdown, dan gambar dalam kontrol konten di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/modify-content-controls/
---

Tutorial ini menjelaskan cara memodifikasi berbagai tipe kontrol konten dalam dokumen Word menggunakan Aspose.Words untuk .NET. Anda dapat memperbarui teks, nilai yang dipilih dari daftar dropdown, atau mengganti gambar dalam kontrol konten.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Ulangi Kontrol Konten
 Muat dokumen Word menggunakan`Document`konstruktor, meneruskan jalur ke dokumen sebagai parameter. Ulangi semua tag dokumen terstruktur dalam dokumen menggunakan a`foreach` lingkaran.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Lakukan tindakan berdasarkan jenis kontrol konten
}
```

## Langkah 3: Ubah Kontrol Konten Teks Biasa
 Untuk kontrol konten bertipe`SdtType.PlainText`, hapus semua turunan yang ada, buat paragraf baru, dan tambahkan proses dengan teks yang diinginkan.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Langkah 4: Ubah Kontrol Konten Daftar Drop-down
 Untuk kontrol konten bertipe`SdtType.DropDownList` , perbarui nilai yang dipilih dengan menyetelnya ke nilai tertentu`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Langkah 5: Ubah Kontrol Konten Gambar
 Untuk kontrol konten bertipe`SdtType.Picture`, ambil bentuk dalam kontrol konten dan ganti gambarnya dengan yang baru.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Langkah 6: Simpan Dokumen yang Dimodifikasi
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Contoh kode sumber untuk Memodifikasi Kontrol Konten menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Itu dia! Anda telah berhasil memodifikasi berbagai tipe kontrol konten di dokumen Word Anda menggunakan Aspose.Words untuk .NET.