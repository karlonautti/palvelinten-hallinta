# Miniprojekti

Tekijät: Karri Salonen ja Tuukka Mero

## Tomisto-ohjelma bundle

Ensiksi luotiin repository yhteiselle projektille. Tehdään tyhjä README.md ja annetaan lisenssi GNU General Public License 3. Sitten kutsuttiin collaboratorit repoon.  

Sitten oli aika kloonata repo koneelle.

![kloonaus](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/kloonaus.png)  

Sitten luodaan Vagrantfile ja laitetaan sinne niin että se luo masterin ja yhden minion koneen sekä asentaa näille molemmille saltin.  

![Vagrantfile](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/Vagrantfile.png)  

Kun Vagranfile on valmis niin ajetaan se komennolla Vagrant up ja se luo onnistuneesti koneet.  

![vagrantkoneet](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/vagrantkoneet.png)  

Sitten pitää hyväksyä avain. Näköjään master ei löydä avainta. Pitää käydä minionin puolella katsomassa mikä on ongelma. Potkaistaan minionin puolella salti uudestaan käyntiin ja katsotaan sitten statuksella onko se yhdistänyt masteriin. Se yhdistyy masteriin ja nyt avain näkyy ja sen voi hyväksyä.

![avaimeton](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/avaimeton.png)  
![minionrestart](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/minionrestart.png)  
![avain](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/avain.png)  

Viimeisenä aika kokeilla että yhteys varmasti toimii niin masterilla pingaan minionia ja saadaan vastaus true, joka tarkoittaa sitä, että yhteys toimii.

![pingaus](https://github.com/karlonautti/palvelinten-hallinta/blob/main/h6/pingaus.png)

## Office Salt-state bundle

Bundlen ideana on automatisoida työpöytäympäristön ohjelmien asennus orjakoneelle

Ensin yhdistin aikaisemmin luotuun gitrepoon seuraavalla tavalla

![Repoliittyminen](https://github.com/TuukkaMero/linux-course/blob/main/gitrepo%20liittyminen.png)

Seuraavaksi yhdistin jo aikaisemmin luotuun master koneeseen ja hyväksyin sieltä orjakoneen avaimen:

![avain](https://github.com/TuukkaMero/linux-course/blob/main/minion%20avain.png)

Loin salt-state office bundle tiedoston

Tiedoston sisältö:

![bundle](https://github.com/TuukkaMero/linux-course/blob/main/office%20bundle.png)

Viimeiseksi testasin ajaa salt-staten orjakoneella "desktop001":

![testi](https://github.com/TuukkaMero/linux-course/blob/main/office%20testi.png)

Testi näytti toimivan ja toisen ajon jälkeen muutoksia ei tapahtunut joten idempotenssi on saavutettu

Viimeiseksi testasin vielä orjakoneelta että kaikki halutut sovellukset oli asennettu:

![sovellukset](https://github.com/TuukkaMero/linux-course/blob/main/minion%20sovellukset.png)

## Lähteet:

https://terokarvinen.com/2024/hello-salt-infra-as-code/  
https://terokarvinen.com/2018/salt-quickstart-salt-stack-master-and-slave-on-ubuntu-linux/?fromSearch=salt%20quickstart%20salt%20stack%20master%20and%20slave%20on%20ubuntu%20linux  
https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file  
https://docs.saltproject.io/salt/install-guide/en/latest/topics/install-by-operating-system/linux-deb.html  



