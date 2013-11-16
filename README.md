Systemy-
========

                               BASH
     
     http://wbzyl.inf.ug.edu.pl/sp/bash

ZAD 1

#1/bin/bash
echo "Czesc $USER"
echo "twoj aktualny katalog to $PWD"
zmienna="a twoj katalog domowy to $HOME"
echo $zmienna
echo "nazwa twojego hosta to: $HOSTNAME"
echo "korzystasz z systemu operacyjnego $OSTYPE"
zmienna2=$(pwd)
echo "\"Ciapki\" - przyklad: $zmienna2"
exit 0

ZAD 2

#!/bin/bash
echo "Nazwa biezacego skryptu: $0"
echo "pierwszy przekazany parametr do skryptu: $2"
echo "..."
echo "dziewiaty przekazany parametr do skryptu: $9"
#
echo "Skrypt uruchomiono z parametrami: $@"
#
echo "Skrypt uruchomiono z parametrami: $*"
echo "kod pworotu ostatnio wykonywanego polecenia: $?"
echo "PID procesu biezacej powloki: $$"
exit 0 

ZAD 3

#!/bin/bash
owoc[0]="jablko"
owoc[1]="gruszka"
owoc[2]="sliwka"
owoc[3]="wisnia"
echo "pierwszy element tablicy owoc to: ${owoc[0]}"
echo "wszystkie elementy tablicy owoc to: ${owoc[*]}"
echo "wszystkie elementy tablicy owoc to: ${owoc[@]}"
echo "drugi element tablicy owoc ma ${owoc[1]} znakow"
echo "tablica owoc ma ${owoc[*]} elementy"
imie=(jola ania kasia basia magda)
echo "wszystkie elementy tablicy imie to: ${imie[@]}"
unset imie
echo "tablica imie ma: ${imie[@]} elementow"
tab1=(`cat /etc/passwd`)
echo "Tablica tab1 ma ${#imie[*]} elementow"
declare tab2=(`cat /etc/passwd`)
echo "tablica tab2 ma ${#tab2[*]} elementow"
exit 0

ZAD 4

#!/bin/bash
echo -n "Podaj pierwsza liczbe: "
read liczba1
echo -n "Podaj druga liczbe: "
read liczba2
echo
suma=$[liczba1 + liczba2]
echo "Suma liczb wynosi: $suma"
roznica=$((liczba1-liczba2))
echo "Roznica liczb wynosi: $roznica"
let iloczyn=liczba1*liczba2
echo "Iloczyn liczb wynosi: $iloczyn"
iloraz=$[liczba1/liczba2]
echo "Iloraz liczb wynosi: $iloraz"
modulo=$[liczba1%liczba2]
echo "Modulo liczb wynosi: $modulo"
exit 0

ZAD 5

#!/bin/bash
if [ -e ~/.bashrc ]
then echo "Masz plik .bashrc"
else echo "Nie masz pliku .bashrc"
fi
exit 0

ZAD 6

#!/bin/bash
echo -n "Czy jest wieczor? Odpowiedz tak lub nie: "
read odp
if [ "$odp" = "tak" ]
then echo "Dobry wieczor"
elif [ "$odp" = "nie" ]
then echo "Dzien dobry"
else
  echo "Nie rozpoznana odpowiedz: $odp"
  exit 1
fi
exit 0

                https://inf.ug.edu.pl/~anenca/systemy/cw5.html
                
ZAD 2

#!/bin/bash

funkcja_z_parametrami()
{
if [ $1 -gt 0 ] 
then echo "funkcja f(x) wynosi 1"
elif [ $1 -eq 0 ] 
then echo "funkcja f(x) wynosi 0"
else echo "funkcja f(x) wynosi -1"
fi
}
funkcja_z_parametrami "1"
