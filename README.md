# psdash_HTTPBasicAuth

**1.主节点和agent节点都执行下面的命令(安装psdash)**

>yum groupinstall "Development Tools"  -y

>yum install python-devel  -y

>yum install python-setuptools  -y

>git clone https://github.com/Jahaja/psdash.git 

>cd psdash 

>pip install -U setuptools

>python setup.py install

**2.主节点执行**

>pip install flask-httpauth

>git clone https://github.com/wenguonideshou/psdash_HTTPBasicAuth.git

>cd psdash_HTTPBasicAuth

>python run.py -l '/var/log/**/*.log'     

-l '日志目录'   支持.*?

**3.agent节点执行**

>psdash -a --register-as xxx -l '/var/log/**/*.log' --register-to http://主节点IP:5000

##如何修改参数？

在run.py的_create_app函数下添加

app.config.xxx = yyy

xxx为下面的参数，yyy为值,比如

PSDASH_ALLOWED_REMOTE_ADDRESSES = "10.0.0.2, 192.29.20.2"

PSDASH_URL_PREFIX = "/psdash"

PSDASH_LOG_LEVEL = logging.INFO

PSDASH_LOG_LEVEL = "%(levelname)s"

PSDASH_NODES = [{'name': 'mywebnode', 'host': '10.0.0.2', 'port': 5000}]

PSDASH_NET_IO_COUNTER_INTERVAL = 3

PSDASH_LOGS_INTERVAL = 60

PSDASH_REGISTER_INTERVAL = 60

PSDASH_LOGS	= ['/var/log/*.log']

PSDASH_REGISTER_TO = 'http://10.0.20.2:5000'

PSDASH_REGISTER_AS = 'myvps'

PSDASH_HTTPS_KEYFILE = '/home/user/private.key'

PSDASH_HTTPS_CERTFILE	= '/home/user/certificate.crt'

PSDASH_ENVIRON_WHITELIST = ['HOME']

详细说明请参考https://github.com/Jahaja/psdash#configuration
