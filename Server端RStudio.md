# 一、准备工作
## 1.安装[jupyter](http://jupyter.org/)（server端）
* 使用conda安装
```
conda install jupyter
```
* 使用pip安装 (有权限)
```
pip install jupyter
```
* 使用pip安装 (无权限)
```
pip install --user jypyter
```
## 2.安装[IRkernel](https://irkernel.github.io/)（server端）
* 使用conda安装
```
conda install r-irkernel
```
* 使用CRAN安装
```
install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))
devtools::install_github('IRkernel/IRkernel')
```
## 2.配置R kernel（server端）
进入R，输入：
```
IRkernel::installspec()
```
## 3.配置端口映射
server端：
```
nohup jupyter notebook --no-browser --port 1075 &
```
*1075为server端任意指定端口，必须和local端相同* 
Local端：
```
ssh -NL 1075\:localhost:1075 zhangx@zlab3.umassmed.edu &
```
* *前一个端口号1075为监听server端口，需和server端口一致，后一个端口1075为local映射端口，方便起见都用一个端口号* 
* *zhangx为登陆服务器用户名，zlab3.umassmed.edu为服务器地址*
## 3.使用jupyter（local端）
设置好后就可以在本地网页浏览器地址栏输入`localhost:1075`使用网页版的jupyter notebook了，感觉和Rstudio差不多：）
