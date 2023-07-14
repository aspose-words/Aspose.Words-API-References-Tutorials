---
title: Sección sin restricciones en el documento de Word
linktitle: Sección sin restricciones en el documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a definir secciones sin restricciones en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-protection/unrestricted-section/
---
En este tutorial, lo guiaremos a través de los pasos para usar la función de sección sin restricciones de Aspose.Words para .NET. Esta característica le permite definir secciones específicas en un documento de Word que no están protegidas, incluso si el resto del documento está protegido. Siga los pasos a continuación:

## Paso 1: Crear el Documento y las Secciones

Comience creando una instancia de la clase Document y un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Agregar contenido al documento
Use el objeto DocumentBuilder para agregar contenido al documento e insertar saltos de sección:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Paso 3: proteger el documento y las secciones

La protección de secciones solo funciona cuando la protección de documentos está habilitada y solo se permite la edición en campos de formulario. Puede proteger el documento usando el método Protect() del objeto Documento:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Asegúrese de especificar el tipo correcto de protección y establecer la contraseña deseada.

## Paso 4: Deshabilitar la protección para una sección específica

De manera predeterminada, todas las secciones están protegidas, pero puede deshabilitar selectivamente la protección para una sección específica utilizando la propiedad ProtectedForForms del objeto Sección:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

En este ejemplo, la protección está deshabilitada para la primera sección.

## Paso 5: Guarde el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para guardar el documento con secciones sin restricciones.

### Ejemplo de código fuente para la sección sin restricciones usando Aspose.Words para .NET

Aquí está el código fuente completo para la sección sin restricciones usando Aspose.Words para .NET:


```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Inserta dos secciones con algo de texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// La protección de secciones solo funciona cuando la protección de documentos está activada y solo se permite la edición en campos de formulario.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//De forma predeterminada, todas las secciones están protegidas, pero podemos desactivar la protección de forma selectiva.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Siguiendo estos pasos, podrá definir fácilmente secciones sin restricciones en su documento de Word con Aspose.Words para .NET.

## Conclusión

En este tutorial, exploramos la función de sección sin restricciones de Aspose.Words para .NET, que permite que secciones específicas en un documento de Word permanezcan sin protección mientras que el resto del documento está protegido. Siguiendo los pasos provistos, puede definir fácilmente secciones dentro de su documento donde los usuarios pueden editar libremente el contenido mientras mantienen la protección para otras secciones. Aspose.Words para .NET ofrece poderosas capacidades para la protección y personalización de documentos, lo que le brinda control sobre los permisos de edición dentro de sus documentos de Word.

### Preguntas frecuentes para la sección no restringida en un documento de Word

#### P: ¿Qué son las secciones sin restricciones en Aspose.Words para .NET?

R: Las secciones sin restricciones en Aspose.Words para .NET son secciones específicas dentro de un documento de Word que no están protegidas, incluso si el resto del documento está protegido. Estas secciones permiten a los usuarios modificar el contenido dentro de ellas mientras mantienen la protección para las partes restantes del documento.

#### P: ¿Cómo puedo crear secciones sin restricciones usando Aspose.Words para .NET?

R: Para crear secciones sin restricciones en un documento de Word usando Aspose.Words para .NET, puede seguir estos pasos:
1.  Crear una instancia de la`Document` clase y un`DocumentBuilder` objeto.
2.  Utilizar el`DocumentBuilder` para agregar contenido al documento e insertar saltos de sección.
3.  Proteja el documento con el`Protect` metodo de la`Document` objeto, especificando el tipo de protección deseado y la contraseña.
4.  Deshabilite la protección para una sección específica configurando el`ProtectedForForms` propiedad de la correspondiente`Section` oponerse a`false`.
5. Guarde el documento modificado.

#### P: ¿Puedo tener varias secciones sin restricciones dentro de un documento de Word?

 R: Sí, puede tener múltiples secciones sin restricciones dentro de un documento de Word. Deshabilitando selectivamente la protección para secciones específicas usando el`ProtectedForForms`propiedad de la`Section`objeto, puede definir múltiples secciones donde los usuarios pueden modificar libremente el contenido mientras mantienen protegidas otras secciones.

#### Q4. ¿Puedo quitar la protección de una sección que estaba protegida inicialmente?
 Sí, puede eliminar la protección de una sección que inicialmente estaba protegida configurando el`ProtectedForForms` propiedad de la correspondiente`Section` oponerse a`false`. Esto permite a los usuarios editar el contenido dentro de esa sección específica sin ninguna restricción.

#### P: ¿Qué tipos de protección se pueden aplicar a un documento de Word?

R: Aspose.Words para .NET ofrece varios tipos de protección que se pueden aplicar a un documento de Word, entre ellos:
- NoProtection: No se aplica ninguna protección.
- AllowOnlyRevisions: los usuarios solo pueden hacer revisiones al documento.
- AllowOnlyComments: los usuarios solo pueden agregar comentarios al documento.
- AllowOnlyFormFields: los usuarios solo pueden editar campos de formulario en el documento.
- Solo lectura: el documento es de solo lectura y no se permite la edición.


