---
title: 단락 노드 생성 및 추가
linktitle: 단락 노드 생성 및 추가
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 단락 노드를 만들고 추가하세요.
type: docs
weight: 10
url: /ko/net/working-with-node/create-and-add-paragraph-node/
---

다음은 .NET용 Aspose.Words를 사용하여 단락 노드를 생성하고 추가하는 방법을 보여주는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다.

## 1단계: 필요한 참조 가져오기
시작하기 전에 Aspose.Words for .NET을 사용하는 데 필요한 참조를 프로젝트에 가져왔는지 확인하세요. 여기에는 Aspose.Words 라이브러리를 가져오고 소스 파일에 필요한 네임스페이스를 추가하는 작업이 포함됩니다.

```csharp
using Aspose.Words;
```

## 2단계: 새 문서 만들기
 이 단계에서는 다음을 사용하여 새 문서를 만듭니다.`Document` 수업.

```csharp
Document doc = new Document();
```

## 3단계: 단락 노드 만들기
 이제 다음을 사용하여 단락 노드를 만듭니다.`Paragraph` 클래스를 만들고 문서를 매개변수로 전달합니다.

```csharp
Paragraph para = new Paragraph(doc);
```

## 4단계: 문서 섹션에 액세스
 문서에 단락을 추가하려면 다음을 사용하여 문서의 마지막 섹션에 액세스해야 합니다.`LastSection` 재산.

```csharp
Section section = doc.LastSection;
```

## 5단계: 문서에 단락 노드 추가
 이제 문서 섹션이 있으므로 다음을 사용하여 섹션에 단락 노드를 추가할 수 있습니다.`AppendChild` 섹션의 메소드`Body` 재산.

```csharp
section.Body.AppendChild(para);
```

## 6단계: 문서 저장
 마지막으로 문서를 저장하려면`Save` DOCX 형식과 같은 원하는 출력 형식을 지정하여 방법을 선택할 수 있습니다.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### .NET용 Aspose.Words를 사용하여 단락 노드 생성 및 추가를 위한 샘플 소스 코드

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

이것은 .NET용 Aspose.Words를 사용하여 단락 노드를 생성하고 추가하는 완전한 코드 예제입니다. 필요한 참조를 가져오고 이전에 설명한 단계에 따라 이 코드를 프로젝트에 통합하십시오.

### FAQ

#### Q: XML 문서의 단락 노드란 무엇입니까?

A: XML 문서의 단락 노드는 텍스트 단락을 나타내는 데 사용됩니다. 여기에는 단락의 텍스트 내용이 포함되어 있으며 XML 문서에서 텍스트를 구성하는 데 사용할 수 있습니다.

#### Q: Node.js에서 단락 노드를 만드는 방법은 무엇입니까?

 A: Node.js에서 단락 노드를 생성하려면 다음을 사용할 수 있습니다.`createElement` 의 방법`Document` "단락"이라는 이름의 새 요소를 생성하는 개체입니다. 그런 다음`createTextNode` 단락의 내용을 포함하는 텍스트 노드를 만드는 방법입니다.

#### Q: 기존 XML 문서에 단락 노드를 추가하는 방법은 무엇입니까?

 A: 기존 XML 문서에 단락 노드를 추가하려면 다음을 사용할 수 있습니다.`appendChild`단락 노드를 XML 문서의 다른 요소의 하위로 추가하는 방법입니다. 예를 들어 문서 루트 요소의 하위 요소로 추가할 수 있습니다.

#### Q: 단락 노드의 내용을 정의하는 방법은 무엇입니까?

 A: 단락 노드의 내용을 설정하려면 다음을 사용할 수 있습니다.`createTextNode` 원하는 콘텐츠가 포함된 텍스트 노드를 생성하는 메서드를 사용한 다음`appendChild` 해당 텍스트 노드를 단락 노드의 하위로 추가하는 방법입니다.

#### Q: 단락 노드의 텍스트 서식을 어떻게 지정합니까?

A: 단락 노드의 텍스트 형식은 Node.js 환경에서 사용하는 XML API에 따라 다릅니다. 일반적으로 특정 속성과 메서드를 사용하여 글꼴, 크기, 색상 등과 같은 서식 속성을 설정할 수 있습니다.