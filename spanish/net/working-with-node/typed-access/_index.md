---
title: Acceso escrito
linktitle: Acceso escrito
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar el acceso con tipo para manipular tablas en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-node/typed-access/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo usar la característica de acceso con tipo con Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Paso 2: Crear un nuevo documento
 En este paso, crearemos un nuevo documento usando el`Document` clase.

```csharp
Document doc = new Document();
```

## Paso 3: Accede a la sección y al cuerpo
Para acceder a las tablas contenidas en el documento, primero debemos acceder a la sección y al cuerpo del documento.

```csharp
Section section = doc.FirstSection;
Body body = section.Body;
```

## Paso 4: acceso rápido y escrito a las tablas
Ahora que tenemos el cuerpo del documento, podemos usar el acceso rápido y escrito para acceder a todas las tablas contenidas en el cuerpo.

```csharp
TableCollection tables = body.Tables;
```

## Paso 5: Examinar tablas
 usando un`foreach` bucle, podemos recorrer todas las tablas y realizar operaciones específicas en cada tabla.

```csharp
foreach(Table table in tables)
{
     // Acceso rápido y mecanografiado a la primera fila de la tabla.
     table.FirstRow?.Remove();

     // Acceso rápido y escrito a la última fila de la tabla.
     table.LastRow?.Remove();
}
```

En este ejemplo, eliminamos la primera y la última fila de cada tabla utilizando el acceso rápido y escrito proporcionado por Aspose.Words.

### Ejemplo de código fuente para acceso escrito con Aspose.Words para .NET

```csharp
Document doc = new Document();

Section section = doc.FirstSection;
Body body = section.Body;

// Acceso rápido escrito a todos los nodos secundarios de la tabla contenidos en el cuerpo.
TableCollection tables = body.Tables;

foreach (Table table in tables)
{
	// Acceso rápido escrito a la primera fila de la tabla.
	table.FirstRow?.Remove();

	// Acceso rápido escrito a la última fila de la tabla.
	table.LastRow?.Remove();
}
```

Este es un código de muestra completo para el acceso escrito a las tablas con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.

---
