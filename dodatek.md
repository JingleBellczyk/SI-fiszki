Definicje

1. Term – stała, zmienna lub n-argumentowa funkcja
2. Formuła atomowa (atom) -  to stwierdzenie, że pomiędzy termami t1 , t2 , ..., tn zachodzi relacja R: R(t1 , t2 , ..., tn ) – proste wyrażenie logiczne lub predykat
3. Klauzula -  to wyrażenie postaci: B1 , B2 , ..., Bm , A1 , A2 , ..., An

1. B1 , B2 , ..., Bm , A1 , A2 , ..., An - formuły atomowe, takie że

                                                    i.     B1 , B2 , ..., Bm stanowią alternatywę konkluzji

                                                   ii.     A1 , A2 , ..., An stanowią koniunkcję warunków 

4. Klauzula hornowska - klauzula, która ma co najwyżej jedną konkluzję
5. Asercja - klauzula hornowska bez warunków, mająca tylko konkluzję (stwierdzenie)
6. Implikacja - klauzula hornowska z jedną konkluzją i przynajmniej jednym warunkiem
7. Formuła dobrze zbudowana (wff, ang. well-formed formula) - to predykat lub wyrażenie proste lub złożone

1. a - formuła atomowa, to zastosowanie ¬,∩,∪,→,∃,∀ do a - też wff

9. Funkcja - n-tka termów poprzedzonych przez symbol funkcji lub nazwę (nazywaną również funktorem) który spełnia definicję funkcji
10. Predykat - n-tka termów, poprzedzonych przez symbol lub nazwę predykatu (mniej formalnie: Predykat to parametryzowane stwierdzenie, tzn. stwierdzenie ze zmiennymi)



przykład budowy drzewa - algrotym ID3

![[Pasted image 20240702002437.png]]
![[Pasted image 20240702002443.png]]
Mamy 2 rekordy z odpowiedzią “TAK” oraz 4 rekordy z odpowiedzią “NIE”.
## Zysk informacyjny

Konstrukcję drzewa zawsze zaczynamy od utworzenia korzenia. Sprawdzamy, czy wszystkie przykłady A,B,C,D,E,F są zaklasyfikowane do tej samej klasy decyzyjnej. W tym wypadku nie są, więc szukamy atrybutu najlepiej dzielącego przykłady ze względu na miarę entropii.

1. przeanalizowaliśmy każdy rekord w zbiorze danych dla matematyki i wyszło że mamy 2 rekordy gdzie ocena z matmy to 3.0, 3 rekordy gdzie ocena to 4.0 oraz 1 rekord gdzie ocena to 5.0
2. Tak samo jak wcześniej obliczamy entropię.
3. Powtarzamy punkt 1 oraz 2 dla Biolki i Polak

I w końcu możemy obliczyć **zysk informacyjny** – przyrost informacji o klasie

1. Bierzemy entropię całego zbioru, którą obliczaliśmy w poprzednim etapie “ENTROPIA”
2. Odejmujemy od niej entropię każdego z atrybutów po kolei
3. Zysk informacyjny to wynik który dostajemy po odjęciu entropii całkowitej od jednego z atrybutów.
4. Wybieramy atrybut z najwyższym zyskiem - Matme.

Jak widać wybrano matematykę, jako korzeń, a następnie stworzono 3 krawędzie, dla każdej z możliwych wartości tego atrybutu - 3.0, 4.0, 5.0  
Wyszło na to że wszystkie rekordy z 3.0 oraz z 5.0 nie mają stypendium, więc krawędzie mogą wskazać na węzeł będący liściem, mówiący “NIE”.  
Rekordy z 4.0 niestety mają niejednoznaczną odpowiedź, więc trzeba dalej budować drzewo.

Tym razem analizujemy tylko rekordy, które nie odpadły, czyli te gdzie Matma ma 4.0.  
Znów obliczamy przyrost informacji, bierzemy kolejny węzeł itd itd.

### 1. Architektura Koder-Dekoder

- **Model składa się z dwóch części**: kodera i dekodera.
- **Koder**: Przetwarza całe wejście (np. zdanie) i tworzy zestaw stanów ukrytych dla wszystkich kroków czasowych (tokenów) jednocześnie. Te stany ukryte zawierają zakodowaną informację o całej sekwencji wejściowej.
- **Dekoder**: Generuje wyjście, używając stanów ukrytych stworzonych przez koder. Dekoder może korzystać ze wszystkich stanów ukrytych, aby zrozumieć kontekst i generować odpowiednie wyjście. Jest to szczególnie przydatne w zadaniach, takich jak tłumaczenie języka, gdzie cała sekwencja musi być zrozumiana i przekształcona w nową sekwencję.

### 2. Architektura Tylko Dekoder

- **Model zawiera tylko dekoder**: Nie ma oddzielnego kodera.
- **Autoregresyjny**: Generuje kolejne tokeny sekwencyjnie, używając wcześniej przetworzonych tokenów. Każdy nowy token jest generowany na podstawie wszystkich poprzednich tokenów w sekwencji.
- **Samouwaga**: Dekoder korzysta z mechanizmu samouwagi, który pozwala mu zwracać uwagę na różne części wcześniej przetworzonych danych wejściowych podczas generowania kolejnych tokenów.
- **Jednokierunkowy**: Przetwarza sekwencję od lewej do prawej, biorąc pod uwagę tylko tokeny, które są przed danym tokenem. To oznacza, że każdy token jest generowany na podstawie informacji dostępnej wcześniej w sekwencji.

Podsumowując:

1. **Architektura Koder-Dekoder**: Koder koduje całe wejście jednocześnie do stanów ukrytych, a dekoder generuje wyjście, używając tych stanów ukrytych.
2. **Architektura Tylko Dekoder**: Model jest autoregresyjny, generuje kolejne tokeny sekwencyjnie na podstawie wcześniej przetworzonych tokenów, i korzysta z samouwagi do przetwarzania kontekstu.

#### Prefix Decoder:

- **Dekoder**: Nie ma oddzielnego enkodera. Zamiast tego, na początku procesu, przetwarza prefiks (np. "Ala ma") jako wstępny kontekst.
- **Generowanie**: Następnie model kontynuuje generowanie tekstu, korzystając z przetworzonego kontekstu początkowego.