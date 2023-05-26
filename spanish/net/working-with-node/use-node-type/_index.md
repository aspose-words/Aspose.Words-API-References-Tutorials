---
title: Usar tipo de nodo
linktitle: Usar tipo de nodo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar el tipo de nodo para acceder a información específica del documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-node/use-node-type/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación que ilustra cómo usar la funcionalidad de tipo de nodo con Aspose.Words para .NET.

## Paso 1: Importa las referencias necesarias
Antes de comenzar, asegúrese de haber importado las referencias necesarias para usar Aspose.Words para .NET en su proyecto. Esto incluye importar la biblioteca Aspose.Words y agregar los espacios de nombres requeridos a su archivo fuente.

```csharp
using Aspose.Words;
```

## Paso 2: Crear un nuevo documento
 En este paso, crearemos un nuevo documento usando el`Document` clase.

```csharp
Document doc = new Document();
```

## Paso 3: obtener el tipo de nodo del documento
 Para obtener el tipo de nodo de un documento, usamos el`NodeType` propiedad.

```csharp
NodeType type = doc.NodeType;
```

### Ejemplo de código fuente para usar el tipo de nodo con Aspose.Words para .NET

```csharp
Document doc = new Document();

NodeType type = doc.NodeType;
```

Este es un ejemplo de código completo para usar el tipo de nodo con Aspose.Words para .NET. Asegúrese de importar las referencias necesarias y siga los pasos descritos anteriormente para integrar este código en su proyecto.

