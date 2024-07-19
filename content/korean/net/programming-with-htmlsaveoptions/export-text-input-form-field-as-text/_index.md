---
title: 텍스트 입력 양식 필드를 텍스트로 내보내기
linktitle: 텍스트 입력 양식 필드를 텍스트로 내보내기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 텍스트 입력 양식 필드를 일반 텍스트로 내보내는 단계별 안내입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 텍스트 입력 양식 필드를 일반 텍스트로 내보내는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 텍스트 입력 양식 필드를 HTML 입력 요소로 내보내는 대신 읽을 수 있는 텍스트로 내보낼 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 내보낼 문서를 로드합니다. 다음 코드를 사용하여 지정된 디렉터리에서 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 코드는`Document` 지정된 디렉토리에서 문서를 로드합니다.

## 3단계: HTML 백업 옵션 구성

이제 텍스트 입력 양식 필드를 일반 텍스트로 내보내도록 HTML 저장 옵션을 구성하겠습니다. 다음 코드를 사용하세요.

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// 지정된 폴더가 존재하고 비어 있어야 합니다.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 이 코드는`HtmlSaveOptions` 그리고`ExportTextInputFormFieldAsText` 옵션`true` 텍스트 입력 양식 필드를 일반 텍스트로 내보냅니다. 또한 추출된 이미지가 저장될 폴더를 지정합니다.

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 앞서 구성한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

이 코드는 텍스트 입력 양식 필드를 일반 텍스트로 내보내 문서를 HTML로 변환하고 내보낸 HTML 파일을 지정된 디렉터리에 저장합니다.

### .NET용 Aspose.Words를 사용하여 텍스트 입력 양식 필드를 텍스트로 내보내기의 소스 코드 예


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// 지정된 폴더는 존재해야 하며 비어 있어야 합니다.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// 양식 필드를 HTML 입력 요소가 아닌 일반 텍스트로 내보내는 옵션을 설정하십시오.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 문서 디렉토리에 대한 올바른 경로를 지정하십시오.`dataDir` 변하기 쉬운.