---
title: 테이블 위치 가져오기
linktitle: 테이블 위치 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 표의 위치를 얻는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/get-table-position/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 표의 위치를 얻는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에서 테이블 위치 지정 속성을 얻을 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드 및 테이블 액세스
테이블로 단어 처리를 시작하려면 해당 테이블이 포함된 문서를 로드하고 액세스해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Tables.docx");

// 어레이에 대한 액세스
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오. 또한 문서에 원하는 위치의 테이블이 포함되어 있는지 확인하십시오.

## 3단계: 배열 위치 지정 속성 가져오기
다음으로 배열의 위치 지정 유형을 확인하고 적절한 위치 지정 속성을 가져옵니다. 다음 코드를 사용하세요.

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 여기서는 배열이 float 유형인지 확인하기 위해 조건을 사용합니다. 그렇다면 우리는`RelativeHorizontalAlignment` 그리고`RelativeVerticalAlignment` 테이블의 상대적 수평 및 수직 정렬을 가져오는 속성입니다. 그렇지 않으면 우리는`Alignment` 배열 정렬을 가져오는 속성입니다.

### .NET용 Aspose.Words를 사용하여 테이블 위치 가져오기의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 표의 위치를 얻는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서에서 프로그래밍 방식으로 테이블 위치 지정 속성을 얻을 수 있습니다. 이 기능을 사용하면 특정 위치에 따라 배열을 분석하고 조작할 수 있습니다.