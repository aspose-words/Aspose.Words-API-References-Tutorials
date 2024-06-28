---
title: 페이지 레이아웃 업데이트
linktitle: 페이지 레이아웃 업데이트
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 결합하고 추가할 때 페이지 레이아웃을 업데이트하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/update-page-layout/
---

이 튜토리얼은 Aspose.Words for .NET의 페이지 레이아웃 업데이트 기능을 사용하는 과정을 안내합니다. 이 기능을 사용하면 Word 문서를 결합하고 추가할 때 페이지 레이아웃이 올바르게 업데이트됩니다.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3단계: 대상 문서의 페이지 레이아웃 업데이트

 소스 문서를 추가하기 전에 페이지 레이아웃이 올바르게 업데이트되었는지 확인하려면`UpdatePageLayout` 대상 문서의 메서드입니다.

```csharp
dstDoc.UpdatePageLayout();
```

## 4단계: 원본 문서를 대상 문서에 추가

 이제 다음을 사용하여 소스 문서를 대상 문서에 추가할 수 있습니다.`AppendDocument` 의 방법`Document` 수업. 그만큼`ImportFormatMode.KeepSourceFormatting` 매개변수를 사용하면 추가 작업 중에 소스 형식이 유지됩니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5단계: 페이지 레이아웃 다시 업데이트

 소스 문서를 추가한 후`UpdatePageLayout`추가 작업 이후의 모든 변경 사항이 렌더링된 출력에 반영되는지 확인하기 위해 대상 문서에 메서드를 다시 적용합니다.

```csharp
dstDoc.UpdatePageLayout();
```

## 6단계: 최종 문서 저장

 마지막으로, 페이지 레이아웃 업데이트 기능을 활성화한 상태로 병합된 문서를 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### .NET용 Aspose.Words를 사용하는 업데이트 페이지 레이아웃의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 C#의 "페이지 레이아웃 업데이트" 기능에 대한 전체 소스 코드입니다.

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// 대상 문서가 PDF, 이미지 등으로 렌더링되는 경우
	// 또는 UpdatePageLayout이 소스 문서보다 먼저 호출됩니다. 첨부되어 있으며,
	// 이후에 변경된 사항은 렌더링된 출력에 반영되지 않습니다.
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// 변경 사항을 렌더링된 출력으로 업데이트하려면 UpdatePageLayout을 다시 호출해야 합니다.
	// 다시 호출하지 않으면 추가된 문서는 다음 렌더링의 출력에 나타나지 않습니다.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 페이지 레이아웃 업데이트 기능을 성공적으로 구현했습니다. 최종 문서에는 페이지 레이아웃이 올바르게 업데이트된 병합된 콘텐츠가 포함됩니다.