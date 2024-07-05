---
title: Sisipkan Dokumen Pada Mail Merge
linktitle: Sisipkan Dokumen Pada Mail Merge
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dokumen di bidang gabungan surat menggunakan Aspose.Words untuk .NET dalam tutorial langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Perkenalan

Selamat datang di dunia otomatisasi dokumen dengan Aspose.Words for .NET! Pernahkah Anda bertanya-tanya bagaimana cara menyisipkan dokumen secara dinamis ke dalam bidang tertentu dalam dokumen utama selama operasi penggabungan surat? Nah, Anda berada di tempat yang tepat. Tutorial ini akan memandu Anda langkah demi langkah melalui proses menyisipkan dokumen di bidang gabungan surat menggunakan Aspose.Words untuk .NET. Ini seperti menyusun sebuah puzzle, di mana setiap bagiannya terpasang dengan sempurna pada tempatnya. Jadi, mari selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET: Anda bisa[unduh versi terbaru di sini](https://releases.aspose.com/words/net/) . Jika Anda perlu membeli lisensi, Anda dapat melakukannya[Di Sini](https://purchase.aspose.com/buy) . Alternatifnya, Anda bisa mendapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) atau mencobanya dengan a[uji coba gratis](https://releases.aspose.com/).
2. Lingkungan Pengembangan: Visual Studio atau C# IDE lainnya.
3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membuat tutorial ini mudah.

## Impor Namespace

Hal pertama yang pertama, Anda harus mengimpor namespace yang diperlukan. Ini seperti landasan proyek Anda.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola. Setiap langkah akan melanjutkan langkah sebelumnya, sehingga mengarahkan Anda pada solusi yang lengkap.

## Langkah 1: Menyiapkan Direktori Anda

Sebelum Anda dapat mulai memasukkan dokumen, Anda perlu menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Anda disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Memuat Dokumen Utama

Selanjutnya, Anda akan memuat dokumen utama. Dokumen ini berisi bidang gabungan tempat dokumen lain akan disisipkan.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Langkah 3: Mengatur Panggilan Balik Penggabungan Bidang

Untuk menangani proses penggabungan, Anda perlu menyetel fungsi panggilan balik. Fungsi ini akan bertanggung jawab untuk memasukkan dokumen pada kolom gabungan yang ditentukan.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Langkah 4: Menjalankan Mail Merge

Sekarang saatnya untuk mengeksekusi gabungan surat. Ini adalah dimana keajaiban terjadi. Anda akan menentukan bidang gabungan dan dokumen yang harus disisipkan di bidang ini.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Langkah 5: Menyimpan Dokumen

Setelah gabungan surat selesai, Anda akan menyimpan dokumen yang dimodifikasi. Dokumen baru ini akan memiliki konten yang disisipkan tepat di tempat yang Anda inginkan.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Langkah 6: Membuat Penangan Panggilan Balik

Pengendali panggilan balik adalah kelas yang membuat pemrosesan khusus untuk bidang gabungan. Ini memuat dokumen yang ditentukan dalam nilai bidang dan memasukkannya ke dalam bidang gabungan saat ini.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Langkah 7: Memasukkan Dokumen

Metode ini menyisipkan dokumen tertentu ke dalam paragraf atau sel tabel saat ini.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Kesimpulan

Dan itu dia! Anda telah berhasil menyisipkan dokumen ke dalam bidang tertentu selama operasi gabungan surat menggunakan Aspose.Words untuk .NET. Fitur canggih ini dapat menghemat banyak waktu dan tenaga, terutama saat menangani dokumen dalam jumlah besar. Anggap saja memiliki asisten pribadi yang mengurus semua pekerjaan berat untuk Anda. Jadi, silakan dan cobalah. Selamat membuat kode!

## FAQ

### Bisakah saya menyisipkan banyak dokumen di bidang gabungan yang berbeda?
Ya kamu bisa. Cukup tentukan bidang gabungan yang sesuai dan jalur dokumen terkait di`MailMerge.Execute` metode.

### Apakah mungkin untuk memformat dokumen yang disisipkan secara berbeda dari dokumen utama?
 Sangat! Anda dapat menggunakan`ImportFormatMode` parameter di`NodeImporter` untuk mengontrol pemformatan.

### Bagaimana jika nama bidang gabungan bersifat dinamis?
Anda dapat menangani nama bidang gabungan dinamis dengan meneruskannya sebagai parameter ke pengendali panggilan balik.

### Bisakah saya menggunakan metode ini dengan format file yang berbeda?
Ya, Aspose.Words mendukung berbagai format file termasuk DOCX, PDF, dan lainnya.

### Bagaimana cara menangani kesalahan selama proses penyisipan dokumen?
Terapkan penanganan kesalahan di pengendali panggilan balik Anda untuk mengelola pengecualian apa pun yang mungkin terjadi.