---
title: 새 서명란 생성 및 서명
linktitle: 새 서명란 생성 및 서명
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에서 새 서명란을 만들고 서명하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 새 서명란 기능을 만들고 서명하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서에 서명란을 삽입하고, 사용자 정의 옵션을 설정하고, 문서에 서명할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 및 생성기 만들기

Document 클래스와 DocumentBuilder 개체의 인스턴스를 만드는 것부터 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 서명란 삽입

DocumentBuilder 개체의 InsertSignatureLine() 메서드를 사용하여 문서에 새 서명란을 삽입합니다.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 3단계: 문서 저장

수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

문서를 저장하려면 올바른 경로와 파일 이름을 지정해야 합니다.

## 4단계: 문서에 서명하기

문서에 서명하려면 서명 옵션을 설정하고 DigitalSignatureUtil 클래스를 사용해야 합니다.

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

문서, 서명란 이미지, 서명된 문서에 대해 올바른 경로를 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 새 서명란을 생성하고 서명하기 위한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 새 서명란을 생성하고 서명하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 Word 문서에 새 서명란을 쉽게 만들고 서명할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 새 서명란을 만들고 서명하는 방법을 배웠습니다. 제공된 단계를 따르면 쉽게 문서에 서명란을 삽입하고 옵션을 사용자 정의하며 디지털 인증서를 사용하여 문서에 서명할 수 있습니다. 문서에 서명란과 디지털 서명을 추가하면 문서의 신뢰성과 무결성이 향상되어 더욱 안전하고 신뢰할 수 있게 됩니다. Aspose.Words for .NET은 Word 문서의 서명 및 디지털 인증서와 함께 Words 처리를 위한 강력한 API를 제공하여 서명 프로세스를 자동화하고 문서의 유효성을 보장할 수 있습니다.

### FAQ

#### Q: Word 문서의 서명란은 무엇입니까?

A: Word 문서의 서명란은 서명을 넣어야 하는 위치를 나타내는 자리 표시자입니다. 일반적으로 이름, 제목, 날짜가 포함되며 손으로 직접 쓰거나 디지털 서명을 위한 공간을 제공합니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 서명란을 어떻게 만들 수 있나요?

A: .NET용 Aspose.Words를 사용하여 Word 문서에 서명란을 만들려면 다음 단계를 따르세요.
1.  인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 물체.
2.  사용`InsertSignatureLine` 의 방법`DocumentBuilder` 문서에 새 서명란을 삽입하려면 개체를 사용하세요.
3. 수정된 문서를 저장합니다.

#### Q: 이름, 제목, 날짜 등 서명란 옵션을 맞춤 설정할 수 있나요?

 A: 예, 서명란 옵션을 사용자 정의할 수 있습니다. 그만큼`SignatureLineOptions` 클래스는 다음과 같이 원하는 옵션을 설정하는 속성을 제공합니다.`Signer`, `SignerTitle`, `ShowDate`등. 서명란을 삽입하기 전에 이러한 속성을 수정할 수 있습니다.

#### Q: 서명란을 만든 후 문서에 어떻게 서명할 수 있나요?

 A: 서명란을 생성한 후 문서에 서명하려면 서명 옵션을 설정하고`DigitalSignatureUtil` 수업. 단계는 다음과 같습니다.
1.  설정`SignatureLineId` 에 있는 재산`SignOptions` 서명란의 ID에 반대합니다.
2.  설정`SignatureLineImage` 에 있는 재산`SignOptions` 사용하려는 서명 이미지에 이의를 제기하세요.
3.  다음을 사용하여 서명 인증서를 로드합니다.`CertificateHolder` 수업.
4.  사용`DigitalSignatureUtil.Sign` 필요한 매개변수를 제공하여 문서에 서명하는 방법입니다.

#### Q: 디지털 서명 이미지를 사용하여 문서에 서명할 수 있나요?

 A: 예, 디지털 서명 이미지를 사용하여 문서에 서명할 수 있습니다. 이렇게 하려면 다음 위치에 이미지 파일을 제공해야 합니다.`SignOptions` 를 사용하는 객체`SignatureLineImage`재산. 이미지는 JPEG, PNG, EMF 등 지원되는 모든 이미지 형식일 수 있습니다.

#### Q: Word 문서에서 새 서명란을 만들고 서명하는 목적은 무엇입니까?

A: Aspose.Words for .NET을 사용하여 Word 문서에서 새 서명란을 만들고 서명하면 서명에 대한 자리 표시자를 추가한 다음 디지털 인증서를 사용하여 문서에 서명할 수 있습니다. 이 프로세스는 승인 또는 합의의 증거를 제공하여 문서의 신뢰성과 무결성을 보장합니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에서 여러 서명란을 만들고 서명할 수 있나요?

A: 예, Aspose.Words for .NET을 사용하여 Word 문서에서 여러 서명란을 만들고 서명할 수 있습니다. 각 서명란에는 고유한 ID와 옵션이 있을 수 있습니다. 문서에 추가 서명란을 만들고 서명하는 단계를 반복할 수 있습니다.

#### Q: 서명 후 서명란을 수정하거나 추가 정보를 추가할 수 있나요?

답변: 서명란에 서명하면 문서 내용의 일부가 되며 별도로 수정할 수 없습니다. 그러나 서명된 서명란 뒤에 추가 정보나 내용을 추가할 수 있습니다.

#### Q: 서명란이 포함된 문서의 디지털 서명을 확인할 수 있나요?

 A: 예, Aspose.Words for .NET은 서명란이 포함된 문서의 디지털 서명을 확인하는 기능을 제공합니다. 당신은 사용할 수 있습니다`DigitalSignatureUtil.Verify` 디지털 서명의 유효성과 진위 여부를 확인하는 방법.

#### Q: Aspose.Words for .NET은 서명란 생성 및 서명을 위해 어떤 파일 형식을 지원합니까?

A: Aspose.Words for .NET은 DOCX 파일 형식으로 서명란을 생성하고 서명하는 것을 지원합니다. 제공된 메서드와 클래스를 사용하여 DOCX 파일에 서명란을 만들고 서명할 수 있습니다.