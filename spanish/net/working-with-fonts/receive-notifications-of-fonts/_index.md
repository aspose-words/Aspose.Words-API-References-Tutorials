---
title: Recibir notificaciones de fuentes
linktitle: Recibir notificaciones de fuentes
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a recibir notificaciones de fuente faltante o sustituida al usar Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/receive-notifications-of-fonts/
---

En este tutorial, lo guiaremos a través de cómo recibir notificaciones de fuentes mientras usa Aspose.Words para .NET. Las notificaciones de fuentes le permiten detectar y administrar fuentes faltantes o sustituidas en sus documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento y configure los ajustes de fuente
 A continuación, cargaremos el documento usando el`Document` class y configure los ajustes de fuente usando el`FontSettings` clase. Estableceremos la fuente predeterminada para usar en caso de que falten fuentes.

```csharp
//Cargue el documento y configure los ajustes de fuente
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Paso 3: Configurar el controlador de notificaciones
 A continuación, definiremos un controlador de notificaciones implementando el`IWarningCallback` interfaz. Esto nos permitirá recopilar advertencias de fuentes al guardar el documento.

```csharp
// Definir el controlador de notificaciones
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Paso 4: aplique la configuración de fuente y guarde el documento
Finalmente, aplicaremos la configuración de fuente al documento y lo guardaremos. Cualquier advertencia de fuente será capturada por el controlador de notificaciones que definimos anteriormente.

```csharp
// Aplicar la configuración de fuente y guardar el documento
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Ejemplo de código fuente para recibir notificaciones de fuentes usando Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Podemos elegir la fuente predeterminada para usar en el caso de que falten fuentes.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Para probar, configuraremos Aspose.Words para buscar fuentes solo en una carpeta que no existe. Dado que Aspose.Words no
// encuentre cualquier fuente en el directorio especificado, luego, durante la representación, las fuentes en el documento se adaptarán con el valor predeterminado
//fuente especificada en FontSettings.DefaultFontName. Podemos atender esta subsumisión usando nuestra devolución de llamada.
fontSettings.SetFontsFolder(string.Empty, false);
// Cree una nueva clase que implemente IWarningCallback que recopile las advertencias producidas durante el guardado del documento.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Conclusión
En este tutorial, vimos cómo recibir notificaciones de fuentes mientras usamos Aspose.Words para .NET. Las notificaciones de fuentes le permiten detectar y administrar fuentes faltantes o sustituidas en sus documentos. Utilice esta función para garantizar la consistencia de las fuentes en sus documentos y tome las medidas adecuadas en caso de que falten fuentes.
