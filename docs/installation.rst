.. _installation:

설치하기
============

Flask는 `Werkzeug
<http://werkzeug.pocoo.org/>`_ 와 `Jinja2 <http://jinja.pocoo.org/2/>`_ 
라이브러리에 의존적이다. Werkzeug는 웹어플리케이션과 다양한 서버 사이의 
개발과 배포를 위한 표준 파이썬 인터페이스인 WSGI를 구현한 툴킷이다.
Jinja2 는 HTML 템플릿을 렌더링 하는 템플릿엔진이다.

여러분은 어떻게 여러분의 컴퓨터에 Flask와 관련된 모든 것들을 빠르게 
얻을 수 있을까? 선택할 수 있는 방법은 여러가지가 있으나 가장 강력한 
방법은 virtualenv을 사용하는 것이다. 그래서 먼저 virtualenv를 살펴보려 한다.

 
Flask 설치를 시작하기 위해 파이썬 2.6 또는 상위 버전을 사용할 것이다. 
그래서 최신 파이썬 2.x버전이 설치되어 있는 것을 확인해라. 
파이썬 3으로 Flask를 이용하려면 'Python 3 Support<http://flask.pocoo.org/docs/0.10/python3>'_를 참고해라.

.. _virtualenv:

virtualenv
----------

virtualenv는 아마도 당신이 개발 과정에서 꼭 사용해야만 하는 툴일것이다.
만약 당신이 운영서버에 쉘(shell) 환경에서 접속해야 하고 다양한 파이썬실행
환경이 필요하다면 유용하게 사용할 수 있는 툴이다.

virtualenv는 어떤 문제를 해결해 줄 수 있는가? 만약 당신이 나처럼 Python을
많이 사용하고 있고 Flask 기반의 웹 어플리케이션과 같이 현재 사용하고 있는
것과 다른 파이썬 환경을 사용해야 한다면 virtualenv를 사용해 볼 수 있는 좋은 
기회가 될 수 있다. 게다가 당신이 진행하고 있는 더 많은 프로젝트들이 서로 다른
Python 버전에서 작동해야 한다거나 혹은 서로 다른 버전의 Python 라이브러리들
에서 작동해야 한다면 어떨까? 현실을 직시해보자! 많은 라이브러리들은 종종 
하위버전 호환성들을 깨뜨린다. 그리고 어떤 심각한 응용프로그램이라 하더라도 
라이브러리와 의존관계가 없을 수는 없다. 그렇다면 두개 혹은 더 많은 당신의 
프로젝트들의 의존관계의 충돌을 해결하기 위해서 무엇을 할것인가?


Virtualenv가 당신을 구해 줄것이다. virtualenv를 이용하여 Python을 아무런 문제
없이 각각의 프로젝트 환경에 맞게 다중설치가 가능하도록 해준다. 이방법은 실제로 
독립된 버전의 Python 실행 환경에 단순히 복사하는 것이 아니라 서로 다른 프로젝트
환경이 독립적으로 실행 환경을 명백하게 가져갈 수 있도록 격리 시키는 방법이다.
이제 virtualenv가 어떻게 작동하는지 알아보자!



만약 당신이 Mac OS X 혹은 Linux 환경이라면, 다음의 두가지 명령어로 virtualenv를
작동시킬 수 있다::

    $ sudo easy_install virtualenv

혹은 좀더 나은 방법으로::

    $ sudo pip install virtualenv


위의 방법을 사용하면 당신의 시스템에 virtualenv가 설치 될걸이다. 아마도 당신의
시스템에서 사용하는 package manager를 사용할 수 도 있다. 
만약 당신이 우분투를 사용한다면 ::

    $ sudo apt-get install python-virtualenv

만약 당신이 Windows 를 사용하고 있거나 `easy_install` 명령어를 가지고 있지 않다면, 
명령어를 먼저 설치해야 한다.  :ref:`windows-easy-install` 을 확인하여 설치 방법에 대한 자세한 
정보를 확인할 수 있다. easy_install이 설치가 완료되면 위와 같은 방법으로 명령어를 실행하여
virtualenv를 설치할 수 있다. 다만, Windows 환경에서는 `sudo` 가 필요없다.



일단 virtualenv가 설치되었다면, 쉘을 실행시키고 자신만의 실행환경을 만들 수 있다.
나는 보통 프로젝트 폴더를 만들고 폴더안에서  `venv` 를 이용하여 다음과 같이 작업한다.
 ::

    $ mkdir myproject
    $ cd myproject
    $ virtualenv venv
    New python executable in venv/bin/python
    Installing distribute............done.


이제, 당신이 해당 프로젝트에서 작업하고 싶을 때마다, 그에 해당하는
실행환경을 활성화 시킬 수 있다. OS X혹은 Linux 환경이라면 다음과 같이
실행한다.::

    $ . venv/bin/activate

만약 당신이 Windows 사용자라면, 다음과 같이 실행한다.::

    $ venv\scripts\activate

어떤 방식이든, 당신은 이제 virtualenv 를 사용할 수밖에 없을 것이다.
(virtualenv이 활성화된 상태를 보여주기 위핸 당신의 쉘 프롬프트가 어떻게 변화 
되는지 주목하라).

그리고 만약 원래 실행환경으로 돌아가고 싶다면, 다음과 같이 실행한다.::

    $ deactivate

이제 당신은 다음의 명령어를 입력하여 활성화된 virtualenv 를 통해 Flask를 
설치할 수 있다.::

    $ pip install Flask

몇초동안만 기다리면 설치가 완료 된다.


시스템 전체에 적용하여 설치
------------------------

이 방법이 가능하긴 하지만, 추천하지는 않겠다.
단지 루트(root)권한을 이용하여 `pip` 를 실행시키면 된다.::

    $ sudo pip install Flask

(Windows 시스템에서는 , 위 명령어를 명령어 프롬프트에서 관리자(administrator) 권한으로
실행시키면 된다. 그리고 `sudo` 는 생략하자.)


위태로운 모험 하기
------------------

만약 당신이 가장 최신버전의 Flask를 이용하여 작업을 하고 싶다면, 
두가지 방법이 있다.: `pip` 를 이용하여 작업환경으로 Flask의 개발중 버전을  가져오거나,
git checkout을 사용할 수 있다. 어떤 방법을 사용하든, virtualenv의 사용을 추천한다.

새로운 virtualenv를 만들고 git checkout을 실행하여 개발모드의 Flask를 실행할 수 있다.::

    $ git clone http://github.com/mitsuhiko/flask.git
    Initialized empty Git repository in ~/dev/flask/.git/
    $ cd flask
    $ virtualenv venv --distribute
    New python executable in venv/bin/python
    Installing distribute............done.
    $ . venv/bin/activate
    $ python setup.py develop
    ...
    Finished processing dependencies for Flask

이 방법을 통해 의존관계에 있는 것들을 가져오게 되고 git에 등록된 현재버전을
virtualenv안으로 가져오게 된다. 그다음에 ``git pull origin`` 을 통하여 최신
버전으로 업데이트가 가능하다. 

.. _windows-easy-install:


Windows에서의 `pip` 와 `setuptools`
-----------------------------------

어쩔때는 *pip*, *setuptools*나 *virtualenv* 같은 파이썬 패키징 도구 설치가 조금 복잡해 보인다. 하지만 그래도 그리
어렵지 않다. 필요한 두 개의 중요한 패키지는 setuptools과 pip이다. 이것들은 virtualenv와 같은 다른것들을 설치할 수 있게 해준다. 다행이도 이를 설치하기 위해 실행할 수 있는 두 개의 "부트스트랩 스크립트"가 있다.

둘 다 가지고 있지 않다면 'get-pip.py'가 당신의 컴퓨터에 이들을 둘 다 설치해 줄 것이다(ez_setup.py를 실행하지 않아도 된다).

'get-pip.py'_

최근 setuptools를 설치하고 싶다면 그 부트스트랩 파일을 이용할 수 있다.

'ez_setup.py'_

다운로드를 한 후에 더블클릭을 해라. 만약 이미 pip가 있다면, 다음과 같이 실행하여 업그레이드 할 수 있다.

    > pip install --upgrade pip setuptools

대부분의 경우, 명령 프롬프트를 키고 :command:`pip`와 :command:`python`을 칠 수 있기를 원하지만
Windows에서는 수행되지 않을 것이다. 윈도우는 어디에 실행파일이 있는지 모르기 때문이다(시도해 볼 수는 있다!)

이 문제를 해결하려면, 당신은 파이썬 설치 폴더로 이동할 수 있어야 한다(예 :file:`C:\Python27`), 그리고 :file:`Tools`, :file:`Scripts`로 이동하여 :file:`win_add2path.py` 파일을 찾아 실행한다. **새** 명령 프롬프트를 켜고 :command:`python` 입력으로 인터프리터를 불러올 수 있는지 확인한다.

마지막으로, 아래와 같이 실행하여 `virtualenv`_를 간단하게 설치할 수 있다.

    > pip install virtualenv

위의 설치 지침을 따랐으면 이제 갈 길을 가면 된다.

.. _get-pip.py: https://raw.githubusercontent.com/pypa/pip/master/contrib/get-pip.py
.. _ez_setup.py: https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py
