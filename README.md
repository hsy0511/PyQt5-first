# PyQt5-first
# PyQt5 사용방법
## 1. 파이썬과 아나콘다를 설치한다.
파이썬 설치 자료 : https://wikidocs.net/8

아나콘다 설치 자료 : https://wikidocs.net/22896

## 2. 파이썬, 아나콘다 설치확인

- 파이썬 설치확인

cmd 창에서 python을 입력했을 때 파이썬 버전이 뜨면 설치가 완료된 것이다.

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/1dd78118-30a4-4fc5-8ee7-25e5af943e7f)

- 아나콘다 설치확인

윈도우 검색창에 anaconda prompt를 검색했을 때 나오면 설치가 완료된 것이다.

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/a087e406-f15c-4dd2-8d6c-cf67d94de57e)

## 3. PyQt5 설치 및 설치 확인
anaconda prompt 창에서 (파이썬 버전3 기준) pip3 install PyQt5를 입력하여 설치한다.

설치 후 한번더 했을 때

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/5c29b870-c2ee-4165-90ee-b4732584732e)

이렇게 나오면 이미 설치가 되어있는 것이다.

## QT 디자이너 사용법 (파이썬과 연동하여 hello world 출력)
PyQt를 설치를 하였으니 QT 디자이너가 있는 경로로 이동하여 디자이너를 실행한다.

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/5720f3e1-d829-457d-942b-270c82d19ccc)

실행시키면 이런창이 나오는데 여기서 Main Window로 폼을 만든다. (이유는 딱히 없다)

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/11e70c3a-842e-4686-89c1-04f5e59f3917)

폼을 만들고 그 안에 input widgets에 있는 Plain Text Edit를 생성한다.

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/f27e849c-6c25-44bb-aac4-78be581bd36a)

그리고 text 박스 끝을 잡아당겨서 크게 만든 후 더블클릭을 이용하여 hello world를 입력한다.

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/81826568-9ad5-4b6d-aa49-390e529da5a4)

이제 저장을 하는데 저장 단축키는 ctrl + s이다. 

저장은 연습용이라는 폴더에 hello라고 저장하겠다.

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/6c34a407-78db-465c-97e2-9cda538a4d28)

저장을 시킨 후 연습용 폴더에 같은 이름으로 파이썬 파일을 만든다. (vs코드에서 실행)

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/ddbfb8a0-2644-4620-b124-e1bc0fe31dce)

파일 생성 후 파이썬 파일에 hello.ui와 연결하는 코드를 작성한다.

```python
import sys
from PyQt5.QtWidgets import *
from PyQt5 import uic
// 디자이너에 사용되는 위젯에 모든 라이브러리를 가져온다.
// ui파일을 클래스 파일로 사용할 수 있게 해주는 라이브러를 uic도 가져온다.


form_class = uic.loadUiType("C:\\Users\\MOA\\Desktop\\QtDesigner\\연습용\\hello.ui")[0]
// ui 파일 경로를 가져와서 uic.loadUiType 함수에 넣게 되면 ui파일을 클래스 파일로 사용할 수 있게된다.
class WindowClass(QMainWindow, form_class):
    def __init__(self):
// init에 self에는 인스턴스 자체가 전달되어 있어 메소드 내에 인스턴스 변수 작성, 참고가 가능해진다.
        super().__init__()
// 부모클래스를 상속시킨다.
        self.setupUi(self)
// 연결한 ui파일을 준비한다.

app = QApplication(sys.argv)
// pyqt를 실행한다.
mainWindow = WindowClass()
mainWindow.show()
app.exec_()

# __init__()
- 컨스트럭터라고 불리는 최기화를 위한 함수(메소드)
- 인스턴스화를 실시할 때 반드시 처음에 호출되는 특수한 함수
- 오브젝트 생성(인스턴스를 생성)과 관련하여 데이터의 초기를 실시하는 함수
```

![image](https://github.com/hsy0511/PyQt5-first/assets/104752580/d0e55d43-d7f3-4161-8f93-22714effeec2)

이렇게 pyqt5 사용법을 알아보았다.
