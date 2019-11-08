# How to Setup the Odoo Simple Development Environment

#### Please read this
- Before you read the following sections, you need a Ubuntu machine (real or virtual machine, it's up to you)

#### Prepare some stuffs
- Open the terminal
- Install some packages
```
sudo apt-get install libxml2-dev libxslt-dev python-dev libsasl2-dev libldap2-dev libssl-dev
```
- Install git & configure the SSH key in gitlab or github
- Install pip3 if it doesn't exist
- Install pew: `pip3 install pew`

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

#### And, how to use VSCode to debug Odoo???
- Ask your mentor for help :D
- Or you can try my guide in [here](https://github.com/tuantrantg/how-to-setup-the-odoo-simple-development-envinroment/blob/master/DEBUG_ODOO_BY_VSCODE.md)
