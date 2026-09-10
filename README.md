# Budin Barrel sajt

Ovo je sajt za Budin Barrel, porodičnu rakiju destileriju Vasiljević iz Smedereva. Sajt je čist HTML, CSS i JavaScript, bez ikakvog frameworka i bez build procesa. Otvoriš fajl i to je to, radi. Hostuje se na Netlify.

## Šta se nalazi u repozitorijumu

- `index.html` - ceo sajt, jedna stranica. Sve sekcije (početna, priča, proizvodi, forma za porudžbinu) su u ovom fajlu, CSS i JavaScript su takođe unutra, nema odvojenih .css ili .js fajlova.
- `uslovi-koriscenja.html` - uslovi korišćenja, povezano iz footera i iz forme za porudžbinu.
- `politika-privatnosti.html` - politika privatnosti, isto povezano iz footera i forme.
- `robots.txt` - govori pretraživačima (Google i slično) da mogu da čitaju sajt.
- `sitemap.xml` - spisak stranica za Google, da ih brže nađe.
- `images/` - sve slike sa sajta. Imena fajlova u ovom folderu moraju da se poklapaju sa onim što piše u `index.html` (npr. `images/proces2.jpg.jpg`), inače se slika ne prikazuje.

Svih pet fajlova (index, uslovi, politika, robots, sitemap) mora da stoji u root-u repozitorijuma, ne u nekom podfolderu, jer se međusobno pozivaju preko relativnih putanja.

## Kako sajt radi iznutra

Nema baze podataka i nema servera koji nešto računa. Korpa (šta je kupac dodao, koliko komada) čuva se u browseru kupca, u localStorage-u - to znači da ako kupac zatvori sajt i vrati se sutra na istom telefonu, korpa je ostala kakva je bila, ali ta korpa ne postoji nigde na serveru niti je vidiš ti.

Srpski i engleski tekst su oba upisana u HTML, samo se jedan sakriva a drugi prikazuje kad se klikne na dugme za jezik. Zato u kodu skoro svuda ideš na dva para tagova, jedan sa `data-sr` i jedan sa `data-en`.

Za porudžbinu se koristi Netlify Forms. To znači da nema pravog backend-a koji prima porudžbinu, nego Netlify sam prepozna formu kad se sajt deployuje (zato u formi postoji `data-netlify="true"` i skriveno polje `form-name`) i čuva svaku porudžbinu u svom sistemu. Tu je i jedno skriveno polje za honeypot, to je trik protiv botova, ne dira se.

## Šta MORA da se uradi posle svakog deploya (ili bar prvog)

Ovo je najvažnija stvar i lako se zaboravi. Netlify ne šalje automatski mejl kad neko popuni formu. Treba ručno otići u Netlify panel:

Site settings > Forms > Form notifications > Add notification > Email notification

i uneti mejl na koji treba da stižu porudžbine. Bez ovog koraka, porudžbine samo sede u Netlify panelu i niko ih ne vidi na mejlu.

## Netlify kredit sistem, da se ne iznenadim

Netlify sad radi na kreditima, ne na starom sistemu gde je bilo tačno 100 besplatnih porudžbina mesečno. Slanje porudžbina preko forme je sada besplatno i bez ograničenja. Ono što i dalje troši kredite je sav ostali saobraćaj na sajtu (posete, slike koje se učitavaju, svaki novi deploy). Besplatan plan ima 300 kredita mesečno za sve to zajedno. Ako se potroše, ceo sajt se gasi do sledećeg meseca, ne samo forma. Prvih par nedelja posle lansiranja vredi proveriti Usage & billing u Netlify panelu, da vidim gde stojim. Ako bude tesno, Personal plan je 9 dolara mesečno i daje 1000 kredita.

## Pravni deo

`uslovi-koriscenja.html` i `politika-privatnosti.html` su startna verzija, napisani da pokriju osnovne stvari (uzrast, porudžbina, dostava, obrada podataka). Nisu pravno proveravani. Kad porudžbine krenu ozbiljnije, trebalo bi da ih pregleda knjigovođa ili pravnik, pogotovo deo oko prodaje alkohola.

## Kako da dodam novi proizvod

U `index.html`, u delu sa proizvodima, svaka kartica proizvoda je jedan blok sa klasom `prod reveal`. Najlakše je da kopiram ceo takav blok za neki postojeći proizvod, nalepim ga, promenim `data-product-id` na nešto novo i jedinstveno, promenim tekst, cenu i sliku, i onda taj isti `data-product-id` dodam i u JavaScript deo gde piše `PRODUCTS`, sa cenom, da bi se cena i naziv pravilno prikazali u korpi i u mejlu koji stigne.

## Kako da testiram lokalno

Najprostije, samo duplim klikom otvorim `index.html` u browseru. Forma za porudžbinu neće raditi kako treba dok sajt nije na Netlify-ju (jer Netlify Forms radi samo na deployovanom sajtu), ali sve ostalo, izgled, korpa, proizvodi, jezik, može da se proveri i lokalno.
