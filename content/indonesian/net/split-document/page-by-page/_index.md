---
title: Pisahkan Dokumen Word Berdasarkan Halaman
linktitle: Pisahkan Dokumen Word Berdasarkan Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membagi dokumen Word menjadi halaman individual menggunakan Aspose.Words untuk .NET. API yang kuat ini menyederhanakan proses pemisahan dokumen, menjadikannya efisien dan nyaman.
type: docs
weight: 10
url: /id/net/split-document/page-by-page/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara membagi dokumen Word menjadi beberapa halaman menggunakan fitur pemrosesan dokumen Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan mendapatkan dokumen terpisah untuk setiap halaman.

## Langkah 1: Memuat dokumen

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Langkah 2: Pemisahan dokumen berdasarkan halaman

Sekarang kita akan mengulangi setiap halaman dokumen dan membagi dokumen menjadi beberapa halaman individual. Begini caranya:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Simpan setiap halaman sebagai dokumen terpisah.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Contoh kode sumber untuk Halaman Demi Halaman menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fitur Halaman demi Halaman Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Simpan setiap halaman sebagai dokumen terpisah.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Dengan kode ini Anda akan dapat membagi dokumen Word menjadi halaman individual menggunakan Aspose.Words untuk .NET. Anda juga dapat menggabungkan dokumen terpisah jika diperlukan.

## Kesimpulan

Selamat! Anda telah mempelajari cara membagi dokumen Word menjadi beberapa halaman menggunakan fitur Halaman demi Halaman dari Aspose.Words untuk .NET. Dengan mengikuti kode sumber yang disediakan, Anda dapat mengekstrak setiap halaman dokumen dan menyimpannya sebagai dokumen terpisah.

Memisahkan dokumen berdasarkan halaman dapat berguna ketika Anda perlu bekerja dengan halaman tertentu atau mendistribusikan konten secara terperinci. Aspose.Words untuk .NET menyediakan API canggih yang menyederhanakan proses pemisahan dokumen, menjadikannya efisien dan nyaman.

Jangan ragu untuk menjelajahi fitur lain yang ditawarkan oleh Aspose.Words untuk .NET untuk meningkatkan kemampuan pemrosesan dokumen dan menyederhanakan alur kerja Anda.

### FAQ

#### Bagaimana cara membagi dokumen menjadi beberapa halaman menggunakan Aspose.Words untuk .NET?

 Untuk membagi dokumen menjadi beberapa halaman, Anda dapat menggunakan`ExtractPages` metode Aspose.Words API untuk mendapatkan rentang halaman. Dengan menentukan halaman awal dan jumlah halaman yang akan diekstraksi, Anda dapat membuat dokumen terpisah untuk setiap halaman.

#### Bisakah saya menyesuaikan format keluaran saat memisahkan dokumen berdasarkan halaman?

Ya, Aspose.Words untuk .NET mendukung berbagai format keluaran saat memisahkan dokumen berdasarkan halaman. Anda dapat menyimpan setiap halaman sebagai dokumen terpisah dalam format seperti DOCX, PDF, HTML, dan lainnya, bergantung pada kebutuhan Anda.

#### Bisakah saya membagi dokumen berdasarkan rentang halaman tertentu?

Sangat! Aspose.Words untuk .NET memungkinkan Anda membagi dokumen berdasarkan rentang halaman tertentu. Dengan menyesuaikan halaman awal dan jumlah halaman yang akan diekstraksi, Anda dapat menentukan dengan tepat rentang halaman untuk memisahkan dokumen.

#### Apakah mungkin untuk menggabungkan kembali dokumen yang terpisah menjadi satu dokumen?

Ya, Anda dapat menggabungkan kembali dokumen yang terpisah menjadi satu dokumen menggunakan fungsionalitas penggabungan yang disediakan oleh Aspose.Words untuk .NET. Dengan menggabungkan dokumen-dokumen terpisah, Anda dapat membuat ulang dokumen asli atau membuat dokumen baru dengan struktur berbeda, sesuai kebutuhan.