---
title: Преобразование полей в теле
linktitle: Преобразование полей в теле
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать Aspose.Words для .NET для преобразования полей страницы в текст в основной части документа Word.
type: docs
weight: 10
url: /ru/net/working-with-fields/convert-fields-in-body/
---

В этом пошаговом руководстве мы расскажем, как использовать функцию ConvertFieldsInBody в Aspose.Words для .NET, используя предоставленный исходный код C#. Эта функция позволяет преобразовывать определенные поля в теле документа в обычный текст, что упрощает обработку документов. Следуйте приведенным ниже инструкциям, чтобы эффективно использовать эту функцию.

## Шаг 1: Предпосылки

Прежде чем начать, убедитесь, что у вас установлен Aspose.Words for .NET и документ готов к обработке. Также убедитесь, что у вас есть путь к папке с вашими документами.

## Шаг 2. Загрузите документ

Начните с объявления переменной для пути к каталогу документов, а затем используйте эту переменную для инициализации объекта Document из указанного документа. В нашем примере документ называется «Связанные поля.docx».

```csharp
// Путь к каталогу ваших документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Linked fields.docx");
```

## Шаг 3. Преобразование полей страницы в обычный текст

 Теперь, когда документ загружен, мы можем перейти к этапам преобразования. Чтобы преобразовать поля страницы в обычный текст в теле первого раздела, вы можете использовать`Range.Fields` метод, чтобы получить все поля в указанном диапазоне, а затем отфильтровать поля типа`FieldType.FieldPage` . Затем вы можете использовать`ForEach` метод для перебора каждого поля и вызова метода`Unlink()` метод преобразования его в обычный текст.

```csharp
// Передайте соответствующие параметры, чтобы преобразовать поля страницы в обычный текст в теле первого раздела.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## Шаг 4: Сохраните измененный документ

После того, как вы преобразовали поля страницы в обычный текст, вы можете сохранить измененный документ, используя`Save()` метод и указать путь и имя выходного файла. В нашем примере мы сохраняем его как «WorkingWithFields.ConvertFieldsInBody.docx».

```csharp
// Сохраните измененный документ
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Пример исходного кода для преобразования полей в теле с помощью Aspose.Words для .NET

Вот полный пример исходного кода для преобразования полей в тело с помощью Aspose.Words для .NET:

```csharp
// Путь к каталогу ваших документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Linked fields.docx");

// Передайте соответствующие параметры, чтобы преобразовать поля страницы в обычный текст в теле первого раздела.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### Часто задаваемые вопросы

#### В: Совместим ли Aspose.Words с различными версиями Microsoft Word?

О: Да, Aspose.Words совместим с различными версиями Microsoft Word, включая Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 и Word 2019.

#### В: Может ли Aspose.Words обрабатывать сложные структуры полей?

О: Абсолютно! Aspose.Words обеспечивает расширенную поддержку сложных структур полей, включая вложенные поля, вычисления и условные выражения. Вы можете использовать мощный API для работы с любым типом структуры поля.

#### В: Поддерживает ли Aspose.Words операции обновления полей?

О: Да, Aspose.Words позволяет программно обновлять поля. Вы можете легко обновлять значения полей, обновлять расчеты и выполнять другие операции, связанные с полями, с помощью API.

#### В: Могу ли я преобразовать поля в обычный текст с помощью Aspose.Words?

О: Конечно! Aspose.Words предоставляет методы для преобразования полей в обычный текст. Это может быть полезно, когда вам нужно извлечь контент без какого-либо форматирования или функций, связанных с полями.

#### В: Можно ли с помощью Aspose.Words создавать документы Word с динамическими полями?

О: Абсолютно! Aspose.Words предлагает надежные функции для создания документов Word с динамическими полями. Вы можете создавать шаблоны с предопределенными полями и динамически заполнять их данными, обеспечивая гибкое и эффективное решение для создания документов.