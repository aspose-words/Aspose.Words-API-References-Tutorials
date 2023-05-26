---
title: حذف الحقول
linktitle: حذف الحقول
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لحذف حقول الدمج في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/delete-fields/
---

لشرح كيفية استخدام ميزة "حذف الحقول" في Aspose. كلمات لـ .NET قمنا بإنشاء دليل خطوة بخطوة أدناه. 

من المهم متابعة كل خطوة عن كثب من أجل تحقيق النتائج المرجوة. 

## الخطوة الأولى: إنشاء مستند جديد

في مقتطف الشفرة هذا ، نبدأ بإنشاء مستند فارغ جديد باستخدام السطر التالي: 

```csharp
Document doc = new Document();
```

## الخطوة 2: إزالة دمج الحقول

 لإزالة جميع حقول الدمج الموجودة في المستند ، نستخدم ملحق`DeleteFields()` وظيفة. 

هذا مفيد بشكل خاص إذا كنت ترغب في الاحتفاظ فقط بالمحتوى الثابت وإزالة أي معلومات دمج. 

### مثال رمز المصدر لحذف الحقول باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// تحميل المستند الحالي.
Document doc = new Document(dataDir + "YourDocument.docx");

// قم بإزالة حقول الدمج.
doc.MailMerge.DeleteFields();

// احفظ المستند المعدل.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 في مثالنا ، نقوم أولاً بتحميل مستند موجود قبل الاتصال`DeleteFields()`. أخيرًا نحفظ المستند المعدل باسم ملف جديد. 

من أجل إزالة حقول الدمج بشكل فعال من مستند باستخدام Aspose.Words ميزة "إزالة الحقول" في .NET ، خذ إشارة من هذا المثال. 

تذكر دائمًا استبدال "دليل المستندات" بمسار الدليل المحدد. 

وبذلك تم الانتهاء من دليلنا حول تنفيذ وظيفة "حذف الحقول" من خلال Aspose.Words for .NET.