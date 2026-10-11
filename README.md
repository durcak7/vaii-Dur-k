# Názov projektu

Ondrej Durčák
5ZYI31

## Stručný opis projektu
Webová aplikácia FloorballPro je špecializovaný e-shop zameraný na predaj florbalového vybavenia, ako sú florbalové hokejky, čepele, loptičky, brankárska výstroj a príslušenstvo. Hlavným účelom aplikácie je poskytnúť hráčom, klubom a nadšencom prehľadný nákupný portál s pokročilým filtrovaním produktov podľa technických parametrov (tvrdosť palice, dĺžka, zahnutie).
Prevádzkovateľ má k dispozícii administrátorské rozhranie na správu katalógu, skladových zásob a vybavovanie zákazníckych objednávok.

## Role v projekte
Návštevník: neprihlásený používateľ, ktorý si môže prezerať katalóg produktov, filtrovať ich, čitať podrobné popisy a pridávať tovar do nákupného košíka.
Zákazník (Registrovaný používateľ): Môže sa prihlásiť, vytvárať objednávky, sledovať históriu svojich nákupov, spravovať svoje doručovacie údaje a písať recenzie na zakúpené produkty.
Správca (Admin): Spravuje celý e-shop – pridáva, upravuje a maže produkty a kategórie, schvaľuje a aktualizuje stavy objednávok (napr. Nová -> Pripravuje sa -> Odoslaná) a spravuje používateľov.

## Prípady použitia podľa rolí
Návštevník vyhľadá florbalovú palicu podľa značky a tvrdosti (flexu) pomocou filtra.
Zákazník si vytvorí objednávku vybraného vybavenia vrátane zadania adresy a výberu spôsobu platby.
Zákazník si prezrie zoznam svojich predchádzajúcich objednávok a ich aktuálny stav v používateľskom profile.
Správca pridá nový produkt (napr. novú hokejku) do katalógu vrátane nahratia jej produktovej fotografie.
Správca zmení stav existujúcej objednávky zákazníka priamo v administračnom rozhraní.

## Plánované entity
User (Používateľ): Uchováva prihlasovacie údaje, meno, e-mail, heslo a rolu používateľa.   
Category (Kategória): Evidencia kategórií produktov (palice, loptičky, tašky).
Product (Produkt): Evidencia tovaru (názov, popis, cena, skladová zásoba, tvrdosť/dĺžka, produktová fotografia, väzba na kategóriu).
Order (Objednávka): Záznam o nákupe (dátum vytvorenia, celková suma, stav objednávky, väzba na používateľa).
OrderItem (Položka objednávky): Prepojenie M:N medzi objednávkou a produktmi, ktoré uchováva objednané množstvo a cenu v čase nákupu. 

## Vzťahy medzi entitami
Category 1 : N Product (Jedna kategória zahŕňa viacero produktov, napr. v kategórii "Hokejky" je veľa rôznych hokejok).
User 1 : N Order (Jeden používateľ môže vytvoriť viacero nákupných objednávok).
Order M : N Product (Jedna objednávka môže obsahovať viacero produktov a jeden produkt môže byť v rôznych objednávkach – realizované cez asociačnú tabuľku OrderItem).

## Hlavné stránky aplikácie
Úvodná stránka (Home): Privítanie, výber najpredávanejších produktov a rýchla navigácia do kategórií.
Katalóg produktov: Zoznam všetkých produktov s možnosťou filtrovania podľa kategórií.
Detail produktu: Podrobnosti o vybranom vybavení, fotogaléria, cena a tlačidlo na pridanie do košíka.
Nákupný košík a pokladňa: Prehľad vybraných položiek, zadanie údajov a odoslanie objednávky.
Moje objednávky (Profil): Zákaznícka sekcia s históriou a stavom nákupov.
Administrácia: Správa produktov, kategórií a objednávok pre správcu.

## Rozdelenie funkcionality
Základné funkcie:
  Používateľská autorizácia a správa rolí (návštevník, zákazník, správca).
  CRUD operácie nad vybranými entitami (správa produktov a kategórií).   
  Práca so súbormi (upload produktových fotografií).   
  Minimálne dve AJAX volania (filtrovanie produktov a zmena stavu objednávky).   
  Responzívny dizajn s vlastným CSS a JavaScript validáciou.  
Rozširujúce funkcie:
  Použitie JS frameworku na interaktívny košík.  
  Pokročilá klientska kontrola formulárov. 
