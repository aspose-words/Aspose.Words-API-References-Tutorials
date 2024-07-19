---
title: قراءة خصائص XControl النشطة من ملف Word
linktitle: قراءة خصائص XControl النشطة من ملف Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: قراءة خصائص عناصر تحكم ActiveX في ملف Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

في هذا الدليل خطوة بخطوة، سنوضح لك كيفية قراءة خصائص عناصر تحكم ActiveX في ملف Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تهيئة المستند

 الخطوة الأولى هي تهيئة`Document` الكائن عن طريق تحميل مستند Word الذي يحتوي على عناصر تحكم ActiveX. تأكد من استبدال`MyDir` بالمسار الفعلي إلى الدليل الذي يحتوي على المستند.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## الخطوة 2: استرداد عناصر تحكم ActiveX

 في هذه الخطوة، سوف نقوم بالتكرار من خلال كل منها`Shape` من المستند لاسترداد عناصر تحكم ActiveX وقراءة خصائصها.

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

### مثال على التعليمات البرمجية المصدر لقراءة خصائص XControl النشطة باستخدام Aspose.Words لـ .NET

فيما يلي التعليمات البرمجية المصدر الكاملة لقراءة خصائص عناصر تحكم ActiveX باستخدام Aspose.Words لـ .NET:

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

يوضح لك هذا الدليل كيفية قراءة خصائص عناصر تحكم ActiveX في ملف Word باستخدام Aspose.Words لـ .NET. باتباع الخطوات الموضحة، يمكنك تهيئة المستند واسترداد عناصر تحكم ActiveX وقراءة خصائصها. استخدم نموذج التعليمات البرمجية المقدم كنقطة بداية وقم بتخصيصه ليناسب احتياجاتك الخاصة.

تتيح لك قراءة خصائص عناصر تحكم ActiveX استخراج المعلومات المهمة من ملفات Word التي تحتوي على عناصر التحكم هذه. يوفر Aspose.Words for .NET ميزات قوية لمعالجة الكلمات باستخدام عناصر تحكم ActiveX وأتمتة معالجة المستندات.

### الأسئلة الشائعة

#### س: ما هي الخطوة الأولى لقراءة خصائص عناصر تحكم ActiveX في ملف Word؟

 ج: الخطوة الأولى هي تهيئة`Document` الكائن عن طريق تحميل مستند Word الذي يحتوي على عناصر تحكم ActiveX. تأكد من استبدال`MyDir` بالمسار الفعلي إلى الدليل الذي يحتوي على المستند.

#### س: كيف يمكنني إدخال عناصر تحكم ActiveX في المستند؟

 ج: لاسترداد عناصر تحكم ActiveX، تحتاج إلى التكرار خلال كل منها`Shape` للمستند وتحقق مما إذا كان عنصر تحكم ActiveX. استخدم ال`OleFormat` ممتلكات`Shape` للوصول إلى`OleControl` الكائن واسترداد الخصائص الضرورية.

#### س: ما هي خصائص عناصر تحكم ActiveX التي يمكنني قراءتها؟

ج: يمكنك قراءة خصائص متنوعة لعناصر تحكم ActiveX، مثل التسمية التوضيحية، والقيمة، والحالة الممكنة أو المعطلة، والنوع، والعقد التابعة المرتبطة بعنصر التحكم.

#### س: كيف يمكنني الحصول على العدد الإجمالي لعناصر تحكم ActiveX في المستند؟

 ج: للحصول على العدد الإجمالي لعناصر تحكم ActiveX في المستند، يمكنك استخدام الملف`GetChildNodes` طريقة`Document` كائن يحدد`NodeType.Shape` اكتب بما في ذلك العقد الفرعية.