## AWS 배포 사이트 : https://www.petmemoir.site/  <sub>(최신화된 url)</sub>
![notion용](https://github.com/sonincheon/Doggo-frontend/assets/142462485/c23a0c72-e634-4726-a5ac-dff07aef02aa)
---
## 김현빈 담당 기능 요약 ##


1. 로그인 페이지
  - 일반 회원 / 카카오 로그인 기능 구현
  - 로그인 시도 시, 기존 데이터베이스에 존재하는 아이디와 패스워드가 일치하고,
    이를 통해 AccessToken과 RefreshToken이 정상적으로 받아와지면 로그인 완료
  - 아이디나 비밀번호가 유효하지 않거나 입력되지 않았을 때, 오류 메시지 출력
  - 카카오 로그인 시, "카카오 로그인 중입니다..." 화면이 출력,
    useSearchParams를 이용하여 URL에 담긴 카카오 로그인 토큰을 받아옴
  - 해당 토큰을 이용하여 카카오 OAuth를 통해 사용자를 인증함
  - 인증 후, 받아오는 카카오 이메일과 사용자의 고유한 ID 값을 각각
    아이디, 비밀번호로 이용하여 회원가입 및 로그인 진행
    
2. 회원가입 페이지
  - 아이디(이메일) 입력 시, 기존 데이터베이스에 존재하는 아이디값들로 중복 확인
  - 가입 가능한 아이디일 시, 해당 아이디(이메일)로 무작위 인증번호 전송
  - MailSender를 이용하여 설정된 이메일, 이름, 전송 내용 양식에 맞추어
    알파벳과 숫자의 무작위 조합으로 인증번호를 생성하여 전송
  - 인증 완료 시, 사용할 패스워드와 사용자의 개인정보 (이름, 생년월일, 성별, 전화번호, 주소)를
    입력, 필수 약관 동의 후 회원가입 완료
  - 아이디(이메일)는 이메일 형식, 패스워드 (알파벳, 숫자, 특수기호 조합으로 8자리 이상) 형식에
    맞춰서 유효성 검사 진행, 유효하지 않으면 회원가입 불가, 입력 부분 하단에 각각
    "이메일 형식으로 입력해주세요 (example@email.com)", "숫자+영문자+특수문자 조합으로 8자리 이상 입력해주세요!"
    메시지 출력됨, 유효한 값 입력 시, 각각 "올바른 형식입니다." 메시지 출력됨
  - 생년월일은 DatePicker를 사용하여 년, 월, 일 선택, 주소는 DaumPost API를 사용하여 주소 입력

3. 아이디 찾기 / 비밀번호 변경 페이지
  - 가입된 이름과 전화번호를 입력하면 해당 정보에 맞는 아이디(이메일)를 일부가 가려진 채로 출력하여 알려줌
  - 가입된 아이디(이메일)와 해당 이메일로 전송된 인증번호(MailSender)를 입력하여 인증 시,
    새로운 비밀번호로 변경 가능


4. 마이페이지 (내 정보, 반려동물 정보)
  - 수정하려는 내 정보 (프로필 사진, 생년월일, 주소, 전화번호, 비밀번호)에 맞추어 모달을 띄우고
    해당 모달을 통해 각각의 요소에 해당하는 정보 수정
  - Common.TakenToken을 사용하여 이메일이 담긴 토큰을 호출, 로그인한 사용자의 이메일 정보를 받아오고
    해당 사용자의 정보를 입력받는 type에 따라 수정하려는 요소를 인식, 이를 통해 내 정보 페이지에서 원하는
    요소를 골라 해당 요소만 수정할 수 있음
  - 정보 수정 메서드는 사용자의 모든 정보 (프로필 사진, 생년월일, 주소, 전화번호, 비밀번호)를
    업데이트 하는데, 수정하고 싶은 요소만 수정시키기 위해 수정(업데이트)하려는 값 이외의
    다른 값들은 (null인 경우) 해당 값들을 업데이트 하지 않음

## 확인사항

- PETMEMOIR 프론트엔드 (https://github.com/PANG2OPPA/PETMEMOIR_Frontend)

- PETMEMOIR 백엔드 (https://github.com/PANG2OPPA/PETMEMOIR_Backend)

- PETMEMOIR 플라스크 (https://github.com/PANG2OPPA/PETMEMOIR_Flask)

- PETMEMOIR 통합 (https://github.com/PANG2OPPA/PETMEMOIR_Totals)

- PETMEMOIR 모바일 (https://github.com/PANG2OPPA/PETMEMOIR_Expo_Mobile)

인사담당관님의 피드백을 환영합니다!
