# Pystarter

This is a starter repo, use this to get started with a new python project and get stuff like automated builds, tests, publish to pypi etc...
Out of the box for free.

## helpful commands

list all commands
```
invoke -l
```

read help from there.

## quickstart

```
echo "suggested you are using virutalenvwrapper setup at (http://virtualenvwrapper.readthedocs.io/en/latest/install.html)"
mkvirtualenv myproj --python=`which python3`
git clone https://hms-dbmi/pystarter
cd pystarter
rm -rf .git
pip install -r requirments-dev.txt
echo "basic environment set up, you are good to go"
git remote add origin https://github.com/hms-dbmi/<your_repo_name>.git
git push -u origin master
echo "See configure section in README.md"
```

## Configure

This setup assumes your project is in the folder called sample.  You should change the name of 
sample to be the name of your project and put all you code in that directory.  Also change:

setup.py/setup   (bottom of file)

As below
name='name of code diretory / project
packages=['put name of code directory here']

change whatever other details you deem appropriate.

NOTE: you will have to keep `setup.requires` up to date with the libraries you use for your project if
you want auto pypi deployment to work.

** ALSO CHANGE ***

in `tasks.py` near the top probably close to line 12

```
PROJECT_NAME = 'sample'
```

here you need to swap sample with name of your code directory

## More Info

- Tests use pytest.  Put all your unit tests in the tests folder, name them test_somthing.py.  Each test
function should start with the name test_ .  That's it, test away and be merry. :)

- This repo is also already pre-configured to run CI tests with travis.  So anything in your tests folder will get
ran each time you push code to github.  You need to make sure your new repo is enabled in travis however for this to happen.

- Publish will publish your code to pypi / cheese shop for easy sharing with the world




