### Podatkovno rudarjenje, vmesno poročilo o opravljenem delu, 01. 04. 2019

# Priprava podatkov in osnovna vizualizacija

**Nejc Prijatelj**

**Žan Pristopec**

**Matevž Kušar**

V tem poročilu smo s pomočjo pythona, statistike in vizualizacije poskusili odgovoriti na čim več vprašanj, ki smo si jih zastavili pri izbiri projekta.

## Podatki

Kratek opis podatkov je bil podan že pri osnutku projekta, tu pa bi si najprej na hitro pogledali kaj točno dani podatki vsebujejo. Povezava do podatkov(https://www.kaggle.com/russellyates88/suicide-rates-overview-1985-to-2016).

Vse podatke ki smo jih dobili s spletne strani Kaggle hranimo v datoteki "master.csv".

Vsak podatek v tej zbirki ima naslednje atribute:
* *country:* država v kateri so bili zabeleženi samomori.
* *year:* leto na katerega se nanašajo podatki.
* *sex:* spol starostne skupine za to leto.
* *age_group:* starostna skupina.
* *count_of_suicides:* število samomorov za to leto.
* *population:* število oseb določenega spola v tem letu, za to starostno skupino.
* *suicide_rate:* pogostost samomorov - število samomorov na 100 tisoč ljudi.
* *country-year_composite_key:* država-leto ključ.
* *HDI_for_year:* indeks človekovega razvoja (izračunano iz življenjske dobe, stopnje izobrazbe in življenjske ravni).
* *GDP_for_year:* bruto domači proizvod države za tisto leto.
* *GDP_per_capita:* bruto domači proizvod na prebivalca države za tisto leto.
* *generation:* generacija (temelji na povprečju starostne skupine).

S pomočjo zgoraj naštetih atributov bomo v vmesnem poročilu podatke prebrali, ter jih vizualno predstavili.

### Pridobivanje podatkov

S preprosto funkcijo smo prebrali podatke iz datoteke "master.csv", v pandas dataframe, s pomočjo katerega smo jih obdelali in prestavili vizualno.

### Nekaj vizualnih predstavitev

Ker je tako velika količina podatkov prevelika da bi iz nje lahko kar tako ugotovili določene zanimive lastnosti, smo se odločili da bomo najprej naredili nekaj grafov da dobimo občutek s čem imamo opravka, in da predstavimo nekatere bolj zanimive podatke.

Spodaj je seznam desetih držav z najvišjo stopnjo samomorov, pri čemer smo uporabili atribut suicides_per_100k, saj le ta ni odvisen od števila prebivalcev, ki jih ima država. 

![Alt text](images/seznam.png?raw=true "Države z največ samomori")


Ugotovili smo, da je slovenija kar visoko na tej lestvici, ter tudi, da je veliko držav na vrhu lestvice severnjaških držav.

Spodaj je število vseh samomorov v podatkovni zbirki, razdeljenih po spolu, kar nam pove, da je stopnja samomorov pri moških več kot trikrat višja kot pri ženskah.

![Alt text](images/sex_difference.png?raw=true "Razlika med spoloma")


Zanimalo nas je ali je BDP povezan s stopnjo samomorov, zato smo za vsako državo izračunali povprečni BDP in poveprečno stopnjo samomorov, s pomočjo česar smo naredili spodnji graf. 

![Alt text](images/GPD_and_suicide_rate.png?raw=true "BDP in samomori")


Iz grafa je razvidno, da revnejše države nimajo nujno tudi višje stopnje samomorov, kot bi marsikdo pričakoval.

Naslednji graf prikazuje število samomorov v vsaki starostni skupini, iz njega pa je razvidno, da je samomorov veliko več pri starejših ljudeh, kar smo tudi pričakovali. Na žalost pa se samomori očitno dogajajo tudi pri zelo mladih, a je le teh znatno manj.

![Alt text](images/starostne_skupine.png?raw=true "Starostne skupine")


Ker nas je zanimalo kako se število samomorov spreminja s časom smo naredili spodnji graf. Število samomorov v posameznih letih na logaritmičnem grafu.

![Alt text](images/po_letih.png?raw=true "število samomorov po letih")


Tu je nekaj zanimivih stvari. Hitro naraščanje samomorov do leta 1995, še posebaj leta 1988 in 1995, potem pa hiter in enakomeren padec. Najbolj presenetljivo pa je leto 2016, kjer je razlika s prejšnjim letom daleč največja.

*Koda za zgoraj pridobljene rezultate se nahaja v datoteki project_code.ipynb(https://github.com/np6818/PR19NPZPTK/blob/master/project_code.ipynb)*
