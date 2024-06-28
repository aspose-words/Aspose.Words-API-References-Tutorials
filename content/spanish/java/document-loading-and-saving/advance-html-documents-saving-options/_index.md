---
title: Opciones avanzadas para guardar documentos HTML con Aspose.Words Java
linktitle: Guardar documentos HTML con
second_title: API de procesamiento de documentos Java Aspose.Words
description: En este tutorial, hemos cubierto varias opciones avanzadas para guardar documentos HTML con Aspose.Words para Java. Estas opciones le permiten crear HTML de alta calidad.
type: docs
weight: 16
url: /es/java/document-loading-and-saving/advance-html-documents-saving-options/
---

En este tutorial, exploraremos las opciones avanzadas para guardar documentos HTML proporcionadas por Aspose.Words para Java. Aspose.Words es una potente API de Java para trabajar con documentos de Word y ofrece una amplia gama de funciones para la manipulación y conversión de documentos.

## 1. Introducción
Aspose.Words para Java le permite trabajar con documentos de Word mediante programación. En este tutorial, nos centraremos en las opciones avanzadas para guardar documentos HTML, que le permiten controlar cómo se convierten los documentos de Word a HTML.

## 2. Exportar información de ida y vuelta
 El`exportRoundtripInformation` El método le permite exportar documentos de Word a HTML conservando al mismo tiempo la información de ida y vuelta. Esta información puede resultar útil cuando desee volver a convertir HTML al formato Word sin perder ningún detalle específico del documento.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Exportar fuentes como Base64
 Con el`exportFontsAsBase64` método, puede exportar las fuentes utilizadas en el documento como datos codificados en Base64 en HTML. Esto garantiza que la representación HTML conserve los mismos estilos de fuente que el documento de Word original.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Exportar recursos
 El`exportResources` El método le permite especificar el tipo de hoja de estilo CSS y exportar recursos de fuentes. También puede configurar una carpeta de recursos y un alias para los recursos en HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://ejemplo.com/recursos");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Convertir metarchivos a EMF o WMF
 El`convertMetafilesToEmfOrWmf`El método le permite convertir metarchivos en el documento al formato EMF o WMF, lo que garantiza la compatibilidad y una representación fluida en HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // El fragmento de código no se muestra por motivos de brevedad.
}
```

## 6. Convertir metarchivos a SVG
 Utilizar el`convertMetafilesToSvg` Método para convertir metarchivos al formato SVG. Este formato es ideal para mostrar gráficos vectoriales en documentos HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // El fragmento de código no se muestra por motivos de brevedad.
}
```

## 7. Agregue el prefijo de nombre de clase CSS
 Con el`addCssClassNamePrefix` método, puede agregar un prefijo a los nombres de clases CSS en el HTML exportado. Esto ayuda a evitar conflictos con estilos existentes.

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

## 8. Exportar URL de CID para recursos MHTML
 El`exportCidUrlsForMhtmlResources` El método se utiliza al guardar documentos en formato MHTML. Permite exportar URL de Content-ID para recursos.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // El fragmento de código no se muestra por motivos de brevedad.
}
```

## 9. Resolver nombres de fuentes
 El`resolveFontNames` El método ayuda a resolver los nombres de las fuentes al guardar documentos en formato HTML, lo que garantiza una representación coherente en diferentes plataformas.

```java
@Test
public void resolveFontNames() throws Exception {
    // El fragmento de código no se muestra por motivos de brevedad.
}
```

## 10. Exportar campo de formulario de entrada de texto como texto
 El`exportTextInputFormFieldAsText` El método exporta campos de formulario como texto sin formato en HTML, haciéndolos fácilmente legibles y editables.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // El fragmento de código no se muestra por motivos de brevedad.
}
```

## 11. Conclusión
En este tutorial, exploramos las opciones avanzadas para guardar documentos HTML proporcionadas por Aspose.Words para Java. Estas opciones le brindan un control detallado sobre el proceso de conversión, lo que le permite crear documentos HTML que se parecen mucho a los documentos originales de Word.

## 12.Preguntas frecuentes
Aquí hay algunas preguntas frecuentes sobre cómo trabajar con Aspose.Words para Java y las opciones para guardar documentos HTML:

### P1: ¿Cómo puedo convertir HTML nuevamente al formato Word usando Aspose.Words para Java?
 Para convertir HTML nuevamente al formato Word, puede usar la API de Aspose.Words`load` Método para cargar el documento HTML y luego guardarlo en formato Word.

### P2: ¿Puedo personalizar los estilos CSS al exportar a HTML?
 Sí, puede personalizar los estilos CSS modificando las hojas de estilo utilizadas en HTML o utilizando el`addCssClassNamePrefix` Método para agregar un prefijo a los nombres de clases CSS.

### P3: ¿Existe alguna forma de optimizar la salida HTML para visualización web?
Sí, puede optimizar la salida HTML para visualización web configurando opciones como exportar fuentes como Base64 y convertir metarchivos a SVG.

### P4: ¿Existe alguna limitación al convertir documentos complejos de Word a HTML?
Si bien Aspose.Words para Java proporciona potentes capacidades de conversión, los documentos complejos de Word con diseños complejos pueden requerir un posprocesamiento adicional para lograr el resultado HTML deseado.
