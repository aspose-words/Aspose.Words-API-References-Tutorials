---
title: In tài liệu trong Aspose.Words cho Java
linktitle: In tài liệu
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách in tài liệu bằng Aspose.Words cho Java. Hướng dẫn từng bước để in liền mạch trong các ứng dụng Java của bạn.
type: docs
weight: 10
url: /vi/java/printing-documents/printing-documents/
---

Nếu bạn đang muốn in tài liệu bằng Aspose.Words cho Java thì bạn đã đến đúng nơi. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình in tài liệu bằng Aspose.Words cho Java bằng mã nguồn được cung cấp.

## Giới thiệu

In tài liệu là một nhiệm vụ phổ biến trong nhiều ứng dụng. Aspose.Words for Java cung cấp một API mạnh mẽ để làm việc với các tài liệu Word, bao gồm cả khả năng in chúng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước quy trình in tài liệu Word.

## Thiết lập môi trường của bạn

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Đã cài đặt Bộ công cụ phát triển Java (JDK)
- Thư viện Aspose.Words for Java đã được tải xuống và thêm vào dự án của bạn

## Đang tải tài liệu

 Để bắt đầu, bạn cần tải tài liệu Word mà bạn muốn in. Thay thế`"Your Document Directory"` với đường dẫn đến tài liệu của bạn và`"Your Output Directory"` với thư mục đầu ra mong muốn.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Tạo lệnh in

Tiếp theo, chúng tôi sẽ tạo lệnh in để in tài liệu đã tải của mình. Đoạn mã bên dưới khởi tạo lệnh in và đặt cài đặt máy in mong muốn.

```java
// Tạo một lệnh in để in tài liệu của chúng tôi.
PrinterJob pj = PrinterJob.getPrinterJob();
//Khởi tạo một tập thuộc tính với số trang trong tài liệu.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Chuyển cài đặt máy in cùng với các thông số khác vào tài liệu in.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## In tài liệu

Bây giờ chúng ta đã thiết lập xong lệnh in, đã đến lúc in tài liệu. Đoạn mã sau liên kết tài liệu với lệnh in và bắt đầu quá trình in.

```java
// Chuyển tài liệu sẽ được in bằng lệnh in.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Mã nguồn hoàn chỉnh
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Tạo một lệnh in để in tài liệu của chúng tôi.
PrinterJob pj = PrinterJob.getPrinterJob();
//Khởi tạo một tập thuộc tính với số trang trong tài liệu.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Chuyển cài đặt máy in cùng với các thông số khác vào tài liệu in.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Chuyển tài liệu sẽ được in bằng lệnh in.
pj.setPrintable(awPrintDoc);
pj.print();
```
Mã nguồn của MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <tóm tắt>
    /// Hàm tạo của lớp PrintDocument tùy chỉnh.
    // / </tóm tắt>
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
        // Các chỉ số bắt đầu và kết thúc trang như được xác định trong tập thuộc tính.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Tính chỉ mục trang sẽ được hiển thị tiếp theo.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Nếu chỉ mục trang lớn hơn tổng phạm vi trang thì không có gì
        // nhiều hơn nữa để kết xuất.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Tính toán kích thước của mỗi phần giữ chỗ hình thu nhỏ theo điểm.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Tính số trang đầu tiên in trên tờ giấy này.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Chọn số trang cuối cùng sẽ được in trên tờ giấy này.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Lặp lại các trang đã chọn từ trang hiện tại được lưu trữ đến trang được tính toán
        // trang cuối.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Tính chỉ số cột và hàng.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Xác định vị trí hình thu nhỏ trong tọa độ thế giới (điểm trong trường hợp này).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Tính toán vị trí bắt đầu bên trái và trên cùng.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Hiển thị trang tài liệu cho đối tượng Đồ họa bằng tọa độ được tính toán
                // và kích thước giữ chỗ hình thu nhỏ.
                // Giá trị trả về hữu ích là tỷ lệ mà trang được hiển thị.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Vẽ đường viền trang (hình thu nhỏ của trang có thể nhỏ hơn hình thu nhỏ
                // kích thước giữ chỗ).
                if (mPrintPageBorders) {
                    // Nhận kích thước thực 100% của trang theo điểm.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Vẽ đường viền xung quanh trang được chia tỷ lệ bằng cách sử dụng hệ số tỷ lệ đã biết.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Vẽ đường viền xung quanh phần giữ chỗ hình thu nhỏ.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Nếu có bất kỳ lỗi nào xảy ra trong quá trình kết xuất thì không cần làm gì cả.
                // Điều này sẽ vẽ một trang trống nếu có bất kỳ lỗi nào trong quá trình kết xuất.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Xác định số cột và hàng trên trang tính cho
        //Giấy hướng cảnh quan.
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
        // Hoán đổi chiều rộng và chiều cao nếu giấy ở hướng dọc.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Phần kết luận

Chúc mừng! Bạn đã in thành công tài liệu Word bằng Aspose.Words cho Java. Hướng dẫn từng bước này sẽ giúp bạn tích hợp tính năng in tài liệu vào các ứng dụng Java của mình một cách liền mạch.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể in các trang cụ thể của tài liệu bằng Aspose.Words cho Java không?

 Có, bạn có thể chỉ định phạm vi trang khi in tài liệu. Trong ví dụ về mã, chúng tôi đã sử dụng`attributes.add(new PageRanges(1, doc.getPageCount()))` để in tất cả các trang. Bạn có thể điều chỉnh phạm vi trang nếu cần.

### Câu hỏi 2: Aspose.Words cho Java có phù hợp để in hàng loạt không?

Tuyệt đối! Aspose.Words for Java rất phù hợp cho các tác vụ in hàng loạt. Bạn có thể lặp qua danh sách tài liệu và in từng tài liệu bằng cách sử dụng mã tương tự.

### Câu hỏi 3: Làm cách nào để xử lý các lỗi in hoặc trường hợp ngoại lệ?

Bạn nên xử lý mọi trường hợp ngoại lệ tiềm ẩn có thể xảy ra trong quá trình in. Kiểm tra tài liệu Aspose.Words for Java để biết thông tin về cách xử lý các ngoại lệ.

### Q4: Tôi có thể tùy chỉnh thêm cài đặt in không?

Có, bạn có thể tùy chỉnh cài đặt in để đáp ứng các yêu cầu cụ thể của mình. Khám phá tài liệu Aspose.Words for Java để tìm hiểu thêm về các tùy chọn in có sẵn.

### Câu hỏi 5: Tôi có thể nhận thêm trợ giúp và hỗ trợ cho Aspose.Words cho Java ở đâu?

 Để được hỗ trợ và trợ giúp thêm, bạn có thể truy cập[Diễn đàn Aspose.Words cho Java](https://forum.aspose.com/).

---

Bây giờ bạn đã học thành công cách in tài liệu bằng Aspose.Words cho Java, bạn có thể bắt đầu triển khai chức năng này trong các ứng dụng Java của mình. Chúc mừng mã hóa!