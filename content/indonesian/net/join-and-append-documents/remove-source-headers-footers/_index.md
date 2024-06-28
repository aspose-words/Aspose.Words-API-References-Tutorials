---
title: Hapus Footer Header Sumber
linktitle: Hapus Footer Header Sumber
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghapus header dan footer saat menggabungkan dan menambahkan dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/remove-source-headers-footers/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Hapus Source Headers Footers dari Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word sambil menghapus header dan footer dari dokumen sumber.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk .NET diinstal. Anda dapat mendownloadnya dari situs Aspose atau menginstalnya melalui NuGet.
2. Visual Studio atau lingkungan pengembangan C# lainnya.

## Langkah 1: Inisialisasi Direktori Dokumen

 Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ubah nilai`dataDir` variabel ke jalur di mana dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Sumber dan Tujuan

Selanjutnya, Anda perlu memuat dokumen sumber dan tujuan menggunakan Aspose.Words.`Document` kelas. Perbarui nama file di`Document` konstruktor sesuai dengan nama dokumen Anda.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Hapus Header dan Footer dari Bagian Dokumen Sumber

 Untuk menghapus header dan footer dari setiap bagian dalam dokumen sumber, Anda dapat mengulangi bagian tersebut menggunakan a`foreach` loop dan panggil`ClearHeadersFooters` metode.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Langkah 4: Nonaktifkan Pengaturan "LinkToPrevious" untuk HeadersFooters

Bahkan setelah menghapus header dan footer dari dokumen sumber, ada kemungkinan bahwa pengaturan "LinkToPrevious" untuk`HeadersFooters` masih dapat diatur. Untuk menghindari perilaku ini, Anda perlu mengaturnya secara eksplisit`false` untuk bagian pertama`HeadersFooters` Properti.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Langkah 5: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting` parameter memastikan bahwa pemformatan sumber dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 6: Simpan Dokumen Akhir

 Terakhir, simpan dokumen yang digabungkan dengan fitur Hapus Sumber Header Footer yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Contoh kode sumber untuk Menghapus Source Headers Footers menggunakan Aspose.Words untuk .NET 

Berikut kode sumber lengkap untuk fitur "Hapus Source Headers Footers" di C# menggunakan Aspose.Words untuk .NET:


```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hapus header dan footer dari setiap bagian di dokumen sumber.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Bahkan setelah header dan footer dihapus dari dokumen sumber, pengaturan "LinkToPrevious".
	// untuk HeadersFooters masih bisa diset. Hal ini akan menyebabkan header dan footer berlanjut dari tujuan
	// dokumen. Ini harus disetel ke false untuk menghindari perilaku ini.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Itu dia! Anda telah berhasil mengimplementasikan fitur Hapus Source Headers Footers menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten gabungan dengan header dan footer yang dihapus dari dokumen sumber.