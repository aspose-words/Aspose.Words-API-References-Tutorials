---
title: Baca Properti XControl Aktif Dari File Word
linktitle: Baca Properti XControl Aktif Dari File Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membaca properti kontrol ActiveX dari file Word menggunakan Aspose.Words untuk .NET dalam panduan langkah demi langkah. Tingkatkan keterampilan otomatisasi dokumen Anda.
type: docs
weight: 10
url: /id/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Perkenalan

Di era digital saat ini, otomatisasi adalah kunci untuk meningkatkan produktivitas. Jika Anda bekerja dengan dokumen Word yang berisi kontrol ActiveX, Anda mungkin perlu membaca propertinya untuk berbagai tujuan. Kontrol ActiveX, seperti kotak centang dan tombol, dapat menyimpan data penting. Dengan menggunakan Aspose.Words untuk .NET, Anda dapat mengekstrak dan memanipulasi data ini secara efisien secara terprogram.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET Library: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. Visual Studio atau IDE C# apa pun: Untuk menulis dan mengeksekusi kode Anda.
3. Dokumen Word dengan kontrol ActiveX: Misalnya, "Kontrol ActiveX.docx".
4. Pengetahuan dasar tentang C#: Keakraban dengan pemrograman C# diperlukan untuk diikuti.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan agar berfungsi dengan Aspose.Words untuk .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Langkah 1: Muat Dokumen Word

Untuk memulai, Anda perlu memuat dokumen Word yang berisi kontrol ActiveX.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Langkah 2: Inisialisasi String untuk Memegang Properti

Selanjutnya, inisialisasi string kosong untuk menyimpan properti kontrol ActiveX.

```csharp
string properties = "";
```

## Langkah 3: Iterasi Melalui Bentuk di Dokumen

Kita perlu mengulangi semua bentuk dalam dokumen untuk menemukan kontrol ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Proses kontrol ActiveX
    }
}
```

## Langkah 4: Ekstrak Properti dari Kontrol ActiveX

Di dalam loop, periksa apakah kontrolnya adalah Forms2OleControl. Jika ya, keluarkan dan ekstrak propertinya.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Langkah 5: Hitung Total Kontrol ActiveX

Setelah mengulangi semua bentuk, hitung jumlah total kontrol ActiveX yang ditemukan.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Langkah 6: Tampilkan Properti

Terakhir, cetak properti yang diekstraksi ke konsol.

```csharp
Console.WriteLine("\n" + properties);
```

## Kesimpulan

Dan itu dia! Anda telah berhasil mempelajari cara membaca properti kontrol ActiveX dari dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial ini mencakup memuat dokumen, mengulangi bentuk, dan mengekstrak properti dari kontrol ActiveX. Dengan mengikuti langkah-langkah ini, Anda dapat mengotomatiskan ekstraksi data penting dari dokumen Word Anda, sehingga meningkatkan efisiensi alur kerja Anda.

## FAQ

### Apa itu kontrol ActiveX di dokumen Word?
Kontrol ActiveX adalah objek interaktif yang tertanam dalam dokumen Word, seperti kotak centang, tombol, dan bidang teks, yang digunakan untuk membuat formulir dan mengotomatiskan tugas.

### Bisakah saya mengubah properti kontrol ActiveX menggunakan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET memungkinkan Anda mengubah properti kontrol ActiveX secara terprogram.

### Apakah Aspose.Words untuk .NET gratis untuk digunakan?
 Aspose.Words untuk .NET menawarkan uji coba gratis, tetapi Anda harus membeli lisensi untuk terus menggunakannya. Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Bisakah saya menggunakan Aspose.Words untuk .NET dengan bahasa .NET lain selain C#?
Ya, Aspose.Words untuk .NET dapat digunakan dengan bahasa .NET apa pun, termasuk VB.NET dan F#.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi terperinci[Di Sini](https://reference.aspose.com/words/net/).