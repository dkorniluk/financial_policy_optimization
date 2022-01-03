# Rozwiązanie modelu

## Zapis rozwiązania modelu za pomocą warunków Karusha-Kuhna-Tuckera

Warunki konieczne, które musi spełniać rozwiązanie optymalne modelu, wynikają z twierdzenia Karusha, Kuhna i Tuckera (KKT), które brzmi następująco (Chong, Żak, 2001, s. 397-398):

Rozważmy problem optymalizacyjny:

<img src="https://render.githubusercontent.com/render/math?math=\min f(x)">
p.w. <img src="https://render.githubusercontent.com/render/math?math=h(x) = 0,">
<img src="https://render.githubusercontent.com/render/math?math=g(x) \leq 0,">

gdzie <img src="https://render.githubusercontent.com/render/math?math=f: \mathbb{R}^{n} \rightarrow \mathbb{R},  h: \mathbb{R}^{n} \rightarrow \mathbb{R}^{m}, m \leq n, g: \mathbb{R}^{n} \rightarrow \mathbb{R}^{p}">.

Niech:  <img src="https://render.githubusercontent.com/render/math?math=J(x^{*}) = \left\{j : g_{j}(x^{*}) = 0 \right\}">. Niech <img src="https://render.githubusercontent.com/render/math?math=x^{*}"> będzie punktem regularnym, tzn. takim, że wektory:
<img src="https://render.githubusercontent.com/render/math?math=\nabla h_{i}(x^{*}, \nabla g_{j}(x^{*}, 1 \leq i \leq m, j \in J(x^{*}">
są liniowo niezależne. <img src="https://render.githubusercontent.com/render/math?math=C^{1}"> oznacza zbiór funkcji ciągłych i różniczkowalnych w sposób ciągły (Założenia twierdzenia KKT można nieco osłabić, ale dla funkcji wykorzystanych w niniejszym modelu nie ma to znaczenia (Palczewski, 2014, s. 57-58)).

Niech <img src="https://render.githubusercontent.com/render/math?math=f, h, g \in C^{1}">. Niech <img src="https://render.githubusercontent.com/render/math?math=x^{*}"> będzie punktem regularnym, stanowiącym ekstremum lokalne f, pod warunkiem że <img src="https://render.githubusercontent.com/render/math?math=h(x) = 0">, <img src="https://render.githubusercontent.com/render/math?math=g(x) \leq 0">. Wtedy istnieje <img src="https://render.githubusercontent.com/render/math?math=\lambda^{*} \in \mathbb{R}^{m}"> (tzw. wektor mnożników Lagrange'a) i <img src="https://render.githubusercontent.com/render/math?math=\mu^{*} \in \mathbb{R}^{p}"> (tzw. wektor mnożników KKT), takie że:

* <img src="https://render.githubusercontent.com/render/math?math=\mu^{*} \geq 0">;
* <img src="https://render.githubusercontent.com/render/math?math=Df(x^{*}) %2B \lambda^{*T}D h(x^{*}) %2B \mu^{*T}D g(x^{*}) = 0^{T} ">;
* <img src="https://render.githubusercontent.com/render/math?math=\mu^{*T} g(x^{*}) = 0">.

Dowód można znaleźć np. we wspomnianym podręczniku do optymalizacji autorstwa Chonga i Żaka (2001, s. 399-401).

Model decyzyjny władz samorządowych z warunkami w postaci KKT należy zapisać w następujący sposób:

<img src="https://render.githubusercontent.com/render/math?math=\max_{\{c_{t}\}, \{u_{t}\}, \{i_{t}\}, \{z_{t}\}}  f(x) =  \sum_{t=1}^{4} \beta^{t} \left( \alpha \ln c_{t} %2B \left(1 - \alpha \right) \ln k_{t%2B1} \right)">

<img src="https://render.githubusercontent.com/render/math?math=\mbox{p.w. } \forall t \in {1, 2, 3, 4}">

<img src="https://render.githubusercontent.com/render/math?math=h_{1t}(x): \theta u_{t} %2B i_{t} %2B c_{t} %2B r b_{t} - y_{t} - z_{t} = 0">
<img src="https://render.githubusercontent.com/render/math?math=h_{2t}(x): b_{t%2B1} - b_{1} - \sum_{\tau=1}^{t} z_{\tau} = 0">
<img src="https://render.githubusercontent.com/render/math?math=h_{3t}(x): k_{t%2B1} - (1-\delta)k_{t} - i_{t} - (1%2B\theta)u_{t} = 0"> 

<img src="https://render.githubusercontent.com/render/math?math=g_{1t}(x): -u_{t} \leq 0">

<img src="https://render.githubusercontent.com/render/math?math=g_{2t}(x): u_{t} - U_{t} \leq 0">

<img src="https://render.githubusercontent.com/render/math?math=g_{3t}(x): -c_{t} \leq 0">

<img src="https://render.githubusercontent.com/render/math?math=g_{4t}(x): -i_{t} \leq 0">

<img src="https://render.githubusercontent.com/render/math?math=g_{5t}(x): \frac{(\chi %2B r) b_{t%2B1}}{y_{t%2B1} %2B u_{t%2B1}} - \frac{1}{3} \sum_{\tau=t-2}^{t} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}} \leq 0 ">

<img src="https://render.githubusercontent.com/render/math?math=g_{6t}(x): c_{t} %2B rb_{t} - y_{t} \leq  0
\mbox{dane: } b_{-1}, b_{0}, b_{1}, k_{1}, c_{-1}, c_{0}, u_{-1}, u_{0}, u_{5}.">

Rozwiązanie modelu polega na znalezieniu wartości składowych wektora: <img src="https://render.githubusercontent.com/render/math?math=x^{*} = [c_{1}^{*}~c_{2}^{*}~c_{3}^{*} c_{4}^{*} u_{1}^{*} u_{2}^{*} u_{3}^{*} u_{4}^{*} i_{1}^{*} i_{2}^{*} i_{3}^{*} i_{4}^{*} z_{1}^{*} z_{2}^{*} z_{3}^{*} z_{4}^{*}]^{T},"> spełniających warunki z twierdzenia KKT. Wymaga to policzenia pochodnych funkcji $f(x) %2B \lambda h(x) %2B \mu g(x)$. Jednocześnie, w przypadku każdego warunku $g_{j}$: jeżeli $g_{j}(x) <0$, to $\mu_{j} = 0$ i analogicznie: jeżeli $\mu_{j} > 0$, to $g_{j}(x) = 0$. Wynika to z faktu, że oba czynniki $g_{j}(x)$ i $\mu_{j}$ nie mogą być jednocześnie niezerowe, gdyż taki iloczyn mógłby być tylko ujemny (co wynika z pierwszego warunku KKT i tego, że $g_{j} \leq 0$), a wówczas suma ujemnych i ewentualnie zerowych iloczynów dałaby liczbę ujemną, a nie zerową, co wymaga trzeci warunek KKT. 

Warunki Kuhna-Tuckera są warunkami koniecznymi tylko wtedy, gdy spełnione są warunki tzw. kwalifikowalności\footnote{Szczegółową dyskusję na ten temat można znaleźć np. w podręczniku do ekonomii matematycznej Chianga (1994).}. Mogą istnieć bowiem rozwiązania optymalne, które nie spełniają warunków KKT, ale musiałyby one znajdować się w specyficznie określonych punktach brzegowych. W przykładzie z podrozdziału \ref{rozdzial_szescienne} pokazano, że rozwiązanie analityczne modelu może sprowadzać się do znalezienia, przy ustalonej strukturze warunków ograniczających, optymalnego poziomu inwestycji zwykłych ($i_{t}^{*}$). O poziomie tym założono w omawianym przykładzie, że nie jest zerowy, a zatem z góry przyjęto, że nie może znaleźć się w punkcie brzegowym. 

Teoretycznie ekstremów lokalnych spełniających warunki KKT mogłoby być więcej niż jeden i wówczas należałoby wybrać spośród nich ekstremum (ewentualnie ekstrema) globalne. Jednak ,,żaden punkt wewnętrzny zbioru rozwiązań dopuszczalnych, nie spełniający warunków KKT, nie może być rozwiązaniem optymalnym'' (Chiang, 1994). Oznacza to, że jeżeli ekstremum globalne istnieje  w punkcie wewnętrznym oraz jeżeli zbiór punktów spełniających warunki KKT jest jednoelementowy, to punkt należący do tego zbioru jest ekstremum globalnym. W dalszej części pracy (w szczególności w porozdziale \ref{rozdzial_szescienne} oraz części B i C aneksu) pokazano, że punkty spełniające warunki KKT dla pewnego podzbioru zbioru rozwiązań dopuszczalnych stanowią rozwiązanie równania sześciennego. Spośród trzech takich rozwiązań, dwa stanowią liczby zespolone, a tylko jeden należy do zbioru liczb rzeczywistych. Oznacza to, że punkt ten musi być globalnym rozwiązaniem optymalnym w ramach omawianego podzbioru.

Wyznaczenie pełnego rozwiązania analitycznego takiego modelu jest niewykonalne ze względu na ogromną złożoność zagadnienia. Już nawet rozwiązanie dla trzeciego i czwartego roku (patrz podrozdział \ref{rozdzial_szescienne}) wymaga bardzo żmudnych i czasochłonnych rachunków, które prowadzą do równania sześciennego. Dlatego w kolejnych podrozdziałach zostaną wyznaczone, metodą analityczną, fragmentaryczne rozwiązania modelu, dla $t = 3,4$ (dla z góry ustalonych wartości zmiennych decyzyjnych z lat $t=1,2$), a następnie, metodą numeryczną, pełne rozwiązanie modelu, dla $t = 1,2,3,4$. Innymi słowy, w kolejnych podrozdziałach przedstawione zostaną rozwiązania analityczne problemu (\ref{problem_maks}) na pewnych podzbiorach pełnego zbioru rozwiązań dopuszczalnych. Rozwiązania takie co do zasady nie będą stanowiły globalnego maksimum problemu (\ref{problem_maks}), jednak pozwolą zbudować cenną intuicję odnośnie do funkcjonowania modelu. Pełne rozwiązanie modelu zostanie wyznaczone metodą numeryczną w rozdziale \ref{analiza_wrazliwosci}, po kalibracji modelu w rozdziale \ref{rozdzial_dane}. Jak się okaże, struktura warunków ograniczających w rozwiązaniu optymalnym z dużym prawdopodobieństwem będzie zgodna z tą, którą założono  na potrzeby rozwiązania analitycznego w rozdziale \ref{rozwiazanie_modelu}. Pozwala to potwierdzić praktyczną użyteczność przedstawionych tu analiz.
 
## Analityczne rozwiązanie dla czwartego roku z napiętym warunkiem IWZ

Uprośćmy teraz problem, znajdując ,,na skróty'' optymalne wartości dla zmiennych z roku czwartego. W tym celu warunek $h_{14}(x)$ należy przekształcić do postaci:

\begin{IEEEeqnarray}{rCl}
\theta u_{4} %2B i_{4} %2B c_{4}   & = &  z_{4} %2B y_{4} - rb_{4}. \nonumber
\end{IEEEeqnarray}

Zmienne $y_{4}$, $b_{4}$ są z góry ustalone w roku czwartym. Widać zatem, że suma wydatków bieżących i inwestycyjnych zależy dodatnio od wielkości zaciągniętego długu w czwartym roku. Optymalnie byłoby zatem powiększyć dług jak najbardziej to możliwe, czyli na tyle, na ile pozwalają reguły fiskalne. Z analizy rozwiązań optymalnych uzyskanych za pomocą metod numerycznych (rozdz. \ref{rozdz_numeryczna_metoda}) wynika, że prawie zawsze napięty jest warunek indywidualnego wskaźnika zadłużenia (IWZ, patrz równanie (\ref{IWZ})), a bardzo rzadko - zrównoważonego wyniku bieżącego (ZWB, patrz równanie (\ref{regula_bez_nadwyzki})). Dlatego dalej założono, że IWZ jest warunkiem napiętym, a ZWB - luźnym. 

Z napiętego warunku IWZ można wyprowadzić wzór na optymalny deficyt w roku czwartym: 
\begin{IEEEeqnarray}{rCl}
\frac{(\chi%2Br) b_{5}^{*}}{y_{5} %2B u_{5}^{*}} & = & \frac{1}{3} \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}} \Rightarrow \nonumber \\
%b_{5}^{*} & = & \frac{{y_{5} %2B u_{5}^{*}} }{\chi %2B r} \left( \frac{1}{3} \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}} \right) \nonumber \\
%z_{4}^{*} & = & b_{5}^{*} - b_{4} \nonumber \\
\Rightarrow z_{4}^{*} & = & \frac{y_{5} %2B u_{5}^{*}}{\chi%2B r} \left( \frac{1}{3} \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}}  \right) - b_{4}. \nonumber
\end{IEEEeqnarray}

Następnie można przekształcić ograniczenie budżetowe tak, aby po lewej stronie występowały tylko zmienne decyzyjne (ponieważ powinny przyjąć optymalne wartości, to zostały oznaczone gwiazdkami), a po prawej stronie -  zmienne z góry ustalone w roku czwartym (ich suma to $\phi= \mbox{const}\lvert_{t=4}$). Wyjątek stanowi zmienna $u_{5} \leq U_{5}$, której wartość jest określana dopiero przez następne władze samorządowe, co wykracza poza omawiane tu zagadnienie optymalizacyjne. Na potrzeby rozwiązania można założyć, że w roku piątym kwota inwestycji unijnych opiewa na maksymalny limit, tj. $u^{*}_{5} = U_{5}$.   

{\footnotesize
\begin{IEEEeqnarray}{rCl}
\theta u_{4}^{*} %2B i_{4}^{*} %2B c_{4}^{*} %2B r b_{4} & = &  z_{4}^{*} %2B y_{4} \Rightarrow \nonumber \\
%
%\theta u_{4}^{*} %2B i_{4}^{*} %2B c_{4}^{*} & = &  \frac{y_{5} %2B U_{5}}{\chi%2B r} \left( \frac{1}{3}  \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}}  \right) - (1%2Br) b_{4} %2B y_{4} \nonumber 
%\\
%\theta u_{4}^{*} %2B i_{4}^{*} %2B c_{4}^{*}\left( 1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B u_{4}^{*}} & = & \frac{y_{5} %2B U_{5}}{\chi%2B r} \frac{1}{3} \sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}}  - (1%2Br ) b_{4} %2B y_{4} \nonumber
%\\
%\theta u_{4}^{*} %2B i_{4}^{*} %2B c_{4}^{*}\left( 1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4} }{y_{4} %2B u_{4}^{*}} & = & \frac{y_{5} %2B U_{5}}{\chi%2B r} \frac{1}{3} \sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} %2B u_{\tau}}  - (1%2Br) b_{4} %2B y_{4} \nonumber
%\\
\label{eq_ograniczenie_t4}
\Rightarrow \theta u_{4}^{*} %2B i_{4}^{*} %2B c_{4}^{*}\left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B u_{4}^{*}} & = & \phi
\end{IEEEeqnarray}
}

Czynnik dyskontujący $\beta^{4}$ można w funkcji celu pominąć, gdyż w tym rozdziale brany pod uwagę jest tylko jeden rok. Model optymalizacyjny można zapisać zatem w następujący sposób: 
\begin{equation}
\max_{c_{4}, u_{4}, i_{4}} \left( \alpha \ln c_{4} %2B \left(1 - \alpha \right) \ln k_{5} \right) \nonumber
\end{equation}
p.w.
\begin{IEEEeqnarray}{rCl}
\theta u_{4} %2B i_{4} %2B c_{4} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B u_{4}} - \phi& = & 0 \nonumber \\
-c_{4} & \leq & 0 \nonumber \\
-i_{4} & \leq & 0 \nonumber \\
-u_{4} & \leq & 0 \nonumber \\
u_{4} - U_{4} & \leq & 0 \nonumber \\
c_{4} %2B r b_{4} & = & y_{4}. \nonumber
\end{IEEEeqnarray}

Funkcja Lagrange'a i warunki konieczne (pierwszego rzędu) przedstawiają się następująco:
\begin{equation}
\begin{split}
\mathcal{L}(c_{4}, u_{4}, i_{4}) = \alpha \ln c_{4} %2B \left(1 - \alpha \right) \ln  \left( (1-\delta) k_{4} %2B (1%2B\theta)u_{4} %2B i_{4} \right) %2B\\
%2B \lambda \left[ \theta u_{4} %2B i_{4} %2B c_{4}\left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B u_{4}} - \phi\right]\\ - \mu_{1}c_{4} - \mu_{2}i_{4} - \mu_{3}u_{4} %2B \mu_{4}(u_{4} - U_{4})
\nonumber
\end{split}
\end{equation}

\begin{equation} 
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} %2B \lambda \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) - \mu_{1}^{*} = 0 
\nonumber
\end{equation}

\begin{equation}
\frac {\partial \mathcal{L}}{\partial i_{4}} =  \frac{1-\alpha}{(1-\delta) k_{4} %2B (1%2B\theta)u_{4}^{*} %2B i_{4}^{*}} %2B \lambda^{*} - \mu_{2}^{*} = 0 
\nonumber
\end{equation}

\begin{equation}
\frac {\partial \mathcal{L}}{\partial u_{4}} = \frac{(1-\alpha)(1%2B\theta)}{(1-\delta) k_{4} %2B (1%2B\theta)u_{4}^{*} %2B i_{4}^{*}} %2B \lambda^{*} \left(\theta %2B (y_{4} - r b_{4} - c_{4}^{*}) \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{(y_{4} %2B u_{4}^{*})^{2}} \right) - \mu_{3}^{*} %2B \mu_{4}^{*} = 0.
\nonumber
\end{equation}   

Teoretycznie należałoby rozważyć szesnaście ($2^{4}$) zestawów potencjalnych rozwiązań optymalnych, gdyż każdy z czterech parametrów $\mu_{i}$ może przyjąć wartość zerową lub dodatnią. Poniżej przeanalizowano jednak tylko cztery wybrane warianty. Przede wszystkim założono, że $c^{*}_{4}>0$, co implikuje $\mu_{1} = 0$, a jednocześnie pozwala uniknąć rozpatrywania ośmiu wariantów. Trudno bowiem wyobrazić sobie samorząd, nawet o bardzo złym stanie infrastruktury, w którym nie poniesiono by żadnych wydatków bieżących. Zrezygnowano także z dwóch nierealistycznych scenariuszy: zerowych inwestycji zwykłych i unijnych dokładnie równych limitowi oraz dodatnich inwestycji zwykłych i zerowych unijnych, a także dwóch sprzecznych scenariuszy, które zakładałyby zerowe i zarazem równe limitowi inwestycje unijne (przy zerowych lub dodatnich inwestycjach zwykłych). Poniżej wyróżniono zatem cztery rodzaje rozwiązań, z których ostatnie zasługuje na szczególną uwagę. 

Zbieżność poniższych rozwiązań, uzyskanych metodą analityczną, z rozwiązaniami otrzymanymi dzięki numerycznym metodom optymalizacyjnym, zaprezentowano szczegółowo w aneksie \ref{Aneks_kody}. Wyjątek stanowi wariant trzeci, który nie został uwzględniony w aneksie (jest mało realny), lecz metoda postępowania w jego przypadku byłaby analogiczna do wariantu drugiego. 

Wariant I

Jeżeli wartość $(1-\delta)k_{4}$ jest odpowiednio wysoka, to największą użyteczność przynosi przeznaczenie całych dostępnych funduszy na wydatki bieżące. Warunek (\ref{eq_warunek}) oznacza, że krańcowa użyteczność z wydatków bieżących sfinansowanych z całego dostępnego budżetu jest wyższa niż z dowolnie małego powiększenia infrastruktury: 
\begin{IEEEeqnarray}{rCl}
\frac {\partial f}{\partial c_{4}} & > &  \frac {\partial f}{\partial k_{5}} \mbox{ dla } k_{5} = (1-\delta) k_{4} \label{eq_warunek} \\
\frac{\alpha \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}} \right)}{\phi%2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r}} & > & \frac{1- \alpha}{(1-\delta)k_{4}}. \nonumber
\end{IEEEeqnarray}
%
\begin{IEEEeqnarray}{rCl}
u^{*}_{4} & =  &0 \nonumber \\ 
i^{*}_{4} & = & 0  \nonumber\\
c^{*}_{4} & = & \frac{\phi%2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{y_{4} - r b_{4}}{y_{4}}}{1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4}}}. \label{eq_tylko_c4}
\end{IEEEeqnarray}

Wariant II

Jeżeli wartość $(1-\delta)k_{4}$ jest niższa, tzn. gdy warunek (\ref{eq_warunek}) nie zachodzi, to optymalnie jest przeznaczyć pewną część budżetu na inwestycje. Poniżej zakłada się, że optymalne inwestycje unijne nie przekroczą maksymalnej kwoty $U_{4}$. W pierwszej kolejności zazwyczaj (przeciwny przypadek został omówiony w dalszej części pracy) powinny być realizowane inwestycje unijne, gdyż są tańsze. Jeśli więc ich wysokość nie przekracza ustalonej granicy, wówczas realizacja jakichkolwiek inwestycji ze środków własnych może nie mieć uzasadnienia. 
%
\begin{IEEEeqnarray}{rCl}
U_{4} > u^{*}_{4} &>& 0 \nonumber \\ 
i^{*}_{4} &=& 0 \nonumber \\
c^{*}_{4} &>& 0 \nonumber \\
\mu_{2}^{*} &>& 0 \nonumber \\
\mu_{3}^{*} &=& 0 \nonumber \\ 
\mu_{4}^{*} &=& 0. \nonumber
\end{IEEEeqnarray}

Wartości trzech niewiadomych: $u^{*}_{4}$, $c^{*}_{4}$ i $\lambda^{*}$ można otrzymać, rozwiązując układ trzech równań złożonych z niżej zapisanych warunków I rzędu oraz ograniczenia budżetowego (\ref{eq_ograniczenie_t4}). Warto nadmienić, iż $\mu_{2}^{*}$ nie znajduje się w tych równaniach, ponieważ parametr ten pełni rolę pomocniczą - może on zostać obliczony z warunku I rzędu dla $i^{*}_{4}$. 

\begin{equation}
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} %2B \lambda^{*} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) = 0 
\label{eq_3_wariant_krotki}
\end{equation}

\begin{equation}
\frac{\partial \mathcal{L}}{\partial u_{4}} = \frac{(1-\alpha)(1%2B\theta)}{(1-\delta) k_{4} %2B (1%2B\theta)u_{4}^{*}} %2B \lambda^{*} \left(\theta %2B (y_{4} - r b_{4} - c_{4}^{*}) \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{(y_{4} %2B u_{4}^{*})^{2}} \right) = 0 
\label{eq_3_wariant_dlugi}
\end{equation}

\begin{equation}
\theta u_{4}^{*} %2B  c_{4}^{*} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B u_{4}^{*}} = \phi.
\label{eq_3_wariant_budzet}
\end{equation}

Próba analitycznego rozwiązania powyższego układu równań prowadzi do na tyle skomplikowanych rachunków, że nie zostały przedstawione. Co więcej, należy uznać całkowity brak inwestycji własnych samorządu za mało prawdopodobną sytuację. Niemniej jednak, optymalne rozwiązanie można uzyskać za pomocą numerycznych metod optymalizacji, o ile otrzymane rozwiązane spełnia powyższe równania. 

Wariant III

Jednocześnie mogą być wykonywane inwestycje własne oraz unijne w wysokości poniżej limitu. Wynika to z faktu, iż wysoki poziom inwestycji unijnych utrudnia spełnianie reguły IWZ w czwartym roku. Powoduje bowiem wzrost dochodów JST, przez co zmniejsza przestrzeń na odsetki i spłatę rat zadłużenia. Dlatego, wbrew intuicji, inwestowanie ze środków własnych może być optymalne mimo możliwości tańszego finansowania unijnego. Podobnie jak w wariancie drugim, także w tym przypadku podanie optymalnego rozwiązania w postaci analitycznej było niemożliwe z uwagi na stopień złożoności rachunków. 

\begin{IEEEeqnarray}{rCl}
U_{4} > u^{*}_{4} & > & 0 \nonumber \\ 
i^{*}_{4} & > & 0 \nonumber \\
c^{*}_{4} & > & 0 \nonumber \\
\mu_{2}^{*} & = & 0 \nonumber \\
\mu_{3}^{*} & = & 0 \nonumber \\ 
\mu_{4}^{*} & = & 0 \nonumber 
\end{IEEEeqnarray}

\begin{equation}
\begin{split}
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} %2B \lambda^{*} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) = 0 
\\
\frac {\partial \mathcal{L}}{\partial i_{4}} =  \frac{1-\alpha}{(1-\delta) k_{4} %2B (1%2B\theta)u_{4}^{*} %2B i_{4}^{*}} %2B \lambda^{*}  = 0  
\\  
\frac {\partial \mathcal{L}}{\partial u_{4}} = \frac{(1-\alpha)(1%2B\theta)}{(1-\delta)k_{4} %2B (1%2B\theta) u_{4}^{*} %2B i_{4}^{*}} %2B \lambda^{*} \left(\theta %2B (y_{4} - r b_{4} - c_{4}^{*}) \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{(y_{4} %2B u_{4}^{*})^{2}} \right) = 0
\\
\theta u_{4}^{*} %2B i_{4}^{*} %2B  c_{4}^{*}\left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B u_{4}^{*}} \right) - \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B u_{4}^{*}} = \phi.
\nonumber
\end{split}
\end{equation}

Wariant IV

Jeżeli wartość $(1-\delta)k_{4}$ jest odpowiednio niska, może opłacać się zrealizować inwestycje unijne na możliwie największą skalę, a dodatkowo zrealizować inwestycje zwykłe. Jest to najbardziej prawdopodobny wariant:

\begin{IEEEeqnarray}{rCl}
u^{*}_{4} & = & U_{4} \nonumber \\ 
i^{*}_{4} & > & 0 \nonumber \\
c^{*}_{4} & > & 0 \nonumber \\
\mu_{2}^{*} & = & 0 \nonumber \\
\mu_{3}^{*} & = & 0 \nonumber \\ 
\mu_{4}^{*} & > & 0 \nonumber 
\end{IEEEeqnarray}

\begin{equation}
\begin{split}
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} %2B \lambda^{*} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}} \right) = 0 \Rightarrow  c_{4} = -\frac{\alpha}{\lambda^{*} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}} \right)}\\
%
\frac {\partial \mathcal{L}}{\partial i_{4}} =  \frac{1-\alpha}{(1-\delta) k_{4} %2B (1%2B\theta)U_{4} %2B i_{4}^{*}} %2B \lambda^{*}  = 0  \Rightarrow  i_{4}^{*} = -\frac{1 - \alpha}{\lambda^{*}} - (1-\delta)k_{4} - (1%2B\theta)U_{4} \nonumber
\end{split}
\end{equation}

\begin{equation}
\begin{split}
\theta U_{4} -\frac{1 - \alpha}{\lambda^{*}} - (1-\delta)k_{4} - (1%2B\theta)U_{4} - \\
- \frac{\alpha}{\lambda^{*} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}} \right)} \left(1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}} \right) - \frac{y_{5}%2BU_{5}}{\chi%2Br} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4}%2BU_{4}} = \phi \nonumber 
\\
\theta U_{4} -\frac{1 - \alpha}{\lambda^{*}} - (1-\delta)k_{4} - (1%2B\theta)U_{4}  -\frac{\alpha}{\lambda^{*}} - \frac{y_{5}%2BU_{5}}{\chi%2Br} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}} = \phi \nonumber 
\\
- U_{4} -\frac{1}{\lambda^{*}} - (1-\delta)k_{4} - \frac{y_{5}%2BU_{5}}{\chi%2Br} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}} = \phi\nonumber 
\\
\lambda^{*}  = -\frac{1}{\phi%2B \frac{y_{5}%2BU_{5}}{\chi%2Br} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}} %2B u_{4}^{*} %2B (1-\delta)k_{4}}  \nonumber
\end{split}
\end{equation}

\begin{IEEEeqnarray}{rCl}
c_{4}^{*} & = & \frac{\alpha (\phi%2B \frac{y_{5}%2BU_{5}}{\chi%2Br} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}} %2B (1-\delta)k_{4} %2B U_{4})}{1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}}} \label{eq_c4_wariant4} \\
i_{4}^{*} & = & (1 - \alpha) \left(\phi%2B \frac{y_{5}%2BU_{5}}{\chi%2Br} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}} \right) - \alpha (1-\delta)k_{4} - (\theta %2B \alpha) U_{4}. \label{eq_i4_wariant4}
\end{IEEEeqnarray}

Optymalny poziom wydatków bieżących zależy dodatnio od: parametru $\alpha$ opisującego preferencje samorządów w odniesieniu do $c$, stałej $\phi_{0}$ oraz dochodów $y_{4}$, które wyznaczają przestrzeń fiskalną, infrastruktury $k_{4}$ (im większa, tym mniej potrzebne są inwestycje) oraz limitu $U_{4}$ (im większy, tym wystarczy realizować mniej inwestycji zwykłych). Z kolei optymalny poziom inwestycji zwykłych również zależą dodatnio od $\phi_{0}$ i $y_{4}$, a ujemnie od: $\alpha$, $k_{4}$, $U_{4}$, a także $\theta$. 

## Analityczne rozwiązanie dla trzeciego roku z napiętym warunkiem IWZ

Po znalezieniu optymalnych wartości zmiennych decyzyjnych z roku czwartego, można przejść do poszukiwania rozwiązań dla roku trzeciego. W tym celu problem decyzyjny został najpierw przeformułowany w warunkach roku trzeciego, a następnie rozwiązany za pomocą warunków KKT. Funkcja celu tego problemu ma następującą postać: 
\begin{equation}
\max_{c_{3}, u_{3}, i_{3}, z_{3}}  f(x_{3}) = \beta^{3} \left( \alpha \ln c_{3} %2B (1 - \alpha) \ln k_{4} \right) %2B \beta^{4} \left( \alpha \ln c_{4}^{*} %2B (1-\alpha) \ln k_{5}^{*} \right).  \nonumber
\end{equation}
 
Zakłada się, że w czwartym roku realizowany jest wariant czwarty z podrozdziału \ref{podrozdzial_napiety_IWZ_bez_nadwyzki}, t.j. z inwestycjami unijnymi na maksymalnym poziomie. Wariant ten wydaje się być najbardziej realistyczny, gdyż z symulacji opisanych w podrozdziale \ref{podrozdz_struktura} wynika, że w zdecydowanej większości przypadków taki wariant jest optymalny. Ponadto, można domniemywać, że inwestycje w czwartym roku mogą być wyjątkowo wysokie z uwagi na ignorowanie przez decydentów przyszłego zadłużenia oraz IWZ dotyczących przyszłych lat. Wartość funkcji można dla uproszczenia podzielić przez $\beta^{3}$:

{\footnotesize
\begin{equation}
\begin{split}
f(x_{3}) & = \alpha \ln c_{3} %2B (1 - \alpha) \ln ((1-\delta) k_{3} %2B (1%2B\theta) u_{3} %2B i_{3}) %2B \\
&%2B \beta \alpha \ln \left( \frac{\alpha \left(  \frac{y_{5} %2B U_{5}}{\chi%2B r} \frac{1}{3} \left(\sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - r b_{\tau}}{y_{\tau} %2B u_{\tau}} %2B \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}}  \right) - (1%2Br) b_{4} %2B y_{4} %2B (1-\delta)((1-\delta)k_{3} %2B (1%2B\theta)u_{3} %2B i_{3}) %2B U_{4} \right) }{1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}}}  \right) %2B 
\\
&%2B \beta  (1-\alpha) \ln ( (1-\alpha) (1-\delta) ((1-\delta) k_{3} %2B (1%2B\theta) u_{3} %2B i_{3}) %2B (1%2B\theta) U_{4} %2B\\
%
&%2B   (1 - \alpha) \left(\frac{y_{5} %2B U_{5}}{\chi%2B r} \frac{1}{3} \left( \sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - r b_{\tau}}{y_{\tau} %2B u_{\tau}}  %2B \frac{y_{4} - r b_{4}}{y_{4} %2B U_{4}} \right) - (1%2Br) b_{4} %2B y_{4}\right)  - (\theta %2B \alpha) U_{4})    \nonumber
\end{split}
\end{equation}
}
\begin{IEEEeqnarray}{lCl}
\mbox{p.w.} \nonumber
\\
& & \nonumber
\\
h_{13}(x_{3}): \theta u_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3} - z_{3} & = & 0
\label{h13}
\\
h_{23}(x_{3}): b_{4} - b_{3} - z_{3} & = & 0
\label{h23}
\\
g_{13}(x_{3}): -u_{3} & \leq & 0 \nonumber
\\
g_{23}(x_{3}): u_{3} - U_{3} & \leq & 0 \nonumber
\\
g_{33}(x_{3}): -c_{3} & \leq & 0 \nonumber
\\
g_{43}(x_{3}): -i_{3} & \leq & 0 \nonumber
\\
g_{53}(x_{3}): \frac{(\chi %2B r) b_{4}}{y_{4} %2B U_{4}} - \frac{1}{3} \left( \frac{y_{1} - c_{1} - r b_{1}}{y_{1} %2B u_{1}} %2B \frac{y_{2} - c_{2} - r b_{2}}{y_{2}%2Bu_{2}} %2B \frac{y_{3} - c_{3} - r b_{3}}{y_{3}%2Bu_{3}} \right)  & \leq & 0 
\label{g53}
\\
g_{63}(x_{3}): c_{3} %2B r b_{3} - y_{3} & \leq & 0. \label{g63}
\end{IEEEeqnarray}

Powyższy problem można uprościć poprzez wyeliminowanie zmiennych $b_{4}$ i $z_{3}$, których wartości mogą zostać obliczone rezydualnie, po znalezieniu optymalnych wartości pozostałych zmiennych decyzyjnych $u_{3}$, $i_{3}$ i $c_{3}$: 

\begin{equation} 
%\theta u_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3} - z_{3} = 0\\
z_{3} = \theta u_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3}, 
\end{equation}

\begin{equation} 
b_{4} = b_{3} %2B \theta u_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3}. 
\end{equation}

Dzięki powyższym przekształceniom, problem ogranicza się do trzech zmiennych decyzyjnych: $u_{3}$, $i_{3}$ i $c_{3}$. Wyeliminowane zostają też warunki ograniczające (\ref{h13}) i (\ref{h23}), które zostaną wykorzystane dopiero w celu obliczenia $b_{4}$ i $z_{3}$. Modyfikacji ulegnie także warunek (\ref{g53}):

{\footnotesize
\begin{equation}
g_{53}(x): \frac{(\chi %2B r) \left(b_{3} %2B \theta u_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3} \right)}{y_{4} %2B U_{4}} - \frac{1}{3} \left( \frac{y_{1} - c_{1} - r b_{1}}{y_{1} %2B u_{1}} %2B \frac{y_{2} - c_{2} - r b_{2}}{y_{2}%2Bu_{2}} %2B \frac{y_{3} - c_{3} - r b_{3}}{y_{3}%2Bu_{3}} \right) \leq  0. 
\nonumber
\end{equation}
}

Wydatki bieżące wynikają z napiętego warunku IWZ.

Poniżej założono także, że warunek (\ref{g53}) jest bardziej rygorystyczny od warunku (\ref{g63}). Z analizy zaprezentowanej w podrozdziale \ref{podrozdz_struktura} wynika, że warunek IWZ jest napięty prawie zawsze, a reguła zrównoważonego wyniku bieżącego - rzadko. Co więcej, JST występują przeciwko regule IWZ (,,Wprowadzony w 2014 r. indywidualny wskaźnik zadłużenia samorządów wymaga zmiany lub wręcz likwidacji, bo dusi inwestycje i nie pozwoli wykorzystać środków unijnych - przekonywali uczestnicy piątkowej debaty zorganizowanej przez Serwis Samorządowy PAP.'' (PAP, 2015) ,,Samorządowcy wskazują, że gorset, który wskaźnik nakłada na JST, jest zbyt ciasny.'' (Portal Samorządowy, 2016)), a nie zrównoważonego wyniku bieżącego, z czego można wnioskować, że mają większe problemy z wypełnieniem IWZ. W związku z tym założono, że w rozwiązaniu optymalnym $c_{3} %2B r b_{3} < y_{3}$. 

Dodatkowo można założyć, że $c_{3} > 0$, ponieważ dla $c_{3} = 0$ użyteczność z krańcowego przyrostu wydatków bieżących byłaby nieskończenie wielka. Podobnie, jak w roku czwartym, dla roku trzeciego można także założyć maksymalne możliwe finansowanie inwestycji ze środków unijnych (patrz podrozdział \ref{podrozdz_dopasowywanie}). W związku z tym mnożniki KKT $\mu_{13} = 0$, $\mu_{33} = 0$, natomiast $u_{3} = U_{3}$, zatem $u_{3}$ przestaje być zmienną decyzyjną. Pozostają zatem niewiadome wartości dwóch zmiennych decyzyjnych: $c_{3}$ oraz $i_{3}$, a także jednego mnożnika KKT: $\mu_{53}$. Tym trzem niewiadomym odpowiadają trzy równania. Dwa równania stanowią warunki pierwszego rzędu, a jedno - związane jest ze spełnieniem reguły IWZ z równością. 

W następstwie poczynienia powyższych założeń utworzono funkcję Lagrange'a w postaci:  

{\scriptsize
\begin{IEEEeqnarray}{rCl}
\mathcal{L}(x, \lambda, \mu) & = & f(x) %2B \sum_{j=1}^{5} \mu_{j3} g_{j3}(x) = \nonumber \\
& = &  \alpha \ln c_{3} %2B (1 - \alpha) \ln ( (1-\delta) k_{3} %2B (1 %2B \theta) U_{3} %2B i_{3}) %2B \nonumber \\
& %2B & \beta \alpha \ln (\frac{ \alpha ( \frac{y_{5} %2B U_{5}}{\chi%2B r} \frac{1}{3} \left(\sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - r b_{\tau}}{y_{\tau} %2B u_{\tau}} %2B \frac{y_{4} - r (b_{3} %2B \theta U_{3} %2B c_{3} %2B i_{3} %2B rb_{3} - y_{3})}{y_{4} %2B U_{4}}  \right) - (1%2Br)(b_{3} %2B \theta U_{3} %2B c_{3} %2B i_{3} %2B rb_{3} - y_{3}))}{1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}}}%2B \nonumber \\
& %2B & \frac{ \alpha ( y_{4} %2B (1-\delta)((1-\delta)k_{3} %2B (1%2B\theta)U_{3} %2B i_{3}) %2B U_{4} ) }{1 %2B \frac{1}{3} \frac{y_{5} %2B U_{5}}{\chi %2B r} \frac{1}{y_{4} %2B U_{4}}}) %2B \nonumber \\
& %2B & \beta (1-\alpha) \ln ((1-\alpha) (1-\delta) ((1-\delta) k_{3} %2B (1%2B\theta) U_{3} %2B i_{3}) %2B (1-\alpha) U_{4} %2B\nonumber \\
 & %2B & (1 - \alpha) (\frac{y_{5} %2B U_{5}}{\chi%2B r} \frac{1}{3} \left(  \frac{y_{2} - c_{2} - r b_{2}}{y_{2} %2B u_{2}} %2B \frac{y_{3} - c_{3} - r b_{3}}{y_{3} %2B U_{3}} %2B \frac{y_{4} - r (b_{3} %2B \theta U_{3} %2B c_{3} %2B i_{3} %2B rb_{3} - y_{3})}{y_{4} %2B U_{4}} \right) \nonumber \\
&-& (1%2Br) (b_{3} %2B \theta U_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3}) %2B y_{4}))  %2B \nonumber \\
& %2B &  \mu_{53} \left( \frac{(\chi %2B r) \left(b_{3} %2B \theta U_{3} %2B i_{3} %2B c_{3} %2B r b_{3} - y_{3} \right)}{y_{4} %2B U_{4}} - \frac{1}{3} \left( \frac{y_{1} - c_{1} - r b_{1}}{y_{1} %2B u_{1}} %2B \frac{y_{2} - c_{2} - r b_{2}}{y_{2} %2B u_{2}} %2B \frac{y_{3} - c_{3} - r b_{3}}{y_{3} %2B U_{3}} \right) \right). 
\nonumber
\end{IEEEeqnarray}
}

Następnie wyprowadzono dwa warunki pierwszego rzędu, czyli obliczono pochodne funkcji Lagrange'a po $c_{3}$ i $i_{3}$ oraz przyrównano je do zera. Połączenie dwóch równań w jedno umożliwiło wyeliminowanie mnożnika $\mu_{53}$ o nieznanej wartości. Po pewnych przekształceniach wykorzystano równanie na napięty warunek IWZ. Dzięki niemu można było wyznaczyć $c_{3}$ jako funkcję $i_{3}$. Ostatecznie zatem w rachunkach pozostanie jedna zmienna decyzyjna - $i_{3}$ i jedno (skomplikowane) równanie. W celu łatwiejszego wykonania obliczeń, zastąpiono długie i złożone wyrazy (niezależne od zmiennej decyzyjnej $i_{3}$) w poszczególnych ułamkach tego równania, pojedynczymi symbolami pomocniczymi i uzyskano w ten sposób proste równanie. Dalsze przekształcenia prostego równania doprowadziły do uzyskania równania sześciennego. Istnieją trzy możliwe rozwiązania równania sześciennego w dziedzinie liczb zespolonych. Szczegółowe obliczenia zaprezentowano w części \ref{zmudne_rachunki} aneksu.

Ze wszystkich symulacji wynika, że spośród trzech wyżej wymienionych rozwiązań równania sześciennego, tylko jedno (\ref{rozw_jedyne}) należy do zbioru liczb rzeczywistych. Pozostałe należą do zbioru liczb zespolonych i nie mają interpretacji ekonomicznej. Poprawność wyniku została zweryfikowana dzięki zgodności rozwiązania numerycznego z rozwiązaniem (\ref{rozw_jedyne}) wyprowadzonym analitycznie. Numeryczny algorytm optymalizacyjny startujący z arbitralnych (dowolnych) wartości zmiennych wielokrotnie odnajdywał bowiem te same rozwiązania optymalne, co wynikające ze wzoru (\ref{rozw_jedyne}). Z drugiej strony, algorytmy numeryczne mogą znajdywać ekstrema lokalne, a nie globalne. Jeśli jednak rozwiązanie analityczne jest takie samo, to dowodzi to globalności danego ekstremum (przy założeniu danej struktury warunków ograniczających). Porównanie wyników osiąganych za pomocą metody analitycznej i numerycznej znajduje się w części B aneksu.  

```{r, echo = FALSE, eval=FALSE}
############################################
# Rozwiązanie metodą Karusha-Kuhna-Tuckera #
############################################

phi0<-(-1-r)
phi1<-(-(y5+u5)/((chi+r)*3*(y3+u3)) -(1+r))
phi2<-((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3-r*b3)/(y3+u3)) - (1+r)*(b3+ theta*u3+r*b3-y3) + y4)
phi3<-(-3*(y3+u3)*(chi+r)/(1+3*(y3+u3)*(chi+r)/(y4+u4))/(y4+u4))
phi4<-(
  -3*(y3+u3)/(1+3*(y3+u3)*(chi+r)/(y4+u4))
  *(((chi+r)*(b3+ theta*u3 + r*b3 - y3))/(y4+u4) 
    - 1/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2)) - 1/3*(y3-r*b3)/(y3+u3))
)
phi5<-(alpha*(((y4+u4)*(3*(y3+u3)))/((chi+r)*(3*(y3+u3))+y4+u4)))
phi6<-(alpha*beta*
         ((((-(y5+u5)/(chi+r)/3*(1/(y3+u3) + r/(y4+u4))) - (1+r))*(((y4+u4)*(3*(y3+u3)))/((chi+r)*(3*(y3+u3))+y4+u4))) - (-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r)*((y4+u4)/(chi+r))))
phi7<-((-delta-r) - ((y5+u5)/(chi+r)/3*(phi3/(y3+u3) + r*(1+phi3)/(y4+U4))) - (1+r)*phi3)
phi8<-(
  ((y5+u5)/(chi+r)/3)
  * ((y3-phi4-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + phi4 + r*b3 - y3))/(y4+u4)))
  -(((1+r)*(b3+theta*u3 + phi4 + r*b3 - y3)))
  +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3) + u4)
)
phi9<-(
  beta*(1-alpha)*(1-alpha)*(((-(y5+u5)/(chi+r)/3*(1/(y3+u3) + r/(y4+u4))-(1+r)))*(((y4+u4)*(3*(y3+u3)))/((chi+r)*(3*(y3+u3))+y4+u4)) - (-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta-r)*((y4+u4)/(chi+r)))
)
phi10<-((1-delta)*(1-alpha)) + (1-alpha)*(phi0 + phi3*phi1) - r*(1+phi3)*(1-alpha)*((y5+u5)/(chi+r)/3)/(y4+u4)
phi11<-(
  (1-delta)*((1-delta)*k3 + (1+theta)*u3)
  +((1-alpha)*(phi4*phi1 + phi2 + (y5+u5)*(y4-r*(b3 + theta*u3 + phi4 +r*b3 - y3))/(chi+r)/3/(y4+u4)) 
    - alpha*(1-delta)*((1-delta)*k3 + (1+theta)*u3) - (theta+alpha)*u4) 
  + (1+theta)*u4
)
phi12<-((1-alpha)*((y4+u4)/(chi+r)))
phi13<-((1-delta)*k3 + (1+theta)*u3)

par_a<-(
  (phi5*phi7+phi3*phi6)*phi10 +
    (phi9 - phi10*phi12)*phi3*phi7
)
par_b<-(
  (phi5*phi8 + phi4*phi6)*phi10 +
    (phi5*phi7+phi3*phi6)*(phi10*phi13 + phi11) +
    (phi9*phi13 - phi11*phi12)*phi3*phi7 +
    (phi9 - phi10*phi12)*(phi3*phi8 + phi4*phi7) 
)
par_c<-(
  (phi5*phi8 + phi4*phi6)*(phi10*phi13 + phi11) +
    (phi9*phi13 - phi11*phi12)*(phi3*phi8 + phi4*phi7) +
    (phi9 - phi10*phi12)*phi4*phi8 +
    (phi5*phi7+phi3*phi6)*phi11*phi13
)
par_d<-(
  (phi5*phi8 + phi4*phi6)*phi11*phi13 +
    (phi9*phi13 - phi11*phi12)*phi4*phi8
)

############################################
#   Rozwiązanie  poprawne                  #
############################################


x<-szescienne1(par_a, par_b, par_c, par_d)
#x

i3<-as.numeric(x)
u3<-U3
u4<-U4


############################################
# Znając i3 oraz napięty IWZ, szukamy c3   #
############################################

rozw_c<-function(rozw2){
  return( ((y4+u4)/(chi+r)/
             3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-rozw2-r*b3)/(y3+u3)))
          - b3 - (1+theta)*u3 - i3 - r*b3 + u3 + y3 - rozw2)
}

c3<-c(nleqslv(c(0.5), rozw_c)$x)
z3<-(1+theta)*u3 + i3 + c3 + r*b3 - u3 - y3
b4<-b3+z3

c4<-(
  (((alpha*(y5+u5)/(chi+r)*1/3)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
   *(y3-c3 - r*b3)/(y3+u3))
  +(((alpha*(y5+u5)/(chi+r)*1/3)
     /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4))))
  -(alpha*((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3))
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  +(alpha*(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
)

#c4<-(
#alpha*(phi +(y5+u5)/(chi+r)*1/3*((y4 - r*(b3 + theta*u3 + i3 + c3 + r*b3 - y3))/(y4+u4)) + (1-delta)*k4 + u4 )
#/(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4))
#  )

k4<-(1-delta)*k3+(1+theta)*u3+i3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 + 
    (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4)) 
               -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
)
i4<-k5-(1-delta)*k4-(1+theta)*u4

# cat(c3, u3, i3)
# cat(c4, u4, i4)

######################################################
#   Sprawdzenie                                      #
######################################################

 phi5/(i3*phi3 + phi4) + phi6/(i3*phi7 + phi8) + phi9/(i3*phi10 + phi11) - phi12/(i3 + phi13)


############################################
# Sprawdzenie z warunkami I rzędu          #
############################################

lewa<-(
  +(alpha/c3) 
  +(alpha*beta*
      ((-(y5+u5)/(chi+r)/3*(1/(y3+u3) + r/(y4+u4))) - (1+r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
  ) 
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3)) + (r/(y4+u4)))-(1+r))/k5
)  

prawa<-(
  +(1-alpha)/k4 
  +(beta*alpha*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta - r))
  /(
    ((y5+u5)/(chi+r)/3)
    * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
    -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
    +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
  )
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*(r/(y4+u4)) -delta -r)/k5
)
pomo<-(
  -lewa/((chi+r)/(y4+u4) + 1/(3*(y3+u3)))
  +prawa/((chi+r)/(y4+u4))
)

pomo
```
