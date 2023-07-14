---
title: قراءة خصائص XControl النشطة من ملف Word
linktitle: قراءة خصائص XControl النشطة من ملف Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: اقرأ خصائص عناصر تحكم ActiveX في ملف Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

في هذا الدليل التفصيلي ، سنوضح لك كيفية قراءة خصائص عناصر تحكم ActiveX في ملف Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تهيئة المستند

 الخطوة الأولى هي تهيئة ملف`Document` الكائن عن طريق تحميل مستند Word الذي يحتوي على عناصر تحكم ActiveX. تأكد من استبدال`MyDir` بالمسار الفعلي للدليل الذي يحتوي على المستند.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## الخطوة 2: استرداد عناصر تحكم ActiveX

 في هذه الخطوة ، سوف نكرر كل منها`Shape` من المستند لاسترداد عناصر تحكم ActiveX وقراءة خصائصها.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### مثال على شفرة المصدر لـ Read Active XControl Properties باستخدام Aspose.Words for .NET

فيما يلي التعليمات البرمجية المصدر الكاملة لقراءة خصائص عناصر تحكم ActiveX باستخدام Aspose.Words for .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## خاتمة

يوضح لك هذا الدليل كيفية قراءة خصائص عناصر تحكم ActiveX في ملف Word باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك تهيئة المستند واسترداد عناصر تحكم ActiveX وقراءة خصائصها. استخدم نموذج التعليمات البرمجية المقدم كنقطة بداية وقم بتخصيصه وفقًا لاحتياجاتك الخاصة.

تسمح لك قراءة خصائص عناصر تحكم ActiveX باستخراج معلومات مهمة من ملفات Word التي تحتوي على عناصر التحكم هذه. يوفر Aspose.Words for .NET ميزات قوية لمعالجة الكلمات باستخدام عناصر تحكم ActiveX وأتمتة معالجة المستندات الخاصة بك.

### أسئلة وأجوبة

#### س: ما هي الخطوة الأولى لقراءة خصائص عناصر تحكم ActiveX في ملف Word؟

 ج: الخطوة الأولى هي تهيئة ملف`Document` الكائن عن طريق تحميل مستند Word الذي يحتوي على عناصر تحكم ActiveX. تأكد من استبدال`MyDir` بالمسار الفعلي للدليل الذي يحتوي على المستند.

#### س: كيف أحصل على عناصر تحكم ActiveX في المستند؟

 ج: لاسترداد عناصر تحكم ActiveX ، تحتاج إلى تكرار كل منها`Shape` من المستند وتحقق مما إذا كان عنصر تحكم ActiveX. استخدم ال`OleFormat` ممتلكات`Shape` للوصول إلى`OleControl` الكائن واسترداد الخصائص الضرورية.

#### س: ما هي خصائص عناصر تحكم ActiveX التي يمكنني قراءتها؟

ج: يمكنك قراءة خصائص متنوعة لعناصر تحكم ActiveX ، مثل التسمية التوضيحية والقيمة والحالة الممكنة أو المعطلة والنوع والعقد الفرعية المرتبطة بعنصر التحكم.

#### س: كيف يمكنني الحصول على العدد الإجمالي لعناصر تحكم ActiveX في المستند؟

 ج: للحصول على العدد الإجمالي لعناصر تحكم ActiveX في المستند ، يمكنك استخدام ملف`GetChildNodes` طريقة`Document` كائن يحدد ال`NodeType.Shape` اكتب وتشمل العقد الفرعية.