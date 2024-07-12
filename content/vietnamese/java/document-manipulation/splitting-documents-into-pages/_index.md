---
title: Chia tài liệu thành các trang trong Aspose.Words cho Java
linktitle: Chia tài liệu thành các trang
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách chia tài liệu thành các trang bằng Aspose.Words cho Java. Hướng dẫn từng bước với mã nguồn để xử lý tài liệu hiệu quả.
type: docs
weight: 23
url: /vi/java/document-manipulation/splitting-documents-into-pages/
---

Nếu bạn đang làm việc với việc xử lý tài liệu bằng Java, Aspose.Words for Java là một API mạnh mẽ có thể giúp bạn chia tài liệu thành các trang riêng biệt một cách hiệu quả. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình tách tài liệu bằng mã nguồn được cung cấp. Đến cuối hướng dẫn này, bạn sẽ có thể chia tài liệu một cách dễ dàng, cải thiện khả năng quản lý tài liệu của mình.

## 1. Giới thiệu

Aspose.Words for Java là một thư viện Java cho phép bạn thao tác các tài liệu Word theo chương trình. Một tác vụ phổ biến là chia tài liệu thành các trang riêng biệt, việc này có thể hữu ích cho nhiều mục đích khác nhau, chẳng hạn như lưu trữ, in hoặc xử lý tài liệu.

## 2. Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Thư viện Aspose.Words cho Java mà bạn có thể tải xuống[đây](https://releases.aspose.com/words/java/).

## 3. Thiết lập môi trường của bạn

Để bắt đầu, hãy thiết lập môi trường phát triển của bạn như sau:

- Tạo một dự án Java trong Môi trường phát triển tích hợp (IDE) ưa thích của bạn.
- Thêm thư viện Aspose.Words for Java vào dự án của bạn. Bạn có thể tham khảo các[tài liệu](https://reference.aspose.com/words/java/) để được hướng dẫn chi tiết.

## 4. Hiểu mã nguồn

Mã nguồn bạn cung cấp được thiết kế để chia tài liệu thành các trang riêng biệt. Hãy chia nhỏ các thành phần chính:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- Chúng tôi trích xuất tên cơ sở và phần mở rộng của tài liệu đầu vào.
- Chúng tôi tải tài liệu bằng Aspose.Words cho Java.

## 5. Tách tài liệu từng bước

### 5.1. Đang tải tài liệu

```java
Document doc = new Document(docName);
```

 Ở bước này, chúng ta tải tài liệu đầu vào vào một`Document` đối tượng, cho phép chúng ta làm việc với nội dung của tài liệu.

### 5.2. Đang khởi tạo DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 Chúng tôi khởi tạo một`DocumentPageSplitter` đối tượng với tài liệu được tải của chúng tôi. Lớp này được cung cấp bởi Aspose.Words cho Java và giúp chúng ta chia tài liệu thành các trang.

### 5.3. Lưu từng trang

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

Trong bước này, chúng tôi lặp qua từng trang của tài liệu và lưu nó dưới dạng một tài liệu riêng biệt. Bạn có thể chỉ định đường dẫn thư mục nơi các trang được chia sẽ được lưu.

## 6. Chạy mã

Để chạy mã này thành công, hãy đảm bảo bạn đã thiết lập môi trường và thêm thư viện Aspose.Words for Java vào dự án của mình. Sau đó, thực thi mã và bạn sẽ chia tài liệu của mình thành các trang riêng biệt.

## Mã nguồn DocumentPageSplitter

```java
/// <tóm tắt>
/// Chia một tài liệu thành nhiều tài liệu, mỗi tài liệu một trang.
/// </tóm tắt>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <tóm tắt>
/// Khởi tạo một phiên bản mới của lớp <see cref="DocumentPageSplitter"/>.
/// Phương pháp này chia tài liệu thành các phần sao cho mỗi trang bắt đầu và kết thúc tại một ranh giới phần.
/// Khuyến cáo không nên sửa đổi tài liệu sau đó.
/// </tóm tắt>
/// <param name="source">Tài liệu nguồn</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <tóm tắt>
/// Lấy tài liệu của một trang.
/// </tóm tắt>
/// <param name="pageIndex">
/// chỉ mục dựa trên 1 của một trang.
/// </param>
/// <trả về>
/// <xem cref="Tài liệu"/>.
/// </return>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <tóm tắt>
/// Lấy tài liệu của một phạm vi trang.
/// </tóm tắt>
//<param name="startIndex">
/// Chỉ mục dựa trên 1 của trang bắt đầu.
/// </param>
/// <param name="endIndex">
/// Chỉ mục dựa trên 1 của trang cuối.
/// </param>
/// <trả về>
/// <xem cref="Tài liệu"/>.
/// </return>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <tóm tắt>
/// Cung cấp các phương thức trích xuất các nút của tài liệu được hiển thị trên một trang được chỉ định.
/// </tóm tắt>
class PageNumberFinder
{
// Nút bản đồ tới số trang bắt đầu/kết thúc.
// Điều này được sử dụng để ghi đè số trang cơ sở do người thu thập cung cấp khi tài liệu được chia nhỏ.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// Ánh xạ số trang tới danh sách các nút được tìm thấy trên trang đó.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <tóm tắt>
/// Khởi tạo một phiên bản mới của lớp <see cref="PageNumberFinder"/>.
/// </tóm tắt>
/// <param name="collector">Một phiên bản bộ sưu tập có bản ghi mô hình bố cục cho tài liệu.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <tóm tắt>
/// Truy xuất chỉ mục dựa trên 1 của trang mà nút bắt đầu.
/// </tóm tắt>
/// <param name="node">
/// Nút.
/// </param>
/// <trả về>
/// Chỉ mục trang.
/// </return>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <tóm tắt>
/// Truy xuất chỉ mục dựa trên 1 của trang mà nút kết thúc ở đó.
/// </tóm tắt>
/// <param name="node">
/// Nút.
/// </param>
/// <trả về>
/// Chỉ mục trang.
/// </return>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <tóm tắt>
//Trả về số lượng trang mà nút đã chỉ định trải dài trên. Trả về 1 nếu nút được chứa trong một trang.
/// </tóm tắt>
/// <param name="node">
/// Nút.
/// </param>
/// <trả về>
/// Chỉ mục trang.
/// </return>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <tóm tắt>
/// Trả về danh sách các nút được chứa ở bất kỳ đâu trên trang được chỉ định hoặc các trang khớp với loại nút đã chỉ định.
/// </tóm tắt>
/// <param name="startPage">
/// Trang bắt đầu.
/// </param>
/// <param name="endPage">
/// Trang cuối.
/// </param>
/// <param name="nodeType">
/// Loại nút.
/// </param>
/// <trả về>
/// <xem cref="IList{T}"/>.
/// </return>
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
		// Một số trang có thể trống.
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
/// <tóm tắt>
/// Tách các nút xuất hiện trên hai trang trở lên thành các nút riêng biệt để chúng vẫn xuất hiện theo cách tương tự
/// nhưng không còn xuất hiện trên một trang nữa.
/// </tóm tắt>
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
	// Truy cập bất kỳ vật liệu tổng hợp nào có thể được chia thành các trang và chia chúng thành các nút riêng biệt.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <tóm tắt>
/// Điều này được <see cref="SectionSplitter"/> gọi để cập nhật số trang của các nút phân tách.
/// </tóm tắt>
/// <param name="node">
/// Nút.
/// </param>
/// <param name="startPage">
/// Trang bắt đầu.
/// </param>
/// <param name="endPage">
/// Trang cuối.
/// </param>
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
	// Thêm từng nút vào danh sách đại diện cho các nút được tìm thấy trên mỗi trang.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//Đầu trang/Chân trang theo các phần và không tự phân chia.
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
/// <tóm tắt>
/// Tách văn bản của lần chạy được chỉ định thành hai lần chạy.
/// Chèn lần chạy mới ngay sau lần chạy được chỉ định.
/// </tóm tắt>
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
/// <tóm tắt>
/// Chia tài liệu thành nhiều phần sao cho mỗi trang bắt đầu và kết thúc tại một ranh giới phần.
/// </tóm tắt>
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
	// Nếu có phần trước đó, hãy thử sao chép mọi chân trang đầu trang được liên kết.
	// Nếu không, chúng sẽ không xuất hiện trong tài liệu được trích xuất nếu thiếu phần trước.
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
	// Nếu đoạn văn chỉ chứa ngắt phần, hãy thêm phần giả mạo vào.
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
		// Xóa đánh số danh sách khỏi đoạn nhân bản nhưng giữ nguyên phần thụt lề
		// vì đoạn văn này được cho là một phần của mục trước đó.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// Đặt lại khoảng cách của các đoạn được phân tách trong bảng vì khoảng cách bổ sung có thể khiến chúng trông khác.
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
		// Sửa lỗi ngắt trang ở cuối phần.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// Thêm đánh số trang mới cho phần thân của phần.
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
	// Một nút có thể trải dài trên nhiều trang, do đó, một danh sách các vị trí được phân chia sẽ được trả về.
	//Nút phân chia là nút đầu tiên trên trang tiếp theo.
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
		// Nếu trang của nút con đã thay đổi thì đây là vị trí phân chia.
		// Thêm cái này vào danh sách.
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
	// Chia các vật liệu tổng hợp về phía sau để các nút nhân bản được chèn theo đúng thứ tự.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// Di chuyển tất cả các nút tìm thấy trên trang tiếp theo vào nút được sao chép. Xử lý các nút hàng riêng biệt.
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
		// Nếu chúng ta đang xử lý một hàng, chúng ta cần thêm các ô giả cho hàng được nhân bản.
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
	// Chèn nút phân tách sau bản gốc.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// Cập nhật số trang mới của nút cơ sở và nút nhân bản, bao gồm cả nút con của nó.
	// Đây sẽ chỉ là một trang duy nhất vì bản tổng hợp nhân bản được chia thành một trang.
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

## Phần kết luận

Bây giờ bạn đã học cách chia tài liệu thành các trang riêng biệt bằng Aspose.Words cho Java. Hướng dẫn này cung cấp hướng dẫn từng bước toàn diện với các ví dụ về mã nguồn. Bạn có thể tùy chỉnh và mở rộng thêm mã này để đáp ứng các yêu cầu cụ thể của mình khi làm việc với tài liệu.
Chắc chắn! Hãy thêm phần Câu hỏi thường gặp vào hướng dẫn của chúng tôi về cách chia tài liệu thành các trang bằng Aspose.Words cho Java.

## Câu hỏi thường gặp

### Làm cách nào để thêm Aspose.Words cho Java vào dự án của tôi?

Để thêm Aspose.Words for Java vào dự án của bạn, hãy làm theo các bước sau:

1.  Tải xuống thư viện Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/).
2. Thêm tệp JAR đã tải xuống vào đường dẫn lớp của dự án của bạn.
3. Bây giờ bạn có thể bắt đầu sử dụng Aspose.Words for Java trong dự án của mình.

### Tôi có thể chia tài liệu ở các định dạng khác, chẳng hạn như PDF hoặc DOCX không?

Không, hướng dẫn này đặc biệt đề cập đến việc chia tách tài liệu ở định dạng DOC bằng Aspose.Words for Java. Nếu cần chia tài liệu ở các định dạng khác, bạn có thể cần khám phá các thư viện hoặc công cụ khác hỗ trợ các định dạng đó.

### Aspose.Words cho Java có phải là thư viện miễn phí không?

 Không, Aspose.Words for Java không phải là thư viện miễn phí. Nó là một sản phẩm thương mại có phí cấp phép. Bạn có thể ghé thăm[Trang định giá Aspose.Words cho Java](https://purchase.aspose.com/words/java) để biết thêm thông tin về chi tiết cấp phép và giá cả.

### Tôi có thể chia tài liệu thành các kích thước và định dạng trang tùy chỉnh không?

Có, bạn có thể tùy chỉnh kích thước trang và định dạng của các tài liệu được chia nhỏ bằng cách sửa đổi thuộc tính thiết lập trang trong Aspose.Words for Java. Tham khảo tài liệu Aspose.Words để biết chi tiết về cách tùy chỉnh cài đặt trang theo yêu cầu của bạn.

### Có bất kỳ hạn chế nào về số lượng trang có thể được chia nhỏ không?

Aspose.Words for Java không áp đặt các giới hạn cụ thể về số lượng trang bạn có thể chia. Tuy nhiên, hãy nhớ rằng các tài liệu rất lớn có thể cần nhiều bộ nhớ và thời gian xử lý hơn. Hãy chú ý đến tài nguyên hệ thống khi làm việc với các tài liệu lớn.

### Làm cách nào để xử lý đầu trang và chân trang khi chia tách tài liệu?

Đầu trang và chân trang có thể được xử lý khi chia tách tài liệu bằng cách sử dụng thư viện Aspose.Words for Java. Bạn có thể sao chép nội dung đầu trang và chân trang từ tài liệu gốc sang tài liệu được chia nhỏ, đảm bảo rằng chúng được giữ nguyên chính xác. Bạn có thể cần tùy chỉnh quy trình này dựa trên các yêu cầu về đầu trang và chân trang cụ thể của mình.