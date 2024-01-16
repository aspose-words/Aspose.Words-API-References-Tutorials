---
title: Aspose.Words for Java でのドキュメントのページへの分割
linktitle: ドキュメントをページに分割する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用してドキュメントをページに分割する方法を学びます。効率的な文書処理のためのソースコードを含むステップバイステップのガイド。
type: docs
weight: 23
url: /ja/java/document-manipulation/splitting-documents-into-pages/
---

Java でドキュメント処理を行っている場合、Aspose.Words for Java は、ドキュメントを効率的に個別のページに分割するのに役立つ強力な API です。このステップバイステップのチュートリアルでは、提供されたソース コードを使用してドキュメントを分割するプロセスを説明します。このチュートリアルを終えると、ドキュメントを簡単に分割できるようになり、ドキュメント管理機能が向上します。

## 1. はじめに

Aspose.Words for Java は、Word ドキュメントをプログラムで操作できるようにする Java ライブラリです。一般的なタスクの 1 つは、ドキュメントを個別のページに分割することです。これは、アーカイブ、印刷、ドキュメント処理などのさまざまな目的に役立ちます。

## 2. 前提条件

コードに入る前に、次の前提条件が満たされていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
- Aspose.Words for Java ライブラリ (ダウンロード可能)[ここ](https://releases.aspose.com/words/java/).

## 3. 環境のセットアップ

開始するには、次のように開発環境をセットアップします。

- 好みの統合開発環境 (IDE) で Java プロジェクトを作成します。
- Aspose.Words for Java ライブラリをプロジェクトに追加します。を参照できます。[ドキュメンテーション](https://reference.aspose.com/words/java/)詳細な手順については、

## 4. ソースコードを理解する

提供されたソース コードは、ドキュメントを個別のページに分割するように設計されています。主要なコンポーネントを分解してみましょう。

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- 入力ドキュメントのベース名と拡張子を抽出します。
- Aspose.Words for Java を使用してドキュメントをロードします。

## 5. ドキュメントを段階的に分割する

### 5.1.ドキュメントをロードする

```java
Document doc = new Document(docName);
```

このステップでは、入力ドキュメントを`Document`オブジェクトを使用すると、ドキュメントのコンテンツを操作できるようになります。

### 5.2. DocumentPageSplitter の初期化

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

を初期化します`DocumentPageSplitter`ロードされたドキュメントを含むオブジェクト。このクラスは Aspose.Words for Java によって提供され、ドキュメントをページに分割するのに役立ちます。

### 5.3.各ページの保存

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

このステップでは、ドキュメントの各ページを繰り返し処理し、別のドキュメントとして保存します。分割ページを保存するディレクトリ パスを指定できます。

## 6. コードの実行

このコードを正常に実行するには、環境をセットアップし、Aspose.Words for Java ライブラリをプロジェクトに追加していることを確認してください。次に、コードを実行すると、ドキュメントが別々のページに分割されます。

## DocumentPageSplitter ソース コード

```java
/// <概要>
//ドキュメントを 1 ページに 1 つずつ複数のドキュメントに分割します。
/// </概要>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <概要>
/// <see cref="DocumentPageSplitter"/> クラスの新しいインスタンスを初期化します。
/// この方法では、ドキュメントがセクションに分割され、各ページがセクション境界で始まり、セクション境界で終わるようになります。
/// 後でドキュメントを変更しないことをお勧めします。
/// </概要>
/// <param name="source">ソースドキュメント</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <概要>
/// ページのドキュメントを取得します。
/// </概要>
///<param name="pageIndex">
/// 1 から始まるページのインデックス。
///</param>
/// <戻り値>
/// <cref="Document"/> を参照してください。
///</リターン>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <概要>
/// ページ範囲のドキュメントを取得します。
/// </概要>
///<param name="startIndex">
/// 開始ページの 1 から始まるインデックス。
///</param>
///<param name="endIndex">
/// 終了ページの 1 から始まるインデックス。
///</param>
/// <戻り値>
/// <cref="Document"/> を参照してください。
///</リターン>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <概要>
/// 指定されたページにレンダリングされるドキュメントのノードを抽出するメソッドを提供します。
/// </概要>
class PageNumberFinder
{
//ノードを開始/終了ページ番号にマップします。
//これは、ドキュメントの分割時にコレクターによって提供されるベースライン ページ番号をオーバーライドするために使用されます。
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
//ページ番号をそのページで見つかったノードのリストにマップします。
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <概要>
/// <see cref="PageNumberFinder"/> クラスの新しいインスタンスを初期化します。
/// </概要>
/// <param name="collector">ドキュメントのレイアウト モデル レコードを持つコレクター インスタンス。</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <概要>
/// ノードが始まるページの 1 から始まるインデックスを取得します。
/// </概要>
///<param name="ノード">
/// ノード。
///</param>
/// <戻り値>
/// ページインデックス。
///</リターン>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <概要>
/// ノードが終了するページの 1 から始まるインデックスを取得します。
/// </概要>
///<param name="ノード">
/// ノード。
///</param>
/// <戻り値>
/// ページインデックス。
///</リターン>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <概要>
//指定されたノードがまたがるページ数を返します。ノードが 1 ページ内に含まれる場合は 1 を返します。
/// </概要>
///<param name="ノード">
/// ノード。
///</param>
/// <戻り値>
/// ページインデックス。
///</リターン>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <概要>
/// 指定されたページの任意の場所に含まれる、指定されたノード タイプに一致するノードのリストを返します。
/// </概要>
///<param name="startPage">
/// スタートページ。
///</param>
///<param name="endPage">
/// 最後のページ。
///</param>
///<param name="nodeType">
/// ノードのタイプ。
///</param>
/// <戻り値>
/// <cref="IList{T}"/> を参照してください。
///</リターン>
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
		//一部のページは空の場合があります。
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
/// <概要>
/// 複数のページにまたがって表示されるノードを別々のノードに分割して、同じように表示されるようにします。
/// しかし、ページ全体に表示されなくなりました。
/// </概要>
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
	//ページ間で分割されている可能性があるコンポジットにアクセスし、それらを個別のノードに分割します。
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <概要>
/// これは、分割ノードのページ番号を更新するために <see cref="SectionSplitter"/> によって呼び出されます。
/// </概要>
///<param name="ノード">
/// ノード。
///</param>
///<param name="startPage">
/// スタートページ。
///</param>
///<param name="endPage">
/// 最後のページ。
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
	//各ページで見つかったノードを表すリストに各ノードを追加します。
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//ヘッダー/フッターはセクションに続き、単独では分割されません。
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
/// <概要>
/// 指定されたランのテキストを 2 つのランに分割します。
/// 指定された実行の直後に新しい実行を挿入します。
/// </概要>
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
/// <概要>
/// ドキュメントを複数のセクションに分割し、各ページがセクション境界で始まり、セクション境界で終わるようにします。
/// </概要>
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
	//前のセクションがある場合は、リンクされているヘッダー フッターをコピーしてみます。
	//そうしないと、前のセクションが欠落している場合、抽出された文書にそれらのセクションが表示されません。
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
	//段落にセクション区切りのみが含まれる場合は、偽の run into を追加します。
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
		//クローンされた段落からリストの番号付けを削除しますが、インデントは同じままにします
		//この段落は前の項目の一部であると考えられているためです。
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		//表内の分割段落の間隔をリセットします。スペースを追加すると、見た目が異なって見える可能性があります。
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
		//セクションの終わりの改ページを修正します。
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	//セクションの本文にも新しいページ番号を追加します。
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
	//ノードは複数のページにまたがる場合があるため、分割位置のリストが返されます。
	//分割ノードは、次のページの最初のノードです。
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
		//子ノードのページが変更された場合、これが分割位置になります。
		//これをリストに追加します。
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
	//コンポジットを後方に分割して、クローン化されたノードが正しい順序で挿入されるようにします。
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	//次のページで見つかったすべてのノードをコピーしたノードに移動します。行ノードを個別に処理します。
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
		//行を扱っている場合は、複製された行にダミー セルを追加する必要があります。
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
	//分割ノードを元のノードの後に挿入します。
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	//ベース ノードとクローン ノード (その子孫を含む) の新しいページ番号を更新します。
	//クローンされたコンポジットは 1 ページに分割されるため、これは 1 ページのみになります。
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

## 結論

Aspose.Words for Java を使用してドキュメントを個別のページに分割する方法を学習しました。このガイドでは、ソース コードの例を含む包括的なステップバイステップのチュートリアルを提供します。このコードをさらにカスタマイズおよび拡張して、ドキュメントを操作するときの特定の要件を満たすことができます。
確かに！ Aspose.Words for Java を使用してドキュメントをページに分割するガイドに FAQ セクションを追加しましょう。

## よくある質問

### Aspose.Words for Java をプロジェクトに追加するにはどうすればよいですか?

Aspose.Words for Java をプロジェクトに追加するには、次の手順に従います。

1.  Aspose.Words for Java ライブラリを次からダウンロードします。[ここ](https://releases.aspose.com/words/java/).
2. ダウンロードした JAR ファイルをプロジェクトのクラスパスに追加します。
3. これで、プロジェクトで Aspose.Words for Java の使用を開始できるようになりました。

### PDF や DOCX などの他の形式でドキュメントを分割できますか?

いいえ、このガイドでは、Aspose.Words for Java を使用した DOC 形式でのドキュメントの分割について具体的に説明します。ドキュメントを他の形式で分割する必要がある場合は、それらの形式をサポートする他のライブラリまたはツールを調べる必要がある場合があります。

### Aspose.Words for Java は無料のライブラリですか?

いいえ、Aspose.Words for Java は無料のライブラリではありません。ライセンス料を支払う商用製品です。訪問できます。[Aspose.Words for Java の価格ページ](https://purchase.aspose.com/words/java)ライセンスと価格の詳細については、こちらをご覧ください。

### ドキュメントをカスタムのページ サイズと形式に分割できますか?

はい、Aspose.Words for Java のページ設定プロパティを変更することで、分割ドキュメントのページ サイズと形式をカスタマイズできます。要件に応じてページ設定をカスタマイズする方法の詳細については、Aspose.Words のドキュメントを参照してください。

### 分割できるページ数に制限はありますか？

Aspose.Words for Java では、分割できるページ数に特別な制限はありません。ただし、非常に大きなドキュメントの場合は、より多くのメモリと処理時間が必要になる可能性があることに注意してください。大きなドキュメントを扱うときは、システム リソースに注意してください。

### ドキュメントを分割するときにヘッダーとフッターを処理するにはどうすればよいですか?

Aspose.Words for Java ライブラリを使用して、ドキュメントを分割するときにヘッダーとフッターを処理できます。ヘッダーとフッターのコンテンツを元のドキュメントから分割ドキュメントにコピーして、それらが正しく保持されるようにすることができます。特定のヘッダーとフッターの要件に基づいてこのプロセスをカスタマイズする必要がある場合があります。