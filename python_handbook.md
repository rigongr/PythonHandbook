<img src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" style="zoom:300%; text-align: center;" />

------

​	

**A Python handbook for:**

- Python (Flask, FastAPI, Pytest)

- Databases (PostgreSQL).

- Git, Docker, Poetry.

- Shell & Terminal commands (Linux)

  

# 01. Testings (Fast API, PyTest, Poetry)



```Python / Testings
# run server
./manage.py --dev runserver --reload

# run tests
./manage.py --dev runtests

# These commands are work related.
```



**PYTHON DEBUGGER (PDB)**

```
interactive - to activate Python shell while debugging with Python Debugger.
```





# 02. Databases (PostgreSQL)

#### POSTGRES:

```Postgres / Linux
    
1) psql -h localhost -U postgres ----> activate the database through terminal
2) \l ----> List available databases
3) \dt ----> List available tables
4) \d table_name ---> Describe a table (columns, types, modifiers, etc)

Creating a user and granting them access:
1) sudo -u postgres psql
2) postgres=# create database mydb;
3) postgres=# create user myuser with encrypted password 'mypass';
4) postgres=# grant all privileges on database mydb to myuser;

Ubuntu, set global configs through terminal:
1) export POSTGRES_URL="127.0.0.1:5432"
2) export POSTGRES_USER="postgres"
3) export POSTGRES_PW="dbpw"
4) export POSTGRES_DB="test"
```





```
1. https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e
   - Creating users / databases, permissions etc.

```





# 03. Git, Poetry, Pip                                               -- Version Control --



#### Git commands:

```Github 
**git log --graph --oneline --decorate --all ----> this shows the previous changes, more information about tags and such.**
**git tag v1.0.15 -----> Creates a tag, it's like a branch but it's unmovable.**
**git commit -a -m "Add account stats endpoint"  -----> for commits on git**
```



#### How to review MR:

```Git
0. git checkout master --> git pull
1. git checkout origin/[name_of_the_branch]
2. git checkout name_of_the_branch
3. git pull
4. ./manage.py --dev runtests (work related)
5. Check if the code is correct
6. MERGE 
```



#### Poetry:

```Poetry
poetry install -----> this installs the poetry in the folder for the first time.
poetry shell ----> Creates / Activates the virtual environment.
poetry update -----> this updates the packages / installs them in the machine.
deactive ----> Exits the current activated virtual environment.

*TO RUN CERTAIN TESTS*
poetry run python -m py.test tests/routes/test_campaign_shared_sets.py::[name_of_the_test] -vv -x --pdb

*TO RUN THE COMPLETE FILE*
poetry run python -m py.test tests/routers/ad_groups/test_critera.py -vv -x --pdb      
```





# 04. Docker



#### Clean up docker space:

```dockerfile
# check docker volume disk usage
----> sudo du -sh /var/lib/docker/volumes

# check total disk usage
----> df -h /

# clear up space
----> docker volume prune
```



# 05. Terminal 

Open a file to edit it in terminal (for example, a text file)

```shell
~$ nano [directory of the file] ---> example ---> nano ~/.profile

~$ sudo -H nautilus ---> Opens up folder explorer. With this, you can copy/paste/extract to folders that require permissions.
```













# Useful Links:



> Create user, database, access ---> https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e
>
> Flask, SQLAlchemy and Postgres ---> https://build.vsupalov.com/flask-sqlalchemy-postgres/
>
> Discord Bot ---> https://discordpy.readthedocs.io/en/stable/faq.html#how-do-i-send-a-message-to-a-specific-channel



# To do:



Research about:

```Python
- Structural Pattern Matching.
```

