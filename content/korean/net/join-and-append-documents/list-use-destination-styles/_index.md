---
title: 목록 사용 대상 스타일
linktitle: 목록 사용 대상 스타일
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 대상 문서의 목록 스타일을 유지하면서 Word 문서를 결합하고 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/list-use-destination-styles/
---

이 튜토리얼은 .NET용 Aspose.Words의 목록 사용 대상 스타일 기능을 사용하는 과정을 안내합니다. 이 기능을 사용하면 대상 문서의 목록 스타일을 사용하면서 Word 문서를 결합하고 추가할 수 있습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.Words가 설치되었습니다. Aspose 웹사이트에서 다운로드하거나 NuGet을 통해 설치할 수 있습니다.
2. Visual Studio 또는 기타 C# 개발 환경.

## 1단계: 문서 디렉터리 초기화

 먼저 문서 디렉터리의 경로를 설정해야 합니다. 값을 수정합니다.`dataDir` 문서가 있는 경로에 대한 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 및 대상 문서 로드

다음으로 Aspose.Words를 사용하여 소스 및 대상 문서를 로드해야 합니다.`Document` 수업. 다음에서 파일 이름을 업데이트합니다.`Document` 문서 이름에 따른 생성자.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3단계: 원본 문서를 대상 문서 다음에 계속하도록 설정

 원본 문서의 내용이 대상 문서가 끝난 후에도 계속되도록 하려면 다음을 설정해야 합니다.`SectionStart` 소스 문서의 첫 번째 섹션 속성을`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4단계: 목록 서식 처리

목록 서식을 처리하려면 소스 문서의 각 단락을 반복하여 목록 항목인지 확인합니다. 그렇다면 목록 ID를 대상 문서의 기존 목록과 비교합니다. 동일한 ID를 가진 목록이 있는 경우 소스 문서에 목록의 복사본을 만들고 복사된 목록을 사용하도록 단락의 목록 형식을 업데이트합니다.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## 5단계: 원본 문서를 대상 문서에 추가

 이제 다음을 사용하여 소스 문서를 대상 문서에 추가할 수 있습니다.`AppendDocument` 의 방법`Document` 수업. 그만큼`ImportFormatMode.UseDestinationStyles` 매개변수는 추가 작업 중에 대상 문서의 목록 스타일이 사용되도록 보장합니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 6단계: 최종 문서 저장

마지막으로, 다음을 사용하여 목록 사용 대상 스타일 기능을 활성화하여 병합된 문서를 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### .NET용 Aspose.Words를 사용하여 목록 사용 대상 스타일에 대한 예제 소스 코드 

다음은 .NET용 Aspose.Words를 사용하는 C#의 "대상 스타일 사용 목록" 기능에 대한 전체 소스 코드입니다.


```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// 대상 문서가 끝난 후 바로 계속되도록 소스 문서를 설정합니다.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// 생성된 목록을 추적하세요.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// 대상 문서에 이 ID를 가진 목록이 이미 포함되어 있는지 확인하세요. 그렇다면 이럴 수도 있겠네요
			// 두 목록이 함께 실행되도록 합니다. 대신 원본 문서에 목록 복사본을 만드세요.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// 이 ID에 대해 새로 복사된 목록이 이미 존재합니다. 저장된 목록을 검색하세요.
				// 현재 단락에서 사용하세요.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// 이 목록의 사본을 문서에 추가하고 나중에 참조할 수 있도록 보관하십시오.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// 이 단락의 목록을 복사된 목록으로 설정합니다.
				para.ListFormat.List = currentList;
			}
		}
	}
	// 원본 문서를 대상 문서의 끝에 추가합니다.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 목록 사용 대상 스타일 기능을 성공적으로 구현했습니다. 최종 문서에는 대상 문서의 목록 스타일과 병합된 콘텐츠가 포함됩니다.