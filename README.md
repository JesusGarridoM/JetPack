# JetPack

JetPack code and documentation is distributed under the Apache 2 license. Contributions back to the source are encouraged.

## Description

JetPack is an innovative automation package that is used to configure the infrastructure hardware and OpenStack software in a fully automated fashion. The toolkit includes scripts from Dell EMC that work with Red Hat OpenStack Platform Director to automate the deployment process, not only to save time but to ensure the process is reliable and repeatable each time.

Please reference the current Dell EMC Ready Architecture For Red Hat OpenStack Platform Software Deployment Guide v16.1 for installation and configuration

## Legal

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

## Commands

Acceder como usuario root

```shell
sudo su
```

Ir a la carpeta root

```shell
cd ~
```

Clonar repositorio

```shell
git clone https://github.com/JesusGarridoM/JetPack.git
```

Copiar archivos .properties y .ini a /root

```shell
cp /root/JetPack/src/deploy/osp_deployer/settings/sample_hci.properties /root/acme.properties
cp /root/JetPack/src/deploy/osp_deployer/settings/sample_hci.ini /root/sample_hci.ini
```

Agregar rutas /root/JetPack/src/deploy y /root/JetPack/src/deploy/auto_common al PYTHONPATH

```shell
#export PATH=$PATH:/root/JetPack/src/deploy
#export PATH=/sbin:/bin:/usr/sbin:/usr/bin:/root/JetPack/src/deploy
export PYTHONPATH=/bin:/usr/bin/python3.6:usr/lib/python3.6:/usr/local/lib/python3.6/site-packages:/root/JetPack/src/deploy:/root/JetPack/src/deploy/auto_common
```

MODIFICAR LOS ARCHIVOS .ini y .properties
Cambiar de ruta

```shell
cd ~/JetPack/src/deploy/setup
```

Ejecutar el Script

```shell
python3.6 setup_usb_idrac.py -s /root/sample_hci.ini -idrac_vmedia_img
```

Checar MD5 de .img y .iso

```shell
md5sum /root/osp_ks.img
md5sum /root/rhel-8.2-x86_64-dvd.iso
```

Moverlos a /home y comprimirlos

```shell
cp /root/osp_ks.img /home/
tar -czf SAH-files.tar.gz "osp_ks.img" "rhel-8.2-x86_64-dvd.iso" # Comprimir .img
```

Descargar los archivos y descomprimirlos

```shell
tar -xzf SAH-files.tar.gz
```

Checar MD5

```shell
# Get-FileHash "C:/.../osp_ks.img" -Algorithm MD5 # Windows
# Get-FileHash "C:/.../rhel-8.2-x86_64-dvd.iso" -Algorithm MD5 # Windows
md5sum ./osp_ks.img
md5sum ./rhel-8.2-x86_64-dvd.iso
```

## MD5

5C969F23E2B6E874FAB473F94DC6641E #Delivery_Jesus

subscription-manager list --all --available --matches="_Openstack_"

/c/Users/Delivery_Jesus/Desktop/Jetpack/NuevaChida/SAH-files.tar.gz

systemctl

[6:50 p. m., 8/3/2023] +52 1 55 4356 0065: [root@localhost ~]# ip a |grep "state UP" -A1
4: ens1f0np0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
link/ether bc:97:e1:cd:46:90 brd ff:ff:ff:ff:ff:ff
--
5: ens1f1np1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
link/ether bc:97:e1:cd:46:91 brd ff:ff:ff:ff:ff:ff
--
6: ens2f0np0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 100
