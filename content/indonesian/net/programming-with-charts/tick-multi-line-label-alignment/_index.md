---
title: Centang Penyelarasan Label Multi Garis Dalam Bagan
linktitle: Centang Penyelarasan Label Multi Garis Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyelaraskan label multi-baris centang di sumbu bagan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-charts/tick-multi-line-label-alignment/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengatur perataan label multi-baris centang di sumbu bagan. Kode sumber yang disediakan menunjukkan cara membuat bagan, mengakses sumbu, dan mengubah perataan label centang.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

- Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mendownloadnya dengan menggunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen keluaran akan disimpan.

## Langkah 2: Buat dokumen baru dan masukkan bagan

 Buat yang baru`Document` objek dan a`DocumentBuilder` untuk membuat dokumen tersebut.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Selanjutnya, gunakan`InsertChart` metode`DocumentBuilder` untuk menyisipkan diagram sebar ke dalam dokumen.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Langkah 3: Atur perataan label centang

 Untuk mengatur perataan label multi-baris centang, akses`AxisX` properti bagan dan atur`TickLabelAlignment` properti ke keselarasan yang diinginkan. Dalam contoh ini, kami mengatur perataan menjadi`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Langkah 4: Simpan dokumen

 Terakhir, simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode`Document` obyek.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Ini menyelesaikan implementasi pengaturan penyelarasan label multi-baris centang menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Centang Penyelarasan Label Multi Baris menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Properti ini hanya berlaku untuk label multi-baris.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara mengatur perataan label multi-baris centang di sumbu bagan menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, Anda dapat membuat dokumen baru, menyisipkan diagram sebar, mengakses sumbu diagram, dan mengubah perataan label centang.

Aspose.Words untuk .NET menyediakan fitur canggih untuk memanipulasi bagan di dokumen Word. Centang label multi-baris berguna ketika label sumbu berisi teks panjang yang memerlukan pembungkusan atau pemisahan menjadi beberapa baris. Dengan mengatur perataan label centang, Anda dapat mengontrol perataan horizontal label multi-baris dalam sumbu bagan, memastikan presentasi dan keterbacaan yang optimal.

Menyesuaikan perataan label multi-baris centang memungkinkan Anda menyempurnakan tampilan bagan Anda, terutama saat menangani label yang panjang atau rumit. Dengan menyelaraskan label ke kanan, kiri, tengah, atau rata, Anda dapat memperoleh susunan label centang yang seimbang dan menarik secara visual di sepanjang sumbu.

Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah mengakses dan memodifikasi properti perataan label centang pada sumbu bagan, memberi Anda kontrol penuh atas tampilan dan tata letak label centang di bagan dokumen Word Anda.

### FAQ

#### Q1. Apa yang dimaksud dengan label multi-baris centang pada sumbu bagan?
Centang label multi-baris dalam sumbu bagan mengacu pada label sumbu yang membentang di beberapa baris ketika teks label panjang atau memerlukan pembungkusan agar sesuai dengan ruang yang tersedia. Daripada memotong teks label atau menyebabkan kekacauan visual, sumbu bagan secara otomatis membagi label menjadi beberapa baris untuk memastikan keterbacaan. Centang label multi-baris sangat berguna ketika menangani kategori panjang atau label nilai dalam bagan.

#### Q2. Bisakah saya menyesuaikan perataan label centang pada sumbu bagan?
 Ya, Anda dapat mengkustomisasi perataan label centang di sumbu bagan menggunakan Aspose.Words untuk .NET. Dengan mengakses`TickLabelAlignment` properti dari`ChartAxis` objek, Anda dapat mengatur perataan yang diinginkan untuk label centang. Opsi perataan mencakup perataan kiri, kanan, tengah, atau rata. Menyesuaikan perataan memungkinkan Anda mengontrol posisi horizontal label centang di sepanjang sumbu bagan, memastikan keterbacaan dan presentasi visual yang tepat.

#### Q3. Kapan saya harus mempertimbangkan untuk mengubah perataan label centang pada sumbu bagan?
Mengubah perataan label centang pada sumbu bagan bermanfaat bila Anda memiliki label panjang atau multi-baris yang memerlukan presentasi dan keterbacaan optimal. Dengan menyesuaikan perataannya, Anda dapat memastikan bahwa label telah disejajarkan dan diberi jarak dengan benar, menghindari tumpang tindih atau terpotong. Pertimbangkan untuk mengubah perataan label centang ketika berhadapan dengan bagan yang memiliki nama kategori panjang, label nilai yang panjang, atau skenario lainnya di mana perataan default tidak memberikan tampilan visual yang diinginkan.

#### Q4. Apakah perataan label centang memengaruhi label satu baris pada sumbu bagan?
Tidak, properti penyelarasan label centang tidak memengaruhi label satu baris di sumbu bagan. Ini dirancang khusus untuk label multi-garis yang memerlukan pembungkus atau pemisahan. Label satu baris disejajarkan berdasarkan pengaturan perataan default sumbu bagan. Properti penyelarasan label centang hanya berlaku untuk label yang tersebar di beberapa baris, sehingga Anda dapat mengontrol perataan setiap baris dalam label multi-baris.

#### Q5. Bisakah saya menyelaraskan label centang secara berbeda untuk sumbu X dan sumbu Y pada bagan?
 Ya, Anda dapat menyelaraskan label centang secara berbeda untuk sumbu X dan sumbu Y dalam bagan menggunakan Aspose.Words untuk .NET. Properti perataan label centang khusus untuk setiap sumbu bagan. Dengan mengakses yang sesuai`ChartAxis` objek untuk sumbu X atau sumbu Y, Anda dapat secara mandiri mengatur perataan label centang ke nilai yang berbeda. Hal ini memberi Anda fleksibilitas untuk menyelaraskan label centang secara berbeda berdasarkan kebutuhan spesifik Anda untuk setiap sumbu dalam bagan.