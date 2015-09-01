# Tutorial w jezyku Polskim (Wlasny dedykowany server DST).

## Ogólne informacje
Zanim przejdziemy do technicznej strony poradnika, musimy zrobić sobie krótki wstep na temat gdzie mozna taki server postawic oraz za jaka cene.
Jesli chcecie postawić swój server DST jako server dedykowany (czyli na srodowisku ktore jest wylacznie dedykowane pod ten server), moze bo byc twój wlasny komputer, lub mozesz kupic swoja wlasna maszyne w "chmurze". Jesli zdecydujesz sie aby trzymac swoj server na serverze dedykowanym, udostepnionym przez firmy zewnetrzne : [Azure](), [Amazon web services](), [Heroku](). Na pewno możesz liczyć ze twój server bdzie mial bardzo szybkie polaczenie internetowe, oraz dodatkowo jest mozliwosc zwiekszania zasobów w miare ich konsumowania, te rozwiazanie moze byc nawet tansze niz posiadanie servera na twoim domowym komuterze. Problem jednak polega na tym ze troszeczke wiecej czasu spedzisz na konfigorowaniu swoich wirtualnych maszyn.

### Systemy operacyjne
Aktualnie DST wspiera Windows oraz Linux. Jesli wybrales swoj system operacyjny na ktorym chcesz postawic swoj dedykowany server przejdz do (sekcji z Windows)[] lub (sekcji z Linux)[].

## Instalacje, oraz konfiguracja servera

### Uwaga
Nie zależnie od systemu operacyjnego, zawsze bdziemy si posugiwali [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD)

### Windows

```bash
login anonymous
force_install_dir C:\path\to\directory
app_update 343050 validate
```

### Linux (Debian/Ubuntu)

#### Instalacja SteamCMD oraz DST
```bash
sudo dpkg—add-architecture i386 # If running a 64bit OS
sudo apt-get update
sudo apt-get install lib32gcc1    # If running a 64bit OS
sudo apt-get install lib32stdc++6 # If running a 64bit OS
sudo apt-get install libgcc1      # If running a 32bit OS
sudo apt-get install libcurl4-gnutls-dev:i386
sudo useradd -m steam
chmod a+rw `tty`  # Note those are backticks, not single quotes
sudo su - steam
mkdir ~/steamcmd
cd ~/steamcmd
wget http://media.steampowered.com/installer/steamcmd_linux.tar.gz
tar -xvzf steamcmd_linux.tar.gz
./steamcmd.sh
login anonymous
force_install_dir /home/steam/steamapps/DST (or whatever absolute path is wanted)
app_update 343050 validate
quit
cd /home/steam/steamapps/DST/bin/
screen -S "DST Server" ./dontstarve_dedicated_server_nullrenderer
```

Dodać info o bledach

#### Uruchomienie servera po instalacji SteamCMD i DST

```bash
cd /home/steam/steamapps/DST/bin/
screen -S "DST Server" bash -c 'LD_LIBRARY_PATH=~/dst_lib ./dontstarve_dedicated_server_nullrenderer'
```

### Desktopowa wersja (posiadajca GUI)

Jesli macie zainstalowanego steama w wersji desktopowej (GUI) i jesli macie zainstalowane DST to dedykowany server powinien wam sie pojawić w ```Tools->Don't Starve Together Dedicated Server```

### Reign of Giants Beta
TODO

## Aktualizacja
TODO

## Konfiguracja

### Command Line Options

## Server Tokens

## Uruchomienie

## Kilka serwerów naa jednej maszynie

## Personalizacja mapy

## Tworzenie mapy

## Mody

## Zarzadzanie / Administracja serwera

## FAQ


References : http://dont-starve-game.wikia.com/wiki/Guides/Don%E2%80%99t_Starve_Together_Dedicated_Servers
