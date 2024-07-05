---
title: Konversi Docx Ke Mhtml Dan Mengirim Email
linktitle: Konversi Docx Ke Mhtml Dan Mengirim Email
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi DOCX ke MHTML dan mengirim email menggunakan Aspose.Words untuk .NET dalam panduan langkah demi langkah ini. Tingkatkan produktivitas Anda dengan otomatisasi yang mudah.
type: docs
weight: 10
url: /id/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Perkenalan

Di era digital saat ini, mengonversi dokumen dari satu format ke format lain dan mengirimkannya melalui email adalah tugas yang umum. Artikel ini akan memandu Anda melalui proses mengonversi file DOCX ke format MHTML dan kemudian mengirimkannya sebagai email menggunakan Aspose.Words untuk .NET. Kami akan menguraikan setiap langkah dalam panduan terperinci dan mudah diikuti, memastikan Anda memahami prosesnya dari awal hingga akhir. Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

1. Aspose.Words for .NET: Unduh dan instal perpustakaan Aspose.Words for .NET dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email untuk .NET: Unduh dan instal perpustakaan Aspose.Email untuk .NET dari[Halaman rilis Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: Pastikan Anda telah menginstal .NET Framework di mesin Anda.
4. Server SMTP: Anda memerlukan akses ke server SMTP untuk mengirim email.

## Impor Namespace

Untuk menggunakan Aspose.Words dan Aspose.Email di proyek Anda, Anda perlu mengimpor namespace yang diperlukan. Tambahkan arahan penggunaan berikut di bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Mari kita bagi prosesnya menjadi beberapa langkah untuk memastikan Anda memahami setiap bagian dengan jelas.

## Langkah 1: Muat Dokumen DOCX

 Pertama, Anda perlu memuat dokumen DOCX yang ingin Anda konversi. Menggunakan`Document` kelas dari Aspose.Words untuk memuat file DOCX Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Langkah 2: Simpan Dokumen sebagai MHTML

 Selanjutnya, simpan dokumen yang dimuat sebagai file MHTML. Ini dilakukan dengan menggunakan`Save` metode`Document` kelas.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Putar ulang streaming ke awal sehingga Aspose.Email dapat membacanya.
stream.Position = 0;
```

## Langkah 3: Buat Pesan Email

Sekarang, buat pesan email dari aliran MHTML menggunakan Aspose.Email. Anda akan menggunakan`MailMessage` kelas untuk tujuan ini.

```csharp
// Buat pesan email MIME Aspose.Email dari aliran.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Langkah 4: Kirim Email

 Terakhir, kirim email menggunakan klien SMTP. Konfigurasikan klien SMTP dengan detail server SMTP Anda dan gunakan`Send` metode untuk mengirim pesan.

```csharp
// Kirim pesan menggunakan Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Kesimpulan

Selamat! Anda telah berhasil mengonversi dokumen DOCX ke MHTML dan mengirimkannya melalui email menggunakan Aspose.Words untuk .NET. Proses ini melibatkan memuat dokumen, mengonversinya menjadi MHTML, membuat pesan email, dan mengirimkannya menggunakan klien SMTP. Dengan langkah-langkah ini, Anda dapat dengan mudah mengotomatiskan konversi dan pengiriman dokumen melalui email di aplikasi Anda.

## FAQ

### Bisakah saya menggunakan metode ini untuk mengonversi format dokumen lain?
Ya, Aspose.Words mendukung berbagai format, dan Anda dapat mengonversi dokumen seperti DOC, DOCX, RTF, dan lainnya ke MHTML.

### Bagaimana cara menambahkan lampiran ke email?
 Anda dapat menggunakan`Attachments` properti dari`MailMessage`kelas untuk menambahkan lampiran ke email Anda.

### Apakah Aspose.Words kompatibel dengan .NET Core?
Ya, Aspose.Words kompatibel dengan .NET Core. Anda juga dapat menggunakannya di aplikasi .NET Core.

### Apakah saya memerlukan lisensi untuk Aspose.Words dan Aspose.Email?
 Ya, kedua perpustakaan memerlukan lisensi. Anda bisa mendapatkan lisensi sementara dari[Asumsikan halaman pembelian](https://purchase.aspose.com/temporary-license/) untuk tujuan evaluasi.

### Di mana saya dapat menemukan dokumentasi lainnya?
 Anda dapat menemukan dokumentasi terperinci untuk Aspose.Words[Di Sini](https://reference.aspose.com/words/net/) dan untuk Aspose.Email[Di Sini](https://reference.aspose.com/email/net/).
