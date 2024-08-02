---
title: Ubah Kontrol Konten
linktitle: Ubah Kontrol Konten
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah tag dokumen terstruktur di Word menggunakan Aspose.Words untuk .NET. Perbarui teks, dropdown, dan gambar selangkah demi selangkah.
type: docs
weight: 10
url: /id/net/programming-with-sdt/modify-content-controls/
---
## Perkenalan

Jika Anda pernah bekerja dengan dokumen Word dan perlu mengubah kontrol konten terstruktur—seperti teks biasa, daftar dropdown, atau gambar—menggunakan Aspose.Words untuk .NET, Anda berada di tempat yang tepat! Tag Dokumen Terstruktur (SDT) adalah alat canggih yang membuat otomatisasi dokumen lebih mudah dan fleksibel. Dalam tutorial ini, kami akan mendalami bagaimana Anda dapat memodifikasi SDT ini agar sesuai dengan kebutuhan Anda. Baik Anda memperbarui teks, mengubah pilihan dropdown, atau menukar gambar, panduan ini akan memandu Anda melalui prosesnya langkah demi langkah.

## Prasyarat

Sebelum kita masuk ke seluk beluk memodifikasi kontrol konten, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET Terpasang: Pastikan Anda telah menginstal perpustakaan Aspose.Words. Jika tidak, Anda bisa[Unduh di sini](https://releases.aspose.com/words/net/).

2. Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda sudah familiar dengan konsep dasar pemrograman C#.

3. Lingkungan Pengembangan .NET: Anda harus memiliki IDE seperti Visual Studio yang disiapkan untuk menjalankan aplikasi .NET.

4. Contoh Dokumen: Kami akan menggunakan contoh dokumen Word dengan berbagai jenis SDT. Anda dapat menggunakan salah satu dari contoh atau membuatnya sendiri.

5.  Akses ke Dokumentasi Aspose: Untuk informasi lebih detail, lihat[Dokumentasi Aspose.Words](https://reference.aspose.com/words/net/).

## Impor Namespace

Untuk mulai bekerja dengan Aspose.Words, Anda perlu mengimpor namespace yang relevan ke proyek C# Anda. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Namespace ini akan memberi Anda akses ke kelas dan metode yang diperlukan untuk memanipulasi tag dokumen terstruktur di dokumen Word Anda.

## Langkah 1: Siapkan Jalur Dokumen Anda

 Sebelum melakukan perubahan apa pun, Anda perlu menentukan jalur ke dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat dokumen Anda disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## Langkah 2: Ulangi Tag Dokumen Terstruktur

 Untuk memodifikasi SDT, pertama-tama Anda harus mengulang semua SDT dalam dokumen. Ini dilakukan dengan menggunakan`GetChildNodes` metode untuk mendapatkan semua tipe node`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Ubah SDT berdasarkan tipenya
}
```

## Langkah 3: Ubah SDT Teks Biasa

Jika SDT adalah tipe teks biasa, Anda dapat mengganti kontennya. Pertama, hapus konten yang ada, lalu tambahkan teks baru.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 Penjelasan: Di sini,`RemoveAllChildren()`menghapus konten SDT yang ada. Kami kemudian membuat yang baru`Paragraph`Dan`Run` objek untuk menyisipkan teks baru.

## Langkah 4: Ubah SDT Daftar Dropdown

 Untuk SDT daftar dropdown, Anda dapat mengubah item yang dipilih dengan mengakses`ListItems` koleksi. Di sini, kita memilih item ketiga dalam daftar.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Penjelasan: Cuplikan kode ini memilih item pada indeks 2 (item ketiga) dari daftar dropdown. Sesuaikan indeks berdasarkan kebutuhan Anda.

## Langkah 5: Ubah SDT Gambar

Untuk memperbarui gambar dalam gambar SDT, Anda dapat mengganti gambar yang ada dengan yang baru.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 Penjelasan: Kode ini memeriksa apakah bentuknya berisi gambar dan kemudian menggantinya dengan gambar baru yang terletak di`ImagesDir`.

## Langkah 6: Simpan Dokumen Anda yang Dimodifikasi

Setelah melakukan semua perubahan yang diperlukan, simpan dokumen yang dimodifikasi dengan nama baru agar dokumen asli Anda tetap utuh.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Penjelasan: Ini menyimpan dokumen dengan nama file baru sehingga Anda dapat dengan mudah membedakannya dari aslinya.

## Kesimpulan

Memodifikasi kontrol konten dalam dokumen Word menggunakan Aspose.Words untuk .NET sangatlah mudah setelah Anda memahami langkah-langkah yang terlibat. Baik Anda memperbarui teks, mengubah pilihan dropdown, atau menukar gambar, Aspose.Words menyediakan API yang tangguh untuk tugas-tugas ini. Dengan mengikuti tutorial ini, Anda dapat secara efektif mengelola dan mengkustomisasi kontrol konten terstruktur dokumen Anda, menjadikan dokumen Anda lebih dinamis dan disesuaikan dengan kebutuhan Anda.

## FAQ

1. Apa itu Tag Dokumen Terstruktur (SDT)?

SDT adalah elemen dalam dokumen Word yang membantu mengelola dan memformat konten dokumen, seperti kotak teks, daftar dropdown, atau gambar.

2. Bagaimana cara menambahkan item dropdown baru ke SDT?

 Untuk menambahkan item baru, gunakan`ListItems` properti dan tambahkan yang baru`SdtListItem` ke koleksi.

3. Bisakah saya menggunakan Aspose.Words untuk menghapus SDT dari dokumen?

Ya, Anda dapat menghapus SDT dengan mengakses node dokumen dan menghapus SDT yang diinginkan.

4. Bagaimana cara menangani SDT yang bersarang di dalam elemen lain?

 Menggunakan`GetChildNodes` metode dengan parameter yang sesuai untuk mengakses SDT bersarang.

5. Apa yang harus saya lakukan jika SDT yang perlu saya modifikasi tidak terlihat di dokumen?

Pastikan SDT tidak disembunyikan atau dilindungi. Periksa pengaturan dokumen dan pastikan kode Anda menargetkan jenis SDT dengan benar.


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