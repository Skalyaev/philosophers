# <p align="center">philosophers</p>
> *Dans ce projet, vous apprendrez les bases du multithreading d'un processus. Vous verrez comment créer des threads et découvrirez les mutex.*
>
> - *Un ou plusieurs philosophes sont assis autour d'une table ronde avec un grand bol de spaghetti au milieu.*
> - *Les philosophes alternent entre manger, réfléchir et dormir. Pendant qu'ils mangent, ils ne pensent ni ne dorment ; pendant qu'ils réfléchissent, ils ne mangent ni ne dorment ; et bien sûr, pendant qu'ils dorment, ils ne mangent ni ne réfléchissent.*
> - *Il y a aussi des fourchettes sur la table, autant de fourchettes que de philosophes.*
> - *Comme manger et servir des spaghetti avec une seule fourchette est très inconfortable, un philosophe prend ses fourchettes droite et gauche pour manger, une dans chaque main.*
> - *Quand un philosophe a fini de manger, il remet ses fourchettes sur la table et commence à dormir. Une fois réveillé, il recommence à réfléchir. La simulation s'arrête quand un philosophe meurt de faim.*
> - *Chaque philosophe a besoin de manger et ne doit jamais mourir de faim.*
> - *Les philosophes ne se parlent pas entre eux.*
> - *Les philosophes ne savent pas si un autre philosophe est sur le point de mourir.*
> - *Inutile de dire que les philosophes doivent éviter de mourir !*

## Preview
```bash
philo 3 610 200 200 3 | sed 's= ms=='
```
<details><summary>output</summary>

```c
0 1 is thinking
0 2 is thinking
0 3 is thinking
1 1 has taken a fork
1 1 has taken a fork
2 1 is eating
202 3 has taken a fork
202 3 has taken a fork
202 1 is sleeping
203 3 is eating
402 1 is thinking
403 3 is sleeping
403 2 has taken a fork
403 2 has taken a fork
404 2 is eating
603 3 is thinking
604 2 is sleeping
604 1 has taken a fork
604 1 has taken a fork
605 1 is eating
804 2 is thinking
805 1 is sleeping
806 3 has taken a fork
806 3 has taken a fork
807 3 is eating
1005 1 is thinking
1007 2 has taken a fork
1007 2 has taken a fork
1007 3 is sleeping
1008 2 is eating
1207 3 is thinking
1208 2 is sleeping
1209 1 has taken a fork
1209 1 has taken a fork
1210 1 is eating
1408 2 is thinking
1410 1 is sleeping
1411 3 has taken a fork
1411 3 has taken a fork
1412 3 is eating
1610 1 is thinking
1612 3 is sleeping
1613 2 has taken a fork
1613 2 has taken a fork
1614 2 is eating
1812 3 is thinking
1814 2 is sleeping
```
</details>

![](https://github.com/Skalyaeve/images-1/blob/main/screenshot/philo.png)
> Visualieur [ici](https://nafuka11.github.io/philosophers-visualizer/)

## Install
```bash
sudo apt update -y
sudo apt install -y gcc
sudo apt install -y make
```
```bash
mkdir -p $HOME/.local/bin
mkdir -p $HOME/.local/src
mkdir -p $HOME/.local/include
```
```bash
link=Skalyaeve/philosophers
name=philo

git clone https://github.com/$link.git $name
cd $name && make && make clean

ln -s $PWD/$name $HOME/.local/bin/$name
ln -s $PWD/src $HOME/.local/src/$name
ln -s $PWD/include $HOME/.local/include/$name
```

## Usage
```bash
export PATH=$HOME/.local/bin:$PATH
philo <count> <ttd> <tte> <tts> [ttw]
```
- **`<count>`** - Nombre de philosophes
- **`<ttd>`** - Temps avant la mort (ms)
- **`<tte>`** - Temps pour manger (ms)
- **`<tts>`** - Temps pour dormir (ms)
- **`[ttw]`** - Nombre de repas à manger

## Uninstall
```bash
name=philo

rm -rf $name
rm $HOME/.local/bin/$name
rm $HOME/.local/src/$name
rm $HOME/.local/include/$name
```

