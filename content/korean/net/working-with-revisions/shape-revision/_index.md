---
title: 모양 개정
linktitle: 모양 개정
second_title: Aspose.Words 문서 처리 API
description: 이 포괄적인 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서의 모양 개정을 처리하는 방법을 알아보세요. 변경 사항 추적, 도형 삽입 등을 마스터하세요.
type: docs
weight: 10
url: /ko/net/working-with-revisions/shape-revision/
---
## 소개

프로그래밍 방식으로 Word 문서를 편집하는 것은 어려운 작업이 될 수 있으며, 특히 도형을 처리할 때 더욱 그렇습니다. 보고서를 작성하든, 템플릿을 디자인하든, 아니면 단순히 문서 작성을 자동화하든 관계없이 모양 개정을 추적하고 관리하는 능력은 매우 중요합니다. Aspose.Words for .NET은 이 프로세스를 원활하고 효율적으로 만들기 위한 강력한 API를 제공합니다. 이 튜토리얼에서는 Word 문서에서 도형을 수정하는 방법에 대해 자세히 알아보고 문서를 쉽게 관리할 수 있는 도구와 지식을 갖추도록 하겠습니다.

## 전제 조건

코드를 살펴보기 전에 필요한 모든 것이 갖추어져 있는지 확인하겠습니다.

-  .NET용 Aspose.Words: Aspose.Words 라이브러리가 설치되어 있는지 확인하세요. 당신은 할 수 있습니다[여기에서 다운로드하세요](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 개발 환경이 설정되어 있어야 합니다.
- C#의 기본 이해: C# 프로그래밍 언어 및 객체 지향 프로그래밍의 기본 개념에 익숙합니다.
- Word 문서: 작업할 Word 문서 또는 튜토리얼 중에 만들 수 있습니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져오겠습니다. 이를 통해 Word 문서 및 도형을 처리하는 데 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## 1단계: 문서 디렉토리 설정

모양 작업을 시작하기 전에 문서 디렉터리의 경로를 정의해야 합니다. 여기에 수정된 문서를 저장합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 만들기

도형을 삽입하고 수정할 새 Word 문서를 만들어 보겠습니다.

```csharp
Document doc = new Document();
```

## 3단계: 인라인 도형 삽입

수정 내용을 추적하지 않고 문서에 인라인 모양을 삽입하는 것부터 시작하겠습니다. 인라인 모양은 텍스트와 함께 흐르는 모양입니다.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 4단계: 개정판 추적 시작

문서의 변경 사항을 추적하려면 개정 추적을 활성화해야 합니다. 이는 모양에 대한 수정 사항을 식별하는 데 필수적입니다.

```csharp
doc.StartTrackRevisions("John Doe");
```

## 5단계: 수정본이 포함된 다른 도형 삽입

이제 개정 추적이 활성화되었으므로 다른 모양을 삽입해 보겠습니다. 이번에는 모든 변경 사항이 추적됩니다.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## 6단계: 모양 검색 및 수정

문서의 모든 모양을 검색하고 필요에 따라 수정할 수 있습니다. 여기서는 모양을 가져오고 첫 번째 모양을 제거하겠습니다.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## 7단계: 문서 저장

변경한 후에는 문서를 저장해야 합니다. 이렇게 하면 모든 개정 및 수정 사항이 저장됩니다.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## 8단계: 모양 이동 수정 사항 처리

모양이 이동되면 Aspose.Words는 이를 개정으로 추적합니다. 즉, 모양의 인스턴스가 두 개 있습니다. 하나는 원래 위치에 있고 다른 하나는 새 위치에 있습니다.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서의 모양 개정을 처리하는 방법을 성공적으로 배웠습니다. 문서 템플릿을 관리하든, 보고서를 자동화하든, 단순히 변경 사항을 추적하든 이러한 기술은 매우 중요합니다. 이 단계별 가이드를 따르면 기본 사항을 숙지했을 뿐만 아니라 고급 문서 처리 기술에 대한 통찰력을 얻을 수 있습니다.

## FAQ

### .NET용 Aspose.Words란 무엇입니까?
Aspose.Words for .NET은 개발자가 C#을 사용하여 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있는 강력한 라이브러리입니다.

### Word 문서의 다른 요소에 대한 변경 내용을 추적할 수 있나요?
예, Aspose.Words for .NET은 텍스트, 표 등을 포함한 다양한 요소에 대한 변경 사항 추적을 지원합니다.

### .NET용 Aspose.Words의 무료 평가판을 어떻게 받을 수 있나요?
 .NET용 Aspose.Words의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### 프로그래밍 방식으로 수정본을 수락하거나 거부할 수 있나요?
예, Aspose.Words for .NET은 프로그래밍 방식으로 개정판을 승인하거나 거부하는 방법을 제공합니다.

### C# 외에 다른 .NET 언어와 함께 .NET용 Aspose.Words를 사용할 수 있나요?
전적으로! Aspose.Words for .NET은 VB.NET 및 F#을 포함한 모든 .NET 언어와 함께 사용할 수 있습니다.