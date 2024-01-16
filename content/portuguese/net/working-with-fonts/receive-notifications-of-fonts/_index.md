---
title: Receba notificações de fontes
linktitle: Receba notificações de fontes
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como receber notificações de fontes ausentes ou substituídas ao usar Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/receive-notifications-of-fonts/
---

Neste tutorial, orientaremos você sobre como receber notificações de fontes ao usar o Aspose.Words for .NET. As notificações de fontes permitem detectar e gerenciar fontes ausentes ou substituídas em seus documentos. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

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

## Etapa 2: carregue o documento e defina as configurações de fonte
 A seguir, carregaremos o documento usando o`Document` class e defina as configurações de fonte usando o`FontSettings` aula. Definiremos a fonte padrão a ser usada em caso de falta de fontes.

```csharp
// Carregue o documento e defina as configurações de fonte
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Etapa 3: definir o gerenciador de notificações
 seguir, definiremos um manipulador de notificação implementando o`IWarningCallback` interface. Isso nos permitirá coletar avisos de fonte ao salvar o documento.

```csharp
// Definir o manipulador de notificação
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Etapa 4: aplique as configurações de fonte e salve o documento
Por fim, aplicaremos as configurações de fonte ao documento e o salvaremos. Quaisquer avisos de fonte serão capturados pelo manipulador de notificação que definimos anteriormente.

```csharp
// Aplique as configurações de fonte e salve o documento
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Exemplo de código-fonte para receber notificações de fontes usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Podemos escolher a fonte padrão a ser usada no caso de alguma fonte faltar.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Para teste, configuraremos Aspose.Words para procurar fontes apenas em uma pasta que não existe. Já que Aspose.Words não
// encontre qualquer fonte no diretório especificado e, durante a renderização, as fontes no documento serão substituídas pelo padrão
// fonte especificada em FontSettings.DefaultFontName. Podemos pegar essa subsuição usando nosso retorno de chamada.
fontSettings.SetFontsFolder(string.Empty, false);
//Crie uma nova classe implementando IWarningCallback que coleta quaisquer avisos produzidos durante o salvamento do documento.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Conclusão
Neste tutorial, vimos como receber notificações de fontes ao usar Aspose.Words for .NET. As notificações de fontes permitem detectar e gerenciar fontes ausentes ou substituídas em seus documentos. Use este recurso para garantir a consistência das fontes em seus documentos e tomar as medidas adequadas em caso de falta de fontes.

### Perguntas frequentes

#### P: Como posso receber notificações de fontes ausentes no Aspose.Words?

 R: Para receber notificações de fontes ausentes no Aspose.Words, você pode usar o`FontSettings` classe e o`FontSubstitutionCallback` evento. Você pode definir um método de retorno de chamada para ser notificado quando forem encontradas fontes ausentes durante o processamento de documentos.

#### P: Como posso lidar com a falta de fontes em meus documentos do Word?

R: Para lidar com a falta de fontes em seus documentos do Word, você pode usar estratégias diferentes. Você pode instalar as fontes ausentes no sistema onde executa o aplicativo Aspose.Words ou pode substituir as fontes ausentes por fontes alternativas disponíveis.

#### P: É possível receber notificações de fontes substituídas no Aspose.Words?

 R: Sim, é possível receber notificações de fontes substituídas no Aspose.Words. Quando as fontes são substituídas durante o processamento do documento, você pode ser notificado usando o`FontSubstitutionCallback` evento e tomar as medidas apropriadas para ajustar a aparência do texto.

#### P: Como posso manter a aparência do texto consistente quando as fontes são substituídas no Aspose.Words?

R: Para manter a consistência na aparência do texto quando as fontes são substituídas, você pode ajustar as propriedades de formatação do texto, como tamanho, estilo e cor da fonte. Você também pode considerar o uso de fontes substitutas que sejam visualmente semelhantes às fontes originais.