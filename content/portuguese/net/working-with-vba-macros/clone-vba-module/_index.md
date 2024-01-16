---
title: Clonar módulo Vba de um documento do Word
linktitle: Clonar módulo Vba de um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como clonar um módulo VBA de um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-vba-macros/clone-vba-module/
---

Neste tutorial, mostraremos como clonar um módulo VBA de um documento Word com macros usando a biblioteca Aspose.Words para .NET. A clonagem de um módulo VBA permite reutilizar ou copiar o código VBA de um documento de origem para outro documento. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto
- Um documento Word contendo um projeto VBA com o módulo que você deseja clonar

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: carregar o documento de origem
A seguir, carregaremos o documento Word de origem, que contém o projeto VBA e o módulo que queremos clonar.

```csharp
// Carregue o documento de origem
Document doc = new Document(dataDir + "VBA project.docm");
```

## Etapa 3: Crie um novo documento com o projeto VBA e clone o módulo
Criaremos um novo documento com um projeto VBA vazio e clonaremos o módulo especificado do documento de origem.

```csharp
// Crie um novo documento com um projeto VBA vazio
Document destDoc = new Document { VbaProject = new VbaProject() };

// Clonar o módulo
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Etapa 4: salve o documento de destino
Por fim, salvaremos o documento de destino com o módulo VBA clonado em um arquivo.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Exemplo de código-fonte para módulo Clone Vba usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Conclusão
Neste tutorial, vimos como clonar um módulo VBA de um documento Word com macros usando Aspose.Words for .NET. A clonagem de módulos VBA permite reutilizar facilmente o código VBA de um documento de origem em outro documento. Sinta-se à vontade para usar este recurso para organizar e gerenciar suas macros em diferentes documentos.

### Perguntas frequentes

#### P: O que é duplicar um módulo VBA?

R: Duplicar um módulo VBA consiste em copiar um módulo contendo código VBA de um documento fonte do Word para outro documento. Isso permite reutilizar o código VBA em diferentes contextos ou compartilhá-lo com outros documentos.

#### P: Quais são os pré-requisitos para clonar um módulo VBA de um documento do Word?

R: Antes de clonar um módulo VBA de um documento do Word, você deve ter conhecimento prático da linguagem de programação C#. Você também precisa instalar a biblioteca Aspose.Words for .NET em seu projeto. Além disso, você precisa de um documento Word contendo um projeto VBA com o módulo que deseja clonar.

#### P: Como definir o diretório do documento no código?

 R: No código fornecido, você precisa substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho apropriado para o diretório onde está localizado o documento do Word que contém o projeto VBA.

#### P: Como salvar o documento de destino com módulo VBA clonado?

 R: Para salvar o documento de destino com o módulo VBA clonado, você pode usar o`Save` método do`Document` class especificando o caminho de destino e o nome do arquivo desejados.