---
title: Sisipkan Gambar Mengambang di Dokumen Word
linktitle: Sisipkan Gambar Mengambang di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan gambar mengambang di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-floating-image/
---
Dalam contoh komprehensif ini, Anda akan mempelajari cara menyisipkan gambar mengambang ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat menambahkan gambar dengan opsi pemosisian dan pembungkusan yang dapat disesuaikan ke dokumen Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan inisialisasi objek DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Gambar Mengambang
Selanjutnya, gunakan metode InsertImage dari kelas DocumentBuilder untuk menyisipkan gambar mengambang. Berikan jalur file gambar, posisi relatif horizontal dan vertikal, lebar, tinggi, dan opsi pembungkusan sebagai parameter:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Langkah 3: Simpan Dokumen
Setelah menyisipkan gambar mengambang, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Contoh Kode Sumber untuk Menyisipkan Gambar Mengambang menggunakan Aspose.Words untuk .NET
Berikut source code lengkap untuk menyisipkan gambar mengambang menggunakan Aspose.Words for .NET:
Gambar mengambang berguna untuk berbagai skenario, seperti menambahkan logo, ilustrasi, atau elemen dekoratif yang dapat diposisikan secara terpisah dari teks dokumen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Ingatlah untuk menyesuaikan kode sesuai dengan kebutuhan spesifik Anda, termasuk jalur file gambar serta opsi pemosisian dan pembungkusan yang diinginkan.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menyisipkan gambar mengambang ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat menyempurnakan dokumen Anda dengan gambar mengambang yang menarik secara visual dan dapat disesuaikan.

### FAQ untuk menyisipkan gambar mengambang di dokumen Word

#### T: Dapatkah saya menyisipkan beberapa gambar mengambang dalam satu dokumen?

J: Tentu saja! Anda dapat menyisipkan gambar mengambang sebanyak yang diperlukan dalam dokumen Word menggunakan Aspose.Words untuk .NET. Cukup ulangi proses penyisipan untuk menambahkan beberapa gambar yang menarik secara visual.

#### T: Opsi pembungkusan apa yang tersedia untuk gambar mengambang?

J: Aspose.Words untuk .NET menyediakan berbagai opsi pembungkusan untuk gambar mengambang, termasuk Square, Tight, Through, TopBottom, dan None. Opsi ini menentukan bagaimana teks berinteraksi dengan gambar mengambang.

#### T: Dapatkah saya menyesuaikan ukuran gambar mengambang?

J: Tentu saja! Anda dapat menentukan lebar dan tinggi gambar mengambang menggunakan parameter masing-masing dalam metode InsertImage. Ini memungkinkan Anda mengontrol dimensi gambar sesuai dengan preferensi desain Anda.

#### T: Dapatkah saya memposisikan gambar mengambang relatif terhadap elemen tertentu dalam dokumen?

J: Ya, Aspose.Words untuk .NET memungkinkan Anda memposisikan gambar mengambang relatif terhadap elemen tertentu, seperti margin, halaman, paragraf, atau tabel. Anda dapat memilih parameter posisi relatif horizontal dan vertikal yang sesuai untuk mencapai penempatan yang diinginkan.

#### T: Apakah Aspose.Words untuk .NET cocok untuk aplikasi desktop dan web?

J: Ya, Aspose.Words for .NET adalah perpustakaan serbaguna yang cocok untuk aplikasi desktop dan web. Baik Anda sedang membangun aplikasi Windows atau sistem berbasis web, Anda dapat mengintegrasikan perpustakaan dengan mudah.
