---
title: 테이블 주변 텍스트 사이의 거리 가져오기
linktitle: 테이블 주변 텍스트 사이의 거리 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 텍스트와 표 사이의 거리를 계산하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 테이블에서 주변 텍스트 사이의 거리를 구하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블과 주변 텍스트 사이의 다양한 거리에 액세스하는 방법을 알게 됩니다.

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 여기에 Word 문서가 있는 곳입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 기존 문서 로드
 다음으로 기존 Word 문서를 인스턴스로 로드해야 합니다.`Document` 수업.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## 3단계: 표와 주변 텍스트 사이의 거리 확인
 표와 주변 텍스트 사이의 거리를 얻으려면 다음을 사용하여 문서의 표에 액세스해야 합니다.`GetChild()` 방법과`NodeType.Table` 재산. 그런 다음 배열 속성을 사용하여 다양한 거리를 표시할 수 있습니다.`DistanceTop`, `DistanceBottom`, `DistanceRight`그리고`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### .NET용 Aspose.Words를 사용하여 테이블 주변 텍스트 사이의 거리 얻기에 대한 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 테이블에서 주변 텍스트 사이의 거리를 얻는 방법을 배웠습니다. 이 단계별 가이드를 따르면 Word 문서에서 표와 주변 텍스트 사이의 다양한 거리에 쉽게 액세스할 수 있습니다. Aspose.Words는 문서의 표를 조작하고 서식을 지정하기 위한 강력하고 유연한 API를 제공합니다. 이러한 지식을 바탕으로 텍스트와 관련된 테이블 레이아웃을 분석하고 특정 요구 사항을 충족할 수 있습니다.