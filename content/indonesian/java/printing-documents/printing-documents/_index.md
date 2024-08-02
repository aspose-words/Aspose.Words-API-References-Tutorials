---
title: Mencetak Dokumen di Aspose.Words untuk Java
linktitle: Mencetak Dokumen
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara mencetak dokumen menggunakan Aspose.Words untuk Java. Panduan langkah demi langkah untuk pencetakan lancar di aplikasi Java Anda.
type: docs
weight: 10
url: /id/java/printing-documents/printing-documents/
---

Jika Anda ingin mencetak dokumen menggunakan Aspose.Words untuk Java, Anda berada di tempat yang tepat. Dalam panduan langkah demi langkah ini, kami akan memandu Anda melalui proses pencetakan dokumen dengan Aspose.Words untuk Java menggunakan kode sumber yang disediakan.

## Perkenalan

Mencetak dokumen adalah tugas umum di banyak aplikasi. Aspose.Words for Java menyediakan API yang kuat untuk bekerja dengan dokumen Word, termasuk kemampuan untuk mencetaknya. Dalam tutorial ini, kami akan memandu Anda melalui proses pencetakan dokumen Word langkah demi langkah.

## Menyiapkan Lingkungan Anda

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

- Kit Pengembangan Java (JDK) diinstal
- Aspose.Words untuk perpustakaan Java diunduh dan ditambahkan ke proyek Anda

## Memuat Dokumen

 Untuk memulai, Anda perlu memuat dokumen Word yang ingin Anda cetak. Mengganti`"Your Document Directory"` dengan jalur ke dokumen Anda dan`"Your Output Directory"` dengan direktori keluaran yang diinginkan.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Membuat Pekerjaan Cetak

Selanjutnya, kita akan membuat pekerjaan pencetakan untuk mencetak dokumen yang kita muat. Cuplikan kode di bawah ini menginisialisasi pekerjaan pencetakan dan menetapkan pengaturan printer yang diinginkan.

```java
// Buat pekerjaan cetak untuk mencetak dokumen kita.
PrinterJob pj = PrinterJob.getPrinterJob();
//Inisialisasi kumpulan atribut dengan jumlah halaman dalam dokumen.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Teruskan pengaturan printer beserta parameter lainnya ke dokumen cetak.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Mencetak Dokumen

Sekarang kita sudah menyiapkan pekerjaan pencetakan, saatnya mencetak dokumen. Cuplikan kode berikut mengaitkan dokumen dengan pekerjaan pencetakan dan memulai proses pencetakan.

```java
// Lulus dokumen yang akan dicetak menggunakan pekerjaan cetak.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Kode Sumber Lengkap
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Buat pekerjaan cetak untuk mencetak dokumen kita.
PrinterJob pj = PrinterJob.getPrinterJob();
//Inisialisasi kumpulan atribut dengan jumlah halaman dalam dokumen.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Teruskan pengaturan printer beserta parameter lainnya ke dokumen cetak.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Lulus dokumen yang akan dicetak menggunakan pekerjaan cetak.
pj.setPrintable(awPrintDoc);
pj.print();
```
Kode sumber MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <ringkasan>
    /// Konstruktor kelas PrintDocument khusus.
    // /</ringkasan>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // Indeks awal dan akhir halaman sebagaimana ditentukan dalam kumpulan atribut.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Hitung indeks halaman yang akan dirender selanjutnya.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Jika indeks halaman lebih dari total rentang halaman maka tidak ada apa-apa
        // lebih banyak untuk dirender.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Hitung ukuran setiap placeholder thumbnail dalam poin.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Hitung jumlah halaman pertama yang akan dicetak pada lembar kertas ini.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Pilih nomor halaman terakhir yang akan dicetak pada lembar kertas ini.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Ulangi halaman yang dipilih dari halaman yang disimpan saat ini untuk dihitung
        // halaman terakhir.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Hitung indeks kolom dan baris.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Tentukan lokasi thumbnail dalam koordinat dunia (dalam hal ini titik).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Hitung posisi awal kiri dan atas.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Render halaman dokumen ke objek Grafik menggunakan koordinat terhitung
                // dan ukuran placeholder thumbnail.
                // Nilai kembalian yang berguna adalah skala rendering halaman.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Gambarlah batas halaman (thumbnail halaman boleh lebih kecil dari thumbnail
                // ukuran pengganti).
                if (mPrintPageBorders) {
                    // Dapatkan ukuran halaman 100% sebenarnya dalam poin.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Gambarlah batas di sekeliling halaman yang diskalakan menggunakan faktor skala yang diketahui.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Gambarkan batas di sekeliling placeholder thumbnail.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Jika ada kesalahan yang terjadi saat rendering maka jangan lakukan apa pun.
                // Ini akan menggambar halaman kosong jika ada kesalahan selama rendering.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Tentukan jumlah kolom dan baris pada lembar untuk
        //Kertas berorientasi lanskap.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // Tukar lebar dan tinggi jika kertas dalam orientasi Potret.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Kesimpulan

Selamat! Anda telah berhasil mencetak dokumen Word menggunakan Aspose.Words for Java. Panduan langkah demi langkah ini akan membantu Anda mengintegrasikan pencetakan dokumen ke dalam aplikasi Java Anda dengan lancar.

## FAQ

### Q1: Bisakah saya mencetak halaman tertentu dari dokumen menggunakan Aspose.Words untuk Java?

 Ya, Anda dapat menentukan rentang halaman saat mencetak dokumen. Dalam contoh kode, kami menggunakan`attributes.add(new PageRanges(1, doc.getPageCount()))` untuk mencetak semua halaman. Anda dapat menyesuaikan rentang halaman sesuai kebutuhan.

### Q2: Apakah Aspose.Words untuk Java cocok untuk pencetakan batch?

Sangat! Aspose.Words untuk Java sangat cocok untuk tugas pencetakan batch. Anda dapat menelusuri daftar dokumen dan mencetaknya satu per satu menggunakan kode serupa.

### Q3: Bagaimana cara menangani kesalahan atau pengecualian pencetakan?

Anda harus menangani potensi pengecualian yang mungkin terjadi selama proses pencetakan. Periksa dokumentasi Aspose.Words untuk Java untuk informasi tentang penanganan pengecualian.

### Q4: Dapatkah saya menyesuaikan pengaturan pencetakan lebih lanjut?

Ya, Anda dapat menyesuaikan pengaturan pencetakan untuk memenuhi kebutuhan spesifik Anda. Jelajahi dokumentasi Aspose.Words untuk Java untuk mempelajari selengkapnya tentang opsi pencetakan yang tersedia.

### Q5: Di mana saya bisa mendapatkan lebih banyak bantuan dan dukungan untuk Aspose.Words untuk Java?

 Untuk dukungan dan bantuan tambahan, Anda dapat mengunjungi[Aspose.Words untuk forum Java](https://forum.aspose.com/).

---

Sekarang setelah Anda berhasil mempelajari cara mencetak dokumen menggunakan Aspose.Words untuk Java, Anda dapat mulai mengimplementasikan fungsi ini di aplikasi Java Anda. Selamat membuat kode!