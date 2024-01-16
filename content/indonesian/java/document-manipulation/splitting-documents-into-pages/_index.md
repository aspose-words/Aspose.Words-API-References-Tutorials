---
title: Memisahkan Dokumen menjadi Halaman di Aspose.Words untuk Java
linktitle: Memisahkan Dokumen menjadi Halaman
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara membagi dokumen menjadi beberapa halaman menggunakan Aspose.Words untuk Java. Panduan langkah demi langkah dengan kode sumber untuk pemrosesan dokumen yang efisien.
type: docs
weight: 23
url: /id/java/document-manipulation/splitting-documents-into-pages/
---

Jika Anda bekerja dengan pemrosesan dokumen di Java, Aspose.Words for Java adalah API canggih yang dapat membantu Anda membagi dokumen menjadi halaman terpisah secara efisien. Dalam tutorial langkah demi langkah ini, kami akan memandu Anda melalui proses pemisahan dokumen menggunakan kode sumber yang disediakan. Di akhir tutorial ini, Anda akan dapat membagi dokumen dengan mudah, sehingga meningkatkan kemampuan manajemen dokumen Anda.

## 1. Perkenalan

Aspose.Words for Java adalah perpustakaan Java yang memungkinkan Anda memanipulasi dokumen Word secara terprogram. Salah satu tugas umum adalah membagi dokumen menjadi beberapa halaman terpisah, yang dapat berguna untuk berbagai tujuan, seperti pengarsipan, pencetakan, atau pemrosesan dokumen.

## 2. Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Words untuk perpustakaan Java, yang dapat Anda unduh[Di Sini](https://releases.aspose.com/words/java/).

## 3. Menyiapkan Lingkungan Anda

Untuk memulai, siapkan lingkungan pengembangan Anda sebagai berikut:

- Buat proyek Java di Lingkungan Pengembangan Terpadu (IDE) pilihan Anda.
- Tambahkan perpustakaan Aspose.Words untuk Java ke proyek Anda. Anda dapat merujuk ke[dokumentasi](https://reference.aspose.com/words/java/) untuk petunjuk rinci.

## 4. Memahami Source Code

Kode sumber yang Anda berikan dirancang untuk membagi dokumen menjadi beberapa halaman terpisah. Mari kita uraikan komponen-komponen utamanya:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- Kami mengekstrak nama dasar dan ekstensi dokumen masukan.
- Kami memuat dokumen menggunakan Aspose.Words untuk Java.

## 5. Memisahkan Dokumen Langkah demi Langkah

### 5.1. Memuat Dokumen

```java
Document doc = new Document(docName);
```

 Pada langkah ini, kami memuat dokumen masukan ke a`Document` objek, yang memungkinkan kita bekerja dengan konten dokumen.

### 5.2. Menginisialisasi DocumentPageSplitter

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 Kami menginisialisasi a`DocumentPageSplitter` objek dengan dokumen kami yang dimuat. Kelas ini disediakan oleh Aspose.Words untuk Java dan membantu kita membagi dokumen menjadi beberapa halaman.

### 5.3. Menyimpan Setiap Halaman

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

Pada langkah ini, kami mengulangi setiap halaman dokumen dan menyimpannya sebagai dokumen terpisah. Anda dapat menentukan jalur direktori tempat halaman terpisah akan disimpan.

## 6. Menjalankan Kode

Agar berhasil menjalankan kode ini, pastikan Anda telah menyiapkan lingkungan dan menambahkan pustaka Aspose.Words untuk Java ke proyek Anda. Kemudian, jalankan kodenya, dan dokumen Anda akan dibagi menjadi beberapa halaman terpisah.

## Kode Sumber DocumentPageSplitter

```java
/// <ringkasan>
/// Membagi dokumen menjadi beberapa dokumen, satu dokumen per halaman.
///</ringkasan>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <ringkasan>
/// Menginisialisasi instance baru dari kelas <see cref="DocumentPageSplitter"/>.
/// Metode ini membagi dokumen menjadi beberapa bagian sehingga setiap halaman dimulai dan diakhiri pada batas bagian.
/// Disarankan untuk tidak mengubah dokumen setelahnya.
///</ringkasan>
/// <param name="source">Dokumen sumber</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <ringkasan>
/// Mendapatkan dokumen suatu halaman.
///</ringkasan>
/// <param nama="pageIndex">
/// 1 berdasarkan indeks suatu halaman.
///</param>
/// <kembali>
/// <lihat cref="Dokumen"/>.
/// </pengembalian>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <ringkasan>
/// Mendapatkan dokumen rentang halaman.
///</ringkasan>
//<param nama="startIndex">
/// 1 berdasarkan indeks halaman awal.
///</param>
/// <nama param = "endIndex">
/// 1 berdasarkan indeks halaman akhir.
///</param>
/// <kembali>
/// <lihat cref="Dokumen"/>.
/// </pengembalian>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <ringkasan>
/// Menyediakan metode untuk mengekstrak node dokumen yang dirender pada halaman tertentu.
///</ringkasan>
class PageNumberFinder
{
// Node peta ke nomor halaman awal/akhir.
// Ini digunakan untuk mengganti nomor halaman dasar yang diberikan oleh kolektor ketika dokumen dipecah.
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// Memetakan nomor halaman ke daftar node yang ditemukan di halaman itu.
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <ringkasan>
/// Menginisialisasi instance baru dari kelas <see cref="PageNumberFinder"/>.
///</ringkasan>
/// <param name="collector">Instance kolektor yang memiliki rekaman model tata letak untuk dokumen.</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <ringkasan>
/// Mengambil indeks berbasis 1 dari halaman tempat node dimulai.
///</ringkasan>
/// <nama param = "simpul">
/// Node.
///</param>
/// <kembali>
/// Indeks halaman.
/// </pengembalian>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <ringkasan>
/// Mengambil indeks berbasis 1 dari halaman tempat node berakhir.
///</ringkasan>
/// <nama param = "simpul">
/// Node.
///</param>
/// <kembali>
/// Indeks halaman.
/// </pengembalian>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <ringkasan>
//Mengembalikan berapa banyak halaman yang dicakup oleh node tertentu. Mengembalikan 1 jika node terdapat dalam satu halaman.
///</ringkasan>
/// <nama param = "simpul">
/// Node.
///</param>
/// <kembali>
/// Indeks halaman.
/// </pengembalian>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <ringkasan>
/// Mengembalikan daftar node yang terdapat di mana saja pada halaman tertentu atau halaman yang cocok dengan tipe node yang ditentukan.
///</ringkasan>
/// <param nama="Halaman Awal">
/// Halaman awal.
///</param>
/// <nama param = "Halaman Akhir">
/// Halaman akhir.
///</param>
/// <param nama="nodeType">
/// Tipe simpul.
///</param>
/// <kembali>
/// <lihat cref="IList{T}"/>.
/// </pengembalian>
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
		// Beberapa halaman mungkin kosong.
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
/// <ringkasan>
/// Memisahkan node yang muncul pada dua halaman atau lebih menjadi node terpisah sehingga tetap muncul dengan cara yang sama
/// namun tidak lagi muncul di seluruh halaman.
///</ringkasan>
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
	// Kunjungi komposit apa pun yang mungkin terbagi menjadi beberapa halaman dan bagi menjadi node terpisah.
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <ringkasan>
/// Ini dipanggil oleh <see cref="SectionSplitter"/> untuk memperbarui nomor halaman dari node yang terpisah.
///</ringkasan>
/// <nama param = "simpul">
/// Node.
///</param>
/// <param nama="Halaman Awal">
/// Halaman awal.
///</param>
/// <nama param = "Halaman Akhir">
/// Halaman akhir.
///</param>
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
	// Tambahkan setiap node ke daftar yang mewakili node yang ditemukan di setiap halaman.
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//Header/Footer mengikuti bagian dan tidak dipisahkan sendiri.
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
/// <ringkasan>
/// Membagi teks proses yang ditentukan menjadi dua proses.
/// Menyisipkan proses baru tepat setelah proses yang ditentukan.
///</ringkasan>
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
/// <ringkasan>
/// Membagi dokumen menjadi beberapa bagian sehingga setiap halaman dimulai dan diakhiri pada batas bagian.
///</ringkasan>
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
	// Jika ada bagian sebelumnya, coba salin semua footer header yang tertaut.
	// Jika tidak, mereka tidak akan muncul dalam dokumen yang diekstraksi jika bagian sebelumnya tidak ada.
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
	// Jika paragraf hanya berisi pemisah bagian, tambahkan penjelasan palsu.
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
		// Hapus penomoran daftar dari paragraf kloning tetapi biarkan indentasinya sama
		// karena paragraf seharusnya menjadi bagian dari item sebelumnya.
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// Atur ulang spasi paragraf terpisah dalam tabel karena spasi tambahan dapat menyebabkan paragraf terlihat berbeda.
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
		// Memperbaiki hentian halaman di akhir bagian.
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// Tambahkan juga penomoran halaman baru untuk badan bagian.
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
	// Sebuah node dapat menjangkau beberapa halaman, sehingga daftar posisi terpisah dikembalikan.
	//Node yang terpisah adalah node pertama pada halaman berikutnya.
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
		// Jika halaman node anak telah berubah, maka ini adalah posisi split.
		// Tambahkan ini ke daftar.
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
	// Pisahkan komposit ke belakang, sehingga node yang dikloning disisipkan dalam urutan yang benar.
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// Pindahkan semua node yang ditemukan pada halaman berikutnya ke dalam node yang disalin. Tangani node baris secara terpisah.
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
		// Jika kita berurusan dengan sebuah baris, kita perlu menambahkan sel tiruan untuk baris yang dikloning.
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
	// Masukkan simpul terpisah setelah yang asli.
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// Perbarui nomor halaman baru dari node dasar dan node yang dikloning, termasuk turunannya.
	// Ini hanya akan menjadi satu halaman karena komposit yang dikloning dipecah menjadi satu halaman.
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

## Kesimpulan

Anda sekarang telah mempelajari cara membagi dokumen menjadi halaman terpisah menggunakan Aspose.Words untuk Java. Panduan ini memberikan tutorial langkah demi langkah yang komprehensif dengan contoh kode sumber. Anda dapat menyesuaikan dan memperluas kode ini lebih lanjut untuk memenuhi kebutuhan spesifik Anda saat bekerja dengan dokumen.
Tentu! Mari tambahkan bagian FAQ ke panduan kami tentang membagi dokumen menjadi beberapa halaman menggunakan Aspose.Words untuk Java.

## FAQ

### Bagaimana cara menambahkan Aspose.Words untuk Java ke proyek saya?

Untuk menambahkan Aspose.Words untuk Java ke proyek Anda, ikuti langkah-langkah berikut:

1.  Unduh perpustakaan Aspose.Words untuk Java dari[Di Sini](https://releases.aspose.com/words/java/).
2. Tambahkan file JAR yang diunduh ke classpath proyek Anda.
3. Anda sekarang dapat mulai menggunakan Aspose.Words untuk Java di proyek Anda.

### Bisakah saya membagi dokumen dalam format lain, seperti PDF atau DOCX?

Tidak, panduan ini secara khusus mencakup pemisahan dokumen dalam format DOC menggunakan Aspose.Words untuk Java. Jika Anda perlu membagi dokumen dalam format lain, Anda mungkin perlu menjelajahi pustaka atau alat lain yang mendukung format tersebut.

### Apakah Aspose.Words untuk Java merupakan perpustakaan gratis?

 Tidak, Aspose.Words untuk Java bukanlah perpustakaan gratis. Ini adalah produk komersial dengan biaya lisensi. Anda dapat mengunjungi[Aspose.Words untuk halaman harga Java](https://purchase.aspose.com/words/java) untuk informasi lebih lanjut tentang perizinan dan rincian harga.

### Bisakah saya membagi dokumen menjadi ukuran dan format halaman khusus?

Ya, Anda dapat mengkustomisasi ukuran halaman dan format dokumen terpisah dengan memodifikasi properti pengaturan halaman di Aspose.Words untuk Java. Lihat dokumentasi Aspose.Words untuk detail tentang cara menyesuaikan pengaturan halaman sesuai dengan kebutuhan Anda.

### Apakah ada batasan jumlah halaman yang dapat dipisah?

Aspose.Words untuk Java tidak memberikan batasan khusus pada jumlah halaman yang dapat Anda bagi. Namun, perlu diingat bahwa dokumen yang sangat besar mungkin memerlukan lebih banyak memori dan waktu pemrosesan. Berhati-hatilah dengan sumber daya sistem saat bekerja dengan dokumen berukuran besar.

### Bagaimana cara menangani header dan footer saat memisahkan dokumen?

Header dan footer dapat ditangani saat memisahkan dokumen dengan menggunakan pustaka Aspose.Words untuk Java. Anda dapat menyalin konten header dan footer dari dokumen asli ke dokumen terpisah, memastikan bahwa konten disimpan dengan benar. Anda mungkin perlu menyesuaikan proses ini berdasarkan kebutuhan header dan footer spesifik Anda.