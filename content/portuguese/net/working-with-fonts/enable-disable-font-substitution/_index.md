---
title: Habilitar Desabilitar Substituição de Fonte
linktitle: Habilitar Desabilitar Substituição de Fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ativar ou desativar a substituição de fontes em documentos do Word usando Aspose.Words for .NET. Garanta que seus documentos tenham aparência consistente em todas as plataformas.
type: docs
weight: 10
url: /pt/net/working-with-fonts/enable-disable-font-substitution/
---
## Introdução

Você já se viu em uma situação em que as fontes meticulosamente escolhidas em um documento do Word são substituídas quando visualizadas em outro computador? Irritante, certo? Isso acontece devido à substituição de fontes, processo em que o sistema substitui uma fonte ausente por uma disponível. Mas não se preocupe! Com Aspose.Words for .NET, você pode gerenciar e controlar facilmente a substituição de fontes. Neste tutorial, orientaremos você nas etapas para ativar ou desativar a substituição de fontes em seus documentos do Word, garantindo que seus documentos sempre tenham a aparência que você deseja.

## Pré-requisitos

Antes de mergulhar nas etapas, vamos garantir que você tenha tudo o que precisa:

-  Aspose.Words para .NET: Baixe a versão mais recente[aqui](https://releases.aspose.com/words/net/).
- Visual Studio: qualquer versão com suporte para .NET.
- Conhecimento básico de C#: Isso o ajudará a acompanhar os exemplos de codificação.

## Importar namespaces

Para começar, certifique-se de ter os namespaces necessários importados em seu projeto. Adicione-os no topo do seu arquivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Agora, vamos dividir o processo em etapas simples e gerenciáveis.

## Etapa 1: configure seu projeto

Primeiro, configure um novo projeto no Visual Studio e adicione uma referência à biblioteca Aspose.Words for .NET. Se ainda não o fez, baixe-o no[Aspor site](https://releases.aspose.com/words/net/).

## Etapa 2: carregue seu documento

Em seguida, carregue o documento com o qual deseja trabalhar. Veja como você faz isso:

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento. Este código carrega o documento na memória para que você possa manipulá-lo.

## Etapa 3: definir as configurações de fonte

 Agora, vamos criar um`FontSettings` objeto para gerenciar as configurações de substituição de fonte:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Etapa 4: definir a substituição de fonte padrão

Defina a substituição de fonte padrão para uma fonte de sua escolha. Esta fonte será usada se a fonte original não estiver disponível:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

Neste exemplo, estamos usando Arial como fonte padrão.

## Etapa 5: desative a substituição de informações de fonte

Para desativar a substituição de informações de fonte, o que impede o sistema de substituir fontes ausentes por fontes disponíveis, use o seguinte código:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Etapa 6: aplicar configurações de fonte ao documento

Agora, aplique estas configurações ao seu documento:

```csharp
doc.FontSettings = fontSettings;
```

## Etapa 7: salve seu documento

Finalmente, salve seu documento modificado. Você pode salvá-lo em qualquer formato que desejar. Para este tutorial, vamos salvá-lo como PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Conclusão

E aí está! Seguindo essas etapas, você pode controlar facilmente a substituição de fontes em seus documentos do Word usando Aspose.Words for .NET. Isso garante que seus documentos mantenham a aparência pretendida, não importa onde sejam visualizados.

## Perguntas frequentes

### Posso usar fontes diferentes de Arial para substituição?

 Absolutamente! Você pode especificar qualquer fonte disponível em seu sistema alterando o nome da fonte no campo`DefaultFontName` propriedade.

### O que acontece se a fonte padrão especificada não estiver disponível?

Se a fonte padrão não estiver disponível, o Aspose.Words usará um mecanismo de fallback do sistema para encontrar uma substituição apropriada.

### Posso ativar a substituição de fontes novamente após desativá-la?

 Sim, você pode alternar o`Enabled` propriedade de`FontInfoSubstitution` de volta para`true` se você deseja ativar a substituição de fontes novamente.

### Existe uma maneira de verificar quais fontes estão sendo substituídas?

Sim, o Aspose.Words fornece métodos para registrar e rastrear a substituição de fontes, permitindo que você veja quais fontes estão sendo substituídas.

### Posso usar este método para outros formatos de documento além de DOCX?

Definitivamente! Aspose.Words oferece suporte a vários formatos e você pode aplicar essas configurações de fonte a qualquer formato compatível.