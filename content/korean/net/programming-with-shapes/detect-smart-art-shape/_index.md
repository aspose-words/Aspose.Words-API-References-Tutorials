---
title: 스마트 아트 모양 감지
linktitle: 스마트 아트 모양 감지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 스마트 아트 모양을 감지하고 그래픽 표현을 식별하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/detect-smart-art-shape/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 스마트 아트 모양을 감지하는 방법을 설명합니다. 스마트 아트 모양은 정보와 아이디어를 시각적으로 표현하는 데 사용되는 그래픽 표현입니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서가 있는 디렉토리의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 로드
 다음을 사용하여 Word 문서를 로드합니다.`Document` 생성자, 문서 경로를 매개변수로 전달합니다.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## 3단계: 스마트 아트 모양 감지
 유형의 하위 노드를 반복합니다.`Shape` 문서에서`GetChildNodes`방법. 다음을 사용하여 각 도형에 스마트 아트가 있는지 확인하세요.`HasSmart Art` 재산.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## 4단계: 결과 출력
문서에서 감지된 Smart Art가 포함된 도형의 개수를 인쇄합니다.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### .NET용 Aspose.Words를 사용하여 스마트 아트 모양 감지에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 스마트 아트 모양을 성공적으로 감지했습니다.