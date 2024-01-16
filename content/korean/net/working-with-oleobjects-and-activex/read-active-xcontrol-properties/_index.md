---
title: Word 파일에서 Active XControl 속성 읽기
linktitle: Word 파일에서 Active XControl 속성 읽기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 파일에서 ActiveX 컨트롤의 속성을 읽습니다.
type: docs
weight: 10
url: /ko/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 Word 파일에서 ActiveX 컨트롤의 속성을 읽는 방법을 보여줍니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 초기화

 첫 번째 단계는 초기화입니다.`Document` ActiveX 컨트롤이 포함된 Word 문서를 로드하여 개체를 만듭니다. 꼭 교체하세요`MyDir` 문서가 포함된 디렉터리의 실제 경로를 사용합니다.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 2단계: ActiveX 컨트롤 복구

 이 단계에서는 각 항목을 반복합니다.`Shape` ActiveX 컨트롤을 검색하고 해당 속성을 읽으려면 문서를 참조하세요.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### .NET용 Aspose.Words를 사용하여 Active XControl 속성 읽기에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 ActiveX 컨트롤의 속성을 읽는 전체 소스 코드입니다.

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## 결론

이 가이드에서는 Aspose.Words for .NET을 사용하여 Word 파일에서 ActiveX 컨트롤의 속성을 읽는 방법을 보여주었습니다. 설명된 단계를 수행하면 문서를 초기화하고 ActiveX 컨트롤을 검색하며 해당 속성을 읽을 수 있습니다. 제공된 샘플 코드를 시작점으로 사용하고 특정 요구 사항에 맞게 사용자 정의하세요.

ActiveX 컨트롤의 속성을 읽으면 이러한 컨트롤이 포함된 Word 파일에서 중요한 정보를 추출할 수 있습니다. Aspose.Words for .NET은 ActiveX 컨트롤을 사용한 단어 처리 및 문서 처리 자동화를 위한 강력한 기능을 제공합니다.

### 자주 묻는 질문

#### Q: Word 파일에서 ActiveX 컨트롤의 속성을 읽는 첫 번째 단계는 무엇입니까?

 A: 첫 번째 단계는`Document` ActiveX 컨트롤이 포함된 Word 문서를 로드하여 개체를 만듭니다. 꼭 교체하세요`MyDir` 문서가 포함된 디렉터리의 실제 경로를 사용합니다.

#### 질문: ActiveX 컨트롤을 문서로 가져오려면 어떻게 해야 합니까?

 A: ActiveX 컨트롤을 검색하려면 각 컨트롤을 반복해야 합니다.`Shape` 문서를 확인하고 ActiveX 컨트롤인지 확인하세요. 사용`OleFormat` 의 자산`Shape` 액세스하려면`OleControl` 개체를 만들고 필요한 속성을 검색합니다.

#### Q: ActiveX 컨트롤의 어떤 속성을 읽을 수 있습니까?

A: 캡션, 값, 활성화 또는 비활성화 상태, 유형, 컨트롤과 연결된 childNodes 등 ActiveX 컨트롤의 다양한 속성을 읽을 수 있습니다.

#### Q: 문서에 있는 ActiveX 컨트롤의 총 개수를 어떻게 알 수 있나요?

 A: 문서에 있는 ActiveX 컨트롤의 총 개수를 얻으려면 다음을 사용할 수 있습니다.`GetChildNodes` 의 방법`Document` 객체를 지정하는 객체`NodeType.Shape` 유형을 지정하고 하위 노드를 포함합니다.