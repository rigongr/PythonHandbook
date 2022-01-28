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



<h2> Redis: </h2>

<h3>
    Step 1.
</h3><h4> Setup & Install (For Linux) </h4>

```shell
$ sudo apt update
$ sudo apt install redis-server

# This will download and install Redis and its dependencies.
# Open this file:
$ sudo nano /etc/redis/redis.conf
# Edit the line `supervised no` to `supervised systemd`. Press CTRL + X, Y, then ENTER to save the file and exit.

# Then, restart the Redis service to reflect the changes you made to the configuration file:
$ sudo systemctl restart redis.service


```

<h3> Step 2. </h3>

<h4> Testing Redis </h4>

```shell
# Start by checking that the Redis service is running:
$ sudo systemctl status redis

# If `active` is on `running` then everything is good so far.
# Here, you can see that Redis is running and is already enabled, meaning that it is set to start up every time the server boots.

# To test that Redis is functioning correctly:
$ redis-cli

# In the prompt that follows, test connectivity with the ping command:
$ 127.0.0.1:6379> ping # IF OK, this should return `PONG`.

# Next, check that you’re able to set keys by running:
$ 127.0.0.1:6379> set test "It's working!"

# Retrieve the value by typing:
$ 127.0.0.1:6379> get test

# As a final test, we will check whether Redis is able to persist data even after it’s been stopped or restarted. To do this, first restart the Redis instance:
$ 127.0.0.1:6379> exit
$ sudo systemctl restart redis

# Then connect with the command-line client again:
$ redis-cli

# And confirm that your test value is still available.
$ 127.0.0.1:6379> get test

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
$ nano [directory of the file] ---> example ---> nano ~/.profile

$ sudo -H nautilus ---> Opens up folder explorer. With this, you can copy/paste/extract to folders that require permissions.
```













# Useful Links:



> Create user, database, access ---> https://medium.com/coding-blocks/creating-user-database-and-adding-access-on-postgresql-8bfcd2f4a91e
>
> Flask, SQLAlchemy and Postgres ---> https://build.vsupalov.com/flask-sqlalchemy-postgres/
>
> Discord Bot ---> https://discordpy.readthedocs.io/en/stable/faq.html#how-do-i-send-a-message-to-a-specific-channel



<hr> </hr>





<img src="/home/rigong/Desktop/1200px-Go_Logo_Blue.svg.png" alt="1200px-Go_Logo_Blue.svg" style="zoom: 50%;" />



<hr> </hr>

# 1. Basics 



**1.1** Project initialziation commands:

```shell

$ mkdir myapp && cd myapp ---> Creates a folder named myapp and switches to that directory.

$ go mod init myapp ---> The go mod init command creates a go.mod file to track your codes dependencies.

$ go get ---> Imports a framework from github. EXAMPLE ---> `$ go get github.com/labstack/echo/v4`  (echo framework)

NOTE: 'init()' function runs before 'main()'. 'main()' function runs after 'init()'
```



****
