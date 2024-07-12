---
title: 부동 테이블 위치 가져오기
linktitle: 부동 테이블 위치 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 부동 테이블의 위치를 얻는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/get-floating-table-position/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 부동 테이블의 위치를 얻는 방법을 알아봅니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에서 부동 테이블의 위치 지정 속성을 얻을 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드 및 테이블 액세스
표로 단어 처리를 시작하려면 표가 포함된 문서를 로드하고 액세스해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오. 또한 문서에 부동 테이블이 포함되어 있는지 확인하세요.

## 3단계: 부동 테이블 위치 지정 속성 가져오기
다음으로 문서의 모든 테이블을 반복하여 부동 테이블 위치 지정 속성을 가져옵니다. 다음 코드를 사용하세요.

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// 배열이 부동 유형인 경우 위치 지정 속성을 인쇄합니다.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 여기서 우리는`foreach` loop는 문서의 모든 배열을 반복합니다. 우리는 배열이 부동 소수점 유형인지 확인합니다.`TextWrapping` 재산. 그렇다면 수평 앵커, 수직 앵커, 절대 수평 및 수직 거리, 겹침 허용, 절대 수평 거리 및 수직 정렬 상대와 같은 테이블의 위치 지정 속성을 인쇄합니다.
 
### .NET용 Aspose.Words를 사용하여 부동 테이블 위치 가져오기의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// 테이블이 부동 유형인 경우 위치 지정 속성을 인쇄합니다.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 부동 테이블의 위치를 얻는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서에서 부동 테이블의 위치 지정 속성을 프로그래밍 방식으로 가져올 수 있습니다. 이 기능을 사용하면 특정 요구 사항에 따라 부동 테이블을 분석하고 조작할 수 있습니다.