---
title: Perbarui Tata Letak Halaman
linktitle: Perbarui Tata Letak Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memperbarui tata letak halaman saat menggabungkan dan menambahkan dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/update-page-layout/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Pembaruan Tata Letak Halaman Aspose.Words untuk .NET. Fitur ini memastikan tata letak halaman diperbarui dengan benar saat menggabungkan dan menambahkan dokumen Word.

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

Selanjutnya, Anda perlu memuat dokumen sumber dan tujuan menggunakan Aspose.Words`Document` kelas. Perbarui nama file di`Document` konstruktor sesuai dengan nama dokumen Anda.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Perbarui Tata Letak Halaman untuk Dokumen Tujuan

 Untuk memastikan bahwa tata letak halaman diperbarui dengan benar sebelum menambahkan dokumen sumber, Anda dapat menghubungi`UpdatePageLayout` metode pada dokumen tujuan.

```csharp
dstDoc.UpdatePageLayout();
```

## Langkah 4: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting` parameter memastikan bahwa pemformatan sumber dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Perbarui Tata Letak Halaman Lagi

 Setelah menambahkan dokumen sumber, Anda perlu memanggil`UpdatePageLayout`metode pada dokumen tujuan lagi untuk memastikan bahwa setiap perubahan yang dilakukan setelah operasi penambahan tercermin dalam keluaran yang dirender.

```csharp
dstDoc.UpdatePageLayout();
```

## Langkah 6: Simpan Dokumen Akhir

 Terakhir, simpan dokumen gabungan dengan fitur Perbarui Tata Letak Halaman diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Contoh kode sumber untuk Memperbarui Tata Letak Halaman menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk fitur "Perbarui Tata Letak Halaman" di C# menggunakan Aspose.Words untuk .NET:

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Jika dokumen tujuan dirender ke PDF, gambar, dll.
	// atau UpdatePageLayout dipanggil sebelum dokumen sumber. Ditambahkan,
	// maka perubahan apa pun yang dilakukan setelahnya tidak akan tercermin dalam keluaran yang diberikan
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Agar perubahan dapat diperbarui pada keluaran yang dirender, UpdatePageLayout harus dipanggil lagi.
	// Jika tidak dipanggil lagi, dokumen yang ditambahkan tidak akan muncul pada output rendering berikutnya.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Perbarui Tata Letak Halaman menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten gabungan dengan tata letak halaman yang diperbarui dengan benar.