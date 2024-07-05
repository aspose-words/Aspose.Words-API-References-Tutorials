---
title: Carregar configurações de fallback do Noto
linktitle: Carregar configurações de fallback do Noto
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como carregar parâmetros de substituição Noto em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/load-noto-fallback-settings/
---
Neste tutorial, orientaremos você sobre como carregar as configurações de substituição de fonte Noto em um documento do Word usando a Biblioteca Aspose.Words para .NET. As configurações de substituição de fontes Noto permitem gerenciar a substituição de fontes ao exibir ou imprimir documentos. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

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

## Etapa 2: carregue o documento e defina as configurações de substituição de fonte
 A seguir, carregaremos o documento usando o`Document` classe e defina as configurações de substituição de fonte usando o`FontSettings`aula. Carregaremos as configurações de fallback da fonte Noto usando o`LoadNotoFallbackSettings()` método.

```csharp
// Carregue o documento e defina as configurações de substituição de fonte
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Etapa 3: salve o documento
Por fim, salvaremos o documento com as configurações de substituição de fonte Noto aplicadas.

```csharp
// Salve o documento
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Exemplo de código-fonte para Noto Fallback Settings usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Conclusão
Neste tutorial, vimos como carregar as configurações de substituição de fonte Noto em um documento do Word com Aspose.Words for .NET. As configurações de substituição de fontes Noto permitem gerenciar a substituição de fontes para melhorar a exibição e impressão de seus documentos. Sinta-se à vontade para usar este recurso para personalizar a substituição da fonte de acordo com suas necessidades.

### Perguntas frequentes

#### P: Como posso carregar as configurações de substituição de fonte Noto em um documento do Word com Aspose.Words?

R: Para carregar as configurações de substituição de fonte Noto em um documento do Word com Aspose.Words, você deve primeiro baixar as fontes Noto da fonte oficial. Em seguida, você pode usar a API Aspose.Words para carregar essas fontes no documento e configurá-las para substituição quando necessário.

#### P: O uso de fontes Noto para substituição em documentos do Word garante uma visualização consistente do texto?

R: Sim, o uso de fontes Noto para substituição em documentos do Word garante uma visualização consistente do texto. As fontes Noto são projetadas para suportar vários idiomas e caracteres, ajudando a manter uma aparência consistente mesmo quando as fontes necessárias não estão disponíveis.

#### P: As fontes Noto são gratuitas?

R: Sim, as fontes Noto são gratuitas e de código aberto. Eles podem ser baixados e usados em seus projetos sem nenhum custo. Isso o torna uma ótima opção para melhorar a exibição de fontes em seus documentos Word sem ter que investir em fontes comerciais.

#### P: O uso de fontes Noto torna meus documentos do Word mais acessíveis?

R: Sim, usar fontes Noto para substituição em documentos do Word ajuda a tornar seus documentos mais acessíveis. As fontes Noto suportam vários idiomas e caracteres, garantindo melhor legibilidade e compreensão para os usuários que visualizam seus documentos em diferentes idiomas.