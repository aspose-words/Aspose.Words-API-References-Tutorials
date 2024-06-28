---
title: การแบ่งเอกสารออกเป็นหน้าต่างๆ ใน Aspose.Words สำหรับ Java
linktitle: การแบ่งเอกสารออกเป็นหน้าต่างๆ
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้วิธีแบ่งเอกสารออกเป็นหน้าต่างๆ โดยใช้ Aspose.Words สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการประมวลผลเอกสารที่มีประสิทธิภาพ
type: docs
weight: 23
url: /th/java/document-manipulation/splitting-documents-into-pages/
---

หากคุณกำลังทำงานกับการประมวลผลเอกสารใน Java Aspose.Words สำหรับ Java เป็น API ที่ทรงพลังที่สามารถช่วยคุณแบ่งเอกสารออกเป็นหน้าต่างๆ ได้อย่างมีประสิทธิภาพ ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดกระบวนการแยกเอกสารโดยใช้ซอร์สโค้ดที่ให้มา เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะสามารถแบ่งเอกสารได้อย่างง่ายดาย และปรับปรุงความสามารถในการจัดการเอกสารของคุณ

## 1. บทนำ

Aspose.Words for Java เป็นไลบรารี Java ที่ให้คุณจัดการเอกสาร Word โดยทางโปรแกรม งานทั่วไปอย่างหนึ่งคือการแบ่งเอกสารออกเป็นหน้าต่างๆ ซึ่งอาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การเก็บถาวร การพิมพ์ หรือการประมวลผลเอกสาร

## 2. ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Words สำหรับไลบรารี Java ซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/words/java/).

## 3. การตั้งค่าสภาพแวดล้อมของคุณ

ในการเริ่มต้น ให้ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณดังนี้:

- สร้างโปรเจ็กต์ Java ใน Integrated Development Environment (IDE) ที่คุณต้องการ
- เพิ่มไลบรารี Aspose.Words สำหรับ Java ให้กับโปรเจ็กต์ของคุณ คุณสามารถอ้างถึง[เอกสารประกอบ](https://reference.aspose.com/words/java/) สำหรับคำแนะนำโดยละเอียด

## 4. การทำความเข้าใจซอร์สโค้ด

ซอร์สโค้ดที่คุณระบุได้รับการออกแบบมาเพื่อแบ่งเอกสารออกเป็นหน้าต่างๆ มาดูรายละเอียดส่วนประกอบสำคัญกัน:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- เราแยกชื่อฐานและนามสกุลออกจากเอกสารอินพุต
- เราโหลดเอกสารโดยใช้ Aspose.Words สำหรับ Java

## 5. การแยกเอกสารทีละขั้นตอน

### 5.1. กำลังโหลดเอกสาร

```java
Document doc = new Document(docName);
```

 ในขั้นตอนนี้ เราจะโหลดเอกสารอินพุตเข้าใน`Document` ซึ่งช่วยให้เราสามารถทำงานกับเนื้อหาของเอกสารได้

### 5.2. กำลังเริ่มต้น DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 เราเริ่มต้นก`DocumentPageSplitter` วัตถุด้วยเอกสารที่เราโหลด คลาสนี้จัดทำโดย Aspose.Words สำหรับ Java และช่วยเราแบ่งเอกสารออกเป็นหน้าต่างๆ

### 5.3. บันทึกแต่ละหน้า

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

ในขั้นตอนนี้ เราจะวนซ้ำแต่ละหน้าของเอกสารและบันทึกเป็นเอกสารแยกต่างหาก คุณสามารถระบุเส้นทางไดเรกทอรีที่จะบันทึกหน้าแยกได้

## 6. การรันโค้ด

หากต้องการเรียกใช้โค้ดนี้ให้สำเร็จ ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณและเพิ่มไลบรารี Aspose.Words for Java ลงในโปรเจ็กต์ของคุณ จากนั้น รันโค้ด จากนั้นเอกสารของคุณจะแบ่งออกเป็นหน้าต่างๆ

## ซอร์สโค้ด DocumentPageSplitter

```java
/// <สรุป>
/// แยกเอกสารออกเป็นหลายเอกสาร หนึ่งรายการต่อหน้า
/// </สรุป>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <สรุป>
/// เตรียมใช้งานอินสแตนซ์ใหม่ของคลาส <see cref="DocumentPageSplitter"/>
/// วิธีนี้จะแบ่งเอกสารออกเป็นส่วนๆ เพื่อให้แต่ละหน้าเริ่มต้นและสิ้นสุดที่ส่วนของขอบเขต
/// แนะนำว่าอย่าแก้ไขเอกสารในภายหลัง
/// </สรุป>
/// <param name="source">เอกสารต้นฉบับ</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <สรุป>
///รับเอกสารของเพจ
/// </สรุป>
/// <ชื่อพารามิเตอร์="pageIndex">
/// ดัชนีตาม 1 ของหน้า
///</พารามิเตอร์>
/// <การส่งคืน>
///<ดูcref="เอกสาร"/>
/// </ผลตอบแทน>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <สรุป>
/// รับเอกสารของช่วงหน้า
/// </สรุป>
//<ชื่อพารามิเตอร์="startIndex">
/// ดัชนีฐาน 1 ของหน้าเริ่มต้น
///</พารามิเตอร์>
/// <ชื่อพารามิเตอร์="endIndex">
/// ดัชนีฐาน 1 ของหน้าสุดท้าย
///</พารามิเตอร์>
/// <การส่งคืน>
///<ดูcref="เอกสาร"/>
/// </ผลตอบแทน>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <สรุป>
/// จัดให้มีวิธีการแยกโหนดของเอกสารที่แสดงผลบนหน้าที่ระบุ
/// </สรุป>
class PageNumberFinder
{
// แมปโหนดกับหมายเลขหน้าเริ่มต้น/สิ้นสุด
// ใช้เพื่อแทนที่หมายเลขหน้าพื้นฐานที่ตัวรวบรวมระบุไว้เมื่อเอกสารถูกแยก
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// จับคู่หมายเลขหน้ากับรายการโหนดที่พบในหน้านั้น
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <สรุป>
/// เตรียมใช้งานอินสแตนซ์ใหม่ของคลาส <see cref="PageNumberFinder"/>
/// </สรุป>
/// <param name="collector">อินสแตนซ์ตัวรวบรวมที่มีบันทึกโมเดลโครงร่างสำหรับเอกสาร</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <สรุป>
/// ดึงดัชนีฐาน 1 ของหน้าที่โหนดเริ่มต้น
/// </สรุป>
/// <ชื่อพารามิเตอร์="โหนด">
///โหนด
///</พารามิเตอร์>
/// <การส่งคืน>
///ดัชนีหน้า
/// </ผลตอบแทน>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <สรุป>
/// ดึงดัชนีฐาน 1 ของหน้าที่โหนดสิ้นสุด
/// </สรุป>
/// <ชื่อพารามิเตอร์="โหนด">
///โหนด
///</พารามิเตอร์>
/// <การส่งคืน>
///ดัชนีหน้า
/// </ผลตอบแทน>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <สรุป>
//ส่งคืนจำนวนเพจที่โหนดที่ระบุครอบคลุม ส่งคืน 1 หากโหนดอยู่ภายในหนึ่งหน้า
/// </สรุป>
/// <ชื่อพารามิเตอร์="โหนด">
///โหนด
///</พารามิเตอร์>
/// <การส่งคืน>
///ดัชนีหน้า
/// </ผลตอบแทน>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <สรุป>
///ส่งคืนรายการโหนดที่มีอยู่ในที่ใดก็ได้ในหน้าที่ระบุหรือหน้าที่ตรงกับประเภทโหนดที่ระบุ
/// </สรุป>
/// <ชื่อพารามิเตอร์="startPage">
///หน้าเริ่มต้น.
///</พารามิเตอร์>
/// <ชื่อพารามิเตอร์="endPage">
///หน้าสุดท้าย.
///</พารามิเตอร์>
/// <ชื่อพารามิเตอร์="nodeType">
///ประเภทโหนด
///</พารามิเตอร์>
/// <การส่งคืน>
///<see cref="IList{T}"/>.
/// </ผลตอบแทน>
public ArrayList<Node> retrieveAllNodesOnPages(int startPage, int endPage, /*NodeType*/int nodeType) throws Exception
{
	if (startPage < 1 || startPage > collector.getDocument().getPageCount())
	{
		throw new IllegalStateException("'startPage' is out of range");
	}
	if (endPage < 1 || endPage > collector.getDocument().getPageCount() || endPage < startPage)
	{
		throw new IllegalStateException("'endPage' is out of range");
	}
	checkPageListsPopulated();
	ArrayList<Node> pageNodes = new ArrayList<>();
	for (int page = startPage; page <= endPage; page++)
	{
		// บางหน้าสามารถเว้นว่างได้
		if (!reversePageLookup.containsKey(page))
		{
			continue;
		}
		for (Node node : reversePageLookup.get(page))
		{
			if (node.getParentNode() != null
				&& (nodeType == NodeType.ANY || node.getNodeType() == nodeType)
				&& !pageNodes.contains(node))
			{
				pageNodes.add(node);
			}
		}
	}
	return pageNodes;
}
/// <สรุป>
/// แยกโหนดที่ปรากฏมากกว่าสองหน้าขึ้นไปออกเป็นโหนดแยกกันเพื่อให้ยังคงปรากฏในลักษณะเดียวกัน
///แต่ไม่ปรากฏข้ามหน้าอีกต่อไป
/// </สรุป>
public void splitNodesAcrossPages() throws Exception
{
	for (Paragraph paragraph : (Iterable<Paragraph>) collector.getDocument().getChildNodes(NodeType.PARAGRAPH, true))
	{
		if (getPage(paragraph) != getPageEnd(paragraph))
		{
			splitRunsByWords(paragraph);
		}
	}
	clearCollector();
	// ไปที่คอมโพสิตใดๆ ที่อาจแบ่งออกเป็นหน้าต่างๆ และแยกออกเป็นโหนดแยกกัน
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <สรุป>
/// สิ่งนี้ถูกเรียกโดย <see cref="SectionSplitter"/> เพื่ออัปเดตหมายเลขหน้าของโหนดแยก
/// </สรุป>
/// <ชื่อพารามิเตอร์="โหนด">
///โหนด
///</พารามิเตอร์>
/// <ชื่อพารามิเตอร์="startPage">
///หน้าเริ่มต้น.
///</พารามิเตอร์>
/// <ชื่อพารามิเตอร์="endPage">
///หน้าสุดท้าย.
///</พารามิเตอร์>
void addPageNumbersForNode(Node node, int startPage, int endPage)
{
	if (startPage > 0)
	{
		nodeStartPageLookup.put(node, startPage);
	}
	if (endPage > 0)
	{
		nodeEndPageLookup.put(node, endPage);
	}
}
private boolean isHeaderFooterType(Node node)
{
	return node.getNodeType() == NodeType.HEADER_FOOTER || node.getAncestor(NodeType.HEADER_FOOTER) != null;
}
private void checkPageListsPopulated() throws Exception {
	if (reversePageLookup != null)
	{
		return;
	}
	reversePageLookup = new HashMap<Integer, ArrayList<Node>>();
	// เพิ่มแต่ละโหนดในรายการที่แสดงถึงโหนดที่พบในแต่ละหน้า
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//ส่วนหัว/ส่วนท้ายเป็นไปตามส่วนต่างๆ และไม่มีการแบ่งแยกกัน
		if (isHeaderFooterType(node))
		{
			continue;
		}
		int startPage = getPage(node);
		int endPage = getPageEnd(node);
		for (int page = startPage; page <= endPage; page++)
		{
			if (!reversePageLookup.containsKey(page))
			{
				reversePageLookup.put(page, new ArrayList<Node>());
			}
			reversePageLookup.get(page).add(node);
		}
	}
}
private void splitRunsByWords(Paragraph paragraph) throws Exception {
	for (Run run : paragraph.getRuns())
	{
		if (getPage(run) == getPageEnd(run))
		{
			continue;
		}
		splitRunByWords(run);
	}
}
private void splitRunByWords(Run run)
{
	String[] words = reverseWord(run.getText());
	for (String word : words)
	{
		int pos = run.getText().length() - word.length() - 1;
		if (pos > 1)
		{
			splitRun(run, run.getText().length() - word.length() - 1);
		}
	}
}
private static String[] reverseWord(String str) {
	String words[] = str.split(" ");
	String reverseWord = "";
	for (String w : words) {
		StringBuilder sb = new StringBuilder(w);
		sb.reverse();
		reverseWord += sb.toString() + " ";
	}
	return reverseWord.split(" ");
}
/// <สรุป>
/// แยกข้อความของการรันที่ระบุออกเป็นสองรัน
///แทรกการรันใหม่หลังจากการรันที่ระบุ
/// </สรุป>
private void splitRun(Run run, int position)
{
	Run afterRun = (Run) run.deepClone(true);
	afterRun.setText(run.getText().substring(position));
	run.setText(run.getText().substring((0), (0) + (position)));
	run.getParentNode().insertAfter(afterRun, run);
}
private void clearCollector() throws Exception
{
	collector.clear();
	collector.getDocument().updatePageLayout();
	nodeStartPageLookup.clear();
	nodeEndPageLookup.clear();
}
}
class PageNumberFinderFactory
{
public static PageNumberFinder create(Document document) throws Exception
{
	LayoutCollector layoutCollector = new LayoutCollector(document);
	document.updatePageLayout();
	PageNumberFinder pageNumberFinder = new PageNumberFinder(layoutCollector);
	pageNumberFinder.splitNodesAcrossPages();
	return pageNumberFinder;
}
}
/// <สรุป>
/// แยกเอกสารออกเป็นหลายส่วนเพื่อให้แต่ละหน้าเริ่มต้นและสิ้นสุดที่ส่วนของขอบเขต
/// </สรุป>
class SectionSplitter extends DocumentVisitor
{
private PageNumberFinder pageNumberFinder;
public SectionSplitter(PageNumberFinder pageNumberFinder)
{
	this.pageNumberFinder = pageNumberFinder;
}
public int visitParagraphStart(Paragraph paragraph) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(paragraph);
}
public int visitTableStart(Table table) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(table);
}
public int visitRowStart(Row row) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(row);
}
public int visitCellStart(Cell cell) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(cell);
}
public int visitStructuredDocumentTagStart(StructuredDocumentTag sdt) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(sdt);
}
public int visitSmartTagStart(SmartTag smartTag) throws Exception {
	return continueIfCompositeAcrossPageElseSkip(smartTag);
}
public int visitSectionStart(Section section) throws Exception {
	Section previousSection = (Section) section.getPreviousSibling();
	// หากมีส่วนก่อนหน้า ให้พยายามคัดลอกส่วนท้ายของส่วนหัวที่เชื่อมโยง
	// มิฉะนั้นจะไม่ปรากฏในเอกสารที่แยกออกมาหากไม่มีส่วนก่อนหน้า
	if (previousSection != null)
	{
		HeaderFooterCollection previousHeaderFooters = previousSection.getHeadersFooters();
		if (!section.getPageSetup().getRestartPageNumbering())
		{
			section.getPageSetup().setRestartPageNumbering(true);
			section.getPageSetup().setPageStartingNumber(previousSection.getPageSetup().getPageStartingNumber() +
												   pageNumberFinder.pageSpan(previousSection));
		}
		for (HeaderFooter previousHeaderFooter : (Iterable<HeaderFooter>) previousHeaderFooters)
		{
			if (section.getHeadersFooters().getByHeaderFooterType(previousHeaderFooter.getHeaderFooterType()) == null)
			{
				HeaderFooter newHeaderFooter =
					(HeaderFooter) previousHeaderFooters.getByHeaderFooterType(previousHeaderFooter.getHeaderFooterType()).deepClone(true);
				section.getHeadersFooters().add(newHeaderFooter);
			}
		}
	}
	return continueIfCompositeAcrossPageElseSkip(section);
}
public int visitSmartTagEnd(SmartTag smartTag) throws Exception {
	splitComposite(smartTag);
	return VisitorAction.CONTINUE;
}
public int visitStructuredDocumentTagEnd(StructuredDocumentTag sdt) throws Exception {
	splitComposite(sdt);
	return VisitorAction.CONTINUE;
}
public int visitCellEnd(Cell cell) throws Exception {
	splitComposite(cell);
	return VisitorAction.CONTINUE;
}
public int visitRowEnd(Row row) throws Exception {
	splitComposite(row);
	return VisitorAction.CONTINUE;
}
public int visitTableEnd(Table table) throws Exception {
	splitComposite(table);
	return VisitorAction.CONTINUE;
}
public int visitParagraphEnd(Paragraph paragraph) throws Exception {
	// หากย่อหน้ามีเพียงตัวแบ่งส่วน ให้เพิ่มการวิ่งปลอมเข้าไป
	if (paragraph.isEndOfSection() && paragraph.getChildNodes().getCount() == 1 &&
		"\f".equals(paragraph.getChildNodes().get(0).getText()))
	{
		Run run = new Run(paragraph.getDocument());
		paragraph.appendChild(run);
		int currentEndPageNum = pageNumberFinder.getPageEnd(paragraph);
		pageNumberFinder.addPageNumbersForNode(run, currentEndPageNum, currentEndPageNum);
	}
	for (Node cloneNode : splitComposite(paragraph))
	{
		Paragraph clonePara = (Paragraph) cloneNode;
		// ลบหมายเลขรายการออกจากย่อหน้าที่คัดลอก แต่ปล่อยให้ดัชนีเหมือนเดิม
		// เนื่องจากย่อหน้าควรจะเป็นส่วนหนึ่งของรายการก่อนหน้า
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// รีเซ็ตระยะห่างของย่อหน้าที่แยกในตาราง เนื่องจากการเว้นวรรคเพิ่มเติมอาจทำให้ย่อหน้าดูแตกต่างออกไป
		if (paragraph.isInCell())
		{
			clonePara.getParagraphFormat().setSpaceBefore(0.0);
			paragraph.getParagraphFormat().setSpaceAfter(0.0);
		}
	}
	return VisitorAction.CONTINUE;
}
public int visitSectionEnd(Section section) throws Exception {
	for (Node cloneNode : splitComposite(section))
	{
		Section cloneSection = (Section) cloneNode;
		cloneSection.getPageSetup().setSectionStart(SectionStart.NEW_PAGE);
		cloneSection.getPageSetup().setRestartPageNumbering(true);
		cloneSection.getPageSetup().setPageStartingNumber(section.getPageSetup().getPageStartingNumber() +
													(section.getDocument().indexOf(cloneSection) -
													 section.getDocument().indexOf(section)));
		cloneSection.getPageSetup().setDifferentFirstPageHeaderFooter(false);
		// แก้ไขตัวแบ่งหน้าที่ส่วนท้ายของส่วน
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// เพิ่มการกำหนดหมายเลขหน้าใหม่สำหรับเนื้อหาของส่วนด้วย
	pageNumberFinder.addPageNumbersForNode(section.getBody(), pageNumberFinder.getPage(section),
		pageNumberFinder.getPageEnd(section));
	return VisitorAction.CONTINUE;
}
private /*VisitorAction*/int continueIfCompositeAcrossPageElseSkip(CompositeNode composite) throws Exception {
	return pageNumberFinder.pageSpan(composite) > 1
		? VisitorAction.CONTINUE
		: VisitorAction.SKIP_THIS_NODE;
}
private ArrayList<Node> splitComposite(CompositeNode composite) throws Exception {
	ArrayList<Node> splitNodes = new ArrayList<>();
	for (Node splitNode : findChildSplitPositions(composite))
	{
		splitNodes.add(splitCompositeAtNode(composite, splitNode));
	}
	return splitNodes;
}
private Iterable<Node> findChildSplitPositions(CompositeNode node) throws Exception {
	// โหนดอาจครอบคลุมหลายหน้า ดังนั้นรายการตำแหน่งที่แยกจึงถูกส่งกลับ
	//โหนดแยกเป็นโหนดแรกในหน้าถัดไป
	ArrayList<Node> splitList = new ArrayList<Node>();
	int startingPage = pageNumberFinder.getPage(node);
	Node[] childNodes = node.getNodeType() == NodeType.SECTION
		? ((Section) node).getBody().getChildNodes().toArray()
		: node.getChildNodes().toArray();
	for (Node childNode : childNodes)
	{
		int pageNum = pageNumberFinder.getPage(childNode);
		if (childNode instanceof Run)
		{
			pageNum = pageNumberFinder.getPageEnd(childNode);
		}
		// หากเพจของโหนดลูกมีการเปลี่ยนแปลง นี่คือตำแหน่งการแยก
		// เพิ่มสิ่งนี้ลงในรายการ
		if (pageNum > startingPage)
		{
			splitList.add(childNode);
			startingPage = pageNum;
		}
		if (pageNumberFinder.pageSpan(childNode) > 1)
		{
			pageNumberFinder.addPageNumbersForNode(childNode, pageNum, pageNum);
		}
	}
	// แยกคอมโพสิตไปด้านหลัง เพื่อให้โหนดที่โคลนถูกแทรกในลำดับที่ถูกต้อง
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// ย้ายโหนดทั้งหมดที่พบในหน้าถัดไปไปยังโหนดที่คัดลอก จัดการโหนดแถวแยกจากกัน
	if (baseNode.getNodeType() != NodeType.ROW)
	{
		CompositeNode composite = cloneNode;
		if (baseNode.getNodeType() == NodeType.SECTION)
		{
			cloneNode = (CompositeNode) baseNode.deepClone(true);
			Section section = (Section) cloneNode;
			section.getBody().removeAllChildren();
			composite = section.getBody();
		}
		while (node != null)
		{
			Node nextNode = node.getNextSibling();
			composite.appendChild(node);
			node = nextNode;
		}
	}
	else
	{
		// หากเรากำลังจัดการกับแถว เราจำเป็นต้องเพิ่มเซลล์จำลองสำหรับแถวที่โคลน
		int targetPageNum = pageNumberFinder.getPage(targetNode);
		Node[] childNodes = baseNode.getChildNodes().toArray();
		for (Node childNode : childNodes)
		{
			int pageNum = pageNumberFinder.getPage(childNode);
			if (pageNum == targetPageNum)
			{
				if (cloneNode.getNodeType() == NodeType.ROW)
					((Row) cloneNode).ensureMinimum();
				if (cloneNode.getNodeType() == NodeType.CELL)
					((Cell) cloneNode).ensureMinimum();
				cloneNode.getLastChild().remove();
				cloneNode.appendChild(childNode);
			}
			else if (pageNum == currentPageNum)
			{
				cloneNode.appendChild(childNode.deepClone(false));
				if (cloneNode.getLastChild().getNodeType() != NodeType.CELL)
				{
					((CompositeNode) cloneNode.getLastChild()).appendChild(
						((CompositeNode) childNode).getFirstChild().deepClone(false));
				}
			}
		}
	}
	// แทรกโหนดแยกหลังต้นฉบับ
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// อัพเดตหมายเลขหน้าใหม่ของโหนดฐานและโหนดที่โคลน รวมถึงการสืบทอด
	// นี่จะเป็นเพียงหน้าเดียวเนื่องจากคอมโพสิตที่ลอกแบบมาจะถูกแยกออกเป็นหน้าเดียว
	int currentEndPageNum = pageNumberFinder.getPageEnd(baseNode);
	pageNumberFinder.addPageNumbersForNode(baseNode, currentPageNum, currentEndPageNum - 1);
	pageNumberFinder.addPageNumbersForNode(cloneNode, currentEndPageNum, currentEndPageNum);
	for (Node childNode : (Iterable<Node>) cloneNode.getChildNodes(NodeType.ANY, true))
	{
		pageNumberFinder.addPageNumbersForNode(childNode, currentEndPageNum, currentEndPageNum);
	}
	return cloneNode;
}
}

class SplitPageBreakCorrector
{
private static final String PAGE_BREAK_STR = "\f";
private static final char PAGE_BREAK = '\f';
public static void processSection(Section section)
{
	if (section.getChildNodes().getCount() == 0)
	{
		return;
	}
	Body lastBody = (Body) Arrays.stream(new Iterator[]{section.getChildNodes().iterator()}).reduce((first, second) -> second)
		.orElse(null);
	RunCollection runs = (RunCollection) lastBody.getChildNodes(NodeType.RUN, true).iterator();
	Run run  = Arrays.stream(runs.toArray()).filter(p -> p.getText().endsWith(PAGE_BREAK_STR)).findFirst().get();
	if (run != null)
	{
		removePageBreak(run);
	}
}
public void removePageBreakFromParagraph(Paragraph paragraph)
{
	Run run = (Run) paragraph.getFirstChild();
	if (PAGE_BREAK_STR.equals(run.getText()))
	{
		paragraph.removeChild(run);
	}
}
private void processLastParagraph(Paragraph paragraph)
{
	Node lastNode = paragraph.getChildNodes().get(paragraph.getChildNodes().getCount() - 1);
	if (lastNode.getNodeType() != NodeType.RUN)
	{
		return;
	}
	Run run = (Run) lastNode;
	removePageBreak(run);
}
private static void removePageBreak(Run run)
{
	Paragraph paragraph = run.getParentParagraph();
	if (PAGE_BREAK_STR.equals(run.getText()))
	{
		paragraph.removeChild(run);
	}
	else if (run.getText().endsWith(PAGE_BREAK_STR))
	{
		run.setText(StringUtils.stripEnd(run.getText(), String.valueOf(PAGE_BREAK)));
	}
	if (paragraph.getChildNodes().getCount() == 0)
	{
		CompositeNode parent = paragraph.getParentNode();
		parent.removeChild(paragraph);
	}
}
}
```

## บทสรุป

ตอนนี้คุณได้เรียนรู้วิธีการแบ่งเอกสารออกเป็นหน้าต่างๆ โดยใช้ Aspose.Words สำหรับ Java แล้ว คู่มือนี้มีบทช่วยสอนแบบทีละขั้นตอนที่ครอบคลุมพร้อมตัวอย่างซอร์สโค้ด คุณสามารถปรับแต่งและขยายโค้ดนี้เพิ่มเติมเพื่อให้ตรงตามความต้องการเฉพาะของคุณเมื่อทำงานกับเอกสาร
แน่นอน! มาเพิ่มส่วนคำถามที่พบบ่อยลงในคำแนะนำของเราเกี่ยวกับการแบ่งเอกสารออกเป็นหน้าต่างๆ โดยใช้ Aspose.Words สำหรับ Java

## คำถามที่พบบ่อย

### ฉันจะเพิ่ม Aspose.Words สำหรับ Java ในโปรเจ็กต์ของฉันได้อย่างไร

หากต้องการเพิ่ม Aspose.Words สำหรับ Java ให้กับโปรเจ็กต์ของคุณ ให้ทำตามขั้นตอนเหล่านี้:

1.  ดาวน์โหลดไลบรารี Aspose.Words สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/words/java/).
2. เพิ่มไฟล์ JAR ที่ดาวน์โหลดไปยัง classpath ของโปรเจ็กต์ของคุณ
3. ตอนนี้คุณสามารถเริ่มใช้ Aspose.Words สำหรับ Java ในโปรเจ็กต์ของคุณได้แล้ว

### ฉันสามารถแยกเอกสารในรูปแบบอื่น เช่น PDF หรือ DOCX ได้หรือไม่

ไม่ คู่มือนี้ครอบคลุมถึงการแยกเอกสารในรูปแบบ DOC โดยใช้ Aspose.Words สำหรับ Java โดยเฉพาะ หากคุณต้องการแบ่งเอกสารเป็นรูปแบบอื่น คุณอาจต้องสำรวจไลบรารีหรือเครื่องมืออื่นๆ ที่รองรับรูปแบบเหล่านั้น

### Aspose.Words สำหรับ Java เป็นไลบรารีฟรีหรือไม่

 ไม่ Aspose.Words สำหรับ Java ไม่ใช่ไลบรารีฟรี เป็นผลิตภัณฑ์เชิงพาณิชย์ที่มีค่าธรรมเนียมใบอนุญาต ท่านสามารถเยี่ยมชมได้ที่[Aspose.Words สำหรับหน้าราคา Java](https://purchase.aspose.com/words/java) สำหรับข้อมูลเพิ่มเติมเกี่ยวกับรายละเอียดใบอนุญาตและราคา

### ฉันสามารถแบ่งเอกสารออกเป็นขนาดและรูปแบบหน้าที่กำหนดเองได้หรือไม่

ใช่ คุณสามารถปรับแต่งขนาดหน้าและรูปแบบของเอกสารแยกได้โดยการแก้ไขคุณสมบัติการตั้งค่าหน้าใน Aspose.Words สำหรับ Java โปรดดูเอกสารประกอบของ Aspose.Words สำหรับรายละเอียดเกี่ยวกับวิธีปรับแต่งการตั้งค่าเพจตามความต้องการของคุณ

### มีข้อจำกัดเกี่ยวกับจำนวนหน้าที่สามารถแบ่งได้หรือไม่?

Aspose.Words สำหรับ Java ไม่ได้กำหนดข้อจำกัดเฉพาะเกี่ยวกับจำนวนหน้าที่คุณสามารถแบ่งได้ อย่างไรก็ตาม โปรดทราบว่าเอกสารที่มีขนาดใหญ่มากอาจต้องใช้หน่วยความจำและเวลาในการประมวลผลมากขึ้น คำนึงถึงทรัพยากรระบบเมื่อทำงานกับเอกสารขนาดใหญ่

### ฉันจะจัดการส่วนหัวและส่วนท้ายเมื่อแยกเอกสารได้อย่างไร

ส่วนหัวและส่วนท้ายสามารถจัดการได้เมื่อแยกเอกสารโดยใช้ไลบรารี Aspose.Words สำหรับ Java คุณสามารถคัดลอกเนื้อหาส่วนหัวและส่วนท้ายจากเอกสารต้นฉบับไปยังเอกสารที่แยกได้ เพื่อให้มั่นใจว่าเนื้อหาเหล่านั้นจะถูกเก็บรักษาไว้อย่างถูกต้อง คุณอาจต้องปรับแต่งกระบวนการนี้ตามความต้องการส่วนหัวและส่วนท้ายเฉพาะของคุณ