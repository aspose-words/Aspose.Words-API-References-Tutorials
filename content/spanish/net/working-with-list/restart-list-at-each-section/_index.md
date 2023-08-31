---
title: Lista de reinicio en cada sección
linktitle: Lista de reinicio en cada sección
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo restablecer una lista numerada para cada sección de un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-list/restart-list-at-each-section/
---

En este tutorial paso a paso, le mostraremos cómo restablecer una lista numerada para cada sección de un documento de Word usando Aspose.Words para .NET. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo has hecho, descarga e instala la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: crear el documento y la lista

Primero, cree un nuevo documento y agregue una lista numerada predeterminada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Paso 2: agregar elementos a la lista

 Luego usa un`DocumentBuilder` para agregar elementos a la lista. Puede utilizar un bucle para agregar varios elementos a la lista:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

En este ejemplo, insertaremos un salto de sección después del elemento número 15 de la lista para ilustrar la renumeración.

## Paso 3: guarde el documento modificado

Finalmente, guarde el documento modificado:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Entonces ! Ha restablecido con éxito una lista numerada para cada sección de un documento de Word utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para restablecer la lista en cada sección

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Siéntase libre de utilizar este código en sus propios proyectos y modificarlo para adaptarlo a sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo reiniciar una lista en cada sección de Aspose.Words?

 R: Para reiniciar una lista en cada sección de Aspose.Words, necesita crear una instancia del`List` clase y asignarle una lista numerada. Entonces puedes usar el`List.IsRestartAtEachSection` propiedad para especificar que la numeración debe reiniciarse en cada sección. Puede asociar esta lista con una o más secciones de su documento para que la numeración se reinicie correctamente en cada sección.

#### P: ¿Puedo personalizar el formato de numeración de las listas en Aspose.Words?

 R: Sí, puedes personalizar el formato de numeración de las listas en Aspose.Words. El`List` La clase ofrece varias propiedades para esto, como por ejemplo`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`etc. Puede utilizar estas propiedades para configurar el tipo de lista (numerada, con viñetas, etc.), el formato de numeración (números arábigos, números romanos, letras, etc.) y otras opciones de formato de numeración.

#### P: ¿Es posible agregar niveles adicionales a una lista numerada en Aspose.Words?

 R: Sí, es posible agregar niveles adicionales a una lista numerada en Aspose.Words. El`ListLevel` La clase le permite establecer propiedades de formato para cada nivel de la lista. Puede configurar opciones como prefijo, sufijo, alineación, sangría, etc. Esto le permite crear listas con múltiples niveles de jerarquía.