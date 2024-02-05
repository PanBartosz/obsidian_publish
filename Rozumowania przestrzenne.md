---
share: "true"
---

## Badania drugie czyli *względna rama odniesienia*
1. W oryginalnym badaniu testowane były następujące pozycje obiektów targetowych: 0, 30, 60, 90, 120, 150, 180, 240 i 330 stopni. 270 stopni było pominięte ze względu na to, że obracanie się na krześle dokładnie do tyłu jest bardzo akrobatyczne i baliśmy się, że badani (w często nowej dla siebie sytuacji badania + VRu) mogą sobie zrobić krzywdę i szyję lub kręgosłup usiłując to zrobić. W obecnym badaniu postanowiłem zredukować liczbę "startowych" pozycji do 0, 45, 90, 135, 180, 225 i 315 stopni. Cały czas pozycja dokładnie-za-badanym jest nielegalna. Oczywiście decyzja taka sprawia, że ewentualne wyniki będą mniej drobnoziarniste, ale może to nie jest wielki problem (na pewno nie tak wielki, jak kolejny problem). Pytanie: czy da się to zrobić racjonalniej/lepiej?
2. Dla poszczególnych relacji przestrzennych ("na prawo od", "na lewo od", "przed", "za") skonstruowałem listy offsetów pierwszego obiektu względem drugiego. Zasadniczo kolejne pozycje obiektów idą co 45 stopni i przedstawiają się tak:
	1. "na prawo od": 0, -45, -90, -135, -180
	2. "na lewo od": 0, 45, 90, 135, 180
	3. "przed" i "za": 0, 45, 90, 135, 180, 225,  270, 315
	W przypadku dwóch pierwszych relacji prawdopodobnie 0 można wyrzucić (bo tutaj raczej nic innego niż "falsz" nie jest możliwe) interesujące mogą być za to warunki z drugim obiektem 180 (czyli po zupełnie drugiej stronie obiektu). Mam taką intuicję, że wyglądać to będzie inaczej w zależności od tego, gdzie jest pierwszy obiekt - np. jeśli będzie para obiektów na wprost i za badanym, to nieco inaczej ludzie będą oceniać "na prawo od" i "na lewo od" niż wtedy, gdy obiekty będą po prawej i lewej stronie badanego. Jeśli chodzi o "przed" i "za" to zupełnie nie mam intuicji. Na pewno różnica ich odległości względem badanego będzie istotna (o tym późnej), ale myślę, że przy skrajnych kątach (180 stopni offsetu) mogą ujawnić się ciekawe przejścia do innej ramy odniesienia. Znów: problem jest taki, czy da się to zrobić racjonalniej/lepiej?
3. Jeśli chodzi o dystanse, to zredukowałem 3 możliwe dystanse od badanego (30, 60 i 90) do dwóch (30 i 60). Głownie po to, aby zmniejszyć liczbę kombinacji warunków eksperymentalnych. Dla każdej relacji przestrzennej zrobiłem listy par (pierwszy obiekt - drugi obiekt) dystansów, które mają moim zdaniem sens:
	1. "za" : 30, 60
	2. "przed" : 60, 30
	3. "na prawo od" i "na lewo od": 30, 60; 60, 30; 30, 30; 60, 60
	Idea jest tutaj trochę taka, że dla "za" i "przed" przy większości pozycji (praktycznie wszystkich, oprócz skrajnych) liczyć się będzie to, który jest dalej, a który jest bliżej. Nie ma moim zdaniem sensu dawać tych obiektów w tej samej odległości od badanego. Jeśli chodzi o "na prawo od" i "na lewo" od, to wszystkie kombinacje wydają mi się badawczo interesujące (szczególnie przy różnych offsetach może różnie wychodzić!). Pytanie jest takie, czy 2 możliwe pozycje są tutaj wystarczające. Dodatkowo jeśli w warunkach "na prawo od" i "na lewo od" offset wynosi 0, to nielegalne są identyczne pozycje (30,30 i 60,60), ponieważ to by skutkowało dwoma obiektami w tym samym miejscu (niezbyt interesujące).
	