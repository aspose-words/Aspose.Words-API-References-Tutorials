---
title: Gabungkan Dokumen Word
linktitle: Gabungkan Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan beberapa dokumen Word menggunakan Aspose.Words untuk .NET. API canggih ini menyederhanakan proses penggabungan dokumen, menjadikannya efisien dan mudah.
type: docs
weight: 10
url: /id/net/split-document/merge-documents/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara menggabungkan beberapa dokumen Word menggunakan fitur Gabung Dokumen Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan mendapatkan dokumen gabungan yang berisi semua dokumen sumber.

## Langkah 1: Cari dokumen untuk digabungkan

Sebelum menggabungkan dokumen, kita perlu mencari lokasi dokumen sumber yang akan digabungkan. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Cari dokumen untuk digabungkan.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Langkah 2: Gabungkan dokumen

Sekarang kita akan menggabungkan dokumen satu per satu untuk membuat dokumen gabungan akhir. Begini caranya:

```csharp
// Buka bagian pertama dari dokumen yang dihasilkan.
Document sourceDoc = new Document(sourceDocumentPath);

// Buat dokumen hasil baru.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Gabungkan dokumen satu per satu.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Contoh kode sumber untuk Menggabungkan Dokumen menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fitur Penggabungan Dokumen Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Temukan dokumen yang digunakan untuk penggabungan.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Buka bagian pertama dari dokumen yang dihasilkan.
Document sourceDoc = new Document(sourceDocumentPath);

// Buat dokumen hasil baru.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Gabungkan bagian dokumen satu per satu.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Kesimpulan

Selamat! Anda telah mempelajari cara menggabungkan beberapa dokumen Word menggunakan fitur Gabung Dokumen Aspose.Words untuk .NET. Dengan mengikuti kode sumber yang disediakan, Anda dapat menggabungkan dokumen terpisah menjadi satu dokumen gabungan sambil mempertahankan format setiap dokumen sumber.

Menggabungkan dokumen dapat berguna ketika Anda ingin menggabungkan informasi dari berbagai sumber atau membuat dokumen terpadu dari bagian-bagian individual. Aspose.Words untuk .NET menyediakan API canggih yang menyederhanakan proses penggabungan dokumen, menjadikannya efisien dan mudah.

Jangan ragu untuk menjelajahi fitur lain yang ditawarkan oleh Aspose.Words untuk .NET untuk meningkatkan kemampuan pemrosesan dokumen dan menyederhanakan alur kerja Anda.

### FAQ

#### Bagaimana cara menggabungkan dokumen dengan format berbeda?

 Saat menggabungkan dokumen, Aspose.Words untuk .NET menyediakan opsi untuk mempertahankan pemformatan setiap dokumen sumber. Dengan menggunakan`ImportFormatMode.KeepSourceFormatting` pilihan, dokumen yang digabungkan akan mempertahankan format dokumen asli. Jika Anda ingin menerapkan pemformatan yang konsisten di seluruh dokumen yang digabungkan, Anda dapat mengubah pemformatan menggunakan Aspose.Words API setelah menggabungkan dokumen.

#### Bisakah saya menggabungkan dokumen dalam format berbeda?

Ya, Aspose.Words untuk .NET mendukung penggabungan dokumen dalam berbagai format, termasuk DOCX, DOC, RTF, dan banyak lagi. Anda dapat memuat dokumen dengan format berbeda ke dalam Aspose.Words API dan menggabungkannya menjadi satu dokumen, apa pun format aslinya.

#### Bisakah saya menggabungkan dokumen dengan struktur kompleks, seperti tabel dan gambar?

Sangat! Aspose.Words untuk .NET mampu menggabungkan dokumen dengan struktur kompleks, termasuk tabel, gambar, header, footer, dan lainnya. API menangani proses penggabungan dengan tetap menjaga integritas dan tata letak konten di setiap dokumen.

#### Apakah mungkin untuk menggabungkan dokumen dengan orientasi atau ukuran halaman berbeda?

Ya, Aspose.Words untuk .NET menangani dokumen dengan orientasi atau ukuran halaman berbeda selama proses penggabungan. Dokumen gabungan yang dihasilkan akan mengakomodasi berbagai orientasi halaman dan ukuran dokumen sumber.