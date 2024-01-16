---
title: Konversi Docx Ke Mhtml Dan Mengirim Email
linktitle: Konversi Docx Ke Mhtml Dan Mengirim Email
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi dokumen Word dari Docx ke MHTML dan mengirimkannya sebagai email menggunakan Aspose.Words dan Aspose.Email. Tutorial langkah demi langkah.
type: docs
weight: 10
url: /id/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan Aspose.Words untuk .NET untuk mengonversi dokumen Word dalam format Docx ke MHTML dan mengirimkannya sebagai email menggunakan Aspose.Email. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan menyiapkan pustaka Aspose.Words untuk .NET dan Aspose.Email di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis](https://releases.aspose.com/words/net/).

## Langkah 1: Menginisialisasi Objek Dokumen

 Pertama, inisialisasi`Document`objek dengan jalur ke dokumen sumber Anda dalam format Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Langkah 2: Menyimpan Dokumen dalam Format MHTML

 Selanjutnya, simpan dokumen ke a`Stream` objek dalam format MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Langkah 3: Memutar Ulang Aliran

Karena Aspose.Email perlu membaca aliran dari awal, putar ulang aliran ke awal:

```csharp
stream.Position = 0;
```

## Langkah 4: Membuat Pesan MIME Aspose.Email

 Membuat`MailMessage` objek dari aliran menggunakan`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Jangan ragu untuk menyesuaikan properti pesan seperti pengirim, penerima, dan subjek.

## Langkah 5: Mengirim Email

 Gunakan Aspose.Email`SmtpClient` untuk mengirim email:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Pastikan Anda memberikan alamat host server SMTP yang benar.

Itu dia! Anda telah berhasil mengonversi dokumen Word dalam format Docx ke MHTML dan mengirimkannya sebagai email menggunakan Aspose.Words untuk .NET dan Aspose.Email.

### Contoh kode sumber untuk Docx Ke Mhtml Dan Mengirim Email menggunakan Aspose.Words untuk .NET

```csharp

	// Dokumen doc = Dokumen baru(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Putar ulang streaming ke awal sehingga Aspose.Email dapat membacanya.
	stream.Position = 0;

	// Buat pesan email MIME Aspose.Email dari aliran.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Kirim pesan menggunakan Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### Bagaimana cara mengonversi file DOCX ke MHTML?

Untuk mengonversi file DOCX ke MHTML, Anda dapat menggunakan alat perangkat lunak atau pustaka yang menyediakan fungsionalitas ini. Aspose.Words untuk .NET adalah opsi yang dapat diandalkan untuk konversi ini. Anda dapat menggunakan API perpustakaan untuk memuat file DOCX dan menyimpannya dalam format MHTML.

#### Bagaimana cara mengirim email dengan lampiran file MHTML?

Untuk mengirim email dengan file MHTML sebagai lampiran, Anda bisa menggunakan perpustakaan atau alat khusus untuk pengiriman email, seperti System.Net.Mail di .NET. Anda harus membuat pesan email, menentukan penerima, subjek, dan konten, lalu menambahkan file MHTML sebagai lampiran ke pesan sebelum mengirimnya.

#### Apa batasan proses konversi dan pengiriman email?

Batasan konversi email dan proses pengiriman bergantung pada alat spesifik yang Anda gunakan. Beberapa alat mungkin memiliki batasan terkait ukuran file, pengaturan keamanan, atau protokol email yang didukung. Penting untuk memilih alat yang sesuai dengan kebutuhan Anda dan mempertimbangkan batasan ini saat menerapkannya.

#### Apakah Aspose merupakan alat yang andal untuk konversi DOCX ke MHTML dan pengiriman email?

Ya, Aspose.Words for .NET adalah alat yang andal untuk konversi DOCX ke MHTML dan pengiriman email. Ini banyak digunakan oleh pengembang dan profesional karena kinerja dan kualitasnya. Alat ini menawarkan dokumentasi komprehensif, fitur-fitur canggih, dan dukungan teknis khusus, menjadikannya pilihan yang direkomendasikan untuk tugas-tugas ini.