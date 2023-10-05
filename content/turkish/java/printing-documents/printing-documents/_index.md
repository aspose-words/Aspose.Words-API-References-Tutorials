---
title: Aspose.Words for Java'da Belgeleri Yazdırma
linktitle: Belgeleri Yazdırma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java kullanarak belgeleri nasıl yazdıracağınızı öğrenin. Java uygulamalarınızda sorunsuz yazdırma için adım adım kılavuz.
type: docs
weight: 10
url: /tr/java/printing-documents/printing-documents/
---

Aspose.Words for Java kullanarak belge yazdırmak istiyorsanız doğru yerdesiniz. Bu adım adım kılavuzda, sağlanan kaynak kodunu kullanarak Aspose.Words for Java ile belgeleri yazdırma sürecinde size yol göstereceğiz.

## giriiş

Belgeleri yazdırmak birçok uygulamada ortak bir görevdir. Aspose.Words for Java, Word belgeleriyle çalışmak için bunları yazdırma yeteneği de dahil olmak üzere güçlü bir API sağlar. Bu eğitimde size bir Word belgesini yazdırma sürecinde adım adım rehberlik edeceğiz.

## Ortamınızı Kurma

Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Kiti (JDK) yüklü
- Aspose.Words for Java kütüphanesi indirildi ve projenize eklendi

## Belgeyi Yükleme

 Başlamak için yazdırmak istediğiniz Word belgesini yüklemeniz gerekir. Yer değiştirmek`"Your Document Directory"` belgenizin yolu ile ve`"Your Output Directory"` İstenilen çıktı dizini ile.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Yazdırma İşi Oluşturma

Daha sonra yüklenen belgemizi yazdırmak için bir yazdırma işi oluşturacağız. Aşağıdaki kod parçacığı bir yazdırma işini başlatır ve istenen yazıcı ayarlarını belirler.

```java
// Belgemizi yazdırmak için bir yazdırma işi oluşturun.
PrinterJob pj = PrinterJob.getPrinterJob();
//Belgedeki sayfa sayısıyla bir öznitelik kümesini başlatın.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Yazıcı ayarlarını diğer parametrelerle birlikte yazdırma belgesine aktarın.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Belgeyi Yazdırma

Artık yazdırma işimizi ayarladığımıza göre belgeyi yazdırmanın zamanı geldi. Aşağıdaki kod parçacığı belgeyi yazdırma işiyle ilişkilendirir ve yazdırma işlemini başlatır.

```java
// Yazdırılacak belgeyi yazdırma işini kullanarak iletin.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Kaynak Kodunu Tamamlayın
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Belgemizi yazdırmak için bir yazdırma işi oluşturun.
PrinterJob pj = PrinterJob.getPrinterJob();
//Belgedeki sayfa sayısıyla bir öznitelik kümesini başlatın.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Yazıcı ayarlarını diğer parametrelerle birlikte yazdırma belgesine aktarın.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Yazdırılacak belgeyi yazdırma işini kullanarak iletin.
pj.setPrintable(awPrintDoc);
pj.print();
```
MultipagePrintDocument'in kaynak kodu
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <özet>
    /// Özel PrintDocument sınıfının yapıcısı.
    // / </özet>
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
        // Öznitelik kümesinde tanımlandığı şekliyle sayfa başlangıç ve bitiş dizinleri.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Daha sonra oluşturulacak sayfa dizinini hesaplayın.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Sayfa dizini toplam sayfa aralığından fazlaysa hiçbir şey yoktur
        // render etmek için daha fazlası.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Her küçük resim yer tutucusunun boyutunu nokta cinsinden hesaplayın.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Bu kağıda yazdırılacak ilk sayfanın sayısını hesaplayın.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Bu kağıda yazdırılacak son sayfanın numarasını seçin.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Saklanan geçerli sayfadan hesaplanan sayfaya seçilen sayfalar arasında geçiş yapın
        // son Sayfa.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Sütun ve satır endekslerini hesaplayın.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Küçük resmin konumunu dünya koordinatlarında tanımlayın (bu durumda noktalar).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Sol ve üst başlangıç konumlarını hesaplayın.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Hesaplanan koordinatları kullanarak belge sayfasını Graphics nesnesine dönüştürün
                // ve küçük resim yer tutucu boyutu.
                // Yararlı dönüş değeri, sayfanın oluşturulduğu ölçektir.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Sayfa kenarlıklarını çizin (sayfa küçük resmi, küçük resimden daha küçük olabilir)
                // yer tutucu boyutu).
                if (mPrintPageBorders) {
                    // Sayfanın gerçek %100 boyutunu puan cinsinden alın.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Bilinen ölçek faktörünü kullanarak ölçeklenen sayfanın çevresine kenarlık çizin.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Küçük resim yer tutucusunun çevresine kenarlık çizin.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Oluşturma sırasında herhangi bir hata oluşursa hiçbir şey yapmayın.
                // Bu, oluşturma sırasında herhangi bir hata olması durumunda boş bir sayfa çizecektir.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Sayfadaki sütun ve satırların sayısını tanımlayın.
        //Manzara odaklı kağıt.
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
        // Kağıt Dikey yöndeyse genişlik ve yüksekliği değiştirin.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Çözüm

Tebrikler! Aspose.Words for Java'yı kullanarak bir Word belgesini başarıyla yazdırdınız. Bu adım adım kılavuz, belge yazdırmayı Java uygulamalarınıza sorunsuz bir şekilde entegre etmenize yardımcı olacaktır.

## SSS

### S1: Aspose.Words for Java'yı kullanarak bir belgenin belirli sayfalarını yazdırabilir miyim?

 Evet, bir belgeyi yazdırırken sayfa aralığını belirleyebilirsiniz. Kod örneğinde şunu kullandık:`attributes.add(new PageRanges(1, doc.getPageCount()))` Tüm sayfaları yazdırmak için Sayfa aralığını gerektiği gibi ayarlayabilirsiniz.

### S2: Aspose.Words for Java toplu yazdırmaya uygun mudur?

Kesinlikle! Aspose.Words for Java, toplu yazdırma görevleri için çok uygundur. Bir belge listesini yineleyebilir ve benzer kodu kullanarak bunları birer birer yazdırabilirsiniz.

### S3: Yazdırma hatalarını veya istisnalarını nasıl halledebilirim?

Yazdırma işlemi sırasında oluşabilecek olası istisnaları ele almalısınız. İstisnaların ele alınması hakkında bilgi için Aspose.Words for Java belgelerine bakın.

### S4: Yazdırma ayarlarını daha da özelleştirebilir miyim?

Evet, yazdırma ayarlarını özel gereksinimlerinizi karşılayacak şekilde özelleştirebilirsiniz. Mevcut yazdırma seçenekleri hakkında daha fazla bilgi edinmek için Aspose.Words for Java belgelerini inceleyin.

### S5: Aspose.Words for Java için nereden daha fazla yardım ve destek alabilirim?

 Ek destek ve yardım için şu adresi ziyaret edebilirsiniz:[Aspose.Words for Java forumu](https://forum.aspose.com/).

---

Artık Aspose.Words for Java kullanarak belgeleri nasıl yazdıracağınızı başarıyla öğrendiğinize göre, bu işlevselliği Java uygulamalarınızda uygulamaya başlayabilirsiniz. Mutlu kodlama!