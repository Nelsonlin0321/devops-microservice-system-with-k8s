### Python Auth Application Setup

```bash
cd auth-python/src
python3 -m venv venv
source ./venv/bin/activate
env | grep VIRTUAL
```

```bash
# OUPUT
VIRTUAL_ENV=/Users/nelsonlin/Desktop/personal-codes/devops-microservice-system-with-k8s/auth-python/src/venv
VIRTUAL_ENV_PROMPT=(venv)
```

```bash
pip install pylint
pip install jedi
```

```bash
pip install pyjwt
pip install flask
pip install flask_mysqldb
```

### Install mysql db on the local machine

```bash
export PATH=${PATH}:/usr/local/mysql-8.0.31-macos12-arm64/bin
export DYLD_LIBRARY_PATH="/usr/local/mysql/lib:$PATH"
vim ~/.zshrc
```

### Initialize database

```base
mysql -u root -p
mysql -u root -p < init.sql
mysql -uroot -e "DROP DATABASES auth"
mysql -uroot -e "DROP USER auth_user@localhost"
```

### Build Docker image

```bash
docker build -t nelsonlin0321/auth:latest .
docker push nelsonlin0321/auth:latest

docker pull nelsonlin0321/auth:latest

```
