
Acest site foarte simplu constă într-un container cu două elemente, un aside și un section. Deschide acest bin pentru a-l vedea în acțiune: exemplu de layout static.

Încearcă să redimensionezi zona "Output". După cum poți vedea, lățimea elementelor este fixă. Dacă fereastra browserului devine mai mică decât lățimea containerului, restul site-ului este pur și simplu decupat. Haide să îndreptăm aceasta prin convertirea fiecărei unități de lungime absolută în CSS la una relativă.

Formula magică
Pentru a ne da seama de valoarea relativă a unui element, trebuie să urmezi pașii:

Găsește valoarea statică a elementului.
Dă-ți seama ce element se comportă ca și context pentru elementul-țintă și găsește-i valoarea statică.

Aplică formula
Hotărăște ce unitate relativă folosești în context.

Haide să începem cu cele ușoare din exemplul nostru și să transformăm elementele aside și section. Pentru ambele, contextul este .container. Înlocuiește aceste valori în formula:

target ÷ context = result

Convertirea containerului
Iată o întrebare mai complicată: care este contextul containerului? În termeni de lățime și înălțime, ar fi părintele lui, elementul body care ocupă întreaga fereastră. Dar care este dimensiunea statică a ferestrei? Pe calculatorul meu, cu o fereastră de browser cu lățimea completă, lățimea este 1440px. Pe calculatorul tău, este probabil să fie altceva. În regulă, și acum?

Chestia este că nu trebuie să răspunzi la această întrebare. Dacă lucrezi cu un designer, acesta îți va spune dimensiunea ecranului la care lucrează, și, dacă lucrezi de unul singur, poți proceda la fel. De exemplu, am realizat acest demo pe pânză de 1440px pe 798px. Aceste dimensiuni se vor comporta ca o dimensiune statică a ferestrei noastre particulare.

Cunoscând acestea, poți converti cu ușurință numerele: 1368/1440 = 0,95 pentru lățime și 400/798 = 0,5013 pentru înălțime. Deoarece elementul .container ar trebui să fie relativ la fereastra însăși, folosește unitățile ferestrei pentru a declara dimensiunea lor respectivă:

Iată, layoutul este aproape în întregime responsiv. Dacă încerci să redimensionezi acum "Output" și te uiți mai atent, poți vedea că unele părți încă pot fi decupate dacă fereastra este prea îngustă. Aceasta se întâmplă din cauza ultimelor două unități statice; marginile elementelor imbricate și padding-ul lui .container.

Atât aside, cât și section au o margine dreaptă de 15px. Contextul lor este containerul, care face formula următoare: 15/1368 = 0,01096. Aceasta este încă o dată o treabă pentru unitatea procent:

Dar ce se întâmplă cu padding-ul pe .container? În acest caz, ținta este padding-ul însăși, care este aria dintre conținut și bordură. Tehnic, se află încă în interiorul unui element. Aceasta înseamnă că, bineînțeles, contextul pentru padding-ul unui element este elementul însuși. Deci, formula este la fel ca mai sus, iar rezultatul este acesta: