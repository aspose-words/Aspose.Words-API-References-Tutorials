---
title: Обратный вызов с переносом
linktitle: Обратный вызов с переносом
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать обратный вызов переноса в Aspose.Words для .NET для обработки переноса слов.
type: docs
weight: 10
url: /ru/net/working-with-hyphenation/hyphenation-callback/
---

В этом пошаговом руководстве мы покажем вам, как использовать функцию обратного вызова с расстановкой переносов в Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1. Сохраните напоминание о расстановке переносов

 Во-первых, мы зарегистрируем обратный вызов для расстановки переносов, используя пользовательский`CustomHyphenationCallback` сорт. Это позволит нам обрабатывать переносы слов в соответствии с нашими собственными правилами:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Убедитесь, что вы внедрили`CustomHyphenationCallback`класса в соответствии с вашими конкретными потребностями.

## Шаг 2: Загрузка документа и расстановка переносов

Затем загрузите документ из указанного каталога и расставьте слова с помощью Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Шаг 3. Обработка ошибок отсутствия словаря

Если словарь переносов отсутствует, мы перехватим соответствующее исключение и отобразим сообщение об ошибке:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Шаг 4. Очистите и отключите напоминание о переносах

Наконец, для чистоты и отключения напоминания о переносах выполните следующие действия:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Это очищает и отключает напоминание о переносе после завершения обработки.

Так ! Вы успешно использовали обратный вызов переноса в Aspose.Words для .NET.

### Пример исходного кода для обратного вызова с расстановкой переносов с помощью Aspose.Words для .NET

```csharp
try
{
	 // Регистрация обратного вызова с расстановкой переносов.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими потребностями.