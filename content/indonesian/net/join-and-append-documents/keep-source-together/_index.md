---
title: Pertahankan Sumber Bersama
linktitle: Pertahankan Sumber Bersama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan dokumen Word menggunakan Aspose.Words untuk .NET sambil mempertahankan pemformatan. Panduan komprehensif ini mencakup semuanya mulai dari penyiapan hingga eksekusi.
type: docs
weight: 10
url: /id/net/join-and-append-documents/keep-source-together/
---
## Perkenalan

Di era digital saat ini, memanipulasi dokumen Word secara terprogram sangat penting di berbagai industri. Aspose.Words untuk .NET memberdayakan pengembang untuk mengotomatiskan tugas penanganan dokumen secara efisien. Panduan komprehensif ini akan memandu Anda melalui proses penggabungan dokumen sambil mempertahankan format sumber menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum mendalami penggabungan dokumen dengan Aspose.Words untuk .NET, pastikan Anda memiliki hal berikut:

- Visual Studio: Lingkungan Pengembangan Terpadu (IDE) untuk pengembangan .NET.
- Aspose.Words untuk .NET: Diinstal dan diatur di lingkungan pengembangan Anda.
- Keakraban dengan C#: Pemahaman dasar bahasa pemrograman C#.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan:

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Langkah 1: Muat Dokumen

 Pertama, muat dokumen sumber dan tujuan ke Aspose.Words`Document` objek.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

// Memuat dokumen sumber dan tujuan
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Langkah 2: Atur Bagian Mulai

Konfigurasikan bagian awal untuk memastikan konten dokumen sumber mengalir terus menerus setelah dokumen tujuan.

```csharp
// Atur dokumen sumber agar muncul tepat setelah konten dokumen tujuan
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Langkah 3: Satukan Paragraf

Untuk menjaga integritas pemformatan, tandai setiap paragraf di dokumen sumber agar tetap berada di paragraf berikutnya.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Langkah 4: Tambahkan Dokumen

 Gabungkan dokumen menggunakan`AppendDocument` metode, memastikan untuk mempertahankan format dokumen sumber.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Simpan Dokumen yang Digabung

Terakhir, simpan dokumen gabungan ke lokasi yang diinginkan.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## Kesimpulan

Kesimpulannya, Aspose.Words untuk .NET menyederhanakan tugas menggabungkan dokumen Word sambil mempertahankan format asli dengan mulus. Kemampuan ini sangat penting untuk aplikasi yang memerlukan pemrosesan dokumen otomatis.

## FAQ

### Bisakah Aspose.Words untuk .NET menggabungkan dokumen dengan format berbeda?
Ya, itu bisa menggabungkan dokumen apa pun formatnya, mempertahankan format sumber.

### Apakah Aspose.Words untuk .NET mendukung penggabungan dokumen besar secara efisien?
Tentu saja, ini menangani dokumen besar dengan kinerja optimal.

### Apakah ada versi uji coba yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis[Di Sini](https://releases.aspose.com/).

### Bagaimana saya bisa mendapatkan dukungan teknis untuk Aspose.Words untuk .NET?
 Dukungan teknis tersedia melalui[Aspose.Forum kata-kata](https://forum.aspose.com/c/words/8).

### Bisakah saya membeli lisensi sementara untuk Aspose.Words untuk .NET?
 Ya, Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).