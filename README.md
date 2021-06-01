# seat-reservation
## Aplikacja do zarzÄ…dzania rezerwacjÄ… miejsc.

### Cel zadania
Celem zadania jest stworzenie aplikacji internetowej, wykorzystujÄ…c biblioteki: React, Redux (lub inne rozwiÄ…zanie implementujÄ…ce architekturÄ™ flux) oraz dowolny wybrany przez siebie istniejÄ…cy design system (np. ant.design).
W repozytorium, w katalogu mockups znajdziesz wizualizacje poszczegÃ³lnych stron, ktÃ³re powinny zostaÄ‡ zaimplementowane w aplikacji.

Mile widziane bÄ™dzie pokrycie kluczowych funkcjonalnoÅ›ci testami jednostkowymi.

RozpoczynajÄ…c prace polecamy skorzystaÄ‡ z generatora dostarczonego przez React, wykorzystujÄ…c szablon redux:
```
npx create-react-app my-app --template redux
```

### Wytyczne

W pierwszym etapie aplikacja powinna pytaÄ‡ o liczbÄ™ miejsc do zarezerwowania oraz czy miejsca powinny byÄ‡ obok siebie (patrz wizualizacja poniÅ¼ej).

![mockups/page_1.png](mockups/page_1.png)

NastÄ™pnie naleÅ¼y pobraÄ‡ z API dostÄ™pne miejsca. W repozytorium dostÄ™pny jest przykÅ‚adowy serwer, ktÃ³ry moÅ¼na uruchomiÄ‡ za pomocÄ…:  
```
npm run api
```

PowyÅ¼ej wspomniany serwer dostarcza endpoint `/seats`, ktÃ³ry zwraca wszystkie miejsca oraz ich poÅ‚oÅ¼enie. Jedno miejsce posiada nastÄ™pujÄ…ce informacje:
```javascript
const seat = {
   id: 's01', // id miejsca
   cords: { // koordynaty, liczone od zera
      x: 0,
      y: 1,
   },
   reserved: false, // boolean - czy miejsce jest juÅ¼ zarezerwowane
};
```

Na podstawie tych danych, powinna zostaÄ‡ wyÅ›wietlona graficzna reprezentacja sali (patrz wizualizacja poniÅ¼ej).
![mockups/page_2.png](mockups/page_2.png)

Aplikacja na tym etapie powinna proponowaÄ‡ miejsca uÅ¼ytkownikowi. JeÅ¼eli zostaÅ‚a wybrana opcja, Å¼e miejsca powinny znajdowaÄ‡ siÄ™ obok siebie, naleÅ¼y zaproponowaÄ‡ takie miejsca, ktÃ³re nie bÄ™dÄ… oddzielone od siebie pustÄ… przestrzeniÄ… oraz innym, juÅ¼ zajÄ™tym miejscem.

Dodatkowo widok sali powinien byÄ‡ "klikalny" - powinna istnieÄ‡ moÅ¼liwoÅ›Ä‡ edycji i ponownego wyboru miejsc. Operacje uÅ¼ytkownik zatwierdza przyciskiem â€žRezerwujâ€ (stan rezerwacji naleÅ¼y zapamiÄ™taÄ‡ wyÅ‚Ä…cznie lokalnie, w store).

Na koniec powinna zostaÄ‡ wyÅ›wietlona strona z podsumowaniem (wizualizacja poniÅ¼ej)

![mockups/page_3.png](mockups/page_3.png)
