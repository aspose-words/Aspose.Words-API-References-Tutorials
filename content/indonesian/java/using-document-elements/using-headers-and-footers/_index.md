---
title: Menggunakan Header dan Footer di Aspose.Words untuk Java
linktitle: Menggunakan Header dan Footer
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari langkah demi langkah cara menggunakan header dan footer di Aspose.Words untuk Java. Buat dokumen profesional dengan mudah.
type: docs
weight: 16
url: /id/java/using-document-elements/using-headers-and-footers/
---

Dalam panduan komprehensif ini, kami akan memandu Anda melalui proses bekerja dengan header dan footer di Aspose.Words untuk Java. Header dan footer adalah elemen penting dalam pemformatan dokumen, dan Aspose.Words menyediakan alat canggih untuk membuat dan menyesuaikannya sesuai kebutuhan Anda.

Sekarang, mari selami setiap langkah ini secara mendetail.

## 1. Pengantar Aspose.Kata-kata

Aspose.Words adalah Java API canggih yang memungkinkan Anda membuat, memanipulasi, dan merender dokumen Word secara terprogram. Ini menyediakan fitur ekstensif untuk pemformatan dokumen, termasuk header dan footer.

## 2. Menyiapkan Lingkungan Java Anda

 Sebelum Anda mulai menggunakan Aspose.Words, pastikan lingkungan pengembangan Java Anda telah diatur dengan benar. Anda dapat menemukan petunjuk pengaturan yang diperlukan di halaman dokumentasi Aspose.Words:[Aspose.Words Dokumentasi Java](https://reference.aspose.com/words/java/).

## 3. Membuat Dokumen Baru

Untuk bekerja dengan header dan footer, Anda perlu membuat dokumen baru menggunakan Aspose.Words. Kode berikut menunjukkan cara melakukan ini:

```java
// Kode Java untuk membuat dokumen baru
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Memahami Pengaturan Halaman

 Pengaturan halaman sangat penting untuk mengontrol tata letak dokumen Anda. Anda dapat menentukan berbagai properti yang terkait dengan header dan footer menggunakan`PageSetup` kelas. Misalnya:

```java
// Menyiapkan properti halaman
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Header/Footer Halaman Pertama yang Berbeda

Aspose.Words memungkinkan Anda memiliki header dan footer berbeda untuk halaman pertama dokumen Anda. Menggunakan`pageSetup.setDifferentFirstPageHeaderFooter(true);` untuk mengaktifkan fitur ini.

## 6. Bekerja dengan Header

### 6.1. Menambahkan Teks ke Header

 Anda dapat menambahkan teks ke header menggunakan`DocumentBuilder`. Berikut ini contohnya:

```java
// Menambahkan teks ke header halaman pertama
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Memasukkan Gambar ke Header

 Untuk menyisipkan gambar ke dalam header, Anda dapat menggunakan`insertImage` metode. Berikut ini contohnya:

```java
// Memasukkan gambar ke dalam header
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Menyesuaikan Gaya Header

Anda dapat menyesuaikan gaya header dengan mengatur berbagai properti seperti font, perataan, dan lainnya, seperti yang ditunjukkan pada contoh di atas.

## 7. Bekerja dengan Footer

### 7.1. Menambahkan Teks ke Footer

 Mirip dengan header, Anda dapat menambahkan teks ke footer menggunakan`DocumentBuilder`. Berikut ini contohnya:

```java
// Menambahkan teks ke footer utama
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Sisipkan teks dan kolom sesuai kebutuhan
```

### 7.2. Memasukkan Gambar ke Footer

 Untuk menyisipkan gambar ke footer, gunakan`insertImage` metode, seperti di header.

### 7.3. Menyesuaikan Gaya Footer

 Sesuaikan gaya footer menggunakan`DocumentBuilder`mirip dengan menyesuaikan header.

## 8. Penomoran Halaman

 Anda dapat memasukkan nomor halaman di header dan footer menggunakan bidang seperti`PAGE`Dan`NUMPAGES`. Bidang ini diperbarui secara otomatis saat Anda menambah atau menghapus halaman.

## 9. Informasi Hak Cipta di Footer

Untuk menambahkan informasi hak cipta ke footer dokumen, Anda bisa menggunakan tabel dengan dua sel, menyelaraskan satu ke kiri dan yang lainnya ke kanan, seperti yang diperlihatkan dalam cuplikan kode.

## 10. Bekerja dengan Banyak Bagian

Aspose.Words memungkinkan Anda bekerja dengan banyak bagian dalam satu dokumen. Anda dapat mengatur pengaturan halaman dan header/footer yang berbeda untuk setiap bagian.

## 11. Orientasi Lanskap

Anda dapat mengubah orientasi bagian tertentu ke mode lanskap jika diperlukan.

## 12. Menyalin Header/Footer dari Bagian Sebelumnya

Menyalin header dan footer dari bagian sebelumnya dapat menghemat waktu saat membuat dokumen yang rumit.

## 13. Menyimpan Dokumen Anda

Setelah membuat dan menyesuaikan dokumen Anda, jangan lupa untuk menyimpannya menggunakan`doc.save()` metode.

## Kode Sumber Lengkap
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Tentukan apakah kita ingin header/footer halaman pertama berbeda dengan halaman lainnya.
        // Anda juga dapat menggunakan properti PageSetup.OddAndEvenPagesHeaderFooter untuk menentukan
        // header/footer yang berbeda untuk halaman ganjil dan genap.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Sisipkan gambar yang diposisikan ke sudut atas/kiri header.
        // Jarak dari tepi atas/kiri halaman diatur ke 10 poin.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Kami menggunakan tabel dengan dua sel untuk membuat satu bagian teks per baris (dengan penomoran halaman).
        // Untuk disejajarkan ke kiri, dan bagian teks lainnya (dengan hak cipta) disejajarkan ke kanan.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Ia menggunakan bidang PAGE dan NUMPAGES untuk menghitung secara otomatis nomor halaman saat ini dan banyak halaman.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Buat hentian halaman untuk membuat halaman kedua di mana header/footer utama akan terlihat.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Bagian ini tidak memerlukan header/footer halaman pertama yang berbeda, kami hanya memerlukan satu halaman judul dalam dokumen,
        //dan header/footer untuk halaman ini telah ditentukan di bagian sebelumnya.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // Bagian ini menampilkan header/footer dari bagian sebelumnya
        // secara default panggil currentSection.HeadersFooters.LinkToPrevious(false) untuk membatalkan lebar halaman ini
        // berbeda untuk bagian baru, dan oleh karena itu kita perlu mengatur lebar sel yang berbeda untuk tabel footer.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Jika kita ingin menggunakan set header/footer yang sudah ada untuk bagian ini.
        // Namun dengan sedikit modifikasi, mungkin lebih baik menyalin header/footer
        // dari bagian sebelumnya dan terapkan modifikasi yang diperlukan sesuai keinginan kita.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Kode sumber metode copyHeadersFootersFromPviousSection
```java
    /// <ringkasan>
    /// Mengkloning dan menyalin header/footer dari bagian sebelumnya ke bagian yang ditentukan.
    ///</ringkasan>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Kesimpulan

Dalam tutorial ini, kita telah membahas dasar-dasar bekerja dengan header dan footer di Aspose.Words untuk Java. Anda telah mempelajari cara membuat, menyesuaikan, dan menata gaya header dan footer, serta teknik pemformatan dokumen penting lainnya.

 Untuk rincian lebih lanjut dan fitur lanjutan, lihat[Aspose.Words Dokumentasi Java](https://reference.aspose.com/words/java/).

## FAQ

### 1. Bagaimana cara menambahkan nomor halaman ke footer dokumen saya?
 Anda dapat menambahkan nomor halaman dengan memasukkan`PAGE` bidang ke footer menggunakan Aspose.Words.

### 2. Apakah Aspose.Words kompatibel dengan lingkungan pengembangan Java?
Ya, Aspose.Words menyediakan dukungan untuk pengembangan Java. Pastikan Anda memiliki pengaturan yang diperlukan.

### 3. Bisakah saya menyesuaikan font dan gaya header dan footer?
Tentu saja, Anda dapat menyesuaikan font, perataan, dan gaya lainnya untuk membuat header dan footer Anda menarik secara visual.

### 4. Apakah mungkin untuk memiliki header yang berbeda untuk halaman ganjil dan genap?
 Ya, Anda bisa menggunakannya`PageSetup.OddAndEvenPagesHeaderFooter` untuk menentukan header berbeda untuk halaman ganjil dan genap.

### 5. Bagaimana cara memulai Aspose.Words untuk Java?
 Untuk memulai, kunjungi[Aspose.Words Dokumentasi Java](https://reference.aspose.com/words/java/) untuk panduan komprehensif tentang penggunaan API.