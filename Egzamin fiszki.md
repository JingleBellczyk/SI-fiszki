#si 

## 1. Temat 1 
2 definiujące perspektywy ai
?
1. budowanie modeli/systemów naśladujacych ludzki mózg
2. konstruowanie algorytmów do rozwiązywania problemów trudnych dla ludzi, w sposób zbliżający się do człowieka

dedukcja
?
1. od ogółu do szczegółu
2. pozwala wyciągnąć prawidłowe wnioski
3. wnioskowanie (to co się dowiemy jest już w danych, tylko trzeba jakoś to wyciągnąć)

indukcja
?
1. Od szczegółu do ogółu
2. często wyciągamy błędne wnioski
3. uczenie (na podstawie doświadczeń wyciągamy wiedzę, która jest tylko tak dobra jak doświadczenia)

wnioskowanie vs uczenie

wnioskowanie: baza wiedzy->twierdzenia ->prawdziwe wnioski(bo z dedukcji)
uczenie:wnioskowanie statystyczne z uogólnieniami i indukcją ->powstają reguły np. Dużo stworzeń morskich składa jaja, więc wszystkie stworzenia morskie to robią(nieprawdziwe)

2 metody wnioskowanie dedukcyjnego
?
1. przeszukiwanie grafów: 
	1. Start – aktualny stan naszego świata
	2. Koniec (cel) – stan pożądany, do którego chcemy dojść (np. znamy jego właściwości)
	3. Rozwiązanie – sposób przekształcenia stanu obecnego w stan docelowy
	Wyzwanie: rozwiązanie uniwersalne, dla wielu zastosowań
	Formalnie: szukamy ścieżek w grafie skierowanym gdy znamy tylko węzeł początkowy i docelowy
	Strategia wyszukiwania – w jaki sposób wybierać kolejne węzły
	Ogólnie mamy zbiór (front) do którego wkładamy kolejne węzły, i na podstawie strategii wybieramy który brać pierwszy
2. Logika symboliczna(metody algebraiczne) - matematyczne udowadanianie - wnioskowanie, przekształcanie symboliczne a=>b

schemat(składniki) wnioskowania dedukcyjnego
?
1. teoria - baza wiedzy(fakty)
2. wnioskowanie logiczne - weryfikacja hipotez, rozumowanie o nowych faktach w bazie wiedzy

słabości wnioskowania dedukcyjnego
?
1. nie może wywnioskować niekompletnych przesłanek
2. wszystkie wnioski są już w jakiś sposób zawarte w bazie
3. fakty w bazie wiedzy mogą się zmieniać, powstają nowe, więc system może nie nadążać, dając stare wnioski

programy do wnioskowania dedukcyjnego
?
MYCIN - system ekspertowy medyczny
Deep Blue - system do szachów
Systran - system tłumaczenia maszynowego

metoda uczenia indukcyjnego
?
algorytm tworzący uogólniającą hipoteze na podst. zestawu konkretnych przykładów
np. 
1. Start - forma(hipoteza) ogólna: Wszystkie zwierzęta mają zęby, które mogą być klasyfikowane jako kły, siekacze lub trzonowce.
2. Uczenie się szczegółów np parametrów - zęby, włosy
3. Hipoteza(Reguła): Probability(herbivores) = f(Canine teeth length, Claw length) - zawiera podobieństwa zwierzą

przykłady zastosowania uczenia indukcyjnego
?
1. AI
2. rozpoznawanie obrazu, mowy, tłumaczenie maszynowe, inteligente konrtolery

wyzwania uczenia indukyjnego
?
przez to że ostateczne reguły mogą nie być prawdziwe to: 
1. wiarygodność
2. wyjaśnialność
3. uczenie oparte o ograniczoną liczbę przykładów

połączenie podejścia indukcyjnego i dedukcyjnego
?
- indukcyjne uczenie
- dedukcyjne wnioskowanie

co to SI
?
- sposób na symulację ludzkiego mózgu - procesów myślenia, zdolności rozwiązywania problemów, modelowanie mózgu
- sposób na rozwiązanie problemów trudnych dla człowieka
	- NP-trudne
	- problemy optymalizacyjne
	- wynik i wydajność

test turinga
?
człowiek pyta człowieka i maszyne różne rzeczy, a potem człowiek ma rozpoznać, który to maszyna

z czego składa się problem
?
1. zbiór danych, opisujące problem
2. zbiór operacji(akcji), które mogą być wykonane, by dojść do rozwiązania
3. cel - czym jest rozwiązanie problemu

agent do rozwiązywania problemów
?
- działa autonomicznie
- posiada percepcję, poprzez sensory, jak człowiek
- może aktualizować swój stan wiedzy, zdobytej przez sensory
- może współdziałać z otoczeniem

typy problemów zw. ze środowiskiem, z perspektywy agenta, który ma je rozwiązać:
?
●       **Dostępne i niedostępne** – czy mamy kompletną informację np. w pokerze nie
●       **Deterministyczne(następny stan = stan bieżący + akcje) i niedeterministyczne** – pewność następnego stanu, czasami nie wiemy co dokładnie da jakaś akcja
●       **Epizodyczne(niezależność epizodów) i nieepizodyczne(zależność epizodów)** – brak ciągu przyczynowo skutkowego? (to epizodyczne)
●       **Statycznie i dynamiczne** – upływ czasu
●       **Dyskretne i ciągłe**

typy problemów, niezależnie od środowiska
?
1. pojedynczego stanu
	- środowisko w pełni dostępne
	- rezultaty akcji znane
2. wielu stanów
	- środowisko nie w pełni dostepne
	- rezultaty akcji znane
3. problem niepewności
	- rezultaty niepewne


![[Pasted image 20240630094607.png]]?
1. **Kroki algorytmu:**
    
    - **state ← UPDATE-STATE(state, percept):** Aktualizacja opisu bieżącego stanu świata na podstawie percepcji (percept).
    - **if seq is empty then:**
        - **goal ← FORMULATE-GOAL(state):** Formułowanie celu na podstawie bieżącego stanu.
        - **problem ← FORMULATE-PROBLEM(state, goal):** Formułowanie problemu na podstawie bieżącego stanu i celu.
        - **seq ← SEARCH(problem):** Wyszukiwanie sekwencji akcji, które rozwiążą sformułowany problem.
        - **if seq = failure then return a null action:** Jeśli wyszukiwanie zakończy się niepowodzeniem, zwróć null (brak akcji).
    - **action ← FIRST(seq):** Pobranie pierwszej akcji z sekwencji akcji.
    - **seq ← REST(seq):** Aktualizacja sekwencji akcji, usunięcie wykonanej akcji.
    - **return action:** Zwrócenie wybranej akcji do wykonania.
    Co robi ten algorytm?
1. **Aktualizuje stan świata:** Na podstawie percepcji agent aktualizuje swoje wewnętrzne wyobrażenie stanu świata.
2. **Formułuje cel i problem:** Jeśli sekwencja akcji jest pusta (agent nie ma planu), formułuje nowy cel i problem, który wymaga rozwiązania.
3. **Wyszukuje sekwencję akcji:** Na podstawie sformułowanego problemu, algorytm wyszukuje sekwencję akcji, które powinny doprowadzić do osiągnięcia celu.
4. **Wykonuje akcję:** Pobiera pierwszą akcję z sekwencji i wykonuje ją.
5. **Aktualizuje sekwencję akcji:** Po wykonaniu akcji, aktualizuje sekwencję, usuwając wykonaną akcję.

elementy grafu
?
1.        Łuk <n1,n2>, wychodzi z n1 i wchodzi do n2, krawędz skierowana
2.        Sąsiedztwo jeśli istnieje łuk <n1,n2> to n1 jest dla n2
3.        Ścieżka -  ⟨n0,n1,...,nk⟩ - istnieje sekwencja łuków
4.        Cykl - ⟨n0,n1,...,nk⟩, gdzie n0=nkn0 = nkn0=nk i k≠0
5.        Ścieżka – p (w drzewie) – optymalne rozwiązanie to cost(p) < cost(p')
6.        WRdP – wsp rozgałęzienia do przodu – ile wychodzi z wezla
7.        WRW – ile wchodzi do wezla
8. Koszt - dodatnia luczba przypisana do łuku cost(<ni,nj>)
9. Koszt ścieżki p, cost(p) =  cost(<n0,n1>) + ... +  cost(<ni,nj>)

SGA
?
skierowany graf acykliczny

drzewo
?
sga z korzeniem(węzeł bez łuków wchodzących), każdy inny węzeł ma 1 wchodzący, liście - węzły bez wychodzący
- jeśli dla każdego węzła WRW(wchodzące) = b, wtedy istnieje bn węzłów o odległości równej n łuków od dowolnego węzła.

problem jako graf
?
- zdefiniowanie węzłów początkowych i docelowych
- rozwiązanie to ścieżka od start do end(przeprowadzamy test celu żeby się dowiedzieć czy skończyliśmy)

Składniki przestrzeni stanów - stany które można osiągnąć w ramach jakiegoś problemu
?
1.        Zbiór stanów
2.        Podzbiór stanów początkowych
3.        operatory na stanach, żeby zmienic 1 stan w 2
4.        Cel – docelowy stan
5.        Kryterium akceptowalności rozwiązań – miara jakości- czy zadowalające rozwiązanie

Ogólny algorytm przeszukiwania
?
- stopniowe rozszerzanie do puntku wyjścia
- strategia – okresla które wezly przeszukiwac
- Ogólnie mamy zbiór (front) do którego wkładamy kolejne węzły, i na podstawie strategii wybieramy który brać pierwszy

Strategie przeszukiwania
?
1. niepoinformowane - ślepe, bez heurystyki
	1. w głąb
	2. wszerz
	3. najniższego kosztu
2. poinformowane - heurystyczne
3. przeszukiwanie z przeciwnikiem - niepewność spowodowana przez drugiego agenta
4. rozwiązywanie problemów z ograniczeniami(CSP)

Ocena strategii przeszukiwania
?
●       Kompletność - jeżeli tylko istnieje rozwiązanie, algorytm gwarantuje znalezienia go w skończonym czasie.
●       Optymalność - gdy znajdzie rozwiązanie, jest to najlepsze rozwiązanie
●       Złożoność
	o   Czasowa w najgorszym przypadku – maksymalna długość ścieżki, maksymalny/średni współczynnik rozgałęzienia do przodu (ile łuków wychodzi z danego węzła, rozgałęzienie wstecz to ile wchodzi do węzła)
	o   Pamięciowa w najgorszym przypadku – maksymalna liczba węzłów na froncie


strategia przeszukiwania  - W głąb(DFS)
?
![[Pasted image 20240630101006.png]]
- kolejka to stos - filo
- niekompletny i nieoptymalny
- o   Złożoność
	- czasowa: O(bd)
	-  pamięciowa: O(bd)
	- b - współczynnik rozgałęzienia, d - głębokość przeszukiwania
- ma odmianę iteracyjny DFS, kompletny i optymalny


strategia przeszukiwania  - wszerz?
![[Pasted image 20240630101213.png]]
- fifo kolejka
- kompletny
- optymalny - o ile koszty niemaleją wraz z głębokością
- Złożoność
	- czasowa: O(bd)
	-  pamięciowa: O(b)
	- b - współczynnik rozgałęzienia, d - głębokość przeszukiwania
- Ma odmianę dwukierunkową, która zaczyna poszukiwanie od węzła startowego i końcowego, wtedy spotkają się gdzieś po środku : O(b^(d/2))

strategia przeszukiwania - najniższego kosztu
?
o   Podobnie jak wszerz ale kolejka priorytetowa wybierająca ten o najniższym koszcie
o   Koszt ścieżki – suma kosztów łuków
o   Gwarantuje optymalne rozwiązanie jeśli koszt łuku to liczba dodatnia, współczynnik rozgałęzienia jest skończony i rozwiązanie istnieje
o   to jak te tramwaje robiliśmy

problemy przeszukiwania niepoinformowanego
?
Problemem są powroty – czyli wielokrotnie sprawdzanie tych samych węzłów
	●       **Blokada generacji stanu identycznego z poprzednikiem** – przed dodaniem nowego stanu do przestrzeni przeszukiwania, sprawdzane jest czy istnieje
	●       **Cykle o jednym łuku** -blokowanie a do b i potem b do a
	●       **Blokada generacji ścieżek zawierających cykle** – blokowanie dowolnych ściezek zawierajacycjh cykle

Funkcja heurystyczna(heurystyka)
?
- funkcja heurystyczna h(n) zawiera informację o węźle czy jest on obiecujący - zwraca nieujemny koszt ścieżki z węzła n do celu
- jest **akceptowalna** jeśli h(n) jest mniejsza lub równa najmniejszej bieżącej wartości rzeczywistej funkcji kosztowej z węzła n do celu : chodzi o to ze np. n = Hłaski cel = faktory, heursytyka np. euklidesowa to odl., ale w rzeczywistosci jest to wieksza wartosc, czyli heurystyka nie może być gorsza niż prawdziwa wartosc - nie zawyża kosztu
- mówi w którym kierunku iść do celu, z redukcją kosztów
- cechy
	- niepewność wyniku
	- dostępna niepełna wiedza
	- poprawia uzyskiwanie rozwiązania
- jakość heurystyki - efektywny współczynnik rozgałęzienia b*, N = 1 + b* + (b*)2 + ... + (b*)d
- dla A*, d=5, N=52, b*=1.91

Strategie wykorzystujące heurystyki
?
-  Najlepszy pierwszy (best -first search)
	- wybierasz węzeł o najlepszej **wartości heurystyki,** tylko według niej.
	-  Niekompletny i nieoptymalny
-  A*
		o   bierze pod uwagę **koszt ścieżki i wartość heurystyki**
		o   Akceptowalny i optymalny.
		o   Optymalny gdy
			▪        rozwiązanie istnieje,
			▪        skończony współczynnik rozgałęzienia – istnieje skonczona liczba wezlow
			▪        koszt łuków większy od pewnego Epsilon>0(czyli każdy łuk musi mieć koszt>0),
			▪        funkcja heurystyczna jest dolną granicą rzeczywistego zbioru – nieprzeszacowuje – jest **akceptowalna**
			▪         funkcja heurystyczna jest optymistyczna czyli daje wynik równy(koszt) lub mniejszy, przez co algorytm rozważa inne potencjalnie optymalne rozwiązania
			- aktulany koszt + estymowany koszt do celu czyli: f(w)=g(w)+h(w)
			- gdy h = 0. i cost(w1,w2)(koszt przejścia z w1 do w2)=1, to A* zachowuje się jak BFS

**Wynajdywanie heurystyk:**
?
●       Relaksacja problemu – upraszczanie ograniczeń, np. opuszczanie jednego lub kilku ograniczeń. W przypadku tramwajów ograniczeniem jest to że musimy poruszać się tak jak są przystanki a dla euklidesowej heurystyki zakładamy że możemy iść w linii prostej
●       Kombinacja akceptowalnych heurystyk
●       Kombinacja liniowa cech – można dobrać wartości współczynników poprzez uczenie maszynowe, wtedy mamy jakieś przybliżenie dla określonego stanu
●       Korekta heurystyki na bazie informacji statystycznej – np. gdy h(x) = 14 to w 90% rzeczywiście jest 18, można wtedy dostosować heurystykę

heurystyka konturowa
?
dobra dla A*

problemy A*
?
- duża złożoność pamięciowa
- Zawsze znajduje optymalne rozwiązanie i jest to pierwsze rozwiązanie znalezione, jeśli: 
	- rozwiązanie istnieje, 
	- współczynnik rozgałęzienia jest skończony (każdy węzeł ma skończoną liczbę sąsiadów), 
	- koszt łuków jest większy niż pewne ε>0, 
	- h(n) jest dolną granicą rzeczywistego minimalnego kosztu ścieżki z najniższym kosztem z n węzła docelowego - heurystyka jest optymistyczna

Zoptymalizowane A*
?
1. **Iterative Deepening A* (IDA***) – jest to połączenie A* i iteracyjnego przeszukiwania w głąb (IDDFS, wspomniane wcześniej), **używa ograniczenia na f =** funkcja kosztu + funkcja heurystyczna, idzie w głąb aż przekroczy limit na f.
	- Kompletny i optymalny
		**złożoność pamięciowa bf*/d, where b – a branching factor, f* – the optimal path cost, d – the lowest cost of a operator**
1. **Simplified Memory-bounded A* (SMA*)** – IDA* bardzo często przeszukuje te same stany **kilkukrotnie** bo to DFS, SMA* tego nie robi (jeśli pamięć pozwala). Przechowuje jakąś ograniczoną ilość węzłów w pamięci. Gdy pamięć jest pełna usuwa najpłytsze węzły o najwyższym koszcie. Koszt usuniętego węzła jest przechowywany w rodzicu aby później móc do niego wrócić. Gdy wyczerpie możliwość rozwijania, wraca do tego co usunął o najniższym koszcie.
- Jest optymalny gdy pamięć pozwala na przechowanie najkrótszej ścieżki, w przeciwnym razie zwraca częściowe rozwiązanie.

Local Search
?
Czasami nie potrzeba całej ścieżki do celu, tylko dotarcie do stanu celu, odbywa się to poprzez poprawianie poszczególnych stanów na podstawie funkcji celu (jak dobry jest nasz stan w porównaniu do celu).
Możemy sprawdzać:
●       Dystans – np. jak wiele zmian potrzeba
●       Podobieństwo – jak wiele cech mamy pasujących
●       Różnicę – np. w wartości funkcji celu
Wprowadza się czasem funkcję straty zamiast celu (loss), im mniejsza tym lepsza
- **Local search zależy jedynie od  lokalnej charakterystyki stanów (tego typu pytanie było na egzaminie)**
- Przykład Przeszukiwania Lokalnego – wspianie w gore – żeby dotrzec do aktualnego najwzywszego punktu
- Wyobraźmy sobie, że próbujesz znaleźć najwyższy szczyt w górzystym terenie, ale możesz widzieć tylko to, co jest bezpośrednio wokół ciebie. Zaczynasz w losowym miejscu i za każdym razem wspinasz się na wyższy punkt, który widzisz w pobliżu. W ten sposób powoli zbliżasz się do najwyższego punktu, nie śledząc całej trasy, którą przebyłeś.
- Tu stosuje się algorytm HillClimbing:
- niekompletny
1. Mamy stan
2. Skanujemy stany sąsiednie
3. Jeśli stan sąsiedni jest lepszy wybieramy go jako najlepszy
4. I tak w kółko aż w danej iteracji nie znajdziemy poprawy

Tabu search
?
Local search czasami utyka w lokalnych optimach, w tym celu wprowadza się stany już odwiedzone (taboo) I specjalnie skacze do innych czasami gorszych, w celu znalezienie globalnego optimum.



## 2. Gry logiczne – klasyczne wyzwanie, algorytmy grające i ich rozwój

gra
?
to  rozgrywka prowadzona przez gracza (lub graczy) zgodnie z ustalonymi zasadami, w której należy osiągnąć ściśle określony cel.

Strategia gry
?
to kompletny zbiór zasad, które determinują posunięcie gracza, wybierane dla sytuacji powstających podczas gry.

Gra w ujęciu formalnym (wg. von Neumanna i Morgensterna, w teorii gier)
?
Gra składa się z zestawu reguł określających możliwości wyboru postępowania jednostek znajdujących się w sytuacji określanej mianem konfliktu interesów, w której każda z jednostek stara się maksymalizować swój własny zysk i jednocześnie minimalizować zysk pozostałych jednostek (graczy). Reguły gry określają też ilość informacji dostępną każdemu z graczy oraz wysokości wygranych i przegranych.

Zadania gracza
?
Gry wymagają od graczy czynienia sekwencji decyzji, które:
●        zwiększają ich **oczekiwaną wypłatę** (tj. łączne wygrane: skutki i rozmiary wygranej/przegranej),
●        biorą pod uwagę **czynniki determinujące bieżącą sytuację** (stan gry)
●        oraz **skończoną ilość czasu** (często znacząco ograniczoną).

problemy graczy
?
●       ograniczony czas nie pozwala podjąć optymalnej decyzji
●       podjęte kroki nie mogą już zostać cofnięte
●       długofalowy wynik każdego podjętego kroku jest niepewny
●       Nie znamy decyzji pozostałych graczy

klasyfikacja gier - liczba graczy
?
●        bezosobowe (zero-player game), np. popularna gra w życie (Conway's live),
●        jednoosobowe (one-player game), np. puzzle, pasjans,
●        dwuosobowe (two-player game), np. szachy, warcaby, otello, go,
●        wieloosobowe (multi player), np. poker, brydż.

klasyfikacja gier - suma
?
●       o sumie zerowej (ze znaną wypłatą), gdzie wygrana jednego gracza jest przegraną drugiego (zero sum games), np. szachy, warcaby, othello, go,
●       o sumie niezerowej (non zero sum), np. dylemat więźnia.

klasyfikacja gier - współpraca
?
●       kooperacyjne (cooperative) – gracze współpracują ze sobą,
●       nie kooperacyjne (non cooperative) – gracze nie współpracują ze sobą.

klasyfikacja gier - losowość
?
●       całkowicie losowe gry, np. ruletka,
●        częściowo losowe gry, np. brydż i inne gry karciane,
●        całkowicie deterministyczne gry, np. warcaby, szachy, othello, go.
![[Pasted image 20240630173636.png]]

cechy gier logicznych
?
●       jeden z najstarszych obszarów zastosowań AI
●       Zasady gier są precyzyjnie określone, rezultat łatwo mierzalny
●       historia sztucznej inteligencji jest nierozerwalnie z nimi związana

Konstrukcja Inteligentnych graczy -założenia
?
- wykonują wybrane przez nich posunięcia spośród zbioru możliwych ruchów.
- Grę można postrzegać jako poszukiwanie takich ruchów gracza, które zapewniają mu zwycięstwo.

drzewo gry
?
●        korzeń jest stanem początkowym gry, a kolejne węzły są stanami, jakie będą po wykonaniu każdego ruchu.
●       Nawet dla prostych gier drzewa są bardzo skomplikowane, – dla szachów typowo 35^100 węzłów drzewa przeszukiwania przy 10^40 różnych możliwych sytuacjach na planszy
●       Istnieją różne metody do oceny aktualnego stanu gry i wyboru kolejnych posunięć, bez konieczności budowy całego drzewa.
●       Jakość poszczególnych węzłów, czyli stanów gry, definiuje się poprzez funkcję oceniającą poszczególne węzły.
●       dla większości gier nie jest możliwe rozwinięcie całego drzewa
●       w stanach końcowych znana jest wypłata - wysokość wygranej bądź przegranej
![[Pasted image 20240630174428.png]]
●       Niebieskie wartości - funkcja wypłaty
●       **Czarne** – ustalane w oparciu o przeszukiwanie

przebieg gry-pojęcia
?
●       Stan początkowy (planszy)
●       Stan bieżący -  ruch gracza lub przeciwnika (przeciwstawne cele i ocena)
●       Operatory – ruchy dozwolone w danej sytuacji
●       Test celu – test końca gry lub liczenie funkcji wypłaty

przyczyny wykorzystania heurystyk w grach
?
●       Drzewo gry nie może być rozwinięte do końca (przez większość gry)
●       Głębokość rozwinięcia zależy od dostępnych zasobów, np. czasu
●       Gracz (program) musi podejmować decyzje na podstawie częściowego drzewa gry rozwiniętego na osiągalną głębokość ze stanu początkowego

cechy heurystyki gry
?
●       Heurystyczna funkcja oceniająca to symulacja ludzkiej oceny
●       wyraża numerycznie jakość pozycji
●       byłoby dobrze, aby była pozytywnie skorelowana z prawdopodobieństwem wygranej,
●       musi zgadzać się z funkcją wypłaty.
●       częsty sposób wyliczenia - ważona suma cech stanu gry
![[Pasted image 20240630174750.png]]

Rozgrywka - kluczowe pojęcia: strategia, posunięcie, MinMax
?
●       Strategia (wygrywająca) – dobór sekwencji ruchów prowadzących do wygranej niezależnie od ruchów przeciwnika
●       Posunięcie – para ruchów:〈ruch własny, ruch przeciwnika〉
●       MinMax -  sposób podjęcia decyzji, co do ruchu minimalizujący wpływ przeciwnika na końcowy rezultat.

Rozwiązania niepoinformowane - cechy
?
●       Brak użycia heurystyki (ang. blind search, brute force)
●       Wszystkie węzły drzewa gry osiągalne z danej pozycji są rozwijane.
●       Drzewo gry zbliżone do ludzkiego – człowiek rozważając hipotetyczne scenariusza nie bierze pod uwagę wszystkich możliwych zdarzeń,  eliminuje mniej prawdopodobne , które intuicyjnie nie prowadzą do celu.

Algorytm Min-Max
?
●       Heurystyczna funkcja kierunkuje poszukiwania
●       Zakładamy, że oponent wybiera najlepsze ruchy
●       Ocena z perspektywy gracza
●       W trakcie naszej tury maksymalizujemy ocenę pozycji, w trakcie tury przeciwnika minimalizujemy

Punkt odcięcia
?
Ustalona głębokość (również głębokość zastosowania funkcji oceniającej).

Problem horyzontu
?
ruch przeciwnika zmieniający drastycznie stan gry (i wartość zwracaną przez funkcję oceniającą)

Stabline pozycje(w grze)
?
takie, które nie wykazują możliwości drastycznej zmiany funkcji oceniającej w najbliższej przyszłości

alfa-beta-cięcie
?
- **Alfa** - najlepsza wartość z poziomu **max**
- **Beta** - najlepsza wartość z poziomu **min**
- Pominięcie poddrzew, które nie zmienią wartości na poziomie wyższym. W wyniku znaczne skrócenie czasu przeszukiwania
- Złożoność zależy od porządku rozwijania węzłów
●       optymistyczna - O(b^d/2)
●       pesymistyczna - O((b/log b)^d)
●       gdzie b —współczynnik rozgałęzienia, d — głębokość przeszukiwania

PROBCUT
?
- rozszerzenia alfa-beta
- Algorytm alfa-beta cięcie rozwija części gałęzi do propagacji wartości - **część tych propagacji jest niepotrzebna**.
	- Mocna korelacja wartości funkcji oceniającej dla kolejnych wartości węzłów
	- możliwość aproksymacji wartości węzłów leżących niżej (na ograniczoną głębokość)

Algorytmy ewolucyjne
?
Zastosowanie w grach:
●       **Narzędzie wspierające znalezienie strategii grania**
	○      konstrukcja/optymalizacja funkcji oceniającej
	○       kodowanie potencjalnej strategii wygrywającej
●       **Moduł odpowiedzialny za podejmowanie optymalnych decyzji**

Deep blue
?
●       **Pierwszy** silnik szachowy, który **pokonał szachowego mistrza świata** - Garry’ego Kasparova w 1997 (rok wcześniej z nim przegrał)
●       Utworzony **na podstawie** algorytmu **alfa-beta cięcie**

## 3. Problemy spełniania ograniczeń - rozwiązywanie przez przeszukiwanie

Charakterystyka problemu
?
1. stan = zbiór zmiennych i ich wartości 
2. cel = zbiór warunków ograniczeń, postaci relacyjnej, określonych na zmiennych 
3. rozwiązanie = przypisanie wartości do zmiennych spełniające wszystkie ograniczenia celu 
	1. operator: przypisanie wartości do zmiennej, duży współczynnik rozgałęzienia 
	2. np. problem ośmiu hetmanów, konstrukcja modelu dla zbioru formuł – podstawa działania model builders

Ograniczenia w CSP
?
- dowolna postać relacyjna (w tym ograniczenia funkcyjne) 
- absolutne – integralna część celu 
- preferowane – wprowadzają porządek częściowy rozwiązań
- ograniczenie zmiennych - dziedzina - dyskretna/ciągła

 Ogólna zasada algorytmów ślepych dla CSP
 ?
 - dekompozycja celu na zbiory ograniczeń dla poszczególnych zmiennych:
	 - redukcja olbrzymiego współczynnika rozgałęzienia

Jak są reprezentowane ograniczenia z CSP na grafie? Z czego się składa graf?
?
●       **Ograniczenia binarne**: Relacje między dwoma zmiennymi (dwuelementowe).
●       **Graf ograniczeń**:
	○       **Zmienne**: Reprezentowane jako węzły grafu.
	○       **Ograniczenia**: Reprezentowane jako łuki grafu, które łączą pary węzłów (zmiennych) związanych ograniczeniami. Łuki są nieetykietowane nazwami relacji i nieskierowane.
		![[Pasted image 20240630185840.png]]
	

Algorytmy niepoinformowane (ślepe) w CSP - Charakterystyka
?
Charakterystyka:
- **Standardowe algorytmy** mają problem z dużym współczynnikiem rozgałęzienia, co oznacza wiele możliwych stanów do przeszukania.
- **Przeszukiwanie z nawrotami (Backtracking Search):**
●       **Podstawowa metoda**:
	○       Proces poszukiwania rozwiązania poprzez **przypisywanie wartości do zmiennych.**
	○  **Nawrót**: Wycofanie się do poprzedniego stanu, gdy ograniczenia nie są spełnione dla danego przypisania wartości.
- Modyfikacje Przeszukiwania z Nawrotami:
	●       Sprawdzanie w przód (Forward Checking) - eliminacja dziedzin zmiennych wartości sprzecznych z przypisanymi do tej pory
	●       Spójność łuków (Arc Consistency)

**Kroki algorytmu backtracking search**:
?
●       Rozpoczyna od pustego przypisania.
●       Wybiera nieprzypisaną zmienną i przypisuje do niej wartość.
●       Sprawdza, czy przypisanie jest zgodne z ograniczeniami.
●       Rekurencyjnie próbuje przypisać wartości kolejnym zmiennym.
●       Jeśli napotka sprzeczność, cofa się (nawrót) i próbuje inne wartości.

**Propagacja ograniczeń (ang. Constraint Propagation)**
?
●       Polega na automatycznym i systematycznym przekazywaniu informacji o ograniczeniach między zmiennymi w celu redukcji przeszukiwanej przestrzeni rozwiązań.

Cele propagacji ograniczeń
?
1.  **Wykrywanie sprzeczności**: Poprzez propagację ograniczeń można szybko identyfikować sytuacje, w których żadne przypisanie wartości do zmiennych nie spełnia wszystkich warunków ograniczeń.
2. **Redukcja dziedzin zmiennych**
3. Szybsze algorytmy

**Techniki propagacji ograniczeń:**
?
1. **Forward Checking**:
	 Po przypisaniu wartości do zmiennej, eliminuje wartości z dziedzin innych zmiennych, które są sprzeczne z nowym przypisaniem.
●       **Spójność łukowa (Arc Consistency)**:
 zachowywanie tylko tych wartości w dziedzinach, które nie są sprzeczne z ograniczeniami
●       **Spójność wyższego rzędu**:
 Propaguje ograniczenia przez więcej niż jeden łuk w grafie, co może skuteczniej redukować przeszukiwaną przestrzeń rozwiązań.

Heurystyka kolejności sprawdzania zmienny i wartości
?
- aby zmniejszyć liczbę przeszukiwanych węzłów
1. Heurystyka najbardziej ograniczonej zmiennej
	- redukcja wsp. rozgałęzienia
	- zmienna która ma najmniej wartości w swojej dziedzinie
2. Heurystyka najbardziej ograniczającej zmiennej
	- redukcja wsp. rozgałęzienia
	- powiązana z największą liczbą innych zmiennych
3. Heurystyka najmniej ograniczającej zmiennej
	- powiązana z najmniejszą liczbą innych zmiennych

**CSP (Constraint Satisfaction Problems)**
?
to problemy, w których trzeba przypisać wartości zmiennym tak, żeby spełniały one określone ograniczenia (warunki).
○       **Wartościowanie spójne** oznacza przypisanie wartości zmiennym bez naruszania żadnych ograniczeń.
○       **Wartościowanie kompletne** oznacza przypisanie wartości wszystkim zmiennym w problemie.
○       **Funkcja celu** dodaje dodatkowe wymagania dotyczące jakości rozwiązania.
○       **Graf więzów** przedstawia zmienne jako węzły, a ograniczenia jako połączenia między nimi.
○       **Rodzaje problemów**:
	■       **Skończone dziedziny (dyskretne)**: Złożoność rośnie wykładniczo wraz z liczbą zmiennych.
	■       **Nieskończone dziedziny (dyskretne i ciągłe)**: Rozwiązywalne dla liniowych więzów, trudne lub niemożliwe do rozwiązania dla nieliniowych ograniczeń.

**2. Podział CSP (Strona 14)**
?
●**Więzy** mogą być
○       unarne (dotyczące jednej zmiennej) lub
○       binarne (dotyczące dwóch zmiennych). Można je też redukować do postaci binarnej za pomocą pomocniczych zmiennych.
●**Cel** może być
○       absolutny (muszą być spełnione wszystkie ograniczenia) lub
○       preferowany (ograniczenia można złamać, ale kosztem np. zmniejszenia jakości rozwiązania).
●**Metody przeszukiwania**:
○       **Ślepe (naiwne)**: Przeszukiwanie bez żadnej strategii, np. przeszukiwanie z nawrotami (backtracking).
○       **Heurystyczne**: Używają pewnych strategii do bardziej efektywnego przeszukiwania.
●       **Propagacja ograniczeń** to technika, która pozwala na wcześniejsze wykrywanie niespójności, co redukuje ilość przeszukiwanych opcji.


Propagacja więzów
?
tak jak w AC-3, propagacja konsekwencji z jednego ograniczenia na drugie

MAC
?
(Maintaining Arc Consistency)
funkcja do utrzymywania spójności łukowej
- AC-3 jest wywoływany dla wszystkich Xj, które nie mają przypisanej wartości i są powiązane z własnie zmienionym Xi

**AC-3**
?
to algorytm, który sprawdza i utrzymuje spójność łukową w grafie ograniczeń. Polega na usuwaniu niespójnych wartości z dziedzin zmiennych.
○       **Funkcja REVISE** weryfikuje dziedzinę zmiennej, eliminując wartości, które są niespójne z ograniczeniami.
○       **MAC (Maintaining Arc Consistency)** to technika wywoływania AC-3 po przypisaniu wartości zmiennej, aby utrzymać spójność łukową dla powiązanych zmiennych.

heurystyki dystrybucji
?
1. najbardziej ograniczonej zmiennej
2. najbardziej ograniczającej zmiennej
3. najmniej ograniczającej wartości - wybór wartości, która najmniej ogranicza możliwości przypisania wartości innym zmiennym

●       **K-spójność**
?oznacza, że dla każdego zbioru k-1 zmiennych, przypisanie wartości k-tej zmiennej będzie spójne.
○       **2-spójność**: Spójność łukowa.
○       **3-spójność**: Spójność ścieżkowa (path consistency).

●       **Specjalne typy więzów**:
?
	○    Alldiff Wszystkie zmienne muszą mieć różne wartości.
	○    Atmost Warunek dotyczący sumy zasobów, np. nie więcej niż 10 jednostek zasobów przypisanych do pewnych zmiennych


●       rejestracja(jak się objawia wynik progpagacji) wyników propagacji(ograniczeń)
?
	○       ograniczanie dziedziny (domain propagation)
	○       ograniczanie zakresu (bounds propagation) sprawdzanie i modyfikacja dolnych i górnych ograniczeń dziedzin zmiennych
![[Pasted image 20240630201254.png]]



**. Strategie przeszukiwania w CSP**
?
●       **Chronological Backtracking**: Powrót do poprzedniego kroku, gdy napotka się sprzeczność.
●       **Backjumping**: Powrót do zmiennej, która bezpośrednio powoduje konflikt.
●       **Conflict-directed backjumping**: Powrót do zmiennej, która pośrednio powoduje konflikt.
●       **Uczenie się więzów**: Dodawanie nowych ograniczeń na podstawie napotkanych sprzeczności, aby uniknąć powtórzenia błędów.
●       **Lokalne przeszukiwanie (local search)** w CSP?
Metoda, w której przeszukuje się przestrzeń możliwych rozwiązań poprzez modyfikację aktualnego stanu, zamiast zaczynać od zera.

Rozwiązania różnych **Struktur problemu**:
?
○        Możliwość podziału problemu na niezależne podproblemy.
○       **Algorytm dla drzewowego CSP**: Rozwiązanie w czasie liniowym zależnym od liczby zmiennych.
○       **Redukcja grafów do postaci drzewa**: Ustalanie wartości dla węzłów i redukcja problemu.


## 4. Wnioskowanie i reprezentacja wiedzy


Agent logiczny
?
To agent działający w oparciu o:
1.      Bazę wiedzy i zapisany w niej opis środowiska
2.      Mechanizmy wnioskowania logicznego
Wykorzystując to wykazuje zdolność do **przewidywania zmian środowiska.**

Powody stworzenia agenta logicznego jako metody rozwiązywania problemów:
?
1.      Konieczność sformułowania jawnej, pełnej specyfikacji stanu
	a.      Zapis stanu
	b.      Akcje zapisane jako procedury
2.      Bardzo duży współczynnik rozgałęzienia
	a.      Wiele możliwych akcji choć niewiele sensownych w poszczególnych klasach stanów środowiska
3.      Jeden cel (‘typ’) celu – mimo rozbicia realizacji na etapy

Techniki dostępne dla agenta logicznego:
?
1.      Przeszukiwanie
2.      Reprezentacja wiedzy o środowiska
	a.      Opis deklaratywny
	b.      Logika predykatów pierwszego rzędu
	c.      Logiki modalne
		i.     Np.: rachunek sytuacji, implementacja podzbioru logik modalnych przez reifikację
	d.      Formalizmy wywodzące z przetwarzania
		i.     Sieci semantyczne
	e.      Logiki do reprezentacji wiedzy
		 i.     Logiki opisowe
		ii.     Wywodzące się z KL-ONE
		iii.      Podział na T-Box (pojęcia) i A-Box (obiekty)
3.      Wnioskowanie
	a.      Automatyczne rozszerzanie wiedzy
	b.      Wiedza explicite i implicite
	c.      Spójność wiedzy
		i.     W ten czy inny sposób oparte na przeszukiwaniu
		ii.     Możliwość zastosowania do określania sekwencji akcji
			1.      Potencjalnie możliwe: docelowy stan jako stan bieżący + sekwencja akcji (formuły) przekształcających stan
			2.      Najczęściej opis zbyt złożony
4.      Planowanie
	a.      Realizacja etapami
	b.      Wykorzystuje przeszukiwanie i/lub wnioskowanie
	c.      Oparte na podziale
		i.     problemu na podproblemy
		ii.     ‘wielkiej’ przestrzeni na ‘małe’, w znacznym stopniu niezależne podprzestrzenie


Dedukcja(logicznie)
?
- logicznie (formalnie) poprawna metoda wnioskowania (od ogółu do szczegółu)
- Wnioskowanie dedukcyjne wykorzystuje operator implikacji:
1. zakłada się, że prawdziwa jest implikacja p→q, 
2. z prawdziwości implikacji i z prawdziwości przesłanki p (która może być zdaniem złożonym) dedukuje się prawdziwość konkluzji q
3. Z pewnej ogólnej reguły (znana) i faktu (znany) dedukujemy nowy fakt (wnioskowanie top-down) – od ogółu do szczegółu

Abdukcja
?
- wnioskowanie o prawdopodobnych przyczynach, jest procesem wyjaśniania tego, co jest nam już wiadome.
- Niepoprawna logicznie forma wnioskowania. Mając implikację p -> q, która jest prawdziwa wiemy, że jeżeli q jest prawdziwe to p też. Problem z abdukcją polega na tym, że atrybuty mogą nie być sensownie powiązane.

Implikacja
?
p→q
Term po lewej stronie (przesłanka) implikuje term po prawej stronie (konkluzję)
(p → q)  ≡  ¬ p ∪ q

Słabości implikacji:
?
1. p i q razem mogą nie mieć sensu
2. fałszywa (FALSE) hipoteza implikuje każdą konkluzję
3. implikacja p →q nie oznacza, że „p powoduje q”
4. proste wyrażenie może być traktowane jak implikacja bez przesłanki (q)

Dedukcja wykorzystująca twierdzenia logiki
?
![[Pasted image 20240701202828.png]]
Wniosek? Profesor uczy, dlatego jest nieszczęśliwy (czyli tak samo jak student)

Dopasowanie(logika)
?
- podejście symbolicznego dopasowania, przypisuje równość (equality) prawdziwych wyrażeń (zdań), realizowane zwykle przez mechanizm wnioskujący

Forward Chaining
?
To paradygmat wnioskowania w przód

Backward chaining
?
![[Pasted image 20240701203422.png]]
![[Pasted image 20240701203641.png]]

Predykat
?
służy do pamiętania faktów.

Predykaty unarne
?
inaczej własności
1. may_move (Object)
2. next_to (Region1, Region2)
3. on_top (Support, Object)

Zaprezentuj **_The circuit breaker in line 4 is open_** w postaci predykatów
?
1. :
	1.  is-open (circuit-breaker, line-4)
	1. circuit-breaker (line-4, is-open)
	2. line-4 (circuit-breaker, is-open)
2. :
	1. is-open (What, Where)
	2. circuit-breaker (Where, Status)
	3. line-4 (Protection, Status)
3. :
	I dla nich ustala się odpowiednie dziedziny, np.:
	1. What = {circuit-breaker, disconnect-switch, lineitself}
	2. Where = {line-1, line-2, line-3, line-4}
	3.  Status = {open, closed, inoperable}
	4. Protection = {relay, circuit-breaker, recloser}

Rezolucja
?
- system do udowadniania nieprawdziwości twierdzeń(klauzuli)
- Dodajemy do zbioru znanych prawdziwych klauzul logicznego zaprzeczenia klauzuli  i szukamy sprzeczności
![[Pasted image 20240701204714.png]]

Zbiór jest unifikowalny jeśli
?
istnieje substytucja termu(podmienienie zmiennych) czyniąca je identycznymi
Możliwe substytucje:
- zmienne przez stąła
- zmienne przez zmienną
-  zmienne przez funkcję, O ILE JEJ NIE ZAWIERA! np.
	- P(x,f(x))
	- P(f(y),y)P(f(y), y)P(f(y),y)
	- Substytucja: x↦f(y)
	- Wynik:
	- P(f(y),f(f(y)))
	- P(f(y),y)

Reprezentacja wiedzy - Trójka
?
<Obiekt, Atrybut, Wartość>, np. <liść, kolor, zielony>

Reprezentacja wiedzy - para
?
**Własność**
Para <Obiekt, Własność>, 
np. <Zwierzę, Oddycha>. Własność to relacja 1-go rzędu (jednoargumentowa).
\
Reprezentacja wiedzy - Relacja dowolnego rzędu
?
o   Binarna – między dwoma obiektami
o   Wyższych rzędów – wiele relacji binarnych, np. (((A, B), C), D)

Sieci semantyczne
?
- taka jak robot kuchenny
- Graficzna reprezentacja wiedzy. Etykietowany digraph (węzły, łuki etykietowane). Zwykle reprezentują obiekty fizyczne/pojęcia abstrakcyjne. Łuki zwykle łączą obiekty z atrybutami.
Definicja: Graf = (  
Zbiór węzłów,  
Zbiór łuków,  
funkcja określająca uporządkowanie połączenia S -> Zbiór liczbowy wag (często jedna waga, więc jednoelementowy) x Zbiór własności)  
)
●       Relacje w sieci semantycznej
o   Ma
o   Ma_część
o   Jest_częścią
o   Używa
o   Jest_elementem
o   Jest_podzbiorem
o   …
![[Pasted image 20240701214025.png]]


## 5. Wprowadzenie do uczenia maszynowego – przykład drzew decyzyjnych

Machine Learning
?
Programy, które potrafią automatycznie polepszać swoje działanie w miarę nabywania doświadczenia.

Uczenie indukcyjne
?
poprzez wyszukiwanie uogólnień np.:
![[Pasted image 20240701234438.png]]

Uczenie pojęć definicja
?
zbieranie tego jak kategoryzować dane na podstawie pozytywnych i negatywnych przykładów testowych

Uczenie się pojęć z nadzorem
?
-        pojęcia służą do klasyfikacji obiektów na grupy - kategorie
-        Posiadamy dane, które mają swoje etykiety. Na przykład mamy 100 zdjęć i każde ma nazwę “kot” lub “pies”.
-        podstawowo rozróżnianie dwóch klas / etykiet -> np. Osoba jest chora lub osoba jest zdrowa

tworzenie pojęć bez nadzoru
?
-  szukanie uogólnień
-        kategorie nie są znane -> obserwacja nieetykietowanych przykładów
-        grupowanie obiektów w kategorie zgodnie z kryteriami podobieństwa
-        podział przykładów trenujących na grupy odpowiadające kategoriom
-        uczenie się pojęć odpowiadających tworzonym kategoriom, aby było możliwe klasyfikowanie nowych przykładów
-        np. mamy dane dotyczące mieszkań, lecz nie mamy ich cen, więc mądry komputer samemu umieszcza nasze dane jako punkty na wielowymiarowej przestrzenii i na tej podstawie je kategoryzuje. Mądry komputer sam stwierdzi “O, ta grupa mieszkań ma dużo pokojów i duży metraż, więc będą blisko siebie w wielowymiarowej przestrzeni. To mieszkanie ma mało  pokojów i jest daleko od centrum, dobra, to będzie raczej się znajdować daleko od tamtej grupy”.

pojęcie(w maszynowym uczeniu)
?
Pojęcie (concept) w kontekście uczenia maszynowego odnosi się do abstrakcyjnej reprezentacji zbioru obiektów lub przypadków, które mają wspólne cechy lub właściwości. Pojęcie jest tym, co staramy się nauczyć lub zrozumieć, na podstawie danych. **Alfabet, Owoc**

Kategoria
?
Kategoria (category) odnosi się do grupy obiektów, które są klasyfikowane razem na podstawie określonych kryteriów lub cech. Kategorie są zbiorem przykładów, które spełniają określone warunki i są traktowane jako podobne w kontekście danego pojęcia. **Litera “n”, banan**

uczenie się aproksymacji funkcji
?
system który uczy się maszynowo ma wygenerować funkcję dobrze aproksymującą funkcję docelową, jej zbiór wartości to liczby rzeczywiste

obciążenie indukcyjne(bias) - w maszynowym uczeniu
?
w uczeniu maszynowym to uprzedzenia lub założenia wprowadzone do modelu uczącego się, które mają na celu uproszczenie procesu nauki i pomagają w podejmowaniu decyzji, **gdy dane treningowe nie są wystarczające do jednoznacznego określenia hipotezy.**


3 zbiory do maszynowego uczenia
?
trenujący
testowy
do dostrajania

K-krotna walidacja krzyżowa (K-fold cross-validation)
?
technika oceny modelu, polegająca na podziale danych na K równych części (folds).
1. **Podział danych:** Dane są dzielone na K części.
2. **Iteracyjne trenowanie i testowanie:** Model jest trenowany K razy, za każdym razem używając jednej części jako zestawu testowego, a pozostałych K-1 części jako zestawu treningowego.
3. **Średnia wyników:** Wyniki z K iteracji są średnią, co daje końcową ocenę przez model.
Dzielimy sobie nasze dane na 10 setów.
Na początku ostatni testuje, reszta trenuje. Sprawdzamy jakie były wyniki i zapisujemy
![[Pasted image 20240702001550.png]]
później pierwszy testuje, pozostałe trenują. Sprawdzamy jakie były wyniki i zapisujemy
![[Pasted image 20240702001554.png]]
Później drugi testuje, pozostałe trenują. Sprawdzamy jakie były wyniki i zapisujemy
![[Pasted image 20240702001559.png]]
Później trzeci testuje….
Na końcu robimy średnią wyników.

drzewo decyzyjne - elementy
?
●       **węzeł** – na rysunku elipsy lub prostokąty. W węźle znajduje się zawsze albo test na wartość pewnego atrybutu (np. elipsa ’Student’, odpowiadająca pytaniu, czy klient był  studentem), albo klasa decyzyjna (tutaj prostokąty ’TAK’, ’NIE’). Konkretne figury geometryczne zostały wprowadzone tylko by ułatwić rozróżnianie węzłów, tzn. nie są elementem konwencji.
●       **krawędź** – łączy dwa węzły, przy czym strzałka określa kierunek połączenia (i zawsze wskazuje w dół, jeżeli korzeń jest na górze). Z każdą krawędzią związana jest pewna etykieta, np. niskie, średnie, tak, nie. Etykiety to możliwe wartości atrybutu związanego z węzłem, z którego wyszła ta krawędź.
●       **liść** – taki węzeł, z którego nie wychodzi żadna krawędź. W liściu zawsze znajdować się będzie przypisanie do jakiejś klasy decyzyjnej, w tym wypadku do ’TAK’ albo ’NIE’. Na rysunku liście to węzły w kształcie prostokątów.
●       **korzeń** – od korzenia drzewo zaczyna rosnąć. Jest to węzeł, do którego nie dochodzi żadna krawędź, czyli w tym wypadku Dochody.

Wnioskowanie (klasyfikacja)
?
- określenie przynależności obiektu do klasy
- Proces wyciągania logicznych wniosków z dostępnych informacji, danych lub przesłanek.
Czyli mamy nauczone drzewo i bierzemy nasz obiekt testowy - człowiek.
Sprawdzamy jakie ma dochody (średnie), to wybieramy środkową strzałkę i lecimy dalej.
Sprawdzamy czy student (tak), to wybieramy lewą strzałkę i mamy odpowiedź. Przejście po algorytmie jest banalnie proste, ale bardziej jajcarska w drzewach jest ich budowa.

### Proces budowy drzewa decyzyjnego
?
1. **Wybór atrybutu:** Na każdym poziomie drzewa wybierany jest atrybut, który najlepiej dzieli zestaw danych. Kryteria wyboru mogą obejmować zysk informacyjny (information gain) lub współczynnik przyrostu informacji (gain ratio).
2. **Podział danych:** Zestaw danych jest podzielony na podzbiory na podstawie wybranego atrybutu.
3. **Rekurencja:** Proces jest powtarzany dla każdego podzbioru, tworząc nowe węzły wewnętrzne i liście.
4. **Zakończenie:** Proces budowy drzewa kończy się, gdy wszystkie przykłady w podzbiorze należą do jednej klasy lub nie ma już atrybutów do podziału.

## Entropia
?
Miara niepewności lub niejednorodności w zbiorze danych. W kontekście uczenia maszynowego, entropia służy do oceny czystości podziału danych - im wyższa entropia, tym większa niepewność (większe zmieszanie klas - to dobrze, bo oznacza, że mamy bardzo zdywersyfikowany zbiór danych, a nie dane jednego typu).
![[Pasted image 20240702002338.png]]![[Pasted image 20240702002341.png]]


Klasa(maszynowe uczenie)
?
Kategoria lub etykieta, do której dane mogą zostać przypisane. Klasa reprezentuje możliwy wynik procesu klasyfikacji.


Kroki algorytmu ID3 (na przykładzie pogoda - gra w tenisa)
?
1. **Obliczanie entropii:** Dla całego zbioru danych oblicza się entropię, która mierzy niepewność lub niejednorodność klas w zbiorze danych.  
    Obliczanie entropii początkowej na podstawie dostępnych klas. Np. z 14 dni przez 9 dni można grać, a przez 5 nie można grać w tenisa. Klasy: “Tak” oraz “Nie”
2. **Wybór atrybutu:** Dla każdego atrybutu oblicza się zysk informacyjny, który mierzy, o ile entropia zmniejsza się po podziale danych według tego atrybutu. **_Wybiera się atrybut z najwyższym zyskiem informacyjnym.  
    _**  
    Obliczenie zysku informacyjnego ze względu na poszczególne atrybuty np. ze względu na pogodę. Obliczamy entropię dla pogody “Słonecznej”, “Pochmurnej” i “Deszczowej”. Bierzemy z tego średnią.  
    **Zysk informacyjny = Entropia początkowa - średnia entropia atrybutu**
3. **Podział danych:** Dane są podzielone na podzbiory według wartości wybranego atrybutu.
4. **Rekurencja:** Algorytm jest rekurencyjnie stosowany do każdego podzbioru, aż wszystkie podzbiory będą jednorodne (czyli zawierają tylko jeden typ klasy) lub nie będzie już atrybutów do podziału.

### Możliwości i ograniczenia ID3
?
●       ID3 nie pozwala na powroty: – wybrany atrybut na poszczególnym poziomie drzewa nie będzie więcej rozpatrywany,
●        jak w hill-climbing, może to doprowadzić do zbieżności do lokalnego optimum
●       Preferowane są krótsze drzewa,
●       Oraz takie, które atrybuty o wysokim zysku informacyjnym plasują blisko korzenia.

Problemy i modyfikacje w budowniu drzew decyzyjnych
?
1. Atrybuty nie determinują klasyfikacji (czyli mamy dane, z których ni chuja nie da się zbudować drzewa)
	1. skutek – warunek zakończenia budowy drzewa nie jest nigdy spełniony;
	2. rozwiązanie – zmiana kryterium zakończenia na: osiągnięcie jednorodnych klas w liściach  
2. Istnieje szereg obiektów o takich samych atrybutach i klasie (czyli mamy dosłownie powtarzające się rekordy. Np. 4 studentów z oceną 3.0 z matmy, 3.0 z biolki, 3.0 z polaka)
	1. skutek – nadmiar nic nie wnoszących danych;
	2. rozwiązanie– wyeliminowanie na wstępie nadmiarowe dane.  
3. Istnieją obiekty o identycznych wartościach atrybutów ale należące do różnych klas (problem podobny jak z datasetem koszulek w liście na laby. Mamy koszulki, które dla tych samych danych mają różną etykietę)
	1. skutek i rozwiązanie dokładnie jak w pkt 1.  
4. Istnieją obiekty z brakującymi wartościami atrybutów
	1. skutek – niekiedy nie można policzyć entropii
	2. rozwiązanie– obiekty z brakującymi wartościami zastąpić obiektami o wszelkich możliwych kombinacjach wartości atrybutów w miejscach braków danych.


Nadmierne dopasowanie (overfitting)
?
Mamy 2 modele. h oraz h’.
-        h jest lepsze na danych treningowych 
-        h’ jest lepsze na danych testowych
Oznacza to, że h jest nadmiernie dopasowany do danych testowych, czyli jest gorszy od h’, ponieważ nie generalizuje problemu wystarczająco dobrze.

Jak zapobiec overfitting w drzewie decyzyjnym
?
●       Zatrzymać wzrost drzewa zanim osiągnie punkt, w którym perfekcyjnie klasyfikuje dane uczące.
●        Pozwolić drzewu ,naddopasować’ dane, a później dokonać przycięcia drzewa (post-pruning).

Przycinanie węzła (pruning) to(w drzewie decyzyjnym)
?
1.  usunięcie poddrzewa zaczynającego się w tym węźle
2.  zrobienie go liściem
3.  przypisanie mu najczęstszej klasy związanej z tym węzłem.
4. Węzeł jest usuwany, jeśli otrzymane drzewo (po usunięciu analizowanego węzła) klasyfikuje nie gorzej niż wyjściowe.


Algorytm C 4.5
?
●       Rozszerzenie algorytmu ID3.
●       Unikanie nadmiernego dopasowania do danych.
●       Obsługa atrybutów o wartościach ciągłych, np., temperatury.
●       Obsługa danych treningowych z brakującym wartościami atrybutów.
●       Obsługa atrybutów z różnym kosztem.
●       Poprawa efektywności obliczeniowej
●       Podczas budowy drzewa nie uwzględnia się danych z brakującą wartością atrybutu

iloraz przyrostu infromacji
?
![[Pasted image 20240702003449.png]]

## 6. Klasyfikacja tekstów - naiwny Bayes


Zadanie lasyfikacji tekstów
?
- Przypisanie dokumentów do predefiniowanego, skończonego zbioru kategorii.
- Jeżeli użytkownik wskazał pewną liczbę dokumentów relewantnych (ważnych) i nierelewantnych (nieważnych), możemy zbudować probabilistyczny klasyfikator oparty na naiwnym klasyfikatorze bayesowskim:

reguła bayesa
?
![[Pasted image 20240702093114.png]]

Klasyfikacja dokumentów - Przykład
?
Przypisane etykiety do dokumentów lub stron WWW mogą być:
-        tematami np. “finance”, "news>world>asia>business",

Klasyfikacja dokumentów manualna
?
- stara
- przez ludzi
- dla małych problemów

Automatyczna klasyfikacja dokumentów - sposoby
?
1. Systemy reguł pisanych ręcznie
	- regex
2. Funkcja oparta na **nadzorowanym** uczeniu
	- k-nearest neighbours
	- naiwny klasyfikatora Bayesa
	- SVM - maszyna wektorów podpierających
	- deep learning
	- wymagają ręcznie anotowanych danych
3. Mieszanka obu

Metoda bayesowska do klasyfikacji
?
- Wykorzystanie prawdopodobieństw każdej kategorii bez informacji o poszczególnych obiektach.
- Kategoryzacja produkuje (na podstawie faktów) dystrybucję prawdopodobieństwa dla możliwych kategorii mając opis poszczególnych obiektów.
- ![[Pasted image 20240702093915.png]]

założenie Bayesowskie P(cj)
?
P(cj) - prawdopodobieństwo klasy k, estymowane na podst.  częśtości klas cj w przykładach treningowych

założenie Bayesowskie P(xi|cj)
?
Może być estymowane, tylko wtedy gdy bardzo, bardzo duża liczba przypadków treningowych jest dostępna.

Założenie warunkowej niezależności Bayesa
?
poszczególne cechy (lub atrybuty) - np. słowa w dokumencie - Xi- są niezależne od siebie, pod warunkiem, że znamy klasę (kategorię) do której należy dany przykład.
![[Pasted image 20240702095233.png]]

Co się dzieje jeżeli nie widzieliśmy żadnych przypadków treningowych, w których pacjent miał grypę i nie miał bóli mięśni
?
Zerowe prawdopodobieństwa nigdy nie mogą być odrzucone!

Wygładzenie(Smoothing)
?
- Wygładzenie to technika stosowana w uczeniu maszynowym, szczególnie w modelach probabilistycznych, aby poradzić sobie z problemem **niewystarczającej liczby danych lub z wartościami zerowymi w danych.
- Wprowadza się ją poprzez dodanie pewnej wartości do liczników częstości wystąpień, aby uniknąć problemu zero-frequency (częstotliwości zerowej).
![[Pasted image 20240702095856.png]]


Stochastyczne modele językowe
?
Modelowanie prawdopodobieństwa generowania wyrażeń (każde słowo po kolei) Np., model unigramowy
![[Pasted image 20240702100227.png]]
![[Pasted image 20240702100137.png]]![[Pasted image 20240702100201.png]]


Klasyfikacja tekstu z wykorzystaniem Naiwnego Klasyfikatora Bayesa - krok po kroku
?
Klasyfikacja tekstu – podstawy
Model, który na podstawie tekstu określa, do której z klas należy dany dokumen
1. **Atrybuty są pozycjami w tekście, wartości to słowa**:
    - Każde słowo w tekście jest traktowane jako cecha (atrybut), a jego pozycja w tekście jako indeks tej cechy.
2. **Model klasyfikacji tekstu**:
    - Naiwny Klasyfikator Bayesa zakłada, że pozycje słów są niezależne od siebie, co oznacza, że prawdopodobieństwo wystąpienia słowa nie zależy od innych słów w tekście.
    - Model używa tych samych parametrów dla każdej pozycji słowa w tekście, co prowadzi do modelu „bag of words” (czyli torba słów, gdzie kolejność słów nie ma znaczenia).
- Uczenie modelu
1. **Zbiór treningowy i słownik**:
    - Z korpusu treningowego wyodrębniamy słownik (Vocabulary), czyli listę wszystkich słów występujących w dokumentach.
2. **Obliczanie składowych prawdopodobieństw**:
    - P(cj): Prawdopodobieństwo wystąpienia klasy cj:
        - Obliczamy to jako stosunek liczby dokumentów przypisanych do klasy cj do całkowitej liczby dokumentów.
    - P(xi∣cj): Prawdopodobieństwo wystąpienia słowa xi​ w klasie cj:
        - Obliczamy to jako stosunek liczby wystąpień słowa xi w dokumentach klasy cj​ do całkowitej liczby słów w tej klasie, uwzględniając wygładzanie, aby uniknąć zerowych prawdopodobieństw.
- Klasyfikacja nowych dokumentów
1. **Przygotowanie danych**
    - Dla nowego dokumentu identyfikujemy pozycje wszystkich słów, które znajdują się w słowniku wyodrębnionym podczas uczenia.
2. **Obliczanie klasy dla dokumentu**
    - Obliczamy prawdopodobieństwo, że dany dokument należy do każdej z możliwych klas cj
    ![[Pasted image 20240702101244.png]]
    - CNB​ to klasa, do której najprawdopodobniej należy dokument.
    - Dla każdej klasy cj obliczamy iloczyn prawdopodobieństw P(xi∣cj) dla wszystkich słów xi w danym dokumencie oraz prawdopodobieństwo P(cj) dla tej klasy.
    - Wybieramy klasę cjo największym obliczonym prawdopodobieństwie.

niebezpieczeństwo niedomiaru(underflow)
?
- Mnożenie wielu prawdopodobieństw, z definicji pomiędzy 0 i 1, może spowodować niedomiar w obliczeniach zmiennoprzecinkowych
- rozwiązanie sumowanie/mnożenie logarytmów p-stw
- ![[Pasted image 20240702102234.png]]

Modele do klasyfikacji dokumentów - wielowartościowy dwumianowy vs wielomianowy
1. Wielowartościowy dwumianowy
	1. słownik słów - wypełniony true/false jesli slowo wystapilo w dokumencie
	2. dla tematu, wystapienie 1 slowa nie mowi nic o szansie wystapienia innych slow
	- P(Xw=term|cj) - liczba dokumentów o temacie cj w ktorych wystepuje cj
2. Wielomianowy
	1. pozycje słow w dokumencie z przypisanymi wartosciami czyli slowami
		1. np. poz7=nad
	2. Dla tematu, wystąpienie słowa na pozycji, nie mowi nic o wystapieniu slow na innych pozycjach
	- P(Xi=w|cj) = liczba razy, ile wystepuje slowo w we wszystkich dokumentach tematu cj
	- lepszy



Selekcja cech - cel
?
- umożliwienie użycia klasyfikatorów
- redukcja czasu uczenia
- poprawa generalizacji
- eliminacja szumu
- tylko na danych treningowych!! bo inaczej overfitting

Sposoby na selekcję cech
?
1. Test chi-kwadrat
	- czy jakaś zmienna zmienna kategoralna jest powiązana z inną
2. Miara informacji wzajemnej(mutual information)
	- jak dużo informacji wnosi wartość 1 zmiennej o wartości 2 zmiennej 
3. Heurystycznie
4. najczęstsze termy
	- 90% jakości innych metod

**Szumy** (maszynowe uczenie)
?
to elementy danych, które wprowadzają zakłócenia i nie reprezentują prawdziwych wzorców. Ich źródła:
- błędy pomiaru
- nieistotne cechy - wprowadzają zbędne info, które zakłócają uczenie

Założenia NB - czemu  głupie(nieadekwatne)?
?
1. Warunkowa niezależność - gorączka w kontekscie np. choroba albo film
2. Pozycyjna niezależność - np river bank i financial bank

## 7. Case-based Reasoning & Unsupervised Learning

#### Case-based Reasoning (CBR)
?
-  Inne nazwy: nauczanie pamięciowe / instancjonalne.
- Mając zestaw obiektów o znanych klasach, określamy klasę nowego obiektu, znajdując najbardziej podobny przykład z zestawu treningowego i przypisując mu tę samą klasę.
- Kluczowe pytania:
	-  Jak ocenić podobieństwo obiektów?
		- Porównanie atrybutów obiektów.
		-  Użycie miar odległości np. Euklides
		-  Wyznaczenie funkcji podobieństwa jako funkcji wektorów wartości atrybutów.
	- Jak podobny powinien być obiekt treningowy, aby podjąć dobrą decyzję?
		- Na tyle podobny, aby jego klasa była reprezentatywna dla nowego obiektu.
	- Czy jeden podobny obiekt wystarczy, aby podjąć dobrą decyzję?
		-  Raczej nie, użycie k-NN (k najbliższych sąsiadów) może prowadzić do lepszych decyzji.

Reguła k-Najbliższych Sąsiadów (k-NN)
?
●       Idea: jeden obiekt może być mylący, więc lepiej brać pod uwagę k najbliższych sąsiadów.
●       Proces klasyfikacji:
1.     Zidentyfikuj k najbliższych sąsiadów x.
2.     Przypisz x do klasy najczęściej występującej wśród tych k sąsiadów.
●       k powinno być liczbą **nieparzystą**, aby unikać remisów.
![[Pasted image 20240702110604.png]]

Pomiar podobieństwa - 3 aposoby
?
1. Obiekty jako wektory cech
	![[Pasted image 20240702110730.png]]
2. Miara Euklidesowa
![[Pasted image 20240702110751.png]]
3. Ogólna miara podobieństwa - różne funkcje odległości, w zależności od typu danych atrybutów (ciągłe, dyskretne, binarne).
![[Pasted image 20240702110847.png]]

Odległość vs podobieństwo
?
- nie każda miara odleglosci to podobienstwo i vice versa
Odległość:
1. **Nieujemność odległości:** Odległość nie może być nigdy ujemna.
2. **Tożsamość nieodróżnialnych:** Odległość między dwoma identycznymi wektorami wynosi zero.
3.  **Symetria:** Odległość od x do y jest taka sama jak od y do x.
4. Metryka musi spełniać nierówność trójkąta: ![[Pasted image 20240702111355.png]]

#### Problemy związane z k-NN

●       **Nieistotne atrybuty**: mogą zakłócać proces klasyfikacji.
●       **Skale wartości atrybutów**: duże domeny mogą dominować nad małymi.
●       **Normalizacja wartości atrybutów**: mapowanie do przedziału [0, 1].
	- skutkuje to zniekształconą interpretacją atrybutów
	- atrybuty binarne zaczynają dominować
●       **Klątwa wymiarowości**: zwiększenie liczby atrybutów prowadzi do wzrostu kosztów obliczeniowych i wymaga więcej przykładów treningowych.
-  **Leniwe**, ponieważ nie tworzą modelu obliczeniowego, - nie uczą sie
- **Wysoki koszt obliczeniowy**, ponieważ wymagają obliczenia **odległości do wszystkich wzorców uczących** (których może być bardzo dużo), co daje liniowy koszt obliczeniowy w stosunku do wielkości zbioru danych uczących.


Ważona metoda najbliższych sąsiadów (Weighted Nearest Neighbours)
?
Prowadzi do głosowania na temat klasyfikacji gwiazdki, biorąc pod uwagę k najbliższych sąsiadów, lecz ich głosy są **ważone w zależności od ich odległości** (dla wybranej metryki) do gwiazdki: im dalej jest głosujący wzorzec, tym ma mniejszą wagę. A więc wzorce położone najbliżej będą miały największy wpływ na wynik klasyfikacji.
![[Pasted image 20240702111902.png]]

**Nadzorowane i nienadzorowane uczenie**
?
●       **Nadzorowane uczenie**: wnioskowanie z przykładów z przypisanymi klasami.
●       **Nienadzorowane uczenie**: odkrywanie użytecznych właściwości danych bez przypisanych klas, najczęściej przez grupowanie (klastry).

Klastry
?
Klastry są grupami obiektów (np. danych), które są do siebie podobne. Właściwości klastrów obejmują różne aspekty takie jak gęstość, spójność, czy rozmiar. Ta zasada mówi, że obiekty w klastrze powinny być bliżej siebie niż obiekty z innych klastrów, co jest kluczowe dla dobrego klasyfikowania.

 **Cel klastrów**:
-  Identyfikacja grup podobnych przykładów.
- Reprezentowanie klastrów, np. przez centroidy.
	-  centroidem nazywamy środek masy danej figury geometrycznej
	-  średnia atrybutów obiektów należących do danego klastra
	-  atrybuty dyskretne muszą zostać przekształcone w liczbowe
-  Pomiar odległości do klastrów i między nimi.
- Przypisanie przykładu do klastra.


strict clustering vs fuzzy clustering
?
- **Strict clustering (ściśle określone klastry)**: Każdy obiekt należy do jednego, wyraźnie określonego klastra. Nie ma żadnego nakładania się klastrów.
- **Fuzzy clustering (rozmyte klastry)**: Obiekty mogą należeć do więcej niż jednego klastra z różnym stopniem przynależności, co pozwala na nakładanie się klastrów

**Wewnętrzna gęstość i spójność klastrów**:
- **Gęstość wewnętrzna**: Odnosi się do tego, jak blisko siebie są obiekty wewnątrz klastra. Im wyższa gęstość, tym obiekty są bliżej siebie.
- **Spójność**: Odzwierciedla, na ile jednorodne lub spójne są obiekty wewnątrz klastra pod względem ich cech.

**Liczba i równowaga klastrów**:
?
 - **Liczba klastrów**: Odnosi się do ilości klastrów używanych do podziału danych. 
- **Równowaga klastrów**: Dotyczy równomiernego rozłożenia obiektów w różnych klastrach. Klastry są bardziej zbalansowane, gdy mają podobną liczbę obiektów.


#### k-Means
?
[https://www.youtube.com/watch?v=4b5d3muPQmA](https://www.youtube.com/watch?v=4b5d3muPQmA)
●       **Wejście**: zestaw przykładów bez etykiet klas, stała k.
●       **Proces**:
1.     Stwórz początkowe klastry i oblicz centroidy.
2.     Przypisz każdy przykład do najbliższego centroidu.
3.     Aktualizuj centroidy.(znajdz srodki  klastrów i zrob jeszcze raz klasetryzacje)
4.     Powtarzaj, aż wszystkie przykłady znajdą się w najbliższym klastrze.
![[Pasted image 20240702112610.png]]

Jak wybrać k do k-means?
?
Trzeba probowac rozne wartosci i ich total variation, szukamy elbow na wykresie

Problemy k-Means
?
●       **Normalizacja atrybutów**: konieczność ujednolicenia skali wartości.
●       **Inicjalizacja**: losowa lub z wiedzą wstępną, wplywa to na liczbe obliczen

Klastry Hierarchiczne - Kategorie:
?
-        top-down: wszystkie obserwacje zaczynają w jednym klastrze następnie są dzielone na mniejsze, np. hierarchical k-means
-        bottop-up: na odwrót
Zalety:
-        liczba klastrów nie musi być wcześniej zdefiniowana


klastry hierarchiczne - kryteria powiązań
?
-        **single-link**: minimum z odległości: bardzo ciasne klastry o wysokim stopniu podobieństwa
-        **average-link**: średnia z odległości
-        **max-link**: maximum z odległości: luźno powiązane klastry

Agregacja hierarchiczna klastrów- algorytm
?
Wejście: zbiór przykładów bez etykiet
1)     dla n przykładów stwórz n klastrów, po jednym przykładzie każdy
2)     znajdź parę klastrów dla których odległość jest najmniejsza
3)     połącz te klastry
4)     **if** kryterium stopu **then** zakończ **else** powtórz od kroku 2
![[Pasted image 20240702113824.png]]
![[Pasted image 20240702113832.png]]


## 9. Eksploracja danych językowych: modele generatywne

**Autoregresywne modele językowe**
?
Autoregresywne modele językowe to rodzaj modeli stosowanych w przetwarzaniu języka naturalnego (NLP), które generują sekwencje słów, przewidując kolejne słowo na podstawie wcześniejszych słów w sekwencji. Innymi słowy, te modele tworzą tekst, **przewidując jedno słowo naraz**, przy czym każda prognoza jest uzależniona od wcześniej wygenerowanych słów. Autoregresja oznacza, że model używa własnych wcześniejszych wyjść (przewidywań) jako części wejścia do prognozowania kolejnych słów.

LLM
?
Large Language Model
Zawiera miliardy parametrów

Właściwości LLM
?
1. **“emergent abilities(rosnące zdolności wraz ze wzrostem)”** - zdolności, które nie występują w małych modelach, ale pojawiają się w dużych modelach
	-  duże modele zaczynają osiągać znacznie lepsze wyniki w zadaniach, gdy osiągają odpowiednią wielkość
2. **“In-context learning”** - generowania oczekiwanych wyników na podstawie dostarczonych **instrukcji w języku naturalnym i/lub kilku demonstracji zadań**. Innymi słowy, model może uczyć się nowych zadań bez potrzeby dodatkowego treningu, po prostu na podstawie przykładów dostarczonych jako część wejścia
	- np Napisz to w formacie fiszek do obsydiana o tak...: - **instrukcja i demonstracja**
	- . UWAGA! - to nie jest uczenie z definicji!!! pytanie egzaminacyjne
3. **“Instruction following”** – odnosi się do zdolności modeli językowych do wykonywania poleceń podanych w formie instrukcji. Model uzyskuje dobrą wydajność na wcześniej niewidzianych danych, ponieważ nauczył się rozumieć i wykonywać różnorodne polecenia.
4. **“Chain-of-thought prompting”** - Model rozwiązuje trudne problemy, korzystając z podpowiedzi zawierających kroki pośrednie, co pomaga w logicznym wnioskowaniu i osiągnięciu prawidłowego wyniku
	- lepiej napisać co chat ma zrobić krok po kroku niż ogólnie
![[Pasted image 20240702115508.png]]


Chat GPT-3
?
- model autoregresywny
- LLM
- casual decoder architecture(architektura dekodera przyczynowego)
	- **Maska uwagi jednokierunkowej**: Gwarantuje, że każdy token wejściowy może zwracać uwagę tylko na wcześniejsze tokeny i na siebie samego.
	-  **Tokeny wejściowe/wyjściowe**: Przetwarzane w ten sam sposób przez dekoder.
- Codex - gpt model który
	-  ćwiczył na kodzie z githuba żeby lepiej logicznie myśleć
	- trenował z kodem i tekstem jednocześnie, zeby odroznial te formy
- **Uczenie ze wzmocnieniem do nauki porównań preferencji przez ludzi - w chatcie można wybrać który tekst był najtrafniejszy**


**LLMs - Architektury 3**
?
1. **Architektura enkoder-dekoder**:
    -  **enkoder** przetwarza wejściową sekwencję danych (np. zdania w języku naturalnym), a **dekoder** generuje sekwencję wyjściową (np. przetłumaczone zdanie).
    - **Enkoder**: Składa się z wielowarstwowych warstw samouważania wielogłowicowego, co pozwala modelowi na efektywne uczenie się zależności między tokenami wejściowymi.
    - **Dekoder**: Wykonuje krzyżową uwagę na reprezentacjach wytworzonych przez enkoder, co umożliwia generowanie sekwencji wyjściowych
    - PO LUDZKU: oprócz tokenów które już wygenerował korzysta tez z tokenów wejściowych z enkodera
    - **Przykłady modeli**: T5 (Text-To-Text Transfer Transformer), BART (Bidirectional and Auto-Regressive Transformer), Flan-T5.
2. **Architektura dekodera przyczynowego**:
    - **Maska uwagi jednokierunkowej**: Każdy token wejściowy ma dostęp tylko do informacji z wcześniejszych tokenów i do siebie samego podczas przetwarzania.
    - **Tokeny wejściowe/wyjściowe**: Są przetwarzane w taki sam sposób przez dekoder, co umożliwia generowanie sekwencji tokenów w sposób autoregresyjny.
    - **Przykłady modeli**: GPT-1, GPT-2, GPT-3, GPT-3.5, OPT, BLOOM, Gopher.
3. **Architektura dekodera z prefiksem**:
    - **Dwukierunkowa uwaga nad tokenami prefiksu**: Umożliwia dekoderowi uwzględnienie zarówno tokenów prefiksu, jak i kontekstu przyszłych tokenów podczas generowania wyjściowych sekwencji.
    - **Kodowanie prefiksu i autoregresywne przewidywanie**: Prefiks jest kodowany dwukierunkowo, a tokeny wyjściowe są przewidywane autoregresyjnie, jeden po drugim, co przyspiesza proces generowania.

dostrajanie llm oparte na uczeniu ze wzmocnieniem
?
![[Pasted image 20240702123743.png]]
1. Najpierw zbieramy zbiór danych demonstracyjnych, które są przykładami promptów napisanych przez ludzi i przesłanych do naszego API. Wykorzystujemy ten zbiór do trenowania naszych podstawowych modeli przy użyciu uczenia nadzorowanego.
2. Następnie gromadzimy zbiór danych porównawczych, gdzie ludzie oznaczają różnice między wynikami naszego modelu a referencyjnym zestawem monitów API. Kolejnym krokiem jest trening modelu nagrody (RM) na tym zbiorze danych, który ma za zadanie przewidzieć, które wyjścia są preferowane przez naszych etykietujących.
3. Na koniec używamy RM jako funkcji nagrody i optymalizujemy naszą politykę opartą na modelu GPT-3, aby maksymalizować tę nagrodę, korzystając z algorytmu PPO (Proximal Policy Optimization).

**Pretraining (wstępne trenowanie)**:
?
- Proces inicjowania modelu z losowymi wagami i trenowania go na dużym zbiorze danych.
- potem uzywa sie takiego modelu z dostosowanymi wagami na innych danych

**FINE-TUNING(nastrajanie)**
?
polega na dostosowaniu parametrów już wstępnie wytrenowanego modelu do nowego, zazwyczaj mniejszego, zbioru danych specyficznego dla danego zadania. Ten proces pozwala modelowi przenieść ogólną wiedzę, którą zdobył podczas wstępnego trenowania, do niuansów nowego zadania

RLHF
?
Reinforcement Learning with Human Feedback (RLHF) to podejście w uczeniu maszynowym, które łączy techniki uczenia ze wzmocnieniem (reinforcement learning, RL) z informacjami zwrotnymi od ludzi. Głównym celem RLHF jest wykorzystanie ludzkiej wiedzy, doświadczenia lub ocen jako źródła sygnałów informacyjnych, które wspomagają proces uczenia się agenta.
Istnieje kilka podejść do RLHF, w tym:
1. **Preferencje użytkownika**: Ludzie mogą dostarczać informacje o preferencjach dotyczących różnych sekwencji działań lub wyników.
2. **Oceny jakościowe**: Ludzie mogą oceniać jakość wyników lub strategii, co pozwala na poprawę działania agenta w przyszłości.
3. **Korekta błędów**: Ludzie mogą korygować działania agenta, wskazując na błędy i sugerując lepsze rozwiązania.

Halucynacje
? 
model nie ma pelnej informacji i zgaduje lub klamie

