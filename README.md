## code
git clone command:
```
    git clone https://github.com/titus-nobody/pycon-tutorial-titus.git
    (but replace that repo URL with the one for your repository)
```

## CI
```    
pip install -U pytest pytest-cov coverage codecov sphinx --use-mirrors
py.test --cov=./

codecov --token=<token>
```


New test Code:
```
def test_daaaangerous():
    with pytest.raises(Exception) as e_info:
        wordcount_lib.daaaangerous()
```
If you want to run `py.test / `coverage report locally:
```
py.test --cov=./ --cov-report=html
```
(make sure you've done pip install pytest-cov)


Basic Git commands to commit
```
git add test_wordcount.py
git commit -m "added new test again"
git push
```

## DOC

sphinx docs:

https://github.com/dib-lab/2016-pycon-tutorial/issues/3

make html

----

to get a list of all .rst files in a directory:
```
ls -1 *.rst | cut -d. -f 1

find . -name \*.rst -print | cut -d. -f2 | cut -c2- -
```
----
```
git add index.rst Makefile make.bat conf.py _static _templates
git commit -am "added sphinx docs"
git push -u origin master
```
----

https://readthedocs.org/dashboard/

## package

```
from setuptools import setup

setup(name='projy-mc-proj',
      version='0.1',
      description='test stuff for pycon tutorial',
      py_modules=['wordcount_lib'],
      scripts=['wordcount'],
      setup_requires=[
          'pytest-runner',
      ],
      tests_require=[
          'pytest',
      ],
)
```


https://testpypi.python.org/pypi

```
~/.pypirc

[distutils]
index-servers=
  pypi
  pypitest

[pypitest]
repository = https://testpypi.python.org/pypi
username = <your user name goes here>
password = <your password goes here>

[pypi]
repository = https://pypi.python.org/pypi
username = <your user name goes here>
password = <your password goes here>
```
