# How to Setup the Odoo Simple Development Environment

#### Please read this
- Before you read the following sections, you need a Ubuntu machine (real or virtual machine, it's up to you)
- You should need to know the basis:
  - You can run Odoo if you have 2 things:
    - ***The environment to run Odoo***
    - ***And the PostgreSQL***
  - I don't mention **the Odoo source code** because you MUST have them to run Odoo, right? ;)
- The Odoo version in this guide is **12.0** or **13.0**
  - The following steps bellow are the basic steps, you can base on these to build your own way :D
  - The Odoo **13.0** requires Python >= 3.6, please check & update the Python version to run Odoo **13.0**. You can find the tutorial to upgrade Python 3.6 in the Internet

#### Prepare some stuffs
- Open the terminal
- Install some packages
```
sudo apt-get install libxml2-dev libxslt-dev python-dev python3-dev python-virtualenv libsasl2-dev libldap2-dev libssl-dev
```
- Install git & configure the SSH key in gitlab or github
- Install pip3 if it doesn't exist
- Install pew: `pip3 install pew` or you can follow [this repo](https://github.com/berdario/pew) to install pew
  - NOTE: if pew is not in your `$PATH`, please add it to your `$PATH` ;)

#### Prepare the PostgreSQL
- You can follow any guide to setup this :)

#### Pull the source code
- Clone the source code Odoo from https://github.com/odoo/odoo
 
#### Create the virtual environment
- Go to the folder of the odoo, run `pew new -p python3 -r requirements.txt -a /dir/of/the/source/code <your_venv_name>` to create the virtual environment of the Odoo

#### Create the dev.conf before running Odoo
- In the folder of the source code, create the new file named `dev.conf` with the content bellow
```
[options]
addons_path = /home/<your_user>/code/odoo/odoo,/home/<your_user>/code/odoo/addons

db_host = localhost
db_port = 8232
db_user = openerp
db_password = openerp

http_port = 8569
```

- NOTE:
  - `db_host`, `db_port`, `db_user` & `db_password` are the informaton that used to connect to the PostgreSQL Server
  - The default value of `http_port` is 8069, but you can change it to other port

#### Run the Odoo :)
- In the folder of the source code
  - Make sure you are in the venv created above by the command: `pew workon <your_venv_name>`
  - Run Odoo by the command: `./odoo-bin -c dev.conf`
- Open the web browser and go to: `localhost:8569`

#### And, how to customize or add the new module to the source???
- Ask your mentor for help :D
- Or you can read **the developer document of Odoo** in [here](https://www.odoo.com/documentation/)
