# Air Flow

[Referência](https://www.youtube.com/watch?v=K9AnJ9_ZAXE&list=PLwFJcsJ61oujAqYpMp1kdUBcPG0sE0QMT)



## Instalation

```
mkdir airflow-course
cd airflow-course
touch .gitignore
touch requirements.txt # Add apache-airflow last version
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
export AIRFLOW_HOME=`pwd`
airflow db init
airflow webserver -p 8080
```


### Create a new user

```
# Stop the server
airflow users create --help
airflow users create --username admin --firstname firstname --lastname lastname --role Admin --email admin@domain.com
# set password as 1234 and confirm
```


## Core concepts

- Dag
- Task
- Operator


## Task lifecicle
