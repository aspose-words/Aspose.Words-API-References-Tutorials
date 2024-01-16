---
title: Tambahkan Dokumen
linktitle: Tambahkan Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan konten satu dokumen ke dokumen lain menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/append-document/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan konten satu dokumen ke dokumen lainnya. Kode sumber yang disediakan menunjukkan cara membuka dokumen sumber dan tujuan, mengimpor dan menambahkan bagian dari dokumen sumber ke dokumen tujuan.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan berada.

## Langkah 2: Buka dokumen sumber dan tujuan

 Buka dokumen sumber dan tujuan menggunakan`Document` konstruktor kelas. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Tambahkan bagian dari dokumen sumber ke dokumen tujuan

 Ulangi seluruh bagian dalam dokumen sumber dan impor setiap bagian ke dalam dokumen tujuan menggunakan`ImportNode` metode. Kemudian, tambahkan bagian yang diimpor ke dokumen tujuan.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Langkah 4: Simpan dokumen tujuan

 Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Ini menyelesaikan implementasi penambahan dokumen menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Menambahkan Dokumen menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ulangi semua bagian dalam dokumen sumber.
	//Node bagian adalah turunan langsung dari node Dokumen sehingga kita cukup menghitung Dokumennya.
	foreach (Section srcSection in srcDoc)
	{
		// Karena kami menyalin bagian dari satu dokumen ke dokumen lainnya,
		// diperlukan untuk mengimpor node Bagian ke dalam dokumen tujuan.
		// Ini menyesuaikan referensi spesifik dokumen apa pun ke gaya, daftar, dll.
		//
		// Mengimpor sebuah node akan membuat salinan dari node asli, tetapi salinannya
		// ss siap dimasukkan ke dalam dokumen tujuan.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Sekarang node bagian baru dapat ditambahkan ke dokumen tujuan.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```