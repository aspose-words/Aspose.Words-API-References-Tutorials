---
title: Crie um projeto Vba em um documento do Word
linktitle: Crie um projeto Vba em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como criar um projeto VBA em um documento Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-vba-macros/create-vba-project/
---

Neste tutorial, mostraremos como criar um projeto VBA em um documento Word usando a biblioteca Aspose.Words para .NET. A criação de um projeto VBA permite adicionar código VBA personalizado ao seu documento do Word. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Crie um novo documento e projeto VBA
 A seguir, criaremos um novo documento instanciando o`Document` class e um projeto VBA vazio instanciando o`VbaProject` aula.

```csharp
// Crie um novo documento
Document doc = new Document();

//Crie um novo projeto VBA
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
```

## Etapa 3: crie um novo módulo e especifique o código-fonte da macro
 Criaremos um novo módulo instanciando o`VbaModule` classe e especificando o nome da macro, tipo (módulo processual) e código fonte.

```csharp
// Crie um novo módulo
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New Source Code";

// Adicione o módulo ao projeto VBA
doc.VbaProject.Modules.Add(module);
```

## Etapa 4: salve o documento
Por fim, salvaremos o documento com o projeto VBA criado em um arquivo.

```csharp
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");
```

### Exemplo de código-fonte para criar projeto Vba usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
VbaProject project = new VbaProject();
project.Name = "AsposeProject";
doc.VbaProject = project;
// Crie um novo módulo e especifique um código-fonte de macro.
VbaModule module = new VbaModule();
module.Name = "AsposeModule";
module.Type = VbaModuleType.ProceduralModule;
module.SourceCode = "New source code";
// Adicione módulo ao projeto VBA.
doc.VbaProject.Modules.Add(module);
doc.Save(dataDir + "WorkingWithVba.CreateVbaProject.docm");

```

## Conclusão
Neste tutorial, vimos como criar um projeto VBA em um documento Word usando Aspose.Words for .NET. A criação de um projeto VBA permite adicionar e personalizar o código VBA em seu documento do Word. Sinta-se à vontade para usar esse recurso para automatizar tarefas ou adicionar funcionalidades personalizadas aos seus documentos do Word.

### Perguntas frequentes

#### P: O que é um projeto VBA em um documento do Word?

R: Um projeto VBA em um documento do Word é uma coleção de módulos VBA contendo código que pode ser usado para automatizar tarefas, adicionar funcionalidades personalizadas ou executar operações específicas em um documento do Word.

#### P: Quais são os pré-requisitos para criar um projeto VBA em um documento Word?

R: Antes de criar um projeto VBA em um documento do Word, você deve ter conhecimento prático da linguagem de programação C#. Você também precisa instalar a biblioteca Aspose.Words for .NET em seu projeto.

#### P: Como definir o diretório do documento no código?

 R: No código fornecido, você precisa substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho apropriado para o diretório onde deseja salvar seu documento do Word com o projeto VBA.

#### P: Como especificar o código-fonte da macro no módulo VBA?

 R: Para especificar o código fonte da macro no módulo VBA, você pode usar o`SourceCode` propriedade do`VbaModule` class atribuindo a ela uma string de caracteres contendo o código VBA.

#### P: Posso adicionar vários módulos VBA a um projeto VBA em um documento do Word?

R: Sim, você pode adicionar vários módulos VBA a um projeto VBA em um documento do Word instanciando vários`VbaModule` objetos e adicioná-los ao`Modules` coleção do`VbaProject` objeto. Isso permite organizar seu código VBA em diferentes módulos para melhor gerenciamento e reutilização.