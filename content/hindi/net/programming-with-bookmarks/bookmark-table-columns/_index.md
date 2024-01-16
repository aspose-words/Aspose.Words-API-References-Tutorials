---
title: Word दस्तावेज़ में तालिका कॉलम बुकमार्क करें
linktitle: Word दस्तावेज़ में तालिका कॉलम बुकमार्क करें
second_title: Aspose.Words दस्तावेज़ प्रोसेसिंग एपीआई
description: .NET के लिए Aspose.Words का उपयोग करके Word दस्तावेज़ में तालिका कॉलम को बुकमार्क करने का तरीका जानें।
type: docs
weight: 10
url: /hi/net/programming-with-bookmarks/bookmark-table-columns/
---

इस लेख में, हम .NET लाइब्रेरी के लिए Aspose.Words में बुकमार्क टेबल कॉलम फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए उपरोक्त C# स्रोत कोड का पता लगाएंगे। यह सुविधा आपको Word दस्तावेज़ में तालिका के एक विशिष्ट कॉलम को बुकमार्क करने और उस कॉलम की सामग्री तक पहुंचने की अनुमति देती है।

## आवश्यक शर्तें

- C# भाषा का बुनियादी ज्ञान।
- Aspose.Words लाइब्रेरी के साथ .NET विकास वातावरण स्थापित।

## चरण 1: तालिका बनाना

 तालिका कॉलम पर बुकमार्क बनाने से पहले, हमें पहले तालिका का उपयोग करना होगा`DocumentBuilder`वस्तु। हमारे उदाहरण में, हम दो पंक्तियों और दो स्तंभों वाली एक तालिका बनाते हैं:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## चरण 2: कॉलम बुकमार्क बनाना

 हम उपयोग करते हैं`StartBookmark` तालिका के किसी विशिष्ट कॉलम पर बुकमार्क बनाने की विधि। हमारे उदाहरण में, हम बुकमार्क के लिए "MyBookmark" नाम का उपयोग करते हैं:

```csharp
builder. StartBookmark("MyBookmark");
```

## चरण 3: कॉलम सामग्री तक पहुंचें

 हम दस्तावेज़ में सभी बुकमार्क देखते हैं और उनके नाम प्रदर्शित करते हैं। यदि कोई बुकमार्क एक कॉलम है, तो हम कॉलम इंडेक्स और का उपयोग करके उस कॉलम की सामग्री तक पहुंचते हैं`GetText` तरीका:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### .NET के लिए Aspose.Words का उपयोग करके बुकमार्क टेबल कॉलम के लिए उदाहरण स्रोत कोड

.NET के लिए Aspose.Words का उपयोग करके तालिका कॉलम पर बुकमार्क बनाने का प्रदर्शन करने के लिए यहां पूर्ण नमूना स्रोत कोड दिया गया है:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## निष्कर्ष

इस लेख में, हमने .NET के लिए Aspose.Words के बुकमार्क टेबल कॉलम फ़ंक्शन का उपयोग करने के तरीके को समझने के लिए C# स्रोत कोड की खोज की। हमने Word दस्तावेज़ में तालिका के एक विशिष्ट कॉलम को बुकमार्क करने और उस कॉलम की सामग्री पर जाने के लिए चरण-दर-चरण मार्गदर्शिका का पालन किया।

### वर्ड दस्तावेज़ में बुकमार्क तालिका कॉलम के लिए अक्सर पूछे जाने वाले प्रश्न

#### प्रश्न: .NET के लिए Aspose.Words में "तालिका कॉलम के लिए बुकमार्क" सुविधा का उपयोग करने के लिए क्या शर्तें हैं?

उ: .NET के लिए Aspose.Words में "टेबल कॉलम के लिए बुकमार्क" सुविधा का उपयोग करने के लिए, आपको C# भाषा का बुनियादी ज्ञान होना चाहिए। आपको Aspose.Words लाइब्रेरी स्थापित करने के साथ एक .NET विकास परिवेश की भी आवश्यकता है।

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में कॉलम वाली तालिका कैसे बनाएं?

 उ: .NET के लिए Aspose.Words का उपयोग करके किसी Word दस्तावेज़ में कॉलम के साथ एक तालिका बनाने के लिए, आप इसका उपयोग कर सकते हैं`DocumentBuilder` तालिका में सेल और सामग्री सम्मिलित करने के लिए ऑब्जेक्ट। यहाँ एक नमूना कोड है:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके तालिका कॉलम को कैसे बुकमार्क करें?

 उ: .NET के लिए Aspose.Words का उपयोग करके तालिका कॉलम पर एक बुकमार्क बनाने के लिए, आप इसका उपयोग कर सकते हैं`StartBookmark` की विधि`DocumentBuilder` किसी विशिष्ट तालिका कॉलम पर बुकमार्क प्रारंभ करने के लिए ऑब्जेक्ट। यहाँ एक नमूना कोड है:

```csharp
builder.StartBookmark("MyBookmark");
```

#### प्रश्न: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क से तालिका कॉलम सामग्री तक कैसे पहुंचें?

उ: .NET के लिए Aspose.Words का उपयोग करके बुकमार्क से तालिका कॉलम की सामग्री तक पहुंचने के लिए, आप दस्तावेज़ में सभी बुकमार्क के माध्यम से लूप कर सकते हैं, जांच सकते हैं कि बुकमार्क एक कॉलम है या नहीं, और सामग्री तक पहुंचने के लिए कॉलम की अनुक्रमणिका का उपयोग करें वह कॉलम. यहाँ एक नमूना कोड है:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // कॉलम की सामग्री के साथ कुछ करें...
         }
     }
}
```

#### प्रश्न: क्या कॉलम बुकमार्क वाली तालिका में मेरे द्वारा बनाए जा सकने वाले कॉलमों की संख्या की कोई सीमा है?

उ: .NET के लिए Aspose.Words का उपयोग करके कॉलम बुकमार्क वाली तालिका में आप कितने कॉलम बना सकते हैं, इसकी कोई विशिष्ट सीमा नहीं है। सीमा मुख्य रूप से आपके सिस्टम पर उपलब्ध संसाधनों और आपके द्वारा उपयोग किए जा रहे वर्ड फ़ाइल प्रारूप की विशिष्टताओं पर निर्भर करती है। हालाँकि, यह अनुशंसा की जाती है कि बहुत अधिक संख्या में कॉलम न बनाएं, क्योंकि इससे अंतिम दस्तावेज़ के प्रदर्शन और पठनीयता पर असर पड़ सकता है।