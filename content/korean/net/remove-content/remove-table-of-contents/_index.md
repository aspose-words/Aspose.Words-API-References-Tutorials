---
title: Word 문서에서 목차 제거
linktitle: Word 문서에서 목차 제거
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 목차를 제거하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/remove-content/remove-table-of-contents/
---
이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 목차를 제거하는 방법을 안내합니다. 목차는 때로는 중복되거나 불필요할 수 있으며, 이 코드는 목차를 효과적으로 제거하는 데 도움이 됩니다. 여러분의 .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되는 단계별 가이드를 제공하겠습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리
- 삭제하려는 목차가 포함된 Word 문서

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 업로드
 다음으로 Word 문서를 인스턴스로 로드하겠습니다.`Document` 을 사용하는 수업`Load` 방법.

```csharp
// 문서를 로드하세요
Document doc = new Document(dataDir + "your-document.docx");
```

## 3단계: 목차 삭제
 목차를 제거하기 위해 TOC(목차) 유형을 반복합니다.`FieldStart` 문서의 노드. 빠르게 액세스하고 삭제할 노드 목록을 생성할 수 있도록 이러한 노드를 저장합니다.

```csharp
// 빠른 액세스를 위해 문서에 TOC 필드의 FieldStart 노드를 저장합니다.
List<FieldStart> fieldStarts = new List<FieldStart>();
// 지정된 TOC 내에서 발견된 노드를 저장하기 위한 목록입니다. 이 방법이 끝나면 삭제됩니다.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// 지정된 TOC 색인이 존재하는지 확인하십시오.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // 이러한 노드를 저장하고 마지막에 모두 삭제하는 것이 더 안전합니다.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // FieldTOC 유형의 FieldEnd 노드를 만나면,
     //우리는 현재 TOC가 끝났다는 것을 알고 있으며 여기에서 중지합니다.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### .NET용 Aspose.Words를 사용하여 목차 제거에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// 문서를 로드하세요
Document doc = new Document(dataDir + "your-document.docx");

// 빠른 액세스를 위해 문서에 TOC 필드의 FieldStart 노드를 저장합니다.
List<FieldStart> fieldStarts = new List<FieldStart>();
// 지정된 TOC 내에서 발견된 노드를 저장하기 위한 목록입니다. 이 방법이 끝나면 제거됩니다.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// 전달된 인덱스에 지정된 TOC가 존재하는지 확인하세요.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// 이러한 노드는 저장했다가 나중에 한꺼번에 삭제하는 것이 더 안전합니다.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// FieldTOC 유형의 FieldEnd 노드를 만나면,
	// 현재 TOC가 끝났음을 알고 여기서 중지합니다.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 목차를 제거하는 단계별 가이드를 제시했습니다. 제공된 코드와 지침을 따르면 목차를 쉽게 제거하고 문서 레이아웃을 개선할 수 있습니다. 특정 요구 사항에 맞게 디렉터리 경로와 파일 이름을 조정하는 것을 잊지 마십시오.

### FAQ

#### Q: Word 문서에서 목차를 제거하기 위해 Aspose.Words를 사용해야 하는 이유는 무엇입니까?

A: Aspose.Words는 .NET 애플리케이션에서 Word 문서를 조작하기 위한 강력하고 다양한 클래스 라이브러리입니다. Aspose.Words를 사용하면 문서에서 목차를 효과적으로 제거할 수 있으며, 이는 목차가 중복되거나 불필요한 경우 유용할 수 있습니다. 이를 통해 문서의 내용을 사용자 정의하고 전반적인 프레젠테이션을 향상시킬 수 있습니다.

#### Q: .NET용 Aspose.Words에서 문서를 어떻게 업로드합니까?

A: Word 문서에서 목차를 제거하려면 먼저 Aspose.Words의 Load() 메서드를 사용하여 문서를 메모리에 로드해야 합니다. 다음은 특정 디렉터리에서 문서를 로드하는 샘플 코드입니다.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "your-document.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서의 실제 경로와 함께.

#### Q: Aspose.Words를 사용하여 문서의 목차를 어떻게 제거합니까?

 A: TOC를 제거하려면`FieldStart` 문서에 TOC의 노드를 입력합니다. 빠른 액세스를 위해 이러한 노드를 저장하고 삭제할 노드 목록을 만들 수 있습니다. 다음은 샘플 코드입니다.

```csharp
// 빠른 액세스를 위해 문서에 TOC 필드의 FieldStart 노드를 저장합니다.
List<FieldStart> fieldStarts = new List<FieldStart>();
//지정된 TOC 내에서 발견된 노드를 저장하는 목록입니다. 이 방법이 끝나면 삭제됩니다.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// 지정한 목차 색인이 있는지 확인하세요.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// 이러한 노드를 저장하고 마지막에 모두 삭제하는 것이 더 안전합니다.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// FieldTOC 유형의 FieldEnd 노드를 만나면,
//우리는 현재 TOC가 끝났다는 것을 알고 있으며 여기에서 중지합니다.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Q: .NET용 Aspose.Words에서 편집된 문서를 어떻게 저장합니까?

A: 목차를 삭제한 후에는 반드시 Save() 메소드를 이용하여 수정된 문서를 저장해야 합니다. 편집된 문서에 대해 원하는 출력 파일 경로와 형식(예: DOCX)을 지정합니다. 다음은 샘플 코드입니다.

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```