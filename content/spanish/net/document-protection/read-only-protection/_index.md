---
title: Protección de solo lectura en documentos de Word
linktitle: Protección de solo lectura en documentos de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo proteger sus documentos de solo lectura en Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/read-only-protection/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de protección de solo lectura de Aspose.Words para .NET. Esta característica le permite hacer que un documento de Word sea de solo lectura para evitar modificaciones no autorizadas. Siga los pasos a continuación:

## Paso 1: crear el documento y aplicar la protección

Comience creando una instancia de la clase Documento y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: escribir contenido en el documento
Utilice el objeto DocumentBuilder para escribir contenido en el documento:

```csharp
builder.Write("Open document as read-only");
```

## Paso 3: establezca una contraseña y haga que el documento sea de solo lectura

Establezca una contraseña para el documento usando la propiedad SetPassword() del objeto WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Asegúrese de reemplazar "Mi contraseña" con la contraseña real que desea utilizar.

## Paso 4: aplicar documento de solo lectura

Haga que el documento sea de solo lectura estableciendo la propiedad ReadOnlyRecommended en verdadero:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Paso 5: aplique protección de solo lectura y guarde el documento

Finalmente, aplique protección de solo lectura usando el método Protect() del objeto Documento:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento protegido.

### Código fuente de ejemplo para protección de solo lectura usando Aspose.Words para .NET

Aquí está el código fuente completo para la protección de solo lectura usando Aspose.Words para .NET:

```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Ingrese una contraseña de hasta 15 caracteres.
doc.WriteProtection.SetPassword("MyPassword");

// Haga que el documento sea de solo lectura.
doc.WriteProtection.ReadOnlyRecommended = true;

// Aplique protección contra escritura como de solo lectura.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Siguiendo estos pasos, podrás proteger fácilmente tus documentos

## Conclusión

En este tutorial, exploramos la función de protección de solo lectura de Aspose.Words para .NET, que le permite hacer que los documentos de Word sean de solo lectura para evitar modificaciones no autorizadas. Si sigue los pasos proporcionados, podrá aplicar fácilmente protección de solo lectura a sus documentos y mejorar su seguridad. La protección de solo lectura ayuda a garantizar la integridad y precisión del contenido de su documento al restringir las capacidades de edición. Aspose.Words para .NET proporciona una API potente y flexible para manejar la protección de documentos y admite varias otras funciones para personalizar y proteger sus documentos de Word.

### Preguntas frecuentes sobre protección de solo lectura en documentos de Word

#### P: ¿Qué es la protección de sólo lectura en Aspose.Words para .NET?

R: La protección de solo lectura en Aspose.Words para .NET es una característica que le permite hacer que un documento de Word sea de solo lectura, evitando modificaciones no autorizadas. Cuando un documento está configurado como de solo lectura, los usuarios pueden abrirlo y verlo, pero no pueden realizar ningún cambio en su contenido.

#### P: ¿Cómo puedo aplicar protección de solo lectura a un documento de Word usando Aspose.Words para .NET?

R: Para aplicar protección de solo lectura a un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Crear una instancia del`Document` clase y un`DocumentBuilder` objeto.
2.  Utilizar el`DocumentBuilder` para escribir contenido en el documento.
3.  Establezca una contraseña para el documento utilizando el`SetPassword` método de la`WriteProtection` objeto.
4.  Selecciona el`ReadOnlyRecommended` propiedad de la`WriteProtection` oponerse a`true` para recomendar abrir el documento como de solo lectura.
5.  Aplique protección de solo lectura usando el`Protect` método de la`Document` objeto, especificando el`ProtectionType` como`ReadOnly`.
6.  Guarde el documento protegido utilizando el`Save` método de la`Document` objeto.

#### P: ¿Puedo eliminar la protección de solo lectura de un documento de Word usando Aspose.Words para .NET?

R: Sí, puede eliminar la protección de solo lectura de un documento de Word usando Aspose.Words para .NET. Para hacer esto, puedes usar el`Unprotect` método de la`Document` clase, que elimina cualquier protección existente del documento.

#### P: ¿Puedo establecer una contraseña diferente para la protección de solo lectura en un documento de Word?

 R: No, la protección de solo lectura en Aspose.Words para .NET no le permite establecer una contraseña separada específicamente para la protección de solo lectura. La contraseña establecida usando el`SetPassword` método de la`WriteProtection` El objeto se aplica a la protección general del documento, incluida la protección de solo lectura y de lectura y escritura.

#### P: ¿Pueden los usuarios evitar la protección de solo lectura en un documento de Word?

R: La protección de sólo lectura en un documento de Word tiene como objetivo desalentar y prevenir modificaciones accidentales o no autorizadas. Si bien proporciona un nivel de protección, los usuarios con suficientes conocimientos técnicos o permisos de edición pueden evitarlo. Sin embargo, la protección de sólo lectura sirve como elemento disuasorio y ayuda a mantener la integridad del documento.