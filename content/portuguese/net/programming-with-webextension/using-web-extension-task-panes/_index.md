---
title: Usando painéis de tarefas de extensão da Web
linktitle: Usando painéis de tarefas de extensão da Web
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar e configurar painéis de tarefas de extensão da Web em documentos do Word usando Aspose.Words for .NET neste tutorial passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-webextension/using-web-extension-task-panes/
---
## Introdução

Bem-vindo a este tutorial detalhado sobre como usar painéis de tarefas de extensão da Web em um documento do Word usando Aspose.Words for .NET. Se você sempre quis aprimorar seus documentos do Word com painéis de tarefas interativos, você está no lugar certo. Este guia irá orientá-lo em todas as etapas para conseguir isso sem problemas.

## Pré-requisitos

Antes de começarmos, vamos ter certeza de que você tem tudo o que precisa:

-  Aspose.Words para .NET: você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento .NET: Visual Studio ou qualquer outro IDE de sua preferência.
- Conhecimento básico de C#: Isso o ajudará a acompanhar os exemplos de código.
-  Licença para Aspose.Words: você pode comprar uma[aqui](https://purchase.aspose.com/buy) ou obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

## Importar namespaces

Antes de começarmos a codificar, certifique-se de ter os seguintes namespaces importados em seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## Guia passo a passo

Agora, vamos dividir o processo em etapas fáceis de seguir.

### Etapa 1: configurando seu diretório de documentos

Em primeiro lugar, precisamos configurar o caminho para o diretório de documentos. É aqui que seu documento do Word será salvo.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para sua pasta de documentos.

### Etapa 2: Criando um Novo Documento

A seguir, criaremos um novo documento do Word usando Aspose.Words.

```csharp
Document doc = new Document();
```

 Esta linha inicializa uma nova instância do`Document` class, que representa um documento do Word.

### Etapa 3: adicionar um painel de tarefas

Agora, adicionaremos um Painel de Tarefas ao nosso documento. Os painéis de tarefas são úteis para fornecer funcionalidades e ferramentas adicionais em um documento do Word.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 Aqui, criamos um novo`TaskPane` objeto e adicione-o ao documento`WebExtensionTaskPanes` coleção.

### Etapa 4: configurando o painel de tarefas

Para tornar nosso Painel de Tarefas visível e definir suas propriedades, usamos o seguinte código:

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` define onde o Painel de Tarefas aparecerá. Neste caso, está à direita.
- `IsVisible` garante que o Painel de Tarefas esteja visível.
- `Width` define a largura do Painel de Tarefas.

### Etapa 5: Configurando a referência de extensão da Web

A seguir, configuramos a Referência de extensão da Web que inclui ID, versão, tipo de loja e loja.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`é um identificador exclusivo para a extensão da web.
- `Version` especifica a versão da extensão.
- `StoreType` indica o tipo de loja (neste caso, OMEX).
- `Store` especifica o código de idioma/cultura da loja.

### Etapa 6: adicionando propriedades à extensão da web

Você pode adicionar propriedades à sua extensão da web para definir seu comportamento ou conteúdo.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 Aqui, adicionamos uma propriedade chamada`mailchimpCampaign`.

### Etapa 7: vinculando a extensão da web

Finalmente, adicionamos ligações à nossa extensão web. As ligações permitem vincular a extensão a partes específicas do documento.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` é o nome da ligação.
- `WebExtensionBindingType.Text` indica que a encadernação é do tipo texto.
- `194740422` é o ID da parte do documento à qual a extensão está vinculada.

### Etapa 8: salvando o documento

Depois de configurar tudo, salve seu documento.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

Esta linha salva o documento no diretório especificado com o nome de arquivo fornecido.

### Etapa 9: Carregando e exibindo informações do painel de tarefas

Para verificar e exibir as informações do painel de tarefas, carregamos o documento e iteramos pelos painéis de tarefas.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

Esse código carrega o documento e imprime o provedor, a versão e o identificador do catálogo de cada painel de tarefas no console.

## Conclusão

E é isso! Você adicionou e configurou com êxito um painel de tarefas de extensão da Web em um documento do Word usando Aspose.Words for .NET. Este poderoso recurso pode aprimorar significativamente seus documentos do Word, fornecendo funcionalidades adicionais diretamente no documento. 

## Perguntas frequentes

### O que é um painel de tarefas no Word?
Um Painel de Tarefas é um elemento de interface que fornece ferramentas e funcionalidades adicionais em um documento do Word, melhorando a interação e a produtividade do usuário.

### Posso personalizar a aparência do Painel de Tarefas?
 Sim, você pode personalizar a aparência do Painel de Tarefas definindo propriedades como`DockState`, `IsVisible` , e`Width`.

### O que são propriedades de extensão da web?
Propriedades de extensão da Web são propriedades personalizadas que você pode adicionar a uma extensão da Web para definir seu comportamento ou conteúdo.

### Como vinculo uma extensão da Web a uma parte do documento?
 Você pode vincular uma extensão da Web a uma parte do documento usando o`WebExtensionBinding` classe, especificando o tipo de ligação e o ID de destino.

### Onde posso encontrar mais informações sobre o Aspose.Words for .NET?
 Você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/words/net/).