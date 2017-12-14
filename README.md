# psdash_HTTPBasicAuth

>主节点和agent节点都执行下面的命令
>yum groupinstall "Development Tools"  -y
>yum install python-devel  -y
>yum install python-setuptools  -y
>git clone https://github.com/Jahaja/psdash.git 
>cd psdash 
>pip install -U setuptools
>python setup.py install
>主节点执行
>pip install flask-httpauth
>git clone https://github.com/wenguonideshou/psdash_HTTPBasicAuth.git
>cd psdash_HTTPBasicAuth
>python run.py -l '/var/log/**/*.log'     
**-l '日志目录'   支持.*?**
>agent节点执行
>psdash -a --register-as xxx -l '/var/log/**/*.log' --register-to http://主节点IP:5000
