---
title: 일본어를 편집 언어로 추가
linktitle: 일본어를 편집 언어로 추가
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 일본어를 편집 언어로 추가하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 일본어를 편집 언어로 추가하는 기능을 단계별로 이해하고 구현하도록 안내합니다. 이 기능을 사용하면 문서를 로드할 때 언어 기본 설정을 지정하고 편집 언어로 일본어를 추가할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 기본 편집 언어가 포함되어 있지 않고 일본어를 추가하려는 Word 문서를 로드합니다. 문서를 로드하려면 다음 코드를 사용하세요.

```csharp
LoadOptions loadOptions = new LoadOptions();

// 문서를 로드할 때 사용할 언어 기본 설정을 지정합니다.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## 3단계: 기본 언어 확인하기

문서를 로드한 후 기본 편집 언어가 일본어로 올바르게 설정되었는지 확인합니다. 극동 언어 ID를 얻으려면 다음 코드를 사용하십시오.

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

코드는 극동 언어 ID가 일본어 ID와 일치하는지 확인합니다. 결과에 따라 해당 메시지가 표시됩니다.

### .NET용 Aspose.Words를 사용하여 편집 언어로 일본어 추가에 대한 예제 소스 코드

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// 문서를 로드할 때 사용할 언어 기본 설정을 지정합니다.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

