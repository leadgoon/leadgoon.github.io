---
layout: post
title: Geopandas 설치하기
tags: [python, geopandas]
---

# 지오판다스 설치하기

파이썬 지오판다스 라이브러리는 지리정보를 분석할때 사용하는 유용한 패키지이다. 아나콘타 프롬프트에서 pip install geopandas 를 치니, 다음과 같은 에러가 나타난다. 

```
ERROR: Command errored out with exit status 1:
     command: 'c:\users\bigdata3\anaconda3\python.exe' -c 'import sys, setuptools, tokenize; sys.argv[0] = '"'"'C:\\Users\\Public\\Documents\\ESTsoft\\CreatorTemp\\pip-install-1sf8dn5j\\fiona\\setup.py'"'"'; __file__='"'"'C:\\Users\\Public\\Documents\\ESTsoft\\CreatorTemp\\pip-install-1sf8dn5j\\fiona\\setup.py'"'"';f=getattr(tokenize, '"'"'open'"'"', open)(__file__);code=f.read().replace('"'"'\r\n'"'"', '"'"'\n'"'"');f.close();exec(compile(code, __file__, '"'"'exec'"'"'))' egg_info --egg-base 'C:\Users\Public\Documents\ESTsoft\CreatorTemp\pip-pip-egg-info-macd92h1'
         cwd: C:\Users\Public\Documents\ESTsoft\CreatorTemp\pip-install-1sf8dn5j\fiona\
    Complete output (1 lines):
    A GDAL API version must be specified. Provide a path to gdal-config using a GDAL_CONFIG environment variable or use a GDAL_VERSION environment variable.
    ----------------------------------------
ERROR: Command errored out with exit status 1: python setup.py egg_info Check the logs for full command output.
```

지오판다스가 실행되기 위한 의존성 패키지가 설치되어 있지 않은 경우가 있어서 의존성 패키지를 먼저 설치하여야 한다. 

먼저 python 버전과 운영체제를 확인하자. 

```
python -m --version

systeminfo | findstr based
```

python 버전은 3.7.4, 시스템은 x64-based PC 라고 뜬다. 


필요한 라이브러리는 다음과 같다. 각자 환경에 맞는 whl 파일을 다운 받도록 하자. 

1. https://www.lfd.uci.edu/~gohlke/pythonlibs/#fiona

2. https://www.lfd.uci.edu/~gohlke/phthonlibs/#shapely

3. https://www.lfd.uci.edu/~gohlke/phthonlibs/#gdal



다운 받은 폴더로 가서 dir *.whl 으로 다운 받은 파일을 확인한다. 

그리고 pyproj, shapely, GDAL, Fiona, geopandas 순으로 설치하여야 에러가 발생하지 않는다. 

```
pip install pyproj
pip install Shapely-1.7.0-cp37-cp37m-win_amd64.whl 
pip install GDAL-3.1.2-cp37-cp37m-win_amd64.whl 
pip install Fiona-1.8.13-cp37-cp37m-win_amd64.whl 
pip install geopandas
```

라고 치면 모두 정상 설치된 것을 볼 수 있다. 

