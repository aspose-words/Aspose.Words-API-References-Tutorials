---
title: مرساة عمودية
linktitle: مرساة عمودية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين مواضع الربط الرأسية لمربعات النص في مستندات Word باستخدام Aspose.Words لـ .NET. يتضمن دليلًا سهلاً خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/vertical-anchor/
---
## مقدمة

هل سبق لك أن وجدت نفسك بحاجة إلى التحكم الدقيق في مكان ظهور النص داخل مربع النص في مستند Word؟ ربما تريد تثبيت النص في أعلى مربع النص أو وسطه أو أسفله؟ إذا كان الأمر كذلك، فأنت في المكان الصحيح! في هذا البرنامج التعليمي، سوف نستكشف كيفية استخدام Aspose.Words لـ .NET لتعيين نقطة الارتساء الرأسية لمربعات النص في مستندات Word. فكر في التثبيت الرأسي باعتباره العصا السحرية التي تضع النص الخاص بك بدقة في المكان الذي تريده داخل الحاوية الخاصة به. على استعداد للغوص في؟ دعونا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في تفاصيل التثبيت العمودي، ستحتاج إلى وضع بعض الأشياء في مكانها الصحيح:

1.  Aspose.Words for .NET: تأكد من تثبيت مكتبة Aspose.Words for .NET. إذا لم يكن لديك بعد، يمكنك[قم بتنزيله هنا](https://releases.aspose.com/words/net/).
2. Visual Studio: يفترض هذا البرنامج التعليمي أنك تستخدم Visual Studio أو .NET IDE آخر للبرمجة.
3. المعرفة الأساسية بـ C#: الإلمام بـ C# و.NET سيساعدك على المتابعة بسلاسة.

## استيراد مساحات الأسماء

للبدء، تحتاج إلى استيراد مساحات الأسماء الضرورية في كود C# الخاص بك. هذا هو المكان الذي تخبر فيه تطبيقك بمكان العثور على الفئات والأساليب التي ستستخدمها. وإليك كيفية القيام بذلك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

توفر مساحات الأسماء هذه الفئات التي ستحتاج إليها للتعامل مع المستندات والأشكال.

## الخطوة 1: تهيئة المستند

أول الأشياء أولاً، تحتاج إلى إنشاء مستند Word جديد. فكر في هذا كإعداد قماشك قبل البدء في الرسم.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 هنا،`Document` هو القماش الفارغ الخاص بك، و`DocumentBuilder` هي فرشاة الرسم الخاصة بك، مما يسمح لك بإضافة الأشكال والنصوص.

## الخطوة 2: أدخل شكل مربع نص

الآن، دعونا نضيف مربع نص إلى وثيقتنا. هذا هو المكان الذي سيعيش فيه النص الخاص بك. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 في هذا المثال،`ShapeType.TextBox` يحدد الشكل الذي تريده، و`200, 200` هي عرض وارتفاع مربع النص بالنقاط.

## الخطوة 3: تعيين المرساة العمودية

هنا يحدث السحر! يمكنك ضبط المحاذاة الرأسية للنص داخل مربع النص. يحدد هذا ما إذا كان النص مرتبطًا بأعلى مربع النص أو وسطه أو أسفله.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 في هذه الحالة،`TextBoxAnchor.Bottom`يضمن تثبيت النص في أسفل مربع النص. إذا كنت تريد أن يتم توسيطه أو محاذاته للأعلى، فستستخدمه`TextBoxAnchor.Center` أو`TextBoxAnchor.Top`، على التوالى.

## الخطوة 4: إضافة نص إلى مربع النص

حان الوقت الآن لإضافة بعض المحتوى إلى مربع النص الخاص بك. فكر في الأمر على أنه ملء اللوحة القماشية الخاصة بك باللمسات النهائية.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 هنا،`MoveTo` يضمن إدراج النص في مربع النص، و`Write` يضيف النص الفعلي.

## الخطوة 5: احفظ المستند

الخطوة الأخيرة هي حفظ المستند الخاص بك. هذا يشبه وضع اللوحة النهائية في الإطار.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## خاتمة

وهنا لديك! لقد تعلمت للتو كيفية التحكم في المحاذاة الرأسية للنص داخل مربع نص في مستند Word باستخدام Aspose.Words for .NET. سواء كنت تقوم بتثبيت النص في الأعلى أو الوسط أو الأسفل، فإن هذه الميزة تمنحك تحكمًا دقيقًا في تخطيط المستند. لذلك، في المرة القادمة التي تحتاج فيها إلى تعديل موضع النص في المستند، ستعرف ما يجب عليك فعله!

## الأسئلة الشائعة

### ما هو الإرساء الرأسي في مستند Word؟
يتحكم الإرساء العمودي في مكان وضع النص داخل مربع نص، مثل المحاذاة العلوية أو الوسطى أو السفلية.

### هل يمكنني استخدام أشكال أخرى إلى جانب مربعات النص؟
نعم، يمكنك استخدام الإرساء الرأسي مع الأشكال الأخرى، على الرغم من أن مربعات النص هي حالة الاستخدام الأكثر شيوعًا.

### كيف أقوم بتغيير نقطة الربط بعد إنشاء مربع النص؟
 يمكنك تغيير نقطة الربط عن طريق ضبط`VerticalAnchor` خاصية على كائن شكل مربع النص.

### هل يمكن تثبيت النص في منتصف مربع النص؟
 قطعاً! مجرد استخدام`TextBoxAnchor.Center` لتوسيط النص عموديًا داخل مربع النص.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words لـ .NET؟
 تحقق من[Aspose.توثيق الكلمات](https://reference.aspose.com/words/net/) لمزيد من التفاصيل والأدلة.