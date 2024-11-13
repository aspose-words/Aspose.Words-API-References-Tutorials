---
title: Расширенные возможности сохранения HTML-документов с помощью Aspose.Words Java
linktitle: Сохранение HTML-документов с помощью
second_title: API обработки документов Java Aspose.Words
description: В этом уроке мы рассмотрели различные расширенные возможности сохранения HTML-документов с помощью Aspose.Words for Java. Эти возможности позволяют вам создавать высококачественные HTML-документы
type: docs
weight: 16
url: /ru/java/document-loading-and-saving/advance-html-documents-saving-options/
---

В этом уроке мы рассмотрим расширенные возможности сохранения HTML-документов, предоставляемые Aspose.Words для Java. Aspose.Words — это мощный Java API для работы с документами Word, предлагающий широкий спектр функций для обработки и преобразования документов.

## 1. Введение
Aspose.Words for Java позволяет вам работать с документами Word программно. В этом руководстве мы сосредоточимся на расширенных параметрах сохранения документов HTML, которые позволяют вам контролировать, как документы Word преобразуются в HTML.

## 2. Экспорт информации о круговом маршруте
The`exportRoundtripInformation` Метод позволяет экспортировать документы Word в HTML, сохраняя информацию о передаче. Эта информация может быть полезна, когда вы хотите преобразовать HTML обратно в формат Word, не теряя никаких деталей, специфичных для документа.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Экспорт шрифтов в формате Base64
 С`exportFontsAsBase64` Метод позволяет экспортировать шрифты, используемые в документе, в виде закодированных в Base64 данных в HTML. Это гарантирует, что представление HTML сохранит те же стили шрифтов, что и исходный документ Word.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Экспорт ресурсов
The`exportResources` Метод позволяет указать тип таблицы стилей CSS и экспортировать ресурсы шрифтов. Вы также можете задать папку ресурсов и псевдоним для ресурсов в HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Конвертировать метафайлы в EMF или WMF
The`convertMetafilesToEmfOrWmf`Метод позволяет преобразовывать метафайлы в документе в формат EMF или WMF, обеспечивая совместимость и плавную визуализацию в HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 6. Конвертировать метафайлы в SVG
 Используйте`convertMetafilesToSvg` метод преобразования метафайлов в формат SVG. Этот формат идеально подходит для отображения векторной графики в HTML-документах.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 7. Добавьте префикс имени класса CSS
 С`addCssClassNamePrefix` Метод позволяет добавлять префикс к именам классов CSS в экспортированном HTML. Это помогает предотвратить конфликты с существующими стилями.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Экспортируйте URL-адреса CID для ресурсов MHTML
The`exportCidUrlsForMhtmlResources` Метод используется при сохранении документов в формате MHTML. Позволяет экспортировать URL Content-ID для ресурсов.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 9. Разрешите названия шрифтов
The`resolveFontNames` Метод помогает разрешать названия шрифтов при сохранении документов в формате HTML, обеспечивая единообразную визуализацию на разных платформах.

```java
@Test
public void resolveFontNames() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 10. Экспорт поля формы ввода текста как текста
The`exportTextInputFormFieldAsText` метод экспортирует поля формы как обычный текст в HTML, что делает их легко читаемыми и редактируемыми.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Фрагмент кода не показан для краткости.
}
```

## 11. Заключение
В этом уроке мы изучили расширенные возможности сохранения HTML-документов, предоставляемые Aspose.Words for Java. Эти возможности дают вам детальный контроль над процессом преобразования, позволяя создавать HTML-документы, которые очень похожи на исходные документы Word.

## 12. Часто задаваемые вопросы
Вот некоторые часто задаваемые вопросы о работе с Aspose.Words для Java и параметрах сохранения документов HTML:

### В1: Как преобразовать HTML обратно в формат Word с помощью Aspose.Words для Java?
 Чтобы преобразовать HTML обратно в формат Word, вы можете использовать API Aspose.Words`load` метод загрузки HTML-документа и последующего сохранения его в формате Word.

### В2: Могу ли я настраивать стили CSS при экспорте в HTML?
 Да, вы можете настраивать стили CSS, изменяя таблицы стилей, используемые в HTML, или используя`addCssClassNamePrefix` метод добавления префикса к именам классов CSS.

### В3: Есть ли способ оптимизировать вывод HTML для отображения в Интернете?
Да, вы можете оптимизировать вывод HTML для отображения на веб-сайтах, настроив такие параметры, как экспорт шрифтов в формате Base64 и преобразование метафайлов в SVG.

### В4: Существуют ли какие-либо ограничения при конвертации сложных документов Word в HTML?
Хотя Aspose.Words для Java предоставляет мощные возможности конвертации, для получения желаемого результата в формате HTML сложным документам Word со сложной структурой может потребоваться дополнительная постобработка.
