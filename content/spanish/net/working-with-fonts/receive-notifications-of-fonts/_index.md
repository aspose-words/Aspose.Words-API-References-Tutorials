---
title: Recibir notificaciones de fuentes
linktitle: Recibir notificaciones de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo recibir notificaciones de fuentes faltantes o sustituidas cuando utilice Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/receive-notifications-of-fonts/
---

En este tutorial, le explicaremos cómo recibir notificaciones de fuentes mientras usa Aspose.Words para .NET. Las notificaciones de fuentes le permiten detectar y administrar fuentes faltantes o sustituidas en sus documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#.
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: definir el directorio de documentos
 Primero, debe configurar la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta apropiada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: cargue el documento y configure los ajustes de fuente
 A continuación, cargaremos el documento usando el`Document` clase y configurar los ajustes de fuente usando el`FontSettings` clase. Configuraremos la fuente predeterminada que se utilizará en caso de que falten fuentes.

```csharp
// Cargue el documento y configure los ajustes de fuente.
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Paso 3: configurar el controlador de notificaciones
 continuación, definiremos un controlador de notificaciones implementando el`IWarningCallback` interfaz. Esto nos permitirá recopilar advertencias de fuentes al guardar el documento.

```csharp
// Definir el controlador de notificaciones
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Paso 4: aplique la configuración de fuente y guarde el documento
Finalmente, aplicaremos la configuración de fuente al documento y lo guardaremos. Cualquier advertencia de fuente será capturada por el controlador de notificaciones que definimos anteriormente.

```csharp
// Aplicar la configuración de fuente y guardar el documento.
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Código fuente de muestra para recibir notificaciones de fuentes usando Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Podemos elegir la fuente predeterminada que usaremos en caso de que falten fuentes.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Para realizar pruebas, configuraremos Aspose.Words para que busque fuentes solo en una carpeta que no existe. Desde Aspose.Words no
// busque cualquier fuente en el directorio especificado, luego, durante la renderización, las fuentes en el documento se adaptarán al valor predeterminado
// fuente especificada en FontSettings.DefaultFontName. Podemos retomar esta sumisión usando nuestra devolución de llamada.
fontSettings.SetFontsFolder(string.Empty, false);
//Cree una nueva clase que implemente IWarningCallback y recopile las advertencias producidas durante el guardado del documento.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Conclusión
En este tutorial, vimos cómo recibir notificaciones de fuentes mientras usamos Aspose.Words para .NET. Las notificaciones de fuentes le permiten detectar y administrar fuentes faltantes o sustituidas en sus documentos. Utilice esta función para garantizar la coherencia de las fuentes en sus documentos y tomar las medidas adecuadas en caso de que falten fuentes.

### Preguntas frecuentes

#### P: ¿Cómo puedo recibir notificaciones sobre fuentes faltantes en Aspose.Words?

 R: Para recibir notificaciones sobre fuentes faltantes en Aspose.Words, puede utilizar el`FontSettings` clase y el`FontSubstitutionCallback` evento. Puede configurar un método de devolución de llamada para recibir notificaciones cuando se encuentren fuentes faltantes durante el procesamiento de documentos.

#### P: ¿Cómo puedo solucionar las fuentes que faltan en mis documentos de Word?

R: Para solucionar las fuentes que faltan en sus documentos de Word, puede utilizar diferentes estrategias. Puede instalar las fuentes que faltan en el sistema donde ejecuta su aplicación Aspose.Words, o puede sustituir las fuentes que faltan con fuentes alternativas que estén disponibles.

#### P: ¿Es posible recibir notificaciones de fuentes sustituidas en Aspose.Words?

 R: Sí, es posible recibir notificaciones de fuentes sustituidas en Aspose.Words. Cuando se sustituyen fuentes durante el procesamiento de un documento, se le puede notificar mediante el`FontSubstitutionCallback` evento y tomar las medidas adecuadas para ajustar la apariencia del texto.

#### P: ¿Cómo puedo mantener la apariencia del texto consistente cuando se sustituyen fuentes en Aspose.Words?

R: Para mantener la coherencia en la apariencia del texto cuando se sustituyen las fuentes, puede ajustar las propiedades de formato del texto, como el tamaño, el estilo y el color de la fuente. También podrías considerar el uso de fuentes sustitutas que sean visualmente similares a las fuentes originales.