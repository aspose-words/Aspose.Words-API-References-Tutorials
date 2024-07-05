---
title: 개정 그룹 세부 정보 가져오기
linktitle: 개정 그룹 세부 정보 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 개정 그룹 세부 정보를 가져옵니다.
type: docs
weight: 10
url: /ko/net/working-with-revisions/get-revision-group-details/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 Word 문서의 개정 그룹 세부 정보를 얻는 방법을 보여 드리겠습니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 개정 내용이 포함된 문서를 업로드하는 것입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2단계: 버전 찾아보기

다음으로 문서에 있는 개정판을 반복하여 유형, 작성자, 날짜 및 개정된 텍스트와 같은 세부 정보를 표시합니다.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### .NET용 Aspose.Words를 사용하여 개정 그룹 세부 정보 가져오기에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서의 개정 그룹 세부 정보를 가져오는 전체 소스 코드입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 개정 그룹 세부 정보를 얻는 방법을 배웠습니다. 루프와 적절한 속성을 사용하여 개정 유형, 작성자, 날짜 및 개정된 텍스트와 같은 세부 정보를 표시할 수 있었습니다. Aspose.Words for .NET은 개정 관리를 포함하여 Word 문서를 조작하기 위한 많은 강력한 기능을 제공합니다. 이제 이 지식을 사용하여 Aspose.Words for .NET을 사용하여 개정 그룹 세부 정보를 자신의 Word 문서로 가져올 수 있습니다.

### FAQ

#### Q: 수정된 문서를 Aspose.Words for .NET에 로드하려면 어떻게 해야 합니까?

 답변:`Document` 개정판이 포함된 파일에서 문서를 로드하는 .NET용 Aspose.Words 클래스입니다. 전체 문서 경로를 지정할 수 있습니다.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET에서 개정 그룹의 세부 정보를 어떻게 얻나요?

A: 루프를 사용하여 문서의 개정판을 살펴보고 각 개정판의 속성에 액세스하여 원하는 세부 정보를 얻으세요. 당신은 사용할 수 있습니다`RevisionType`, `Author`, `DateTime` 그리고`ParentNode` 개정 유형, 작성자, 날짜 및 개정된 텍스트를 각각 가져오는 속성입니다.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### Q: 개정판이 Aspose.Words for .NET의 그룹에 속하는지 확인하는 방법은 무엇입니까?

 답변:`Group` 의 재산`Revision` 개정이 그룹에 속하는지 확인하는 개체입니다. 만약`Group` 재산은`null`, 이는 개정이 어떤 그룹에도 속하지 않음을 의미합니다.

```csharp
if (revision.Group != null)
{
      // 개정이 그룹에 속해 있습니다.
}
else
{
      // 개정판이 어떤 그룹에도 속해 있지 않습니다.
}
```