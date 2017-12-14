# psdash_HTTPBasicAuth

**1.主节点和agent节点都执行下面的命令(安装psdash)**
>Debian/Ubuntu:

>>\# apt-get install build-essential python-dev -y

>RHEL (Fedora, CentOS):

>>\# yum groupinstall "Development Tools"  -y

>>\# yum install python-devel  -y

>>\# yum install python-setuptools  -y

>>\# git clone https://github.com/Jahaja/psdash.git 

>>\# cd psdash 

>>\# pip install -U setuptools

>>\# python setup.py install

**2.主节点执行**

>>\# pip install flask-httpauth

>>\# git clone https://github.com/wenguonideshou/psdash_HTTPBasicAuth.git

>>\# cd psdash_HTTPBasicAuth

>>\# python run.py -l '/var/log/**/*.log'     

**3.agent节点执行**

>>\# psdash -a --register-as xxx -l '/var/log/**/*.log' --register-to http://主节点IP:5000

## 如何修改参数？

在run.py的app = Flask(__name__)下面添加如下语句

app.config.xxx = yyy

xxx为下面的参数, yyy为值, 比如

    app.config.PSDASH_ALLOWED_REMOTE_ADDRESSES = "10.0.0.2, 192.29.20.2"
    app.config.PSDASH_URL_PREFIX = "/psdash"
    app.config.PSDASH_LOG_LEVEL = logging.INFO
    app.config.PSDASH_LOG_LEVEL = "%(levelname)s"
    app.config.PSDASH_NODES = [{'name': 'mywebnode', 'host': '10.0.0.2', 'port': 5000}]
    app.config.PSDASH_NET_IO_COUNTER_INTERVAL = 3
    app.config.PSDASH_LOGS_INTERVAL = 60
    app.config.PSDASH_REGISTER_INTERVAL = 60
    app.config.PSDASH_LOGS	= ['/var/log/*.log']
    app.config.PSDASH_REGISTER_TO = 'http://10.0.20.2:5000'
    app.config.PSDASH_REGISTER_AS = 'myvps'
    app.config.PSDASH_HTTPS_KEYFILE = '/home/user/private.key'
    app.config.PSDASH_HTTPS_CERTFILE	= '/home/user/certificate.crt'
    app.config.PSDASH_ENVIRON_WHITELIST = ['HOME']

详细说明请参考https://github.com/Jahaja/psdash#configuration
