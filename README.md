# colab
구글 코랩(Google Colab) 초보자 사용 설명서
1. 구글 코랩이란?

구글 코랩(Google Colaboratory)은 웹 브라우저에서 파이썬(Python) 코드를 작성하고 실행할 수 있는 클라우드 기반 개발 환경입니다.

주요 특징
별도의 파이썬 설치 없이 사용 가능
인터넷 브라우저에서 실행
무료 CPU 및 제한적인 GPU 사용 가능
구글 드라이브와 연동 가능
데이터 분석 및 인공지능 학습에 활용 가능

접속 주소: https://colab.research.google.com/

2. 코랩 시작하기
구글 코랩 홈페이지에 접속합니다.
구글 계정으로 로그인합니다.
상단 메뉴에서 파일을 선택합니다.
새 노트를 클릭합니다.
새로운 코딩 화면이 나타납니다.

노트북 이름은 화면 상단에서 변경할 수 있습니다.

예시: 나의 첫 번째 코랩 실습.ipynb

3. 코랩 화면 구성
메뉴	기능
코드 셀	파이썬 코드 작성
실행 버튼(▶)	코드 실행
+ 코드	새로운 코드 셀 추가
+ 텍스트	설명 및 제목 작성
런타임	실행 환경 설정
파일	파일 업로드 및 관리
목차	노트북의 제목과 구조 확인
셀(Cell)이란?

코랩은 코드를 셀 단위로 작성하고 실행합니다.

코드 셀: 파이썬 코드를 작성하는 공간
텍스트 셀: 설명이나 메모를 작성하는 공간
4. 파이썬 코드 실행하기
실습 1. 화면에 글자 출력하기
python
print("안녕하세요!")
print("코랩 공부를 시작합니다.")


실행 결과:

text
안녕하세요!
코랩 공부를 시작합니다.


코드 실행 방법:

셀 왼쪽의 실행 버튼 클릭
Shift + Enter 키 누르기
실습 2. 숫자 계산하기
python
a = 10
b = 20

print(a + b)  # 덧셈
print(a - b)  # 뺄셈
print(a * b)  # 곱셈
print(a / b)  # 나눗셈


결과:

text
30
-10
200
0.5

실습 3. 변수 사용하기
python
name = "홍길동"
age = 25

print("이름:", name)
print("나이:", age)

5. 파이썬 기본 문법
문법	설명	예시
print()	화면 출력	print("Hello")
변수	데이터 저장	a = 10
list	여러 데이터 저장	[1, 2, 3]
if	조건문	if a > 10:
for	반복문	for i in range(5):
def	함수 정의	def hello():
import	라이브러리 불러오기	import pandas
반복문 예제
python
for i in range(5):
    print(i)

조건문 예제
python
score = 85

if score >= 80:
    print("합격입니다.")
else:
    print("불합격입니다.")

함수 예제
python
def greeting(name):
    print(name + "님 안녕하세요!")

greeting("홍길동")

6. 파일 업로드하기

코랩에서는 컴퓨터에 저장된 파일을 업로드할 수 있습니다.

방법 1. 화면에서 업로드
왼쪽 사이드바에서 폴더 아이콘 클릭
파일 업로드 버튼 클릭
컴퓨터에서 파일 선택
방법 2. 코드로 업로드
python
from google.colab import files

uploaded = files.upload()


CSV, 엑셀, 이미지 등 필요한 파일을 업로드할 수 있습니다.

파일 다운로드하기
python
from google.colab import files

files.download("파일이름.csv")

7. 구글 드라이브 연결하기

구글 드라이브를 연결하면 파일을 지속적으로 저장하고 불러올 수 있습니다.

드라이브 연결 코드
python
from google.colab import drive

drive.mount('/content/drive')


실행 후 권한 승인 절차를 진행합니다.

CSV 파일 읽기
python
import pandas as pd

df = pd.read_csv(
    '/content/drive/MyDrive/data.csv'
)

print(df.head())

엑셀 파일 읽기
python
import pandas as pd

df = pd.read_excel(
    '/content/drive/MyDrive/data.xlsx'
)

print(df.head())

8. 데이터 분석하기

코랩은 데이터 분석에 매우 유용합니다.

주요 라이브러리
라이브러리	기능
NumPy	수치 계산
Pandas	데이터 분석
Matplotlib	그래프 작성
Seaborn	통계 시각화
Scikit-learn	머신러닝
데이터 분석 실습
python
import pandas as pd

data = {
    '이름': ['철수', '영희', '민수'],
    '점수': [80, 90, 75]
}

df = pd.DataFrame(data)

print(df)

print("평균 점수:", df['점수'].mean())

자주 사용하는 Pandas 명령어
python
df.head()       # 처음 5개 데이터
df.tail()       # 마지막 5개 데이터
df.info()       # 데이터 정보
df.describe()   # 기초 통계
df.shape        # 행과 열 개수
df.columns      # 열 이름
df.isnull().sum()  # 결측치 확인

9. 그래프 그리기

Matplotlib을 이용하면 데이터를 그래프로 표현할 수 있습니다.

python
import matplotlib.pyplot as plt

names = ['철수', '영희', '민수']
scores = [80, 90, 75]

plt.bar(names, scores)

plt.title('학생별 점수')
plt.xlabel('이름')
plt.ylabel('점수')

plt.show()

10. 코랩 단축키
단축키	기능
Shift + Enter	셀 실행 후 다음 셀 이동
Ctrl + Enter	현재 셀 실행
Alt + Enter	실행 후 아래 새 셀 추가
Ctrl + M, A	위에 셀 추가
Ctrl + M, B	아래에 셀 추가
Ctrl + M, D	셀 삭제
Ctrl + S	저장
11. 런타임 이해하기

런타임(Runtime)은 파이썬 코드가 실제로 실행되는 컴퓨터 환경입니다.

실행 환경 종류
종류	용도
CPU	일반적인 파이썬 실행
GPU	인공지능 및 딥러닝 연산
TPU	특정 머신러닝 연산
주의사항
일정 시간 사용하지 않으면 연결이 끊길 수 있습니다.
런타임이 초기화되면 변수와 임시 파일이 사라질 수 있습니다.
중요한 데이터는 구글 드라이브에 저장하세요.
GPU는 사용량과 제공 시간이 제한될 수 있습니다.
12. 코랩 학습 로드맵
1주 차: 코랩 기초
코랩 접속 및 노트북 만들기
코드 셀 실행하기
print()와 변수 사용하기
숫자 계산하기
파일 저장 및 다운로드
2주 차: 파이썬 기초
리스트와 딕셔너리
조건문과 반복문
함수 만들기
문자열 다루기
3주 차: 데이터 분석
Pandas 기초
CSV 및 엑셀 파일 읽기
데이터 정리
통계 분석
그래프 그리기
4주 차: 인공지능 기초
NumPy 기초
머신러닝 개념
Scikit-learn 실습
간단한 예측 모델 만들기
13. 종합 실습

다음 코드를 실행하면 변수, 리스트, 계산, 출력, 조건문을 한 번에 연습할 수 있습니다.

python
# 1. 이름 입력
name = "홍길동"

# 2. 점수 저장
scores = [80, 90, 85, 95, 70]

# 3. 평균 계산
average = sum(scores) / len(scores)

# 4. 결과 출력
print("이름:", name)
print("점수:", scores)
print("평균:", average)

# 5. 합격 여부 확인
if average >= 80:
    print("합격입니다!")
else:
    print("불합격입니다.")

14. 초보자가 자주 겪는 문제
문제 1. 코드가 실행되지 않아요.
실행 버튼을 눌렀는지 확인합니다.
런타임이 연결되어 있는지 확인합니다.
코드의 괄호와 따옴표가 올바른지 확인합니다.
문제 2. 파일을 찾을 수 없어요.
파일 이름이 정확한지 확인합니다.
파일이 업로드되어 있는지 확인합니다.
파일 경로가 올바른지 확인합니다.
문제 3. 라이브러리가 없다고 나와요.

필요한 경우 다음과 같이 설치합니다.

python
!pip install pandas

문제 4. 실행 결과가 이상해요.
셀 실행 순서를 확인합니다.
변수가 올바르게 지정되었는지 확인합니다.
필요한 셀을 다시 실행합니다.
15. 유용한 사이트
사이트	설명
Google Colab	코딩 실습
Python 공식 홈페이지	파이썬 정보
Python 공식 튜토리얼	파이썬 문법 학습
Pandas 공식 문서	데이터 분석
Matplotlib 공식 문서	그래프 작성
마무리

코랩을 처음 배우는 사람은 다음 순서로 공부하는 것이 좋습니다.

코랩 화면과 셀 사용법 익히기
파이썬 기본 문법 배우기
파일 업로드와 구글 드라이브 연결하기
Pandas를 활용한 데이터 분석
그래프 작성하기
머신러닝과 인공지능 실습하기

가장 중요한 학습 방법은 직접 코드를 입력하고 실행해 보는 것입니다.

하루 20~30분씩 꾸준히 실습하면 코랩의 기본 사용법을 익히는 데 큰 도움이 됩니다.
