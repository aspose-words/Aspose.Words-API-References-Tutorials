---
title: Aspose.Words for Java에서 문서 인쇄하기
linktitle: 문서 인쇄
second_title: Aspose.Words Java 문서 처리 API
description: Aspose.Words for Java를 사용하여 문서를 인쇄하는 방법을 알아보세요. Java 애플리케이션에서 원활한 인쇄를 위한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/java/printing-documents/printing-documents/
---

Aspose.Words for Java를 사용하여 문서를 인쇄하려는 경우 올바른 위치에 있습니다. 이 단계별 가이드에서는 제공된 소스 코드를 사용하여 Aspose.Words for Java로 문서를 인쇄하는 과정을 안내합니다.

## 소개

문서 인쇄는 많은 응용 프로그램에서 일반적인 작업입니다. Aspose.Words for Java는 Word 문서 인쇄 기능을 포함하여 작업할 수 있는 강력한 API를 제공합니다. 이 튜토리얼에서는 Word 문서를 인쇄하는 과정을 단계별로 안내합니다.

## 환경 설정

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- JDK(Java 개발 키트)가 설치되었습니다.
- Java 라이브러리용 Aspose.Words가 다운로드되어 프로젝트에 추가되었습니다.

## 문서 로드

 시작하려면 인쇄하려는 Word 문서를 로드해야 합니다. 바꾸다`"Your Document Directory"` 문서의 경로와`"Your Output Directory"` 원하는 출력 디렉토리로.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## 인쇄 작업 만들기

다음으로, 로드된 문서를 인쇄하기 위한 인쇄 작업을 생성하겠습니다. 아래 코드 조각은 인쇄 작업을 초기화하고 원하는 프린터 설정을 지정합니다.

```java
// 문서를 인쇄할 인쇄 작업을 만듭니다.
PrinterJob pj = PrinterJob.getPrinterJob();
//문서의 페이지 수로 속성 세트를 초기화합니다.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// 다른 매개변수와 함께 프린터 설정을 인쇄 문서에 전달합니다.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## 문서 인쇄

이제 인쇄 작업을 설정했으므로 문서를 인쇄할 차례입니다. 다음 코드 조각은 문서를 인쇄 작업과 연결하고 인쇄 프로세스를 시작합니다.

```java
// 인쇄 작업을 사용하여 인쇄할 문서를 전달합니다.
pj.setPrintable(awPrintDoc);
pj.print();
```
## 완전한 소스 코드
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// 문서를 인쇄할 인쇄 작업을 만듭니다.
PrinterJob pj = PrinterJob.getPrinterJob();
//문서의 페이지 수로 속성 세트를 초기화합니다.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// 다른 매개변수와 함께 프린터 설정을 인쇄 문서에 전달합니다.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// 인쇄 작업을 사용하여 인쇄할 문서를 전달합니다.
pj.setPrintable(awPrintDoc);
pj.print();
```
MultipagePrintDocument의 소스 코드
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <요약>
    /// 사용자 정의 PrintDocument 클래스의 생성자입니다.
    // / </summary>
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
        // 속성 세트에 정의된 페이지 시작 및 끝 색인입니다.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // 다음에 렌더링할 페이지 인덱스를 계산합니다.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // 페이지 인덱스가 전체 페이지 범위보다 크면 아무것도 없습니다.
        // 렌더링할 것이 더 많습니다.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // 각 축소판 자리 표시자의 크기를 포인트 단위로 계산합니다.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // 이 용지에 인쇄할 첫 번째 페이지의 수를 계산하십시오.
        int startPage = pagesOnCurrentSheet + fromPage;
        // 이 용지에 인쇄할 마지막 페이지 번호를 선택합니다.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //저장된 현재 페이지에서 선택한 페이지를 반복하여 계산합니다.
        // 마지막 페이지.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // 열과 행 인덱스를 계산합니다.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // 세계 좌표(이 경우 점)에서 썸네일 위치를 정의합니다.
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // 왼쪽 및 위쪽 시작 위치를 계산합니다.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // 계산된 좌표를 사용하여 문서 페이지를 그래픽 객체로 렌더링합니다.
                // 및 썸네일 자리 표시자 크기.
                // 유용한 반환 값은 페이지가 렌더링된 규모입니다.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // 페이지 테두리 그리기(페이지 축소판은 축소판보다 작을 수 있음)
                // 자리 표시자 크기).
                if (mPrintPageBorders) {
                    // 페이지의 실제 100% 크기를 포인트 단위로 가져옵니다.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // 알려진 배율 인수를 사용하여 배율이 조정된 페이지 주위에 테두리를 그립니다.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // 축소판 자리 표시자 주위에 테두리를 그립니다.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // 렌더링 중에 오류가 발생하면 아무 것도 수행하지 마십시오.
                // 렌더링 중에 오류가 있으면 빈 페이지가 그려집니다.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // 시트의 열과 행 수를 정의합니다.
        //가로 방향의 종이.
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
        // 용지가 세로 방향인 경우 너비와 높이를 바꿉니다.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## 결론

축하해요! Aspose.Words for Java를 사용하여 Word 문서를 성공적으로 인쇄했습니다. 이 단계별 가이드는 문서 인쇄를 Java 애플리케이션에 원활하게 통합하는 데 도움이 됩니다.

## 자주 묻는 질문

### Q1: Aspose.Words for Java를 사용하여 문서의 특정 페이지를 인쇄할 수 있나요?

 예, 문서를 인쇄할 때 페이지 범위를 지정할 수 있습니다. 코드 예제에서는 다음을 사용했습니다.`attributes.add(new PageRanges(1, doc.getPageCount()))` 모든 페이지를 인쇄하려면 필요에 따라 페이지 범위를 조정할 수 있습니다.

### Q2: Aspose.Words for Java는 배치 인쇄에 적합합니까?

전적으로! Aspose.Words for Java는 배치 인쇄 작업에 매우 적합합니다. 문서 목록을 반복하고 유사한 코드를 사용하여 하나씩 인쇄할 수 있습니다.

### Q3: 인쇄 오류나 예외를 어떻게 처리할 수 있나요?

인쇄 프로세스 중에 발생할 수 있는 잠재적인 예외를 처리해야 합니다. 예외 처리에 대한 정보는 Aspose.Words for Java 설명서를 확인하세요.

### Q4: 인쇄 설정을 추가로 사용자 정의할 수 있습니까?

예, 특정 요구 사항에 맞게 인쇄 설정을 사용자 정의할 수 있습니다. 사용 가능한 인쇄 옵션에 대해 자세히 알아보려면 Aspose.Words for Java 문서를 살펴보세요.

### Q5: Aspose.Words for Java에 대한 추가 도움말과 지원은 어디서 얻을 수 있나요?

 추가 지원 및 지원을 받으려면 다음을 방문하세요.[Aspose.Words for Java 포럼](https://forum.aspose.com/).

---

이제 Aspose.Words for Java를 사용하여 문서를 인쇄하는 방법을 성공적으로 배웠으므로 Java 애플리케이션에서 이 기능 구현을 시작할 수 있습니다. 즐거운 코딩하세요!