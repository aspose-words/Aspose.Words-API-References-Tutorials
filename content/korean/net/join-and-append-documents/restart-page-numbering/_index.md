---
title: 페이지 번호 매기기 다시 시작
linktitle: 페이지 번호 매기기 다시 시작
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 결합하고 추가하는 동안 페이지 번호 매기기를 다시 시작하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/restart-page-numbering/
---

이 튜토리얼은 Aspose.Words for .NET의 페이지 번호 다시 시작 기능을 사용하는 과정을 안내합니다. 이 기능을 사용하면 원본 문서에서 페이지 번호 매기기를 다시 시작하는 동안 Word 문서를 결합하고 추가할 수 있습니다.

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

## 3단계: 페이지 번호 매기기를 다시 시작하도록 원본 문서 설정

 소스 문서에서 페이지 번호 매기기를 다시 시작하려면`SectionStart` 소스 문서의 첫 번째 섹션 속성을`SectionStart.NewPage` 그리고 설정`RestartPageNumbering`재산`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## 4단계: 원본 문서를 대상 문서에 추가

 이제 다음을 사용하여 소스 문서를 대상 문서에 추가할 수 있습니다.`AppendDocument` 의 방법`Document` 수업. 그만큼`ImportFormatMode.KeepSourceFormatting` 매개변수를 사용하면 추가 작업 중에 소스 형식이 유지됩니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5단계: 최종 문서 저장

 마지막으로, 페이지 번호 매기기 다시 시작 기능을 사용하여 병합된 문서를 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### .NET용 Aspose.Words를 사용하여 페이지 번호 다시 시작에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 C#의 "페이지 번호 매기기 다시 시작" 기능에 대한 전체 소스 코드입니다.
 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 페이지 번호 다시 시작 기능을 성공적으로 구현했습니다. 최종 문서에는 원본 문서에서 다시 시작되는 페이지 번호 매기기와 함께 병합된 내용이 포함됩니다.