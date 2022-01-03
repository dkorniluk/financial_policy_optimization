## Numeryczna metoda rozwiązania modelu

Analityczna metoda rozwiązania modelu, zaprezentowana w podrozdziałach \ref{podrozdzial_napiety_IWZ_bez_nadwyzki} - \ref{rozdzial_szescienne} gwarantuje uzyskanie optymalnego wyniku jedynie w pewnym podzbiorze zbioru rozwiązań dopuszczalnych, który cechuje z góry ustalona struktura warunków ograniczających (czyli określony ex ante podział na warunki luźne i napięte). Metoda numeryczna, opisana w niniejszym podrozdziale, jest komplementarna względem analitycznej. Po pierwsze, wykonana tylko dla trzeciego i czwartego roku, pozwala sprawdzić, czy rozwiązując model bez zakładania struktury warunków ograniczających, rozwiązanie wskazywane jako optymalne jest takie samo, co w rozwiązaniu analitycznym. Wprawdzie taka kontrolna weryfikacja nie zapewnia całkowitej pewności, ale jednak gwarantuje bardzo wysokie prawdopodobieństwo otrzymania optymalnego rezultatu. Po drugie, metoda numeryczna umożliwia, w przeciwieństwie do analitycznej, znalezienie rozwiązania dla całej czteroletniej kadencji władz samorządowych.  

Wiarygodność zaproponowanej tu numerycznej metody wynika z tego, że stanowi ona meta-algorytm wykorzystujący jednocześnie dwanaście metod optymalizacji zawartych w pakiecie \textit{optimx} (Nash i Varadhan, 2011 i Nash, 2014)\nocite{Nash_Varadhan_2011}\nocite{Nash_2014} systemu R. W pierwszym kroku tego meta-algorytmu, wykonywane są niezależnie, przy założeniu losowych wartości startowych, algorytmy dwunastu numerycznych metod optymalizacji. Każdy z tych dwunastu algorytmów składa się z od kilku do nawet kilkuset kroków, w zależności od tego, jak szybko uzyskiwana jest zbieżność. Część z tych metod w ogóle nie znajduje dopuszczalnego rozwiązania, ale zazwyczaj przynajmniej jedna z nich jest w stanie uzyskać pewne rozwiązanie. Jednak taki wynik jest przeważnie tylko ekstremum lokalnym. Numeryczne metody optymalizacji są bowiem wrażliwe na wartości startowe i jeżeli algorytm rozpocznie swoje działanie na obszarze odległym od optimum globalnego, to możliwe jest jego ,,utknięcie'' w punkcie stanowiącym ekstremum lokalne. Co więcej, w podsumowaniu pierwszego kroku meta-algorytmu, różne metody wskazują często na różne rozwiązania optymalne, o różnych wartościach funkcji celu, a przecież tylko co najwyżej jedno z nich, tj. generujące najwyższą użyteczność, może być ekstremum globalnym. Dlatego w drugim kroku meta-algorytmu, ponownie wykonuje się dwanaście algorytmów, tym razem z wartością startową będącą rozwiązaniem o najwyższej użyteczności spośród uzyskanych w kroku pierwszym. Kolejne iteracje są wykonywane, dopóki wartość najlepszego rozwiązania, z dwunastu wskazywanych jako optymalne, nie stabilizuje się.     

Dwanaście stosowanych w meta-algorytmie numerycznych metod optymalizacji można podzielić na: niewykorzystujące pochodnych (\textit{nelder-mead, newuoa, bobyqa, nmkb, hjkb}), newtonowskie (\textit{nlm, nlminb}), quasi-newtonowskie (\textit{BFGS, L-BFGS-B, ucminf}) i gradientowe (\textit{CG, spg}). Należy zaznaczyć, że terminologia ta pochodzi z opracowania Nasha i Varadhana (2011, s. 5) i nie jest całkowicie precyzyjna. Wynika to z faktu, że zazwyczaj algorytm optymalizacyjny można uruchomić z podaniem w roli argumentu funkcji gradientu i/lub hesjanu albo bez podawania tych funkcji. W zależności od tego konieczna będzie aproksymacja gradientu i/lub hesjanu lub też nie będzie ona wymagana. W efekcie, metodę można określić mianem quasi-newtonowskiej albo newtonowskiej.     

Metody niewykorzystujące pochodnych są rozwinięciem popularnej metody Neldera - Meada (1965). \nocite{Nelder_Mead_1965} W uproszczeniu, polega ona na stopniowym przekształcaniu sympleksu (w przestrzeni dwuwymiarowej jest to trójkąt, w trójwymiarowej - czworościan itd.) - tak, aby w kolejnej iteracji najgorszy (tj. o najgorszej wartości funkcji celu) punkt zastąpić nowym, specjalnie utworzonym punktem. Dzięki temu sympleks przesuwa się w stronę przeciwną niż najgorszy punkt. Krok przesunięcia wydłuża się, jeżeli nowy punkt staje się najlepszym spośród wierzchołków sympleksu lub skraca, gdy nowy punkt jest lepszy jedynie od dotychczas najgorszego wierzchołka. 
 
Bardziej złożonym algorytmem nie wymagającym pochodnych jest \textit{newuoa} (Powell, 2007)\nocite{Powell_2007}, którego nazwa prawdopodobnie pochodzi od akronimu: ,,NEW Unconstrained Optimization Algorithm'' (nowy algorytm optymalizacji bez ograniczeń). Polega on na utworzeniu, w każdej, $k$-tej iteracji, funkcji $q_{k}$ za pomocą kwadratowej interpolacji funkcji celu $f$ o $n$ zmiennych, a następnie minimalizacji $q_{k }$ w obrębie dopuszczalnego obszaru (ang. trust region), który stopniowo ulega zawężeniu. Interpolacja nie zakłada jednak styczności funkcji $q$ z funkcją $f$ w $n$ punktach, tylko w $m<n$, a dodatkowymi warunkami niezbędnymi do wyznaczenia współczynników funkcji $Q$ są warunki na to, aby macierze drugich pochodnych $q$ w kolejnych iteracjach były możliwie zbliżone (w sensie normy Frobeniusa, czyli pierwiastka z sumy kwadratów wszystkich elementów macierzy).     

Na bazie algorytmu \textit{newuoa}, Powell (2007) utworzył algorytm \textit{bobyqa} (,,Bound Optimization BY Quadratic Approximation'' - optymalizacja z ograniczeniami poprzez aproksymację kwadratową), który różni się od poprzedniego wprowadzonymi do modelu optymalizacyjnego ograniczeniami nałożonymi na zmienne decyzyjne. Uwzględnienie ograniczeń pozwala na uproszczenie i skrócenie pewnych obliczeń. Autorzy pakietu \textit{optimx} zastrzegli (Nash i Varadhan, 2011, s. 4), że dopiero testują, czy \textit{bobyqa} rozwiązuje problemy bez ograniczeń tak skutecznie jak \textit{newuoa}. Dlatego na razie obie metody zostały zawarte w pakiecie.

Kelley (1999, s. 141) zauważył, że algorytm Neldera-Meada ma tendencję do utykania w ekstremum lokalnym. Kryterium detekcji utknięcia, jakie przyjął, polegało na sprawdzeniu, czy wartość funkcji celu w najlepszym wierzchołku poprawia się wystarczająco silnie w kolejnej iteracji. Postęp ów jest porównywany z kwadratową normą gradientu sympleksu pomnożoną przez niewielką stałą. Jeżeli postęp występuje, ale jest niewystarczający, algorytm ulega ukierunkowanemu restartowi (ang. oriented restart). Wszystkie wierzchołki, poza najlepszym, zostają przesunięte o połowę odległości między najlepszym wierzchołkiem a jego najbliższym sąsiadem. Taki zabieg zapewnia też korzystną właściwość sympleksu, tj. ograniczenie wzrostu współczynnika uwarunkowania (ilorazu norm macierzy i jej odwrotności). W pakiecie \textit{optimx} metoda \textit{nmkb} została zaimplementowana za zgodą Kelleya przez Varadhana, który dokonał ,,pewnych nietrywialnych modyfikacji'' (szczegóły w dokumentacji pakietu \textit{dfoptim}\nocite{dfoptim}).

Ostatnim algorytmem niewymagającym obliczania pochodnych jest algorytm Hooka-Jeevesa (1961)\nocite{Hooke_Jeeves_1961}, wprowadzony do pakietu \textit{dfoptim} przez Borchersa również na podstawie algorytmu z książki Kelleya (1999), a następnie wykorzystany w pakiecie \textit{optimx}. Metoda Hooka-Jeevesa wymaga określenia ex ante punktu startowego i macierzy bazy ortogonalnej (może być nią np. macierz jednostkowa). Najpierw sprawdzane są wartości funkcji celu w kolejnych punktach położonych w ustalonej odległości, w kierunkach wyznaczonych przez wektory ww. macierzy oraz w kierunkach im przeciwnych (czyli w wybranych punktach ,,naokoło'' punktu centralnego). Gdy tylko w pewnym punkcie nastąpi poprawa wartości funkcji, to staje się on nowym punktem bazowym. Jednak, wbrew intuicji, nie staje się on nowym centralnym punktem w drugiej rundzie eksploracji punktów. Algorytm Hooka-Jeevesa określa się mianem ,,agresywnego'' (Kelley, 1999, s. 146), gdyż nowym centrum staje się punkt położony w tym samym kierunku, co nowy punkt bazowy, ale dwa razy dalej od poprzedniego punktu centralnego. Dzięki temu ogranicza się częstość ponownego sprawdzania tych samych punktów. Jeżeli w nowej iteracji nie uda się uzyskać poprawy, to nowym centrum staje się dotychczasowy punkt bazowy. Jeżeli powtórnie obniżenie wartości funkcji celu nie będzie możliwe, to skracana jest odległość, zgodnie z którą wyznaczane są punkty ,,naokoło'' punktu centralnego. Algorytm kończy działanie, gdy odległość ta obniży się poniżej ustalonego progu.        

Celem lepszego przybliżenia metod newtonowskich i quasi-newtonowskich, wykorzystujących nie tylko wektor pierwszych, ale także macierz drugich pochodnych zwaną hesjanem, warto zacząć od przedstawienia klasycznej metody Newtona. Zgodnie z twierdzeniem Taylora, funkcję nieliniową $f(x)$ można aproksymować w otoczeniu punktu $x_{c}$ za pomocą następującej funkcji kwadratowej (por. Kelley, 1999, s. 15)\nocite{Keley_1999}:

<img src="https://render.githubusercontent.com/render/math?math=f(x) \approx m_{c}(x) = f(x_{c}) %2B \nabla f(x_{c})^{T} (x-x_{c}) %2B \frac{1}{2}(x-x_{c})^{T} \nabla^{2} f(x_{c}) (x-x_{c})">.

Jeżeli <img src="https://render.githubusercontent.com/render/math?math=\nabla^{2} f(x_{c})"> jest macierzą dodatnio określoną, to <img src="https://render.githubusercontent.com/render/math?math=x_{%2B}"> stanowi minimum lokalne <img src="https://render.githubusercontent.com/render/math?math=f(x)">, gdy <img src="https://render.githubusercontent.com/render/math?math=\nabla m_{c} (x_{%2B}) = 0">.

<img src="https://render.githubusercontent.com/render/math?math=0 = \nabla m_{c} (x_{%2B})  = \nabla f(x_{c}) %2B \nabla^{2} f(x_{c}) (x_{%2B} - x_{c})">

Stąd: 
<img src="https://render.githubusercontent.com/render/math?math=x_{%2B} = x_{c} - (\nabla^{2} f(x_{c}))^{-1} \nabla f(x_{c})"> 

<img src="https://render.githubusercontent.com/render/math?math=\nabla^{2} f(x_{c}) (x_{%2B} - x_{c}) = -\nabla f(x_{c})">. 

Podstawowym algorytmem służącym do poszukiwania minimum lokalnego jest metoda Newtona:

Oblicz <img src="https://render.githubusercontent.com/render/math?math=\left\| \nabla f(x) \right\|">

 * (a) Dopóki <img src="https://render.githubusercontent.com/render/math?math=\left\| \nabla f(x) \right\| > \varepsilon">
 * (b) Oblicz <img src="https://render.githubusercontent.com/render/math?math=\nabla^{2} f(x)">
 * (c) Rozwiąż <img src="https://render.githubusercontent.com/render/math?math=\nabla^{2} f(x) d  = - \nabla f(x)">
 * (d) Zastąp <img src="https://render.githubusercontent.com/render/math?math=x"> przez <img src="https://render.githubusercontent.com/render/math?math=x %2B d">
 * (e) Oblicz <img src="https://render.githubusercontent.com/render/math?math=\nabla f(x)">.

Istnieje wiele odmian metody Newtona. Wektor $g$ przybliżający gradient $\nabla f$ może być obliczany w kroku (e) ze wzoru analitycznego albo aproksymowany za pomocą skończonych różnic, macierz H przybliżająca hesjan $\nabla^{2} f$ może być kalkulowana w kroku (b) jeszcze na trzeci sposób - metodą BFGS - od nazwisk autorów: Broydena, Fletchera, Goldfarba i Shano (Head, Zerner, 1985)\nocite{BFGS_1985}. W niektórych algorytmach, w celu zaoszczędzenia czasu, kalkulacja gradientu i hesjanu nie odbywa się w każdej iteracji. W pewnych algorytmach nowy $x$ powstaje w kroku (d) z kolei poprzez dodanie do starego $x$ pewnej modyfikacji $d$, tj. $\lambda d$, gdzie $\lambda$ określa długość kroku w kierunku gradientu za pomocą jednej z metod: wyszukiwania liniowego (Kelley, 1999, s. 39-50), dogleg (Dennis, Mei, 1979)\nocite{Dennis_Mei_1979} lub hookstep (Mor\'{e}, 1978)\nocite{More_1978}. Więcej na temat różnych odmian metody Newtona można przeczytać w artykule Schnabela, Koontza i Weissa (1985)\nocite{Schnabel_Koontz_Weiss_1985}. Inną ważną kwestię stanowi sposób rozwiązania układu równań (c). Zazwyczaj stosowana jest w tym celu metoda dekompozycji macierzy Choleskiego, lecz wymaga ona dodatniej określoności macierzy współczynników układu równań. Powstały zatem metody odporne na brak dodatniej określoności $\nabla^{2}f$ - wykorzystują one inne macierze współczynników - należą do nich m.in. dogleg i hookstep. Generalnie, metody polegające na aproksymacji, a nie obliczaniu wprost hesjanu nazywają się quasi-newtonowskimi.       

W pakiecie \textit{optimx} zostały zaimplementowane dwa algorytmy newtonowskie (Nash i Varadhan, 2011, s. 5). Oznacza to, że dopuszczają one podanie funkcji obliczającej hesjan, co umożliwia zastosowanie wprost metody Newtona. Jednak w niniejszej pracy nie skorzystano z tej opcji. Zamiast niej, we wszystkich algorytmach newtonowskich i quasi-newtonowskich zastosowano numeryczne przybliżenia gradientu i hesjanu, czyli w praktyce posługiwano się algorytmami quasi-newtonowskimi.

Pierwszy algorytm, \textit{nlm} (ang. nonlinear minimization) został opracowany na podstawie algorytmu stworzonego przez Dennisa i Schnabela (1983)\nocite{Dennis_Schnabel_1983}, opisanego także w pracy Schnabela, Koontza i Weissa (1985). Procedura \textit{nlm} wykorzystuje przeszukiwanie liniowe w etapie (d) wyżej przytoczonego algorytmu - ,,z kwadratową interpolacją dla pierwszego nawrotu oraz sześcienną interpolacją dla każdego następnego nawrotu w każdej iteracji'' (Schnabel, Koontz, Weiss, 1985, s. 8). W artykule tym można także poznać szczegóły techniczne algorytmu, dotyczące m.in.: kryteriów stopu; długości kroku potrzebnego do numerycznej aproksymacji pochodnych, a także sposobu ich obliczania (w początkowych iteracjach następnikowe, następnie centralne); aproksymacji hesjanu w sytuacji, gdy nie jest on macierzą dodatnio określoną; skalowania zmiennych niezależnych (co sprowadza się np. do podzielenia przez milion wartości tych zmiennych, których rząd wielkości jest bliski miliona, itd.).  

Metoda \textit{BFGS} należy do klasy metod opartych na równaniu siecznej: 
<img src="https://render.githubusercontent.com/render/math?math=H_{%2B} (x_{%2B} - x_{c}) = \nabla f(x_{%2B}) - \nabla f(x_{c})">.

Wszystkie metody siecznych, w tym \textit{BFGS}, dla optymalizacji jednowymiarowej sprowadzają się do  równania (\ref{sieczna_1D}). Na jego podstawie można stwierdzić, że metoda siecznych przybliża drugą pochodną za pomocą względnego przyrostu $f'(x)$ na odcinku wyznaczonym przez $x$ z poprzednich iteracji ($x_{0}$ i $x_{1}$):
<img src="https://render.githubusercontent.com/render/math?math=x_{2} = x_{1} - \frac{f'(x_{1})(x_{1} - x_{0})}{f'(x_{1}) - f'(x_{0})} =  x_{1} - \frac{f'(x_{1})}{\frac{f'(x_{1}) - f'(x_{0})}{x_{1} - x_{0}}} \approx x_{1} - \frac{f'(x_{1})}{f''(x_{1})}">

Równanie dla funkcji wielu zmiennych przedstawia się następująco (Davidon, 1959; Fletcher i Powell, 1963)\nocite{Davidon_1959}\nocite{Fletcher_Powell_1963}:
<img src="https://render.githubusercontent.com/render/math?math=H_{%2B} = H_{c} %2B \frac{(\nabla f(x_{%2B}) - \nabla f(x_{c})) (\nabla f(x_{%2B}) - \nabla f(x_{c}))^{T}}{(\nabla f(x_{%2B}) - \nabla f(x_{c}))^{T} (x_{%2B} - x_{c}) } - \frac{(H_{c}(x_{%2B} - x_{c}))(H_{c}(x_{%2B} - x_{c}))^{T}}{(x_{%2B} - x_{c})^{T}H_{c}(x_{%2B} - x_{c})}">.

W celu zbudowania intuicji można zauważyć, że gdyby móc poskracać w równaniu (\ref{DFP}) te same wyrażenia w liczniku i mianowniku (co nie jest dopuszczalne w rachunku macierzowym), to uzyskalibyśmy równanie (\ref{rownanie_siecznej}). 

W pakiecie \textit{optimx} metoda \textit{BFGS} została zmodyfikowana w oparciu o poprawki (m.in. dotyczące eliminacji wyszukiwania liniowego, które wyznacza $x_{%2B}$) autorstwa Fletchera (1970)\nocite{Fletcher_1970} i Nasha (1979)\nocite{Nash_1979}. 

Z kolei pakiet \textit{nlminb} wykorzystuje tzw. procedury (ang. routines) PORT zakodowane i opisane przez  Gaya (1990)\nocite{Gay_1990}, który z kolei opierał się m.in. na metodzie Davidona zmodyfikowanej  przez Stewarta (1967)\nocite{Stewart_1967}.  

Następny algorytm, \textit{L-BFGS-B}, został opisany przez Byrda i in. (1995)\nocite{Byrd_1995}. Dodane w jego nazwie litery to skróty od ,,limited-memory'' (L) i ,,bounded'' (B). Jest to bowiem algorytm zaprojektowany w celu zmniejszenia wymogów pamięciowych służących do obliczania i przechowywania dodatnio-określonej aproksymacji hesjanu. Ponadto, algorytm ten jest przeznaczony do problemów z warunkami ograniczającymi argumenty funkcji celu. Szkic tej metody można przedstawić następująco: 


* Zatrzymaj, jeżeli test zbieżności jest spełniony. 
* Oblicz punkt Cauchy'ego. Punkt ten stanowi minimum kwadratowego modelu minimalizowanej funkcji, wzdłuż gradientu, ale przy założeniu, że $x$ mieści się na odcinku wyznaczonym przez warunki ograniczające. 
* Oblicz kierunek przeszukiwania np. metodą gradientu sprzężonego. 
* Wykonaj przeszukiwanie liniowe, przy zadanym warunku wymaganego spadku oraz wyznacz długość kroku.
* Oblicz gradient w znalezionym punkcie. 
* Jeżeli zmiana gradientu spełnia warunek krzywizny, to zaktualizuj listę par korekty - zastępując najstarszą przez najnowszą. Przez listę par korekty należy rozumieć m ostatnich par w postaci: $(s_{i}, y_{i}) = (x_{k%2B1} - x_{k}, \nabla_{k%2B1} - \nabla_{k})$
* Wyznacz aproksymację hesjanu przy użyciu aktualnej listy par korekty. Można to osiągnąć względnie szybko w sensie złożoności obliczeniowej, z wykorzystaniem odpowiednich wzorów. 
* Zwiększ numer iteracji o 1 i wróć do punktu 1. 

Ostatni quasi-newtonowski algorytm użyty w optymalizacji numerycznej, \textit{ucminf} (Nielsen, 2000)\nocite{Nielsen_2000}, również wykorzystuje metodę BFGS, a także miękkie wyszukiwanie liniowe\footnote{Wyszukiwanie liniowe może być dokładne lub miękkie. Pierwsza metoda polega na dokładnym poszukiwaniu minimum funkcji w zadanym kierunku. Druga metoda polega na odnalezieniu w zadanym kierunku punktu, dla którego wartość funkcji wystarczająco obniża się, a następnie na aktualizacji kierunku. Wyszukiwanie miękkie jest częściej stosowane w praktyce, gdyż wymaga mniejszej liczby operacji, a przy tym zadany kierunek przeszukiwania przeważnie jest tylko kierunkiem w przybliżeniu prowadzącym do ekstremum funkcji.} z wykorzystaniem metody zaufanego obszaru. W przeciwieństwie do wcześniej opisanej metody \textit{BFGS}, \textit{ucminf} aproksymuje odwrotność hesjanu za pomocą wzoru będącego odpowiednikiem równania (\ref{DFP}):

<img src="https://render.githubusercontent.com/render/math?math=H_{%2B}^{-1} = \left( I - \frac{(\nabla f(x_{%2B}) - \nabla f(x_{c}))(x_{%2B} - x_{c})^{T}}{(\nabla f(x_{%2B}) - \nabla f(x_{c}))^{T}(x_{%2B} - x_{c})} \right)^{T}  H_{c}^{-1} \left( I - \frac{(\nabla f(x_{%2B}) - \nabla f(x_{c}))(x_{%2B} - x_{c})^{T}}{(\nabla f(x_{%2B}) - \nabla f(x_{c}))^{T}(x_{%2B} - x_{c})} \right)^{T}">
<img src="https://render.githubusercontent.com/render/math?math=%2B \frac{(x_{%2B} - x_{c})(x_{%2B} - x_{c})^{T}}{(\nabla f(x_{%2B}) - \nabla f(x_{c}))^{T}(x_{%2B} - x_{c})}">

Kolejne metody wymagają obliczania pochodnych funkcji celu, ale nie wymagają kalkulacji macierzy przybliżonego hesjanu. W pierwszym kroku algorytmu \textit{cg} (ang. conjugate gradient - gradient sprzężony) oblicza się gradient funkcji celu w punkcie startowym. W ten sposób wyznacza się kierunek najszybszego spadku wartości funkcji. Za pomocą metody optymalizacji jednowymiarowej funkcji celu (np. ww. metody Newtona), określa się minimum na odcinku położonym wzdłuż owego kierunku. Punkt ten staje się punktem startowym w drugiej iteracji. Ponownie obliczany jest kierunek najszybszego spadku. Jednak począwszy od drugiej iteracji, kierunek, wzdłuż którego wyszukuje się kolejny punkt, stanowi sumę bieżącego kierunku najszybszego spadku oraz pomnożonego przez parametr $\beta$ kierunku z poprzedniej iteracji. Domyślna formuła na $\beta$, w pakiecie \textit{optimx} pochodzi z artykułu Fletchera i Reevesa (1964)\nocite{Fletcher_Reeves_1964} i stanowi iloraz kwadratów norm gradientów z następujących po sobie iteracji. Im większy postęp w optymalizacji, tj. norma gradientu z bieżącej iteracji mniejsza co do modułu od normy z poprzedniej iteracji, tym mniejsza korekta kierunku najszybszego spadku. 

Algorytm \textit{spg} (ang. spectral projected gradient) pochodzi z artykułu Birgina, Mart\'{i}neza i Raydana (2001)\nocite{Birgin_Martinez_Raydan_2001}. Punktem wyjścia tej metody stanowi równanie siecznej (\ref{rownanie_siecznej}) (por. Birgin, Mart\'{i}nez, Raydan i in., 2014)\nocite{Birgin_Martinez_Raydan_2014}. W \textit{spg} zakłada się bardzo prostą postać macierzy $H_{%2B} = \sigma I$. Równanie siecznej można więc zapisać następująco:

<img src="https://render.githubusercontent.com/render/math?math=\sigma (x_{%2B} - x_{c}) \approx \nabla f(x_{%2B}) - \nabla f(x_{c})">.

Dokładne rozwiązanie tego równania nie istnieje, ale istnieje rozwiązanie minimalizujące sumę kwadratów reszt\footnote{Jest to  równanie odpowiadające ekonometrycznemu estymatorowi klasycznej metody najmniejszych kwadratów: $\hat{\beta} = (X^{T}X)^{-1}(X^{T}y)$. }: 

<img src="https://render.githubusercontent.com/render/math?math=\sigma = \frac{(x_{%2B} - x_{c})^{T} (\nabla f(x_{%2B}) - \nabla f(x_{c})) }{(x_{%2B} - x_{c})^{T} (x_{%2B} - x_{c})}">.

Dodatkowo nakłada się ograniczenie: $\sigma_{min} \leq \sigma \leq \sigma_{max}$. Jednocześnie $\sigma$ stanowi tzw. iloraz Rayleigha w odniesieniu do macierzy uśrednionego hesjanu na przedziale $(x_{c}, x_{%2B})$. Skądinąd wiadomo, że iloraz Rayleigha należy do przedziału pomiędzy minimalną a maksymalną wartością własną uśrednionego hesjanu. Zbiór wszystkich wartości własnych danej macierzy nazywa się spektrum macierzy, co tłumaczy genezę nazwy metody. Ostatecznie zatem w  metodzie \textit{spg}, macierz $\nabla^{2} f(x)$ zostaje zastąpiona przeskalowaną macierzą jednostkową $\sigma I$ w punkcie c) algorytmu Newtona. Zmodyfikowany jest także punkt d), gdzie stosuje się przeszukiwanie liniowe.  

Niektóre z metod optymalizacji omawianych w niniejszym podrozdziale umożliwiają wprowadzenie wprost warunków ograniczających. Mimo to, wszystkie metody optymalizacji stosowanego tutaj metaalgorytmu zastosowano dla funkcji celu bez ograniczeń. Warunki ograniczające wymienione w podrozdziale \ref{zapis_rozwiazania} zostały bowiem uwzględnione w funkcji celu w postaci tzw. składnika kary pomnożonego przez największą co do modułu wartość zmiennej decyzyjnej. Kara przyjmuje wartość zerową, jeżeli żaden z 24 warunków ograniczających (dwanaście na ujemność zmiennych decyzyjnych: $c_{t}, i_{t}, u_{t}, t \in \{1,2,3,4\}$, cztery w postaci $u_{t} > U_{t}$, cztery na reguły nadwyżki bieżącej i cztery na reguły IWZ) nie jest spełniony. Za każdy niespełniony warunek wartość kary rośnie o 9999 (czyli bardzo dużą liczbę w porównaniu z typowymi wartościami funkcji celu). Pomnożenie kary przez największą co do modułu wartość zmiennej decyzyjnej zabezpiecza przed sytuacją, gdy kara wprawdzie nie byłaby zerowa, ale mimo to algorytm wybierałby takie rozwiązanie jako optymalne, gdyż zmienne decyzyjne przyjmowałyby wartości o ogromnym rzędzie wielkości (nie mające interpretacji ekonomicznej). W części aneksu (\ref{aneks_przykladowe_analit}), w sekcji ,,deklaracja funkcji użyteczności'' zaprezentowano funkcję celu ze składnikiem kary dla algorytmu szukającego optymalnego rozwiązania dla trzeciego roku. W tym przypadku kara składa się z dziewięciu warunków ograniczających (m.in. bez ograniczeń na zmienne z pierwszego i drugiego roku). 

```{r, echo = FALSE, eval=FALSE}
############################################
# Rozwiązanie metodami iteracyjnymi        #
############################################

metody<-c("BFGS", "CG", "Nelder-Mead", "L-BFGS-B", "nlm", "nlminb", "spg", "ucminf", "newuoa", "bobyqa", "nmkb", "hjkb")

uz<-0*c(1:12)

roz<-function(rozw){
  wsp<-as.matrix(coef(optimx (rozw, uzyt, method=metody)))
  uz<-apply(wsp, 1, uzyt)
  rozw2<-wsp[which.min(uz),]
  #print(summary(optimx (rozw, uzyt, method=metody)))
  return(as.vector(rozw2))
}

konw<-function(rozw){
  maks<-uzyt(rozw)
  rozw2<-rozw
  zatrzymaj<-0
  while (zatrzymaj==0){
    rozw2<-roz(rozw2)
    if ((uzyt(rozw2) - maks)>-0.0001){
      zatrzymaj<-1
      #print(summary(optimx (rozw2, uzyt, method=metody)))
    }
    maks<-uzyt(rozw2)
  }
  return(roz(rozw2))
}

p<-0*c(1:3)
rozw<-c(0.6, 0.1, 0.1)
p<-konw(rozw)

p[1]->c3
p[2]->u3
p[3]->i3

u4<-U4
c4<-(
  (((alpha*(y5%2Bu5)/(chi%2Br)*1/3)
    /(1%2B 1/3*((y5%2Bu5)/(chi%2Br))/(y4%2Bu4)))
   *(y3-c3 - r*b3)/(y3%2Bu3))
  %2B(((alpha*(y5%2Bu5)/(chi%2Br)*1/3)
     /(1%2B 1/3*((y5%2Bu5)/(chi%2Br))/(y4%2Bu4)))
    *(((y2-c2 - r*b2)/(y2%2Bu2))%2B((y4 - r*(b3 %2B theta*u3 %2B i3 %2B c3 %2B r*b3 - y3))/(y4%2Bu4))))
  -(alpha*((1%2Br)*(b3%2Btheta*u3 %2B c3 %2B i3 %2B r*b3 - y3))
    /(1%2B 1/3*((y5%2Bu5)/(chi%2Br))/(y4%2Bu4)))
  %2B(alpha*(y4 %2B (1-delta)*((1-delta)*k3 %2B (1%2Btheta)*u3 %2B i3) %2B u4)
    /(1%2B 1/3*((y5%2Bu5)/(chi%2Br))/(y4%2Bu4)))
)
k4<-(1-delta)*k3%2B(1%2Btheta)*u3%2Bi3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 %2B (1%2Btheta)*u3 %2B i3) %2B (1-alpha)*u4 %2B 
    (1-alpha)*((y5%2Bu5)/(chi%2Br)/3*((y2-c2-r*b2)/(y2%2Bu2) %2B (y3- c3-r*b3)/(y3%2Bu3) %2B (y4 -r*b4)/(y4%2Bu4)) 
               -     (1%2Br)*(b3%2B theta*u3 %2B i3 %2B c3 %2B r*b3 - y3) %2B y4)
)
i4<-k5-(1-delta)*k4-(1%2Btheta)*u4
z3<-(1%2Btheta)*u3 %2B i3 %2B c3 %2B r*b3 - u3 - y3
b4<-b3%2Bz3
```
