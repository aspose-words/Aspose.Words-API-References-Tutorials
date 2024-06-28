---
title: जावा के लिए Aspose.Words में दस्तावेज़ों को पृष्ठों में विभाजित करना
linktitle: दस्तावेज़ों को पृष्ठों में विभाजित करना
second_title: Aspose.Words जावा दस्तावेज़ प्रोसेसिंग एपीआई
description: जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को पृष्ठों में विभाजित करना सीखें। कुशल दस्तावेज़ प्रसंस्करण के लिए स्रोत कोड के साथ चरण-दर-चरण मार्गदर्शिका।
type: docs
weight: 23
url: /hi/java/document-manipulation/splitting-documents-into-pages/
---

यदि आप जावा में दस्तावेज़ प्रसंस्करण के साथ काम कर रहे हैं, तो जावा के लिए Aspose.Words एक शक्तिशाली एपीआई है जो दस्तावेज़ों को कुशलतापूर्वक अलग-अलग पृष्ठों में विभाजित करने में आपकी सहायता कर सकता है। इस चरण-दर-चरण ट्यूटोरियल में, हम आपको दिए गए स्रोत कोड का उपयोग करके दस्तावेज़ों को विभाजित करने की प्रक्रिया में मार्गदर्शन करेंगे। इस ट्यूटोरियल के अंत तक, आप दस्तावेज़ों को आसानी से विभाजित करने में सक्षम होंगे, जिससे आपकी दस्तावेज़ प्रबंधन क्षमताओं में सुधार होगा।

## 1 परिचय

Aspose.Words for Java एक जावा लाइब्रेरी है जो आपको Word दस्तावेज़ों को प्रोग्रामेटिक रूप से हेरफेर करने की अनुमति देती है। एक सामान्य कार्य किसी दस्तावेज़ को अलग-अलग पृष्ठों में विभाजित करना है, जो विभिन्न उद्देश्यों के लिए उपयोगी हो सकता है, जैसे संग्रह करना, मुद्रण करना या दस्तावेज़ प्रसंस्करण करना।

## 2. पूर्वापेक्षाएँ

इससे पहले कि हम कोड में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:

- आपके सिस्टम पर जावा डेवलपमेंट किट (जेडीके) स्थापित है।
-  जावा लाइब्रेरी के लिए Aspose.Words, जिसे आप डाउनलोड कर सकते हैं[यहाँ](https://releases.aspose.com/words/java/).

## 3. अपना वातावरण स्थापित करना

आरंभ करने के लिए, अपना विकास परिवेश इस प्रकार सेट करें:

- अपने पसंदीदा एकीकृत विकास परिवेश (आईडीई) में एक जावा प्रोजेक्ट बनाएं।
- अपने प्रोजेक्ट में Aspose.Words for Java लाइब्रेरी जोड़ें। आप इसका उल्लेख कर सकते हैं[प्रलेखन](https://reference.aspose.com/words/java/) विस्तृत निर्देशों के लिए.

## 4. सोर्स कोड को समझना

आपके द्वारा प्रदान किया गया स्रोत कोड किसी दस्तावेज़ को अलग-अलग पृष्ठों में विभाजित करने के लिए डिज़ाइन किया गया है। आइए प्रमुख घटकों को तोड़ें:

```java
String fileName = FilenameUtils.getBaseName(docName);
String extensionName = FilenameUtils.getExtension(docName);
System.out.println("Processing document: " + fileName + "." + extensionName);
Document doc = new Document(docName);
```

- हम इनपुट दस्तावेज़ का आधार नाम और एक्सटेंशन निकालते हैं।
- हम जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ लोड करते हैं।

## 5. दस्तावेज़ों को चरण दर चरण विभाजित करना

### 5.1. दस्तावेज़ लोड हो रहा है

```java
Document doc = new Document(docName);
```

 इस चरण में, हम इनपुट दस्तावेज़ को a में लोड करते हैं`Document` ऑब्जेक्ट, जो हमें दस्तावेज़ की सामग्री के साथ काम करने की अनुमति देता है।

### 5.2. दस्तावेज़पेजस्प्लिटर प्रारंभ करना

```java
DocumentPageSplitter splitter = new DocumentPageSplitter(doc);
```

 हम आरंभ करते हैं a`DocumentPageSplitter` हमारे लोड किए गए दस्तावेज़ के साथ ऑब्जेक्ट करें। यह क्लास जावा के लिए Aspose.Words द्वारा प्रदान की गई है और दस्तावेज़ को पृष्ठों में विभाजित करने में हमारी सहायता करती है।

### 5.3. प्रत्येक पृष्ठ सहेजा जा रहा है

```java
for (int page = 1; page <= doc.getPageCount(); page++) {
    Document pageDoc = splitter.getDocumentOfPage(page);
    pageDoc.save("Your Directory Path" + MessageFormat.format("{0} - page{1}.{2}", fileName, page, extensionName));
}
```

इस चरण में, हम दस्तावेज़ के प्रत्येक पृष्ठ को दोहराते हैं और इसे एक अलग दस्तावेज़ के रूप में सहेजते हैं। आप निर्देशिका पथ निर्दिष्ट कर सकते हैं जहां विभाजित पृष्ठ सहेजे जाएंगे।

## 6. कोड चलाना

इस कोड को सफलतापूर्वक चलाने के लिए, सुनिश्चित करें कि आपने अपना वातावरण सेट कर लिया है और अपने प्रोजेक्ट में जावा लाइब्रेरी के लिए Aspose.Words जोड़ा है। फिर, कोड निष्पादित करें, और आपका दस्तावेज़ अलग-अलग पृष्ठों में विभाजित हो जाएगा।

## दस्तावेज़पेजस्प्लिटर स्रोत कोड

```java
/// <सारांश>
/// एक दस्तावेज़ को कई दस्तावेज़ों में विभाजित करता है, प्रति पृष्ठ एक।
///</सारांश>
class DocumentPageSplitter
{
private PageNumberFinder pageNumberFinder;
/// <सारांश>
/// <देखें cref='DocumentPageSplitter'/> वर्ग का एक नया उदाहरण आरंभ करता है।
/// यह विधि दस्तावेज़ को अनुभागों में विभाजित करती है ताकि प्रत्येक पृष्ठ एक अनुभाग सीमा पर शुरू और समाप्त हो।
/// यह अनुशंसा की जाती है कि दस्तावेज़ को बाद में संशोधित न करें।
///</सारांश>
/// <param name='source'>स्रोत दस्तावेज़</param>
public DocumentPageSplitter(Document source) throws Exception
{
	pageNumberFinder = PageNumberFinderFactory.create(source);
}
private Document getDocument() {
	return pageNumberFinder.getDocument();
}
/// <सारांश>
/// किसी पृष्ठ का दस्तावेज़ प्राप्त करता है.
///</सारांश>
/// <परम नाम='पेजइंडेक्स'>
/// किसी पृष्ठ का 1-आधारित सूचकांक।
/// </परम>
/// <रिटर्न>
/// <देखें cref='दस्तावेज़'/>.
///</रिटर्न>
public Document getDocumentOfPage(int pageIndex) throws Exception {
	return getDocumentOfPageRange(pageIndex, pageIndex);
}
/// <सारांश>
/// पृष्ठ श्रेणी का दस्तावेज़ प्राप्त करता है।
///</सारांश>
//<परम नाम='स्टार्टइंडेक्स'>
/// प्रारंभ पृष्ठ का 1-आधारित सूचकांक।
/// </परम>
/// <param name='endIndex'>
///अंतिम पृष्ठ का 1-आधारित सूचकांक।
/// </परम>
/// <रिटर्न>
/// <देखें cref='दस्तावेज़'/>.
///</रिटर्न>
public Document getDocumentOfPageRange(int startIndex, int endIndex) throws Exception {
	Document result = (Document) getDocument().deepClone(false);
	for (Node section : pageNumberFinder.retrieveAllNodesOnPages(startIndex, endIndex, NodeType.SECTION))
	{
		result.appendChild(result.importNode(section, true));
	}
	return result;
}
}
/// <सारांश>
/// किसी दस्तावेज़ के नोड्स को निकालने के लिए तरीके प्रदान करता है जो निर्दिष्ट पृष्ठों पर प्रस्तुत किए जाते हैं।
///</सारांश>
class PageNumberFinder
{
// प्रारंभ/अंत पृष्ठ संख्याओं पर नोड मैप करें।
// इसका उपयोग दस्तावेज़ के विभाजित होने पर संग्राहक द्वारा प्रदान किए गए बेसलाइन पेज नंबरों को ओवरराइड करने के लिए किया जाता है।
private Map<Node, Integer> nodeStartPageLookup = new HashMap<>();
private Map<Node, Integer> nodeEndPageLookup = new HashMap<>();
private LayoutCollector collector;
// पृष्ठ संख्या को उस पृष्ठ पर पाए गए नोड्स की सूची में मैप करता है।
private Map<Integer, ArrayList<Node>> reversePageLookup;
/// <सारांश>
/// <देखें cref='PageNumberFinder'/> वर्ग का एक नया उदाहरण प्रारंभ करता है।
///</सारांश>
/// <param name='collector'>एक संग्राहक उदाहरण जिसमें दस्तावेज़ के लिए लेआउट मॉडल रिकॉर्ड हैं।</param>
public PageNumberFinder(LayoutCollector collector)
{
	this.collector = collector;
}
public Document getDocument()
{
	return collector.getDocument();
}
/// <सारांश>
/// उस पृष्ठ का 1-आधारित सूचकांक पुनर्प्राप्त करता है जिस पर नोड शुरू होता है।
///</सारांश>
/// <परम नाम = "नोड">
/// नोड.
/// </परम>
/// <रिटर्न>
/// पेज इंडेक्स.
///</रिटर्न>
public int getPage(Node node) throws Exception {
	return nodeStartPageLookup.containsKey(node)
		? nodeStartPageLookup.get(node)
		: collector.getStartPageIndex(node);
}
/// <सारांश>
/// उस पृष्ठ का 1-आधारित सूचकांक पुनर्प्राप्त करता है जिस पर नोड समाप्त होता है।
///</सारांश>
/// <परम नाम = "नोड">
/// नोड.
/// </परम>
/// <रिटर्न>
/// पेज इंडेक्स.
///</रिटर्न>
public int getPageEnd(Node node) throws Exception {
	return nodeEndPageLookup.containsKey(node)
		? nodeEndPageLookup.get(node)
		: collector.getEndPageIndex(node);
}
/// <सारांश>
//निर्दिष्ट नोड कितने पृष्ठों तक फैला है, यह लौटाता है। यदि नोड एक पृष्ठ में समाहित है तो 1 लौटाता है।
///</सारांश>
/// <परम नाम = "नोड">
/// नोड.
/// </परम>
/// <रिटर्न>
/// पेज इंडेक्स.
///</रिटर्न>
public int pageSpan(Node node) throws Exception {
	return getPageEnd(node) - getPage(node) + 1;
}
/// <सारांश>
/// उन नोड्स की सूची लौटाता है जो निर्दिष्ट पृष्ठ पर कहीं भी मौजूद हैं या वे पृष्ठ जो निर्दिष्ट नोड प्रकार से मेल खाते हैं।
///</सारांश>
/// <परम नाम='स्टार्टपेज'>
/// आरंभ पृष्ठ.
/// </परम>
/// <param name='endPage'>
/// अंतिम पृष्ठ.
/// </परम>
/// <परम नाम = "नोड टाइप">
/// नोड प्रकार.
/// </परम>
/// <रिटर्न>
/// <देखें cref='IList{T}'/>.
///</रिटर्न>
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
		// कुछ पन्ने खाली हो सकते हैं.
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
/// <सारांश>
/// दो या दो से अधिक पृष्ठों पर दिखाई देने वाले नोड्स को अलग-अलग नोड्स में विभाजित करता है ताकि वे अभी भी उसी तरह दिखाई दें
/// लेकिन अब किसी पृष्ठ पर दिखाई नहीं देता।
///</सारांश>
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
	// किसी भी कंपोजिट पर जाएँ जो संभवतः पृष्ठों में विभाजित है और उन्हें अलग-अलग नोड्स में विभाजित करें।
	collector.getDocument().accept(new SectionSplitter(this));
}
/// <सारांश>
/// स्प्लिट नोड्स के पेज नंबर अपडेट करने के लिए <देखें cref='SectionSplitter'/> द्वारा इसे कॉल किया जाता है।
///</सारांश>
/// <परम नाम = "नोड">
/// नोड.
/// </परम>
/// <परम नाम='स्टार्टपेज'>
/// आरंभ पृष्ठ.
/// </परम>
/// <param name='endPage'>
/// अंतिम पृष्ठ.
/// </परम>
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
	// प्रत्येक नोड को एक सूची में जोड़ें जो प्रत्येक पृष्ठ पर पाए गए नोड्स का प्रतिनिधित्व करता है।
	for (Node node : (Iterable<Node>) collector.getDocument().getChildNodes(NodeType.ANY, true))
	{
		//शीर्षलेख/पादलेख अनुभागों का अनुसरण करते हैं और स्वयं विभाजित नहीं होते हैं।
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
/// <सारांश>
/// निर्दिष्ट रन के टेक्स्ट को दो रन में विभाजित करता है।
/// निर्दिष्ट रन के ठीक बाद नया रन सम्मिलित करता है।
///</सारांश>
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
/// <सारांश>
/// एक दस्तावेज़ को कई अनुभागों में विभाजित करता है ताकि प्रत्येक पृष्ठ एक अनुभाग सीमा पर शुरू और समाप्त हो।
///</सारांश>
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
	// यदि कोई पिछला अनुभाग है, तो किसी भी लिंक किए गए हेडर फ़ुटर को कॉपी करने का प्रयास करें।
	// अन्यथा, यदि पिछला अनुभाग गायब है तो वे निकाले गए दस्तावेज़ में दिखाई नहीं देंगे।
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
	// यदि पैराग्राफ में केवल अनुभाग विराम है, तो नकली रन इन जोड़ें।
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
		// क्लोन किए गए पैराग्राफ से सूची क्रमांकन हटाएं लेकिन इंडेंट वही छोड़ें
		// चूँकि पैराग्राफ को पहले वाले आइटम का हिस्सा माना जाता है।
		if (paragraph.isListItem())
		{
			double textPosition = clonePara.getListFormat().getListLevel().getTextPosition();
			clonePara.getListFormat().removeNumbers();
			clonePara.getParagraphFormat().setLeftIndent(textPosition);
		}
		// तालिकाओं में विभाजित अनुच्छेदों की रिक्ति को रीसेट करें क्योंकि अतिरिक्त रिक्ति के कारण वे अलग दिख सकते हैं।
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
		// अनुभाग के अंत में पृष्ठ विराम को ठीक करता है।
		SplitPageBreakCorrector.processSection(cloneSection);
	}
	SplitPageBreakCorrector.processSection(section);
	// अनुभाग के मुख्य भाग के लिए नया पृष्ठ क्रमांकन भी जोड़ें।
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
	// एक नोड कई पृष्ठों तक फैला हो सकता है, इसलिए विभाजित स्थितियों की एक सूची लौटा दी जाती है।
	//विभाजित नोड अगले पृष्ठ पर पहला नोड है।
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
		// यदि चाइल्ड नोड का पृष्ठ बदल गया है, तो यह विभाजित स्थिति है।
		// इसे सूची में जोड़ें.
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
	// कंपोजिट को पीछे की ओर विभाजित करें, ताकि क्लोन किए गए नोड्स को सही क्रम में डाला जा सके।
	Collections.reverse(splitList);
	return splitList;
}
private CompositeNode splitCompositeAtNode(CompositeNode baseNode, Node targetNode) throws Exception {
	CompositeNode cloneNode = (CompositeNode) baseNode.deepClone(false);
	Node node = targetNode;
	int currentPageNum = pageNumberFinder.getPage(baseNode);
	// अगले पृष्ठ पर पाए गए सभी नोड्स को कॉपी किए गए नोड में ले जाएँ। पंक्ति नोड्स को अलग से संभालें।
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
		// यदि हम किसी पंक्ति के साथ काम कर रहे हैं, तो हमें क्लोन पंक्ति के लिए डमी सेल जोड़ने की आवश्यकता है।
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
	// मूल के बाद स्प्लिट नोड डालें।
	baseNode.getParentNode().insertAfter(cloneNode, baseNode);
	// बेस नोड और उसके वंशजों सहित क्लोन नोड के नए पेज नंबर अपडेट करें।
	// यह केवल एक पृष्ठ होगा क्योंकि क्लोन किया गया समग्र एक पृष्ठ पर विभाजित हो जाएगा।
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

## निष्कर्ष

अब आपने सीख लिया है कि जावा के लिए Aspose.Words का उपयोग करके किसी दस्तावेज़ को अलग-अलग पृष्ठों में कैसे विभाजित किया जाए। यह मार्गदर्शिका स्रोत कोड उदाहरणों के साथ एक व्यापक चरण-दर-चरण ट्यूटोरियल प्रदान करती है। दस्तावेज़ों के साथ काम करते समय आप अपनी विशिष्ट आवश्यकताओं को पूरा करने के लिए इस कोड को और अधिक अनुकूलित और विस्तारित कर सकते हैं।
निश्चित रूप से! आइए जावा के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को पृष्ठों में विभाजित करने पर हमारी मार्गदर्शिका में एक FAQ अनुभाग जोड़ें।

## अक्सर पूछे जाने वाले प्रश्न

### मैं अपने प्रोजेक्ट में Java के लिए Aspose.Words कैसे जोड़ूँ?

अपने प्रोजेक्ट में Java के लिए Aspose.Words जोड़ने के लिए, इन चरणों का पालन करें:

1.  जावा लाइब्रेरी के लिए Aspose.Words डाउनलोड करें[यहाँ](https://releases.aspose.com/words/java/).
2. डाउनलोड की गई JAR फ़ाइल को अपने प्रोजेक्ट के क्लासपाथ में जोड़ें।
3. अब आप अपने प्रोजेक्ट में Java के लिए Aspose.Words का उपयोग शुरू कर सकते हैं।

### क्या मैं दस्तावेज़ों को PDF या DOCX जैसे अन्य स्वरूपों में विभाजित कर सकता हूँ?

नहीं, यह मार्गदर्शिका विशेष रूप से जावा के लिए Aspose.Words का उपयोग करके DOC प्रारूप में दस्तावेज़ों को विभाजित करने को कवर करती है। यदि आपको दस्तावेज़ों को अन्य प्रारूपों में विभाजित करने की आवश्यकता है, तो आपको उन प्रारूपों का समर्थन करने वाले अन्य पुस्तकालयों या उपकरणों का पता लगाने की आवश्यकता हो सकती है।

### क्या जावा के लिए Aspose.Words एक निःशुल्क लाइब्रेरी है?

 नहीं, जावा के लिए Aspose.Words एक मुफ़्त लाइब्रेरी नहीं है। यह लाइसेंस शुल्क वाला एक व्यावसायिक उत्पाद है। आप विजिट कर सकते हैं[जावा मूल्य निर्धारण पृष्ठ के लिए Aspose.Words](https://purchase.aspose.com/words/java) लाइसेंसिंग और मूल्य निर्धारण विवरण पर अधिक जानकारी के लिए।

### क्या मैं दस्तावेज़ों को कस्टम पेज आकारों और प्रारूपों में विभाजित कर सकता हूँ?

हां, आप जावा के लिए Aspose.Words में पेज सेटअप गुणों को संशोधित करके विभाजित दस्तावेज़ों के पेज आकार और प्रारूप को अनुकूलित कर सकते हैं। अपनी आवश्यकताओं के अनुसार पृष्ठ सेटिंग्स को अनुकूलित करने के तरीके के विवरण के लिए Aspose.Words दस्तावेज़ देखें।

### क्या विभाजित किये जा सकने वाले पृष्ठों की संख्या पर कोई सीमा है?

जावा के लिए Aspose.Words आपके द्वारा विभाजित किए जा सकने वाले पृष्ठों की संख्या पर विशिष्ट सीमाएं नहीं लगाता है। हालाँकि, ध्यान रखें कि बहुत बड़े दस्तावेज़ों के लिए अधिक मेमोरी और प्रोसेसिंग समय की आवश्यकता हो सकती है। बड़े दस्तावेज़ों के साथ काम करते समय सिस्टम संसाधनों का ध्यान रखें।

### दस्तावेज़ों को विभाजित करते समय मैं शीर्षलेख और पादलेख कैसे संभाल सकता हूँ?

जावा लाइब्रेरी के लिए Aspose.Words का उपयोग करके दस्तावेज़ों को विभाजित करते समय शीर्षलेख और पादलेख को संभाला जा सकता है। आप मूल दस्तावेज़ से शीर्ष लेख और पाद लेख सामग्री को विभाजित दस्तावेज़ों में कॉपी कर सकते हैं, यह सुनिश्चित करते हुए कि वे सही ढंग से संरक्षित हैं। आपको अपनी विशिष्ट शीर्षलेख और पाद लेख आवश्यकताओं के आधार पर इस प्रक्रिया को अनुकूलित करने की आवश्यकता हो सकती है।