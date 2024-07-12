---
title: Pertahankan Penomoran Sumber
linktitle: Pertahankan Penomoran Sumber
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengimpor dokumen sambil mempertahankan pemformatan menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah dengan contoh kode.
type: docs
weight: 10
url: /id/net/join-and-append-documents/keep-source-numbering/
---
## Perkenalan

 Saat bekerja dengan Aspose.Words untuk .NET, mengimpor dokumen dari satu sumber ke sumber lain sambil mempertahankan pemformatan dapat ditangani secara efisien menggunakan`NodeImporter` kelas. Tutorial ini akan memandu Anda melalui proses langkah demi langkah.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:
- Visual Studio diinstal pada mesin Anda.
-  Aspose.Words untuk .NET diinstal. Jika tidak, unduh dari[Di Sini](https://releases.aspose.com/words/net/).
- Pengetahuan dasar tentang pemrograman C# dan .NET.

## Impor Namespace

Pertama, sertakan namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Langkah 1: Siapkan Proyek Anda

Mulailah dengan membuat proyek C# baru di Visual Studio dan instal Aspose.Words melalui NuGet Package Manager.

## Langkah 2: Inisialisasi Dokumen
Buat instance dari sumber (`srcDoc`) dan tujuan (`dstDoc`) dokumen.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Konfigurasikan Opsi Impor
Siapkan opsi impor untuk mempertahankan format sumber, termasuk paragraf bernomor.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Langkah 4: Impor Paragraf
Ulangi paragraf dalam dokumen sumber dan impor ke dokumen tujuan.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Langkah 5: Simpan Dokumen
Simpan dokumen gabungan ke lokasi yang Anda inginkan.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Kesimpulan

 Kesimpulannya, menggunakan Aspose.Words untuk .NET untuk mengimpor dokumen sambil mempertahankan format sangatlah mudah dengan`NodeImporter` kelas. Metode ini memastikan dokumen Anda mempertahankan tampilan dan struktur aslinya dengan mulus.

## FAQ

### Bisakah saya mengimpor dokumen dengan gaya pemformatan berbeda?
 Ya, itu`NodeImporter` kelas mendukung impor dokumen dengan gaya pemformatan yang bervariasi.

### Bagaimana jika dokumen saya berisi tabel dan gambar yang rumit?
Aspose.Words untuk .NET menangani struktur kompleks seperti tabel dan gambar selama operasi impor.

### Apakah Aspose.Words kompatibel dengan semua versi .NET?
Aspose.Words mendukung versi .NET Framework dan .NET Core untuk integrasi yang lancar.

### Bagaimana cara menangani kesalahan selama impor dokumen?
Gunakan blok coba-tangkap untuk menangani pengecualian yang mungkin terjadi selama proses impor.

### Di mana saya dapat menemukan dokumentasi lebih rinci tentang Aspose.Words untuk .NET?
 Mengunjungi[dokumentasi](https://reference.aspose.com/words/net/) untuk panduan komprehensif dan referensi API.
