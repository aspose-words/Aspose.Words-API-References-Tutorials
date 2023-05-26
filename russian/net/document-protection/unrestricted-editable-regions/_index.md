---
title: Неограниченные редактируемые области
linktitle: Неограниченные редактируемые области
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как создавать неограниченные редактируемые области в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/unrestricted-editable-regions/
---

В этом руководстве мы покажем вам, как использовать функцию неограниченных редактируемых областей Aspose.Words для .NET. Эта функция позволяет определить области в документе Word, содержимое которых можно редактировать без ограничений, даже если остальная часть документа доступна только для чтения. Выполните следующие действия:

## Шаг 1: Загрузка документа и установка защиты

Начните с загрузки существующего документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Защитите документ, установив тип защиты только для чтения и пароль

## Шаг 2: Создание редактируемой области

Начните с создания редактируемой области с помощью объектов EditableRangeStart и EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Объект EditableRange создается для только что созданного EditableRangeStart.
EditableRange editableRange = edRangeStart.EditableRange;

// Поместите что-нибудь в редактируемый диапазон.
builder.Writeln("Paragraph inside first editable range");

// Редактируемый диапазон является корректным, если у него есть начало и конец.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Шаг 3. Добавьте содержимое за пределы редактируемых областей.

Вы можете добавить контент за пределы редактируемых областей, которые останутся доступными только для чтения:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Шаг 4: Сохраните документ

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Обязательно укажите правильный путь и имя файла для сохранения документа с редактируемыми областями.

### Пример исходного кода для неограниченных редактируемых областей с использованием Aspose.Words для .NET

Вот полный исходный код для неограниченных редактируемых областей с использованием Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Загрузите документ и сделайте его доступным только для чтения.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// Запустите редактируемый диапазон.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// Объект EditableRange создается для только что созданного EditableRangeStart.
	EditableRange editableRange = edRangeStart.EditableRange;

	// Поместите что-нибудь в редактируемый диапазон.
	builder.Writeln("Paragraph inside first editable range");

	// Редактируемый диапазон является корректным, если у него есть начало и конец.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Следуя этим шагам, вы можете легко создавать неограниченные редактируемые области в документе Word с помощью Aspose.Words для .NET.


