---
title: إزالة جدول المحتويات في مستند Word
linktitle: إزالة جدول المحتويات في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إزالة جدول المحتويات في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/remove-content/remove-table-of-contents/
---
في هذا البرنامج التعليمي، سنرشدك إلى كيفية إزالة جدول المحتويات في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يمكن أن يكون جدول المحتويات زائدًا أو غير ضروري في بعض الأحيان، وسيساعدك هذا الرمز على إزالته بشكل فعال. سنقدم لك دليلاً خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك
- مستند Word يحتوي على جدول محتويات تريد حذفه

## الخطوة 1: تحديد دليل المستند
 أولاً، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل الوثيقة
 بعد ذلك، سنقوم بتحميل مستند Word إلى مثيل الملف`Document` الطبقة باستخدام`Load` طريقة.

```csharp
// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

## الخطوة 3: حذف جدول المحتويات
 لإزالة جدول المحتويات، سنقوم بالتكرار عبر نوع جدول المحتويات (TOC).`FieldStart` العقد في الوثيقة. سنقوم بتخزين هذه العقد حتى نتمكن من الوصول إليها بسرعة وإنشاء قائمة بالعقد المراد حذفها.

```csharp
// قم بتخزين عقد FieldStart لحقول جدول المحتويات في المستند للوصول إليها بسرعة.
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

     // عندما نواجه عقدة FieldEnd من النوع FieldTOC،
     //نحن نعلم أننا وصلنا إلى نهاية جدول المحتويات الحالي ونتوقف هنا.
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


### نموذج التعليمات البرمجية المصدر لإزالة جدول المحتويات باستخدام Aspose.Words لـ .NET 
```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");

// قم بتخزين عقد FieldStart لحقول جدول المحتويات في المستند للوصول إليها بسرعة.
List<FieldStart> fieldStarts = new List<FieldStart>();
// هذه قائمة لتخزين العقد الموجودة داخل جدول المحتويات المحدد. سيتم إزالتها في نهاية هذه الطريقة.
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

	// بمجرد أن نواجه عقدة FieldEnd من النوع FieldTOC،
	// نحن نعلم أننا وصلنا إلى نهاية جدول المحتويات الحالي ونتوقف هنا.
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
في هذا البرنامج التعليمي، قدمنا دليلًا خطوة بخطوة لإزالة جدول المحتويات من مستند Word باستخدام مكتبة Aspose.Words لـ .NET. باتباع التعليمات البرمجية والتعليمات المقدمة، يمكنك بسهولة حذف جدول المحتويات وتحسين تخطيط المستند. تذكر أن تقوم بتكييف مسار الدليل وأسماء الملفات لتناسب احتياجاتك الخاصة.

### الأسئلة الشائعة

#### س: لماذا يجب علي استخدام Aspose.Words لإزالة جدول المحتويات في مستند Word؟

ج: Aspose.Words هي مكتبة فئة قوية ومتعددة الاستخدامات لمعالجة مستندات Word في تطبيقات .NET. باستخدام Aspose.Words، يمكنك إزالة جدول المحتويات من مستنداتك بشكل فعال، وهو ما قد يكون مفيدًا إذا كان جدول المحتويات زائدًا عن الحاجة أو غير ضروري. يتيح لك ذلك تخصيص محتوى المستند الخاص بك وتحسين العرض العام له.

#### س: كيف يمكنني تحميل مستند في Aspose.Words لـ .NET؟

ج: لإزالة جدول المحتويات في مستند Word، يجب عليك أولاً تحميل المستند إلى الذاكرة باستخدام أسلوب Load() الخاص بـ Aspose.Words. إليك نموذج التعليمات البرمجية لتحميل مستند من دليل محدد:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى المستند الخاص بك.

#### س: كيف يمكنني إزالة جدول المحتويات في مستند باستخدام Aspose.Words؟

 ج: لإزالة جدول المحتويات، تحتاج إلى التكرار من خلال ملف`FieldStart` اكتب عقد جدول المحتويات في المستند. يمكنك تخزين هذه العقد للوصول السريع إليها وإنشاء قائمة بالعقد المراد حذفها. هنا نموذج التعليمات البرمجية:

```csharp
// قم بتخزين عقد FieldStart لحقول جدول المحتويات في المستند للوصول إليها بسرعة.
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

// عندما نواجه عقدة FieldEnd من النوع FieldTOC،
//نحن نعلم أننا وصلنا إلى نهاية جدول المحتويات الحالي ونتوقف هنا.
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

#### س: كيف يتم حفظ المستند الذي تم تحريره في Aspose.Words لـ .NET؟

ج: بعد حذف جدول المحتويات، يجب عليك حفظ المستند المعدل باستخدام طريقة Save(). حدد مسار وتنسيق ملف الإخراج المطلوب (على سبيل المثال، DOCX) للمستند الذي تم تحريره. هنا نموذج التعليمات البرمجية:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```