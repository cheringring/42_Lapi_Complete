Exercise 00: Z 파일 생성

목적: Unix 파일 시스템 기본 조작

    핵심 기술: echo 명령어를 통한 파일 생성, 리다이렉션(>), 실행 권한 부여(chmod 755)

    평가 포인트: 파일 내용 정확성, 권한 설정(755), 파일 이름(z)

    실수 방지: 공백 없이 echo "Z" > z 실행, ls -l로 권한 확인

Exercise 01: testShell00

목적: 타임스탬프/권한 제어

    요구 사항:

        2024년 6월 1일 23:42 타임스탬프(touch -t 202406012342)

        455 권한(r--r-xr-x)

        40바이트 크기

    검증 방법: tar -tvf testShell00.tar로 압축 내용 확인

Exercise 02: 디렉토리 구조

목적: 복합 권한 설정

    계층 구조:

    bash
    test0(drwx--xr-x), test1(-rwx--xr--), 
    test2(dr-x-wxr--), test3(-rw-r----x)

    숫자 변환 공식:
    r=4, w=2, x=1 조합 사용 (예: 715 = rwx--xr-x)

Exercise 03: SSH

목적: 원격 시스템 제어

    핵심 단계:

        ED25519 키 생성(ssh-keygen -t ed25519)

        공개키 복사(ssh-copy-id)

        타임스탬프 획득(date +%s)

Exercise 04: midLS

목적: 파이프라인 활용

    데이터 처리 흐름:
    ls -t → head -n 3 → sort -r

    핵심 옵션: 시간 역순 정렬(-t), 결과 제한(head), 재정렬(sort -r)

Exercise 05: GiT commit

목적: 버전 관리 기초

    표준 절차:
    init → add → commit → log 포맷팅

    검증 키: 커밋 해시(%H)의 유일성

Exercise 06: gitignore

목적: 프로젝트 관리

    필터 패턴:

    text
    # Vim 임시 파일
    *.[swp|swo]
    # macOS 시스템 파일
    .DS_Store

Exercise 07: diff

목적: 파일 비교 기술

    출력 최적화:
    diff -u로 유니파이드 포맷 → tail -n +3으로 헤더 제거

Exercise 08: clean

목적: 시스템 정리 자동화

    find 명령 패턴:

    bash
    find . \( -name "*~" -o -name "*.swp" \) -delete

    -o(OR) 연산자로 다중 패턴 처리

Exercise 09: 파일 링크

목적: inode 이해

    링크 유형:

        Hard link: 동일 inode(ln test0 test7)

        Symbolic: 포인터 생성(ln -s test0 test6)
