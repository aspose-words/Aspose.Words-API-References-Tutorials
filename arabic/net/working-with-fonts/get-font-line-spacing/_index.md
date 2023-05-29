---
title: احصل على تباعد أسطر الخط
linktitle: احصل على تباعد أسطر الخط
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية الحصول على تباعد بين الخطوط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/get-font-line-spacing/
---
في هذا البرنامج التعليمي ، سنخبرك بكيفية الحصول على تباعد أسطر الخط في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يحدد تباعد أسطر الخط المسافة العمودية بين سطور النص. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: إنشاء مستند جديد ومولد مستندات
 أولاً ، سننشئ مستندًا جديدًا عن طريق إنشاء مثيل لملف`Document` class ومنشئ المستندات عن طريق إنشاء مثيل لملف`DocumentBuilder` فصل.

```csharp
// قم بإنشاء مستند جديد
Document doc = new Document();

// قم بإنشاء منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: تكوين الخط
 بعد ذلك ، سنقوم بتكوين الخط عن طريق تعيين ملف`Name` خاصية منشئ الوثيقة.

```csharp
//تكوين الخط
builder.Font.Name = "Calibri";
```

## الخطوة 3: أضف نصًا إلى المستند
سنستخدم الآن منشئ المستندات لإضافة نص منسق إلى المستند.

```csharp
// أضف نصًا إلى المستند
builder. Writen("qText");
```

## الخطوة 4: احصل على تباعد الأسطر
 الآن سوف نصل إلى`Font` كائن من الفقرة الأولى من المستند واسترداد قيمة`LineSpacing` ملكية.

```csharp
// احصل على تباعد الأسطر للخط
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### نموذج لشفرة مصدر للحصول على تباعد أسطر الخطوط باستخدام Aspose.Words for .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية الحصول على تباعد أسطر الخط في مستند Word باستخدام Aspose.Words for .NET. يعد تباعد أسطر الخطوط أمرًا مهمًا للتحكم في التباعد الرأسي بين سطور النص. لا تتردد في استخدام هذه الميزة لتخصيص مظهر النص في مستنداتك.
