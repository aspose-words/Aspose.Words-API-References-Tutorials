---
title: Usando listas en Aspose.Words para Java
linktitle: Usando listas
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a usar listas en Aspose.Words para Java con este tutorial paso a paso. Organice y formatee sus documentos de manera efectiva.
type: docs
weight: 18
url: /es/java/using-document-elements/using-lists/
---

En este tutorial completo, exploraremos cómo usar listas de manera efectiva en Aspose.Words para Java, una poderosa API para trabajar con documentos de Microsoft Word mediante programación. Las listas son esenciales para estructurar y organizar el contenido de sus documentos. Cubriremos dos aspectos clave del trabajo con listas: reiniciar listas en cada sección y especificar niveles de lista. ¡Vamos a sumergirnos!

## Introducción a Aspose.Words para Java

Antes de comenzar a trabajar con listas, familiaricémonos con Aspose.Words para Java. Esta API proporciona a los desarrolladores las herramientas para crear, modificar y manipular documentos de Word en un entorno Java. Es una solución versátil para tareas que van desde la simple generación de documentos hasta el formato complejo y la gestión de contenido.

### Configurando su entorno

 Para comenzar, asegúrese de tener Aspose.Words para Java instalado y configurado en su entorno de desarrollo. Puedes descargarlo[aquí](https://releases.aspose.com/words/java/). 

## Reiniciar listas en cada sección

En muchos escenarios, es posible que necesites reiniciar las listas en cada sección de tu documento. Esto puede resultar útil para crear documentos estructurados con varias secciones, como informes, manuales o artículos académicos.

Aquí hay una guía paso a paso sobre cómo lograr esto usando Aspose.Words para Java:

### Inicialice su documento: 
Comience creando un nuevo objeto de documento.

```java
Document doc = new Document();
```

### Agregar una lista numerada: 
Agregue una lista numerada a su documento. Usaremos el estilo de numeración predeterminado.

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### Configurar los ajustes de la lista: 
\Habilite la lista para reiniciar en cada sección.

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### Configuración del generador de documentos: 
Cree un DocumentBuilder para agregar contenido a su documento.

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### Agregar elementos de la lista: 
Utilice un bucle para agregar elementos de lista a su documento. Insertaremos un salto de sección después del elemento 15.

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### Guarde su documento: 
Guarde el documento con las opciones deseadas.

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

Siguiendo estos pasos, puede crear documentos con listas que se reinician en cada sección, manteniendo una estructura de contenido clara y organizada.

## Especificación de niveles de lista

Aspose.Words para Java le permite especificar niveles de lista, lo cual es particularmente útil cuando necesita diferentes formatos de lista dentro de su documento. Exploremos cómo hacer esto:

### Inicialice su documento: 
Crea un nuevo objeto de documento.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Cree una lista numerada: 
Aplique una plantilla de lista numerada de Microsoft Word.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### Especificar niveles de lista: 
Itere a través de diferentes niveles de lista y agregue contenido.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Cree una lista con viñetas: 
Ahora, creemos una lista con viñetas.

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### Especificar niveles de lista con viñetas: 
Similar a la lista numerada, especifique niveles y agregue contenido.

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### Formato de lista de parada: 
Para detener el formato de la lista, establezca la lista en nula.

```java
builder.getListFormat().setList(null);
```

### Guarde su documento: 
Guarde el documento.

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

Si sigue estos pasos, puede crear documentos con niveles de lista personalizados, lo que le permitirá controlar el formato de las listas en sus documentos.

## Código fuente completo
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // IsRestartAtEachSection se escribirá solo si el cumplimiento es mayor que OoxmlComplianceCore.Ecma376.
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Cree una lista numerada basada en una de las plantillas de listas de Microsoft Word
        // aplicarlo al párrafo actual del creador de documentos.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        // Hay nueve niveles en esta lista, probémoslos todos.
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Cree una lista con viñetas basada en una de las plantillas de listas de Microsoft Word
        // aplicarlo al párrafo actual del creador de documentos.
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Esta es una forma de detener el formato de la lista.
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea una lista basada en una plantilla.
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        // Para reutilizar la primera lista, debemos reiniciar la numeración creando una copia del formato de la lista original.
        List list2 = doc.getLists().addCopy(list1);
        // Podemos modificar la nueva lista de cualquier forma, incluso estableciendo un nuevo número de inicio.
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## Conclusión

¡Felicidades! Ha aprendido a trabajar con listas en Aspose.Words para Java de forma eficaz. Las listas son cruciales para organizar y presentar el contenido de sus documentos. Ya sea que necesite reiniciar listas en cada sección o especificar niveles de lista, Aspose.Words para Java proporciona las herramientas que necesita para crear documentos de apariencia profesional.

Ahora puede utilizar estas funciones con confianza para mejorar sus tareas de generación y formato de documentos. Si tiene alguna pregunta o necesita más ayuda, no dude en comunicarse con el[Aspose foro de la comunidad](https://forum.aspose.com/) para apoyo.

## Preguntas frecuentes

### ¿Cómo instalo Aspose.Words para Java?
 Puede descargar Aspose.Words para Java desde[aquí](https://releases.aspose.com/words/java/) y siga las instrucciones de instalación en la documentación.

### ¿Puedo personalizar el formato de numeración de las listas?
Sí, Aspose.Words para Java ofrece amplias opciones para personalizar los formatos de numeración de listas. Puede consultar la documentación de la API para obtener más detalles.

### ¿Aspose.Words para Java es compatible con los últimos estándares de documentos de Word?
Sí, puede configurar Aspose.Words para Java para que cumpla con varios estándares de documentos de Word, incluida ISO 29500.

### ¿Puedo generar documentos complejos con tablas e imágenes usando Aspose.Words para Java?
¡Absolutamente! Aspose.Words para Java admite el formato avanzado de documentos, incluidas tablas, imágenes y más. Consulte la documentación para ver ejemplos.

### ¿Dónde puedo obtener una licencia temporal de Aspose.Words para Java?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
