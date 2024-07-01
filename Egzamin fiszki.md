#si 

## 1. Temat 1 
2 definiujące perspektywy ai
??
1. budowanie modeli/systemów naśladujacych ludzki mózg
2. konstruowanie algorytmów do rozwiązywania problemów trudnych dla ludzi, w sposób zbliżający się do człowieka

dedukcja
??
1. od ogółu do szczegółu
2. pozwala wyciągnąć prawidłowe wnioski
3. wnioskowanie (to co się dowiemy jest już w danych, tylko trzeba jakoś to wyciągnąć)

indukcja
??
1. Od szczegółu do ogółu
2. często wyciągamy błędne wnioski
3. uczenie (na podstawie doświadczeń wyciągamy wiedzę, która jest tylko tak dobra jak doświadczenia)

wnioskowanie vs uczenie::wnioskowanie: baza wiedzy->twierdzenia ->prawdziwe wnioski(bo z dedukcji)
??
uczenie:wnioskowanie statystyczne z uogólnieniami i indukcją ->powstają reguły np. Dużo stworzeń morskich składa jaja, więc wszystkie stworzenia morskie to robią(nieprawdziwe)

2 metody wnioskowanie dedukcyjnego
??
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
??
1. teoria - baza wiedzy(fakty)
2. wnioskowanie logiczne - weryfikacja hipotez, rozumowanie o nowych faktach w bazie wiedzy

słabości wnioskowania dedukcyjnego
??
1. nie może wywnioskować niekompletnych przesłanek
2. wszystkie wnioski są już w jakiś sposób zawarte w bazie
3. fakty w bazie wiedzy mogą się zmieniać, powstają nowe, więc system może nie nadążać, dając stare wnioski

programy do wnioskowania dedukcyjnego
??
MYCIN - system ekspertowy medyczny
Deep Blue - system do szachów
Systran - system tłumaczenia maszynowego

metoda uczenia indukcyjnego
??
algorytm tworzący uogólniającą hipoteze na podst. zestawu konkretnych przykładów
np. 
1. Start - forma(hipoteza) ogólna: Wszystkie zwierzęta mają zęby, które mogą być klasyfikowane jako kły, siekacze lub trzonowce.
2. Uczenie się szczegółów np parametrów - zęby, włosy
3. Hipoteza(Reguła): Probability(herbivores) = f(Canine teeth length, Claw length) - zawiera podobieństwa zwierzą

przykłady zastosowania uczenia indukcyjnego
??
1. AI
2. rozpoznawanie obrazu, mowy, tłumaczenie maszynowe, inteligente konrtolery

wyzwania uczenia indukyjnego
??
przez to że ostateczne reguły mogą nie być prawdziwe to: 
1. wiarygodność
2. wyjaśnialność
3. uczenie oparte o ograniczoną liczbę przykładów

połączenie podejścia indukcyjnego i dedukcyjnego
??
- indukcyjne uczenie
- dedukcyjne wnioskowanie

co to SI
??
- sposób na symulację ludzkiego mózgu - procesów myślenia, zdolności rozwiązywania problemów, modelowanie mózgu
- sposób na rozwiązanie problemów trudnych dla człowieka
	- NP-trudne
	- problemy optymalizacyjne
	- wynik i wydajność

test turinga
??
człowiek pyta człowieka i maszyne różne rzeczy, a potem człowiek ma rozpoznać, który to maszyna

z czego składa się problem
??
1. zbiór danych, opisujące problem
2. zbiór operacji(akcji), które mogą być wykonane, by dojść do rozwiązania
3. cel - czym jest rozwiązanie problemu

agent do rozwiązywania problemów
??
- działa autonomicznie
- posiada percepcję, poprzez sensory, jak człowiek
- może aktualizować swój stan wiedzy, zdobytej przez sensory
- może współdziałać z otoczeniem

typy problemów zw. ze środowiskiem, z perspektywy agenta, który ma je rozwiązać:
??
●       **Dostępne i niedostępne** – czy mamy kompletną informację np. w pokerze nie
●       **Deterministyczne(następny stan = stan bieżący + akcje) i niedeterministyczne** – pewność następnego stanu, czasami nie wiemy co dokładnie da jakaś akcja
●       **Epizodyczne(niezależność epizodów) i nieepizodyczne(zależność epizodów)** – brak ciągu przyczynowo skutkowego? (to epizodyczne)
●       **Statycznie i dynamiczne** – upływ czasu
●       **Dyskretne i ciągłe**

typy problemów, niezależnie od środowiska
??
1. pojedynczego stanu
	- środowisko w pełni dostępne
	- rezultaty akcji znane
2. wielu stanów
	- środowisko nie w pełni dostepne
	- rezultaty akcji znane
3. problem niepewności
	- rezultaty niepewne


![[Pasted image 20240630094607.png]]??
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
??
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
??
skierowany graf acykliczny

drzewo
??
sga z korzeniem(węzeł bez łuków wchodzących), każdy inny węzeł ma 1 wchodzący, liście - węzły bez wychodzący
- jeśli dla każdego węzła WRW(wchodzące) = b, wtedy istnieje bn węzłów o odległości równej n łuków od dowolnego węzła.

problem jako graf
??
- zdefiniowanie węzłów początkowych i docelowych
- rozwiązanie to ścieżka od start do end(przeprowadzamy test celu żeby się dowiedzieć czy skończyliśmy)

Składniki przestrzeni stanów - stany które można osiągnąć w ramach jakiegoś problemu
??
1.        Zbiór stanów
2.        Podzbiór stanów początkowych
3.        operatory na stanach, żeby zmienic 1 stan w 2
4.        Cel – docelowy stan
5.        Kryterium akceptowalności rozwiązań – miara jakości- czy zadowalające rozwiązanie

Ogólny algorytm przeszukiwania
??
- stopniowe rozszerzanie do puntku wyjścia
- strategia – okresla które wezly przeszukiwac
- Ogólnie mamy zbiór (front) do którego wkładamy kolejne węzły, i na podstawie strategii wybieramy który brać pierwszy

Strategie przeszukiwania
??
1. niepoinformowane - ślepe, bez heurystyki
	1. w głąb
	2. wszerz
	3. najniższego kosztu
2. poinformowane - heurystyczne
3. przeszukiwanie z przeciwnikiem - niepewność spowodowana przez drugiego agenta
4. rozwiązywanie problemów z ograniczeniami(CSP)

Ocena strategii przeszukiwania
??
●       Kompletność - jeżeli tylko istnieje rozwiązanie, algorytm gwarantuje znalezienia go w skończonym czasie.
●       Optymalność - gdy znajdzie rozwiązanie, jest to najlepsze rozwiązanie
●       Złożoność
	o   Czasowa w najgorszym przypadku – maksymalna długość ścieżki, maksymalny/średni współczynnik rozgałęzienia do przodu (ile łuków wychodzi z danego węzła, rozgałęzienie wstecz to ile wchodzi do węzła)
	o   Pamięciowa w najgorszym przypadku – maksymalna liczba węzłów na froncie
	strategia przeszukiwania  - W głąb(DFS)
	
![[Pasted image 20240630101006.png]]
- kolejka to stos - filo
- niekompletny i nieoptymalny
- o   Złożoność
	- czasowa: O(bd)
	-  pamięciowa: O(bd)
	- b - współczynnik rozgałęzienia, d - głębokość przeszukiwania
- ma odmianę iteracyjny DFS, kompletny i optymalny


strategia przeszukiwania  - wszerz??
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
??
o   Podobnie jak wszerz ale kolejka priorytetowa wybierająca ten o najniższym koszcie
o   Koszt ścieżki – suma kosztów łuków
o   Gwarantuje optymalne rozwiązanie jeśli koszt łuku to liczba dodatnia, współczynnik rozgałęzienia jest skończony i rozwiązanie istnieje
o   to jak te tramwaje robiliśmy

problemy przeszukiwania niepoinformowanego
??
Problemem są powroty – czyli wielokrotnie sprawdzanie tych samych węzłów
	●       **Blokada generacji stanu identycznego z poprzednikiem** – przed dodaniem nowego stanu do przestrzeni przeszukiwania, sprawdzane jest czy istnieje
	●       **Cykle o jednym łuku** -blokowanie a do b i potem b do a
	●       **Blokada generacji ścieżek zawierających cykle** – blokowanie dowolnych ściezek zawierajacycjh cykle

Funkcja heurystyczna(heurystyka)
??
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
??
	●       Najlepszy pierwszy (best -first search)
		o   wybierasz węzeł o najlepszej **wartości heurystyki,** tylko według niej.
		o   Niekompletny i nieoptymalny
	●       A*
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
??
●       Relaksacja problemu – upraszczanie ograniczeń, np. opuszczanie jednego lub kilku ograniczeń. W przypadku tramwajów ograniczeniem jest to że musimy poruszać się tak jak są przystanki a dla euklidesowej heurystyki zakładamy że możemy iść w linii prostej
●       Kombinacja akceptowalnych heurystyk
●       Kombinacja liniowa cech – można dobrać wartości współczynników poprzez uczenie maszynowe, wtedy mamy jakieś przybliżenie dla określonego stanu
●       Korekta heurystyki na bazie informacji statystycznej – np. gdy h(x) = 14 to w 90% rzeczywiście jest 18, można wtedy dostosować heurystykę

heurystyka konturowa
??
dobra dla A*

problemy A*
??
- duża złożoność pamięciowa
- Zawsze znajduje optymalne rozwiązanie i jest to pierwsze rozwiązanie znalezione, jeśli: 
	- rozwiązanie istnieje, 
	- współczynnik rozgałęzienia jest skończony (każdy węzeł ma skończoną liczbę sąsiadów), 
	- koszt łuków jest większy niż pewne ε>0, 
	- h(n) jest dolną granicą rzeczywistego minimalnego kosztu ścieżki z najniższym kosztem z n węzła docelowego - heurystyka jest optymistyczna

Zoptymalizowane A*
??
1. **Iterative Deepening A* (IDA***) – jest to połączenie A* i iteracyjnego przeszukiwania w głąb (IDDFS, wspomniane wcześniej), **używa ograniczenia na f =** funkcja kosztu + funkcja heurystyczna, idzie w głąb aż przekroczy limit na f.
	- Kompletny i optymalny
		**złożoność pamięciowa bf*/d, where b – a branching factor, f* – the optimal path cost, d – the lowest cost of a operator**
1. **Simplified Memory-bounded A* (SMA*)** – IDA* bardzo często przeszukuje te same stany **kilkukrotnie** bo to DFS, SMA* tego nie robi (jeśli pamięć pozwala). Przechowuje jakąś ograniczoną ilość węzłów w pamięci. Gdy pamięć jest pełna usuwa najpłytsze węzły o najwyższym koszcie. Koszt usuniętego węzła jest przechowywany w rodzicu aby później móc do niego wrócić. Gdy wyczerpie możliwość rozwijania, wraca do tego co usunął o najniższym koszcie.
- Jest optymalny gdy pamięć pozwala na przechowanie najkrótszej ścieżki, w przeciwnym razie zwraca częściowe rozwiązanie.

Local Search
??
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
??
Local search czasami utyka w lokalnych optimach, w tym celu wprowadza się stany już odwiedzone (taboo) I specjalnie skacze do innych czasami gorszych, w celu znalezienie globalnego optimum.



## 2. Gry logiczne – klasyczne wyzwanie, algorytmy grające i ich rozwój

gra
??
to  rozgrywka prowadzona przez gracza (lub graczy) zgodnie z ustalonymi zasadami, w której należy osiągnąć ściśle określony cel.

Strategia gry
??
to kompletny zbiór zasad, które determinują posunięcie gracza, wybierane dla sytuacji powstających podczas gry.

Gra w ujęciu formalnym (wg. von Neumanna i Morgensterna, w teorii gier)
??
Gra składa się z zestawu reguł określających możliwości wyboru postępowania jednostek znajdujących się w sytuacji określanej mianem konfliktu interesów, w której każda z jednostek stara się maksymalizować swój własny zysk i jednocześnie minimalizować zysk pozostałych jednostek (graczy). Reguły gry określają też ilość informacji dostępną każdemu z graczy oraz wysokości wygranych i przegranych.

Zadania gracza
??
Gry wymagają od graczy czynienia sekwencji decyzji, które:
●        zwiększają ich **oczekiwaną wypłatę** (tj. łączne wygrane: skutki i rozmiary wygranej/przegranej),
●        biorą pod uwagę **czynniki determinujące bieżącą sytuację** (stan gry)
●        oraz **skończoną ilość czasu** (często znacząco ograniczoną).

problemy graczy
??
●       ograniczony czas nie pozwala podjąć optymalnej decyzji
●       podjęte kroki nie mogą już zostać cofnięte
●       długofalowy wynik każdego podjętego kroku jest niepewny
●       Nie znamy decyzji pozostałych graczy

klasyfikacja gier - liczba graczy
??
●        bezosobowe (zero-player game), np. popularna gra w życie (Conway's live),
●        jednoosobowe (one-player game), np. puzzle, pasjans,
●        dwuosobowe (two-player game), np. szachy, warcaby, otello, go,
●        wieloosobowe (multi player), np. poker, brydż.

klasyfikacja gier - suma
??
●       o sumie zerowej (ze znaną wypłatą), gdzie wygrana jednego gracza jest przegraną drugiego (zero sum games), np. szachy, warcaby, othello, go,
●       o sumie niezerowej (non zero sum), np. dylemat więźnia.

klasyfikacja gier - współpraca
??
●       kooperacyjne (cooperative) – gracze współpracują ze sobą,
●       nie kooperacyjne (non cooperative) – gracze nie współpracują ze sobą.

klasyfikacja gier - losowość
??
●       całkowicie losowe gry, np. ruletka,
●        częściowo losowe gry, np. brydż i inne gry karciane,
●        całkowicie deterministyczne gry, np. warcaby, szachy, othello, go.
![[Pasted image 20240630173636.png]]

cechy gier logicznych
??
●       jeden z najstarszych obszarów zastosowań AI
●       Zasady gier są precyzyjnie określone, rezultat łatwo mierzalny
●       historia sztucznej inteligencji jest nierozerwalnie z nimi związana

Konstrukcja Inteligentnych graczy -założenia
??
- wykonują wybrane przez nich posunięcia spośród zbioru możliwych ruchów.
- Grę można postrzegać jako poszukiwanie takich ruchów gracza, które zapewniają mu zwycięstwo.

drzewo gry
??
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
??
●       Stan początkowy (planszy)
●       Stan bieżący -  ruch gracza lub przeciwnika (przeciwstawne cele i ocena)
●       Operatory – ruchy dozwolone w danej sytuacji
●       Test celu – test końca gry lub liczenie funkcji wypłaty

przyczyny wykorzystania heurystyk w grach
??
●       Drzewo gry nie może być rozwinięte do końca (przez większość gry)
●       Głębokość rozwinięcia zależy od dostępnych zasobów, np. czasu
●       Gracz (program) musi podejmować decyzje na podstawie częściowego drzewa gry rozwiniętego na osiągalną głębokość ze stanu początkowego

cechy heurystyki gry
??
●       Heurystyczna funkcja oceniająca to symulacja ludzkiej oceny
●       wyraża numerycznie jakość pozycji
●       byłoby dobrze, aby była pozytywnie skorelowana z prawdopodobieństwem wygranej,
●       musi zgadzać się z funkcją wypłaty.
●       częsty sposób wyliczenia - ważona suma cech stanu gry
![[Pasted image 20240630174750.png]]

Rozgrywka - kluczowe pojęcia
??
●       Strategia (wygrywająca) – dobór sekwencji ruchów prowadzących do wygranej niezależnie od ruchów przeciwnika
●       Posunięcie – para ruchów:〈ruch własny, ruch przeciwnika〉
●       MinMax -  sposób podjęcia decyzji, co do ruchu minimalizujący wpływ przeciwnika na końcowy rezultat.

Rozwiązania niepoinformowane - cechy
??
●       Brak użycia heurystyki (ang. blind search, brute force)
●       Wszystkie węzły drzewa gry osiągalne z danej pozycji są rozwijane.
●       Drzewo gry zbliżone do ludzkiego – człowiek rozważając hipotetyczne scenariusza nie bierze pod uwagę wszystkich możliwych zdarzeń,  eliminuje mniej prawdopodobne , które intuicyjnie nie prowadzą do celu.

Algorytm Min-Max
??
●       Heurystyczna funkcja kierunkuje poszukiwania
●       Zakładamy, że oponent wybiera najlepsze ruchy
●       Ocena z perspektywy gracza
●       W trakcie naszej tury maksymalizujemy ocenę pozycji, w trakcie tury przeciwnika minimalizujemy

Punkt odcięcia
??
Ustalona głębokość (również głębokość zastosowania funkcji oceniającej).

Problem horyzontu
??
ruch przeciwnika zmieniający drastycznie stan gry (i wartość zwracaną przez funkcję oceniającą)

Stabline pozycje(w grze)
??
takie, które nie wykazują możliwości drastycznej zmiany funkcji oceniającej w najbliższej przyszłości

alfa-beta-cięcie
??
- **Alfa** - najlepsza wartość z poziomu **max**
- **Beta** - najlepsza wartość z poziomu **min**
- Pominięcie poddrzew, które nie zmienią wartości na poziomie wyższym. W wyniku znaczne skrócenie czasu przeszukiwania
- Złożoność zależy od porządku rozwijania węzłów
●       optymistyczna - O(b^d/2)
●       pesymistyczna - O((b/log b)^d)
●       gdzie b —współczynnik rozgałęzienia, d — głębokość przeszukiwania

PROBCUT
??
- rozszerzenia alfa-beta
- Algorytm alfa-beta cięcie rozwija części gałęzi do propagacji wartości - **część tych propagacji jest niepotrzebna**.
	- Mocna korelacja wartości funkcji oceniającej dla kolejnych wartości węzłów
	- możliwość aproksymacji wartości węzłów leżących niżej (na ograniczoną głębokość)

Algorytmy ewolucyjne
??
Zastosowanie w grach:
●       **Narzędzie wspierające znalezienie strategii grania**
	○      konstrukcja/optymalizacja funkcji oceniającej
	○       kodowanie potencjalnej strategii wygrywającej
●       **Moduł odpowiedzialny za podejmowanie optymalnych decyzji**

Deep blue
??
●       **Pierwszy** silnik szachowy, który **pokonał szachowego mistrza świata** - Garry’ego Kasparova w 1997 (rok wcześniej z nim przegrał)
●       Utworzony **na podstawie** algorytmu **alfa-beta cięcie**

## 3. Problemy spełniania ograniczeń - rozwiązywanie przez przeszukiwanie

Charakterystyka problemu
??
1. stan = zbiór zmiennych i ich wartości 
2. cel = zbiór warunków ograniczeń, postaci relacyjnej, określonych na zmiennych 
3. rozwiązanie = przypisanie wartości do zmiennych spełniające wszystkie ograniczenia celu 
	1. operator: przypisanie wartości do zmiennej, duży współczynnik rozgałęzienia 
	2. np. problem ośmiu hetmanów, konstrukcja modelu dla zbioru formuł – podstawa działania model builders

Ograniczenia w CSP
??
- dowolna postać relacyjna (w tym ograniczenia funkcyjne) 
- absolutne – integralna część celu 
- preferowane – wprowadzają porządek częściowy rozwiązań
- ograniczenie zmiennych - dziedzina - dyskretna/ciągła

 Ogólna zasada algorytmów ślepych dla CSP
 ??
 - dekompozycja celu na zbiory ograniczeń dla poszczególnych zmiennych:
	 - redukcja olbrzymiego współczynnika rozgałęzienia

CSP jako Graf Ograniczeń
??
●       **Ograniczenia binarne**: Relacje między dwoma zmiennymi (dwuelementowe).
●       **Graf ograniczeń**:
	○       **Zmienne**: Reprezentowane jako węzły grafu.
	○       **Ograniczenia**: Reprezentowane jako łuki grafu, które łączą pary węzłów (zmiennych) związanych ograniczeniami. Łuki są nieetykietowane nazwami relacji i nieskierowane.
		![[Pasted image 20240630185840.png]]
	
Algorytmy niepoinformowane (ślepe) w CSP
??
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
??
●       Rozpoczyna od pustego przypisania.
●       Wybiera nieprzypisaną zmienną i przypisuje do niej wartość.
●       Sprawdza, czy przypisanie jest zgodne z ograniczeniami.
●       Rekurencyjnie próbuje przypisać wartości kolejnym zmiennym.
●       Jeśli napotka sprzeczność, cofa się (nawrót) i próbuje inne wartości.

**Propagacja ograniczeń (ang. Constraint Propagation)**
??
●       Polega na automatycznym i systematycznym przekazywaniu informacji o ograniczeniach między zmiennymi w celu redukcji przeszukiwanej przestrzeni rozwiązań.

Cele propagacji ograniczeń
??
1.  **Wykrywanie sprzeczności**: Poprzez propagację ograniczeń można szybko identyfikować sytuacje, w których żadne przypisanie wartości do zmiennych nie spełnia wszystkich warunków ograniczeń.
2. **Redukcja dziedzin zmiennych**
3. Szybsze algorytmy

**Techniki propagacji ograniczeń:**
??
1. **Forward Checking**:
	 Po przypisaniu wartości do zmiennej, eliminuje wartości z dziedzin innych zmiennych, które są sprzeczne z nowym przypisaniem.
●       **Spójność łukowa (Arc Consistency)**:
 zachowywanie tylko tych wartości w dziedzinach, które nie są sprzeczne z ograniczeniami
●       **Spójność wyższego rzędu**:
 Propaguje ograniczenia przez więcej niż jeden łuk w grafie, co może skuteczniej redukować przeszukiwaną przestrzeń rozwiązań.

Heurystyka kolejności sprawdzania zmienny i wartości
??
- aby zmniejszyć liczbę przeszukiwanych węzłów
1. Heurystyka najbardziej ograniczonej zmiennej
	- redukcja wsp. rozgałęzienia
	- zmienna która ma najmniej wartości w swojej dziedzinie
2. Heurystyka najbardziej ograniczającej zmiennej
	- redukcja wsp. rozgałęzienia
	- powiązana z największą liczbą innych zmiennych
3. Heurystyka najmniej ograniczającej zmiennej
	- powiązana z największą liczbą innych zmiennych

**CSP (Constraint Satisfaction Problems)**
??
to problemy, w których trzeba przypisać wartości zmiennym tak, żeby spełniały one określone ograniczenia (warunki).
○       **Wartościowanie spójne** oznacza przypisanie wartości zmiennym bez naruszania żadnych ograniczeń.
○       **Wartościowanie kompletne** oznacza przypisanie wartości wszystkim zmiennym w problemie.
○       **Funkcja celu** dodaje dodatkowe wymagania dotyczące jakości rozwiązania.
○       **Graf więzów** przedstawia zmienne jako węzły, a ograniczenia jako połączenia między nimi.
○       **Rodzaje problemów**:
	■       **Skończone dziedziny (dyskretne)**: Złożoność rośnie wykładniczo wraz z liczbą zmiennych.
	■       **Nieskończone dziedziny (dyskretne i ciągłe)**: Rozwiązywalne dla liniowych więzów, trudne lub niemożliwe do rozwiązania dla nieliniowych ograniczeń.

**2. Podział CSP (Strona 14)**
??
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
??
tak jak w AC-3, propagacja konsekwencji z jednego ograniczenia na drugie

MAC
??
(Maintaining Arc Consistency)
funkcja do utrzymywania spójności łukowej
- AC-3 jest wywoływany dla wszystkich Xj, które nie mają przypisanej wartości i są powiązane z własnie zmienionym Xi

**AC-3**
??
to algorytm, który sprawdza i utrzymuje spójność łukową w grafie ograniczeń. Polega na usuwaniu niespójnych wartości z dziedzin zmiennych.
○       **Funkcja REVISE** weryfikuje dziedzinę zmiennej, eliminując wartości, które są niespójne z ograniczeniami.
○       **MAC (Maintaining Arc Consistency)** to technika wywoływania AC-3 po przypisaniu wartości zmiennej, aby utrzymać spójność łukową dla powiązanych zmiennych.

heurystyki dystrybucji
??
1. najbardziej ograniczonej zmiennej
2. najbardziej ograniczającej zmiennej
3. najmniej ograniczającej wartości - wybór wartości, która najmniej ogranicza możliwości przypisania wartości innym zmiennym

●       **K-spójność**
??oznacza, że dla każdego zbioru k-1 zmiennych, przypisanie wartości k-tej zmiennej będzie spójne.
○       **2-spójność**: Spójność łukowa.
○       **3-spójność**: Spójność ścieżkowa (path consistency).

●       **Specjalne typy więzów**:
??
	○       **Alldiff**: Wszystkie zmienne muszą mieć różne wartości.
	○       **Atmost**: Warunek dotyczący sumy zasobów, np. nie więcej niż 10 jednostek zasobów przypisanych do pewnych zmiennych
	
●       rejestracja(jak się objawia wynik progpagacji) wyników propagacji(ograniczeń)
??
	○       ograniczanie dziedziny (domain propagation)
	○       ograniczanie zakresu (bounds propagation) sprawdzanie i modyfikacja dolnych i górnych ograniczeń dziedzin zmiennych
![[Pasted image 20240630201254.png]]



**. Strategie przeszukiwania w CSP**
??
●       **Chronological Backtracking**: Powrót do poprzedniego kroku, gdy napotka się sprzeczność.
●       **Backjumping**: Powrót do zmiennej, która bezpośrednio powoduje konflikt.
●       **Conflict-directed backjumping**: Powrót do zmiennej, która pośrednio powoduje konflikt.
●       **Uczenie się więzów**: Dodawanie nowych ograniczeń na podstawie napotkanych sprzeczności, aby uniknąć powtórzenia błędów.
●       **Lokalne przeszukiwanie (local search)** w CSP??
Metoda, w której przeszukuje się przestrzeń możliwych rozwiązań poprzez modyfikację aktualnego stanu, zamiast zaczynać od zera.

Rozwiązania różnych **Struktur problemu**:
??
○        Możliwość podziału problemu na niezależne podproblemy.
○       **Algorytm dla drzewowego CSP**: Rozwiązanie w czasie liniowym zależnym od liczby zmiennych.
○       **Redukcja grafów do postaci drzewa**: Ustalanie wartości dla węzłów i redukcja problemu.


## 4. Wnioskowanie i reprezentacja wiedzy


Agent logiczny
??
To agent działający w oparciu o:
1.      Bazę wiedzy i zapisany w niej opis środowiska
2.      Mechanizmy wnioskowania logicznego
Wykorzystując to wykazuje zdolność do **przewidywania zmian środowiska.**

Powody stworzenia agenta logicznego jako metody rozwiązywania problemów:
??
1.      Konieczność sformułowania jawnej, pełnej specyfikacji stanu
	a.      Zapis stanu
	b.      Akcje zapisane jako procedury
2.      Bardzo duży współczynnik rozgałęzienia
	a.      Wiele możliwych akcji choć niewiele sensownych w poszczególnych klasach stanów środowiska
3.      Jeden cel (‘typ’) celu – mimo rozbicia realizacji na etapy

Techniki dostępne dla agenta logicznego:
??    
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
??
- logicznie (formalnie) poprawna metoda wnioskowania (od ogółu do szczegółu)
- Wnioskowanie dedukcyjne wykorzystuje operator implikacji:
1. zakłada się, że prawdziwa jest implikacja p→q, 
2. z prawdziwości implikacji i z prawdziwości przesłanki p (która może być zdaniem złożonym) dedukuje się prawdziwość konkluzji q
3. Z pewnej ogólnej reguły (znana) i faktu (znany) dedukujemy nowy fakt (wnioskowanie top-down) – od ogółu do szczegółu

Abdukcja
??
- wnioskowanie o prawdopodobnych przyczynach, jest procesem wyjaśniania tego, co jest nam już wiadome.
- Niepoprawna logicznie forma wnioskowania. Mając implikację p -> q, która jest prawdziwa wiemy, że jeżeli q jest prawdziwe to p też. Problem z abdukcją polega na tym, że atrybuty mogą nie być sensownie powiązane.

Implikacja
??
p→q
Term po lewej stronie (przesłanka) implikuje term po prawej stronie (konkluzję)
(p → q)  ≡  ¬ p ∪ q

Słabości implikacji:
??
1. p i q razem mogą nie mieć sensu
2. fałszywa (FALSE) hipoteza implikuje każdą konkluzję
3. implikacja p →q nie oznacza, że „p powoduje q”
4. proste wyrażenie może być traktowane jak implikacja bez przesłanki (q)

Dedukcja wykorzystująca twierdzenia logiki
??
![[Pasted image 20240701202828.png]]
Wniosek? Profesor uczy, dlatego jest nieszczęśliwy (czyli tak samo jak student)

Dopasowanie(logika)
??
- podejście symbolicznego dopasowania, it przypisuje równość (equality) prawdziwych wyrażeń (zdań), realizowane zwykle przez mechanizm wnioskujący

Forward Chaining
??
To paradygmat wnioskowania w przód

Backward chaining
??
![[Pasted image 20240701203422.png]]
![[Pasted image 20240701203641.png]]

Predykat
??
służy do pamiętania faktów.

Predykaty unarne
??
inaczej własności
1. may_move (Object)
2. next_to (Region1, Region2)
3. on_top (Support, Object)

Zaprezentuj **_The circuit breaker in line 4 is open_** w postaci predykatów
??
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
??
- system do udowadniania nieprawdziwości twierdzeń(klauzuli)
- Dodajemy do zbioru znanych prawdziwych klauzul logicznego zaprzeczenia klauzuli  i szukamy sprzeczności
![[Pasted image 20240701204714.png]]

Zbiór jest unifikowalny jeśli
??
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
??
<Obiekt, Atrybut, Wartość>, np. <liść, kolor, zielony>

Reprezentacja wiedzy - para
??
**Własność**
Para <Obiekt, Własność>, 
np. <Zwierzę, Oddycha>. Własność to relacja 1-go rzędu (jednoargumentowa).
\
Reprezentacja wiedzy - Relacja dowolnego rzędu
??
o   Binarna – między dwoma obiektami
o   Wyższych rzędów – wiele relacji binarnych, np. (((A, B), C), D)

Sieci semantyczne
??
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