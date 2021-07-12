# Instalação do Virtualbox no Linux APT

## Antes de começar
Nos exemplos eu vou usar o sistema operacional Debian.

Para acompanhar você precisa estar usando um sistema baseado no Debian

## Usando o apt-get
No Linux diversas formas para instalar o Virtualbox , o modo mais fácil é via apt da seguinte forma.


### Adicionando o Virtualbox sources.list
Adicione a seguinte linha à sua **/etc/apt/sources.list**.

```sh
 deb http://download.virtualbox.org/virtualbox/debian sua-distro contrib
```

Em vez de sua-distro precisamos inserir

De acordo com sua distribuição, substitua **sua-distro** por 

- artful
- zesty
- yakkety
- xenial
- trusty
- stretch
- jessie
- wheezy 


**Versões antigas do Virtualbox suportam distribuições diferentes**.

### Baixando chave publica
A chave pública Oracle para apt-secure pode ser baixada

Aqui para Debian 8 ("Jessie") / Ubuntu 16.04 ("Xenial") e mais tarde
```sh
 https://www.virtualbox.org/download/oracle_vbox_2016.asc
```

Aqui para distribuições mais antigas.
```sh
 https://www.virtualbox.org/download/oracle_vbox.asc
```

### Adicionando chave publica
Você pode adicionar a chave da seguinte forma.

Se baixou a chave para Debian 8 ("Jessie")/Ubuntu 16.04 ("Xenial") ou posteriores
```sh
# apt-key add oracle_vbox_2016.asc
```

Senão vamos usar o
```sh
# apt-key add oracle_vbox.asc
```

### Atualizando repositório
Agora devemos atualizar o repositório usando
```sh
# apt-get update
```

### Procurando o Virtualbox
Para pesquisar o Linux podemos usar
```sh
$ apt-cache search virtualBox
```

Retorno
```sh
 virtualbox-4.3 - Oracle VM VirtualBox
 virtualbox-5.0 - Oracle VM VirtualBox
 virtualbox - x86 virtualization solution - base binaries
 virtualbox-dbg - x86 virtualization solution - debugging symbols
 virtualbox-dkms - x86 virtualization solution - kernel module sources for dkms
 virtualbox-guest-dkms - x86 virtualization solution - guest addition module source for dkms
 virtualbox-guest-source - x86 virtualization solution - guest addition module source
 virtualbox-guest-utils - x86 virtualization solution - non-X11 guest utilities
 virtualbox-guest-x11 - x86 virtualization solution - X11 guest utilities
 virtualbox-qt - x86 virtualization solution - Qt based user interface
 virtualbox-source - x86 virtualization solution - kernel module source
```

### Instalando o Virtualbox
Podemos ver que nos retornou diversas versões , vamos escolher uma e instalar.

Nesse caso vou usar o VirtualBox na versão 5.0
- virtualbox-5.0

Podemos instalar usando **apt-get**.
```sh
# apt-get install virtualbox-5.0
```

### Instalando DKMS
Os usuários do Ubuntu/Debian podem querer instalar o pacote dkms para garantir que os módulos do kernel do host VirtualBox (vboxdrv, vboxnetflt e vboxnetadp) sejam devidamente atualizados. 

O pacote dkms pode ser instalado através do gerenciador de pacotes Synaptic ou através do **apt-get**:
```sh
# apt-get install dkms
```

## Referencias 
[Linux Download] (https://www.virtualbox.org/wiki/Linux_Downloads) 
