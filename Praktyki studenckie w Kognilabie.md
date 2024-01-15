---
share: "true"
---

## Lista potencjalnych projektów na okres zastoju

We względu na to, że jeszcze przez 3-4 tygodnie w Kognilab nie planujemy powrotu do przeprowadzania badań z udziałem ludzi, chciałbym zaproponować kilka dodatkowych projektów do wykonania w ramach praktyk studenckich. Projekty te nie są bezpośrednio związane z przeprowadzaniem badań, ale w Kognilabie myśleliśmy o nich od dawna. Oczywiście wykonanie projektów wlicza się do godzin odbytych praktyk.
### Zaprojektowanie systemu *born-open data* dla pracowni Kognilab
W ramach badań prowadzonych w Laboratorium Filozofii Eksperymentalnej "Kognilab" staramy się udostępniać badne badawcze, ale nie zawsze to wychodzi. Problem nie wynika z naszej niechęci do tych praktyk, ale raczej z faktu, że przygotowanie, obróbka i dokumentacja danych badawczych wymaga nakładów czasu i pracy oraz nie wydaje się najważniejszą kwestią podczas prowadzenia badań. Jednym ze sposobów poradzenia sobie z tymi problemami jest zaproponowana przez Roudera (2016) koncepcja danych otwartych od narodzin (*born-open data*). Podstawowa idea jest taka, aby zaprojektować system zbierania i archiwizacji danych w ten sposób, aby dane upubliczniały się automatycznie. Pozwala to wyeliminować słabość moralną czynnika ludzkiego (badaczy) i zwiększyć skuteczność udostępniania danych.

#### Założenia projektowe
1. W pracowni Kognilab prowadzimy zasadniczo dwa typy badań.
	- Badania on-line przeprowadzane przez system do prowadzenia ankiet LimeSurvey (własna instancja, dostępne API)
	- Badania w laboratorium z wykorzystaniem eyetrackingu (w PsychoPy) lub VR (w Godocie)
2. Posiadamy dysk sieciowy typu NAS, na którym można prowadzić archiwizację danych badawczych.
3. Dane udostępniamy z reguły na OSF (Open Science Framerowk), ale o ile wiem OSF ma integrację z GitHubem, co oznacza, że system może być oparty na systemie kontroli wersji Git.
4. Zasadniczo nawet jeśli dane będą "otwarte od narodzin", to należy w wytycznych i w projekcie systemu uwzględnić fakt, że pewne dane będą udostępnione publicznie dopiero po upływie pewnego okresu embargo lub po publikacji oryginalnego artykułu wykorzystującego te dane.
5. Dowolna kombinacja istniejących narzędzi lub nowych narzędzi jest dozwolona. Nie ma specjalnie żadnych ograniczeń co do tego, może oprócz takiego, że preferowane są wolne (lub przynajmniej darmowe) narzędzia.
6. Fajnie byłoby gdyby ewentualne wykorzystane skrypty i programy działały zarówno pod Linuksem jak i Windowsem. A przynajmniej, zeby nie było oczywiste, że nie działają na Linuksie.
7. Dane zbierane przez Kognilab są w różnych formatach. Przykładowe formaty:
	- CSV dla badań ankietowych przez LimeSurveya
	- CSV o zupełnie innej strukturze dla badań behawioralnych w PsychoPy
	- JSON dla eksperymentów w VR
	- HDF5 dla eksperymentów eyetrackingowych
	- XLSX również czasami się pojawia jeśli dane są zbierane w zupełnie customowy sposób
#### *Problemy do rozwiązania*
W ramach praktyk chciałbym zaprosić Państwa do wspólnego zastanowienia się nad tym, jak można ulepszyć praktyki udostępniania danych badawczych. Poniżej krótka lista problemów, które należałoby rozwiązać wraz z potencjalnymi propozycjami rozwiązania

1. W jaki sposób zaprojektować automatycznie udostępnianie danych z badań ankietowych? 
	- można wykorzystać automatyczne API do ściągania danych z LimeSurveya
2. W jaki sposób zaprojektować automatyczne udost,epnianie danych z badań laboratoryjnych?
	- można korzystając z doświadczenia Roudera zaprojektować skrypt, który automatycznie będzie commitował i pushował dane na zewnętrzny serwer Git (np. GitHub)
3. W jaki sposób można rozwiązać problem automatycznej dokumentacji danych?
	- należałoby skonstruować formatkę, w której zawarte byłyby podstawowe meta-dane; być może na podstawie tej formatki dałoby się konstruować plik `README.md` w repozytorium?
	- nie rozwiązuje do problemu opisu zmiennych itp. (zob. propozycja projektu o dokumentowaniu danych badawczych)
4. Jak ustandaryzować strukturę katalogów itp.? W internecie znajduje się sporo propozycji (jak zawsze jest 15 różnych standardów). Mnie fajnym punktem wyjścia (z którego z lenistwa nie korzystam) wydaje się zawsze ta templatka: http://projecttemplate.net/
#### *Deliverables*
1. Rzeczywista implementacja systemu "danych otwartych od narodzin". Może to być np. zbiór skryptów do automatycznego tworzenia i aktualizowania repozytoriów Git dla badań prowadzonych w KogniLabie, ściągania i archiwizowania na Git danych z ankiet i tak dalej. Warto tutaj spojrzeć do artykułów z bibliografii, aby zobaczyć, o co tutaj chodzi. 
2. Dokumentacja stworzonego systemu napisana w taki sposób, aby dało się z niej skorzystać w przyszłości.
3. Poradnik (*How To*) w formie tekstowej i/lub wideo obejmujący postawowe czynności administracyjne takie jak:
	- dodawanie nowych badań do zbioru badań
	- aktualizowania informacji o badaniu
	- podpinaniu repozytoriów Git (lub jakichś innych) do OSF
	
**Bibliografia**
- Rouder, J. N. (2016). The what, why, and how of born-open data. _Behavior research methods_, _48_, 1062-1069.
- Vuorre, M., & Curley, J. P. (2018). Curating research assets: A tutorial on the Git version control system. _Advances in Methods and Practices in Psychological Science_, _1_(2), 219-236.
- Dijkers, M. P. (2019). A beginner’s guide to data stewardship and data sharing. _Spinal Cord_, _57_(3), 169-182.

### Stworzenie standardów dokumentowania danych badawnych dla pracowni Kognilab

Współcześnie coraz większa wagę przykłada się do dokumentowania danych badawczych. Co z tego, że udostępnimy nasze dane społeczności badaczy, jeżeli tylko my wiemy, co one oznaczają i jak z nich korzystać. Oczywiście podobnie jak z udostępnianiem danych, sytuacja z dokumentowaniem ich wygląda podobnie słabo. W literaturze (zob. Arslan 2019, który omawia najpopularniejsze rozwiązania) pojawiły się jednak pewne narzędzia pozwalające ten proces ustandandaryzować (albo lepiej powiedzieć, dostosować się do pewnych istniejących już standardów). Celem tego miniprojektu jest przygotowanie poradnika skierowanego (przede wszystkim) do studentów i członków Laboratorium Filozofii Eksperymentalnej "Kognilab" opisujący korzystanie z narzędzi ułatwiających dokumentowanie danych i opisuj,ace współczesne standardy robienia tego.
#### Założenia projektowe
- przede wszystkim należy skoncentrować się tutaj na badaniach ankietowych i standardowych formatach danych
- poradnik powinien skierowany być do osób niekoniecznie bardzo technicznych (nie wszyscy studenci i pracownicy to mistrzowie programowania)
- poradnik najlepiej byłoby przygotować w formie pisemnej oraz w formie video - w przypadku korzystania z oprogramowania takie poradniki sprawdzają się chyba lepiej (z mojego doświadczenia)
#### *Deliverables*
 - poradniki opisujący standardy oraz narzędzia do dokumentowania danych
 - rozbudowanie istniejącej strony internetowej

**Bibliografia**
- http://dokumentujdane.kognilab.pl/ - obecny projekt strony internetowej
- Arslan, R. C. (2019). How to automatically document data with the codebook package to facilitate data reuse. _Advances in Methods and Practices in Psychological Science_, _2_(2), 169-187.
### Przeanalizowanie danych z IPQ z badań VRowych

W kilku badaniach VRowych korzystaliśmy ze stworzonej przez nas adaptacji kwestionariusza *igroup presence questionnaire*, który ma na celu mierzenie immersywności doświadczeń w wirtualnej rzeczywistości. Dane te jednak są na razie kompletnie niewykorzystane. Zadaniem jest przygotowanie analizy statystycznej tych danych.
#### Założenia projektowe
1. Przeprowadzona analiza statystyczna powinna uwzględniać:
	- statystyki deskryptywne dla analizowanych zbiorów danych
	- podstawowe statystyki dotyczące rzetelności skali (alfa Cronbacha itp.) oraz porównanie z dostępnymi na stronie autorów danymi dotyczącymi rzetelności skali i jej podskal
	- analizę czynnikową danych porównywalną z analizą czynnikową przeprowadzoną przez autorów oraz porównanie z dostępnymi na stronie autorów danymi dotyczącymi struktury skali i jej podskal
#### *Deliverables*
1. Skonstruowany w RMarkdown albo w Jupyter Notebook raport statystyczny wraz z omówieniem wyników.

- https://igroup.org/pq/ipq/index.php - informacje na temat kwestionariusza

