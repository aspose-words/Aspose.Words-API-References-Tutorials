---
title: Konversi File Word ke PDF
linktitle: Konversi File Word ke PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi dokumen Word dari Docx ke PDF menggunakan Aspose.Words untuk .NET. Tutorial langkah demi langkah dengan contoh kode sumber.
type: docs
weight: 10
url: /id/net/basic-conversions/docx-to-pdf/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan Aspose.Words untuk .NET untuk mengonversi dokumen Word dalam format Docx ke PDF. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Words untuk .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis](https://releases.aspose.com/words/net/).

## Langkah 1: Menginisialisasi Objek Dokumen

 Pertama, inisialisasi`Document`objek dengan jalur ke dokumen sumber Anda dalam format Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Langkah 2: Menyimpan Dokumen dalam Format PDF

 Selanjutnya simpan dokumen dalam format PDF dengan memanggil`Save` metode pada`Document` objek dan memberikan jalur dan nama file untuk dokumen PDF keluaran:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

Itu dia! Anda telah berhasil mengonversi dokumen Word dalam format Docx ke PDF menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber Docx Ke Pdf menggunakan Aspose.Words untuk .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya sesuai dengan kebutuhan spesifik Anda.

### FAQ untuk Konversi Word ke PDF

#### Q1. Apa saja persyaratan untuk melakukan konversi DOCX ke PDF dengan Aspose.Words untuk .NET?
Untuk menjalankan konversi DOCX ke PDF dengan Aspose.Words untuk .NET, Anda memerlukan:
Aspose.Words untuk .NET diinstal pada mesin Anda
File DOCX yang valid untuk dikonversi
Lisensi yang valid untuk menggunakan Aspose.Words untuk .NET (atau Anda dapat menggunakan versi uji coba gratis)

#### Q2. Bagaimana cara menginstal Aspose.Words untuk .NET?
Anda dapat menginstal Aspose.Words untuk .NET dengan mengikuti langkah-langkah berikut:

Buka Visual Studio atau lingkungan pengembangan pilihan Anda.

Buat proyek baru atau buka proyek yang sudah ada.

Klik kanan proyek di Solution Explorer.

Pilih "Kelola Paket NuGet" dari menu konteks.

Cari "Aspose.Words" di kotak pencarian.

Pilih versi terbaru Aspose.Words untuk .NET.

Klik "Instal" untuk menambahkan referensi ke proyek Anda.

#### Q3. Opsi konversi apa lagi yang tersedia dengan Aspose.Words untuk .NET?
Selain mengonversi DOCX ke PDF, Aspose.Words for .NET mendukung berbagai konversi lainnya, seperti:

DOCX ke format file lain, seperti DOC, RTF, HTML, XML, dll.

Konversikan file PDF ke format seperti DOCX, DOC, HTML, dll.

Konversi file EPUB, ODT, OTT, TXT, dll. ke format lain.


#### Q4. Di mana saya dapat menemukan lebih banyak contoh kode dan sumber daya untuk Pemrosesan Kata dengan Aspose.Words untuk .NET?
 Anda dapat menemukan lebih banyak contoh kode dan sumber daya di[Aspose.Words untuk Referensi .NET API](https://reference.aspose.com/words/net/) Dan[Aspose.Words untuk Tutorial .NET API](https://reference.aspose.com/tutorials/words/net/). Sumber daya ini menyediakan panduan langkah demi langkah, kode contoh, dan tutorial.