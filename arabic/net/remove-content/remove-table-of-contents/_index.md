---
title: إزالة جدول المحتويات في مستند Word
linktitle: إزالة جدول المحتويات في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إزالة جدول المحتويات في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/remove-content/remove-table-of-contents/
---
في هذا البرنامج التعليمي ، سنرشدك إلى كيفية إزالة جدول المحتويات في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. قد يكون جدول المحتويات أحيانًا زائدًا عن الحاجة أو غير ضروري ، وسيساعدك هذا الرمز في إزالته بشكل فعال. سنقدم لك دليلًا تفصيليًا لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك
- مستند Word يحتوي على جدول محتويات تريد حذفه

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند
 بعد ذلك ، سنقوم بتحميل مستند Word في مثيل`Document` فئة باستخدام`Load` طريقة.

```csharp
// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

## الخطوة 3: احذف جدول المحتويات
 لإزالة جدول المحتويات ، سنقوم بالمرور عبر نوع TOC (جدول المحتويات)`FieldStart` العقد في المستند. سنخزن هذه العقد حتى نتمكن من الوصول إليها بسرعة وإنشاء قائمة بالعقد لحذفها.

```csharp
// تخزين عقد FieldStart لحقول جدول المحتويات في المستند للوصول السريع.
List<FieldStart> fieldStarts = new List<FieldStart>();
// هذه قائمة لتخزين العقد الموجودة داخل جدول المحتويات المحدد. سيتم حذفها في نهاية هذه الطريقة.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// تحقق من وجود فهرس جدول المحتويات المحدد.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // من الآمن تخزين هذه العقد وحذفها جميعًا في النهاية.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // عندما نواجه عقدة FieldEnd من النوع FieldTOC ،
     //نعلم أننا وصلنا إلى نهاية جدول المحتويات الحالي ونتوقف هنا.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### عينة من التعليمات البرمجية المصدر لـ Remove Table Of Contents باستخدام Aspose.Words for .NET 
```csharp

//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");

// قم بتخزين عقد FieldStart لحقول جدول المحتويات في المستند للوصول السريع.
List<FieldStart> fieldStarts = new List<FieldStart>();
// هذه قائمة لتخزين العقد الموجودة داخل جدول المحتويات المحدد. ستتم إزالتها في نهاية هذه الطريقة.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// تأكد من وجود جدول المحتويات المحدد بواسطة الفهرس الذي تم تمريره.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// من الآمن تخزين هذه العقد وحذفها جميعًا مرة واحدة لاحقًا.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// بمجرد أن نواجه عقدة FieldEnd من النوع FieldTOC ،
	// نعلم أننا وصلنا إلى نهاية جدول المحتويات الحالي ونتوقف هنا.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## خاتمة
في هذا البرنامج التعليمي ، قدمنا دليلًا تفصيليًا لإزالة جدول المحتويات من مستند Word باستخدام مكتبة Aspose.Words لـ .NET. باتباع التعليمات البرمجية والإرشادات المتوفرة ، يمكنك بسهولة التخلص من جدول المحتويات وتحسين تخطيط المستند. تذكر تعديل مسار الدليل وأسماء الملفات لتناسب احتياجاتك الخاصة.

### التعليمات

#### س: لماذا يجب علي استخدام Aspose.Words لإزالة جدول المحتويات في مستند Word؟

ج: Aspose.Words مكتبة فصول قوية ومتعددة الاستخدامات لمعالجة مستندات Word في تطبيقات .NET. باستخدام Aspose.Words ، يمكنك إزالة جدول المحتويات بشكل فعال من مستنداتك ، وهو ما يمكن أن يكون مفيدًا إذا كان جدول المحتويات زائدًا عن الحاجة أو غير ضروري. يتيح لك ذلك تخصيص محتوى المستند وتحسين عرضه التقديمي بشكل عام.

#### س: كيف يمكنني تحميل مستند في Aspose.Words لـ .NET؟

ج: لإزالة جدول المحتويات في مستند Word ، يجب أولاً تحميل المستند في الذاكرة باستخدام طريقة Load () الخاصة بـ Aspose.Words. إليك نموذج التعليمات البرمجية لتحميل مستند من دليل محدد:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي إلى المستند الخاص بك.

#### س: كيف يمكنني إزالة جدول المحتويات في مستند باستخدام Aspose.Words؟

 ج: لإزالة جدول المحتويات ، تحتاج إلى التكرار من خلال ملف`FieldStart` اكتب عقد جدول المحتويات في المستند. يمكنك تخزين هذه العقد للوصول السريع وإنشاء قائمة بالعقد لحذفها. إليك نموذج التعليمات البرمجية:

```csharp
// تخزين عقد FieldStart لحقول جدول المحتويات في المستند للوصول السريع.
List<FieldStart> fieldStarts = new List<FieldStart>();
//هذه قائمة لتخزين العقد الموجودة داخل جدول المحتويات المحدد. سيتم حذفها في نهاية هذه الطريقة.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// تحقق من وجود فهرس جدول المحتويات المحدد.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// من الآمن تخزين هذه العقد وحذفها جميعًا في النهاية.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// عندما نواجه عقدة FieldEnd من النوع FieldTOC ،
//نعلم أننا وصلنا إلى نهاية جدول المحتويات الحالي ونتوقف هنا.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### س: كيف تحفظ المستند المحرر في Aspose.Words for .NET؟

ج: بعد حذف جدول المحتويات ، يجب عليك حفظ المستند المعدل باستخدام طريقة Save (). حدد مسار ملف الإخراج المطلوب والتنسيق (على سبيل المثال ، DOCX) للمستند المحرر. إليك نموذج التعليمات البرمجية:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```