# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 홍수정
- 리뷰어 : 최지수

# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
      퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부
          
- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
  주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.

- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
  ”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 네. 다양한 프롬프트를 시도해서 모델의 반응을 다양하게 보여주셨습니다.
       
- [X]  **4. 회고를 잘 작성했나요?**
    - 네. 프롬프트 엔지니어링을 하시면서 특정 배경 이미지를 가지고 오는 원인이나 이유에 대해서 많은 고민을 하신 것 같습니다.
    
- [X]  **5. 코드가 간결하고 효율적인가요?**
      - 수정님! 파이썬에
       * isort: import 한 프로젝트 패키지 순서를 알맞게 재배열
       * flake 또는 black: 코드를 pep8을 준수 할 수 있도록 자동으로 수정해줍니다.  
         flake는 제안을 해주고 따로 옵션을 줘야 코드상에 반영되는데  
         black의 경우는 바로 코드에 적용을 해줍니다. 보통 black을 다른 개발환경에서 많이 지원해줍니다!

# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```

# 회고
액자라는 단어가 들어가지 않았는데 배경에 계속 액자 사진을 삽입하는 것이 아마 paint라는 단어 벡터가 액자에 걸린
이미지를 많이 학습해서 나온 벡터라 그런 것이 아닌가 하였습니다. 만약에 중의적인 문장으로 프로픔트 엔지니어링을 하면
간접적으로 모델에 어떤 데이터가 주로 학습되었는지 유추해볼 수 있을 것 같습니다.

또, NLP에서처럼 매니폴드 공간 상에서 이미지가 가시화된 형태로 맵을 그리면 재밌는 인사이트를 얻을 수 있을 것 같습니다.