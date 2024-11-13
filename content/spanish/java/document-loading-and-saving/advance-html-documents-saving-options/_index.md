---
title: Opciones avanzadas para guardar documentos HTML con Aspose.Words Java
linktitle: Guardar documentos HTML con
second_title: API de procesamiento de documentos Java Aspose.Words
description: En este tutorial, hemos cubierto varias opciones avanzadas para guardar documentos HTML con Aspose.Words para Java. Estas opciones le permiten crear HTML de alta calidad.
type: docs
weight: 16
url: /es/java/document-loading-and-saving/advance-html-documents-saving-options/
---

En este tutorial, exploraremos las opciones avanzadas de guardado de documentos HTML que ofrece Aspose.Words para Java. Aspose.Words es una potente API de Java para trabajar con documentos de Word y ofrece una amplia gama de funciones para la manipulación y conversión de documentos.

## 1. Introducción
Aspose.Words para Java le permite trabajar con documentos de Word de forma programada. En este tutorial, nos centraremos en las opciones avanzadas para guardar documentos HTML, que le permiten controlar cómo se convierten los documentos de Word a HTML.

## 2. Exportar información de ida y vuelta
El`exportRoundtripInformation` Este método le permite exportar documentos de Word a HTML y conservar la información de ida y vuelta. Esta información puede resultar útil cuando desea convertir HTML nuevamente a formato Word sin perder ningún detalle específico del documento.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Exportar fuentes como Base64
 Con el`exportFontsAsBase64` Con este método, puede exportar las fuentes utilizadas en el documento como datos codificados en Base64 en el HTML. Esto garantiza que la representación HTML conserve los mismos estilos de fuente que el documento Word original.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Recursos de exportación
El`exportResources` El método permite especificar el tipo de hoja de estilo CSS y exportar recursos de fuentes. También puede establecer una carpeta de recursos y un alias para los recursos en el HTML.

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
    // Fragmento de código no mostrado por brevedad.
}
```

## 6. Convertir metarchivos a SVG
 Utilice el`convertMetafilesToSvg` Método para convertir metarchivos al formato SVG. Este formato es ideal para mostrar gráficos vectoriales en documentos HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Fragmento de código no mostrado por brevedad.
}
```

## 7. Agregar prefijo al nombre de la clase CSS
 Con el`addCssClassNamePrefix` Método: puede agregar un prefijo a los nombres de clase CSS en el HTML exportado. Esto ayuda a evitar conflictos con los estilos existentes.

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
El`exportCidUrlsForMhtmlResources` Este método se utiliza al guardar documentos en formato MHTML. Permite exportar URL de Content-ID para recursos.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Fragmento de código no mostrado por brevedad.
}
```

## 9. Resolver nombres de fuentes
El`resolveFontNames` El método ayuda a resolver los nombres de fuentes al guardar documentos en formato HTML, lo que garantiza una representación consistente en diferentes plataformas.

```java
@Test
public void resolveFontNames() throws Exception {
    // Fragmento de código no mostrado por brevedad.
}
```

## 10. Exportar campo de formulario de entrada de texto como texto
El`exportTextInputFormFieldAsText` El método exporta los campos del formulario como texto simple en HTML, lo que los hace fácilmente legibles y editables.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Fragmento de código no mostrado por brevedad.
}
```

## 11. Conclusión
En este tutorial, exploramos las opciones avanzadas de guardado de documentos HTML que ofrece Aspose.Words para Java. Estas opciones le brindan un control detallado sobre el proceso de conversión, lo que le permite crear documentos HTML que se parecen mucho a los documentos Word originales.

## 12. Preguntas frecuentes
A continuación se presentan algunas preguntas frecuentes sobre cómo trabajar con Aspose.Words para Java y las opciones de guardado de documentos HTML:

### P1: ¿Cómo puedo convertir HTML nuevamente al formato Word usando Aspose.Words para Java?
 Para convertir HTML nuevamente al formato Word, puede utilizar la API de Aspose.Words`load` Método para cargar el documento HTML y luego guardarlo en formato Word.

### P2: ¿Puedo personalizar los estilos CSS al exportar a HTML?
 Sí, puedes personalizar los estilos CSS modificando las hojas de estilo utilizadas en el HTML o utilizando el`addCssClassNamePrefix` Método para agregar un prefijo a los nombres de clases CSS.

### P3: ¿Existe alguna forma de optimizar la salida HTML para la visualización web?
Sí, puede optimizar la salida HTML para visualización web configurando opciones como exportar fuentes como Base64 y convertir metarchivos a SVG.

### P4: ¿Existen limitaciones al convertir documentos complejos de Word a HTML?
Si bien Aspose.Words para Java ofrece potentes capacidades de conversión, los documentos de Word complejos con diseños intrincados pueden requerir un posprocesamiento adicional para lograr la salida HTML deseada.
