---
title: "Optimization of financial policy"
author: "Dominik Korniluk, PhD"
output: rmarkdown::github_document
---


## Optimization

Celem bieżącej części rozprawy jest sformułowanie optymalnej polityki finansowej samorządów w zakresie wydatków bieżących oraz inwestycyjnych gmin i miast powiatowych w ciągu czteroletniej kadencji władz samorządowych. Zgodnie z ustaleniami zawartymi w powiązanej literaturze, przyjęto założenie, że optymalna polityka powinna uwzględniać regułę zrównoważonego wyniku bieżącego i indywidualny wskaźnik zadłużenia. Powinna też zależeć od: parametrów określających preferencje samorządów, stopy procentowej, zapadalności długu, tempa wzrostu dochodów bieżących, stopy amortyzacji, początkowych wskaźników zadłużenia, wydatków bieżących oraz poziomu infrastruktury, a także limitu funduszy przeznaczonych na inwestycje unijne i udziału środków unijnych w finansowaniu inwestycji.    

Przedstawiony w niniejszej pracy doktorskiej model opisuje problem, przed którym stoją decydenci jednostki samorządu terytorialnego (wójt, burmistrz gminy lub prezydent miasta) w okresie, w którym istotną rolę w finansowaniu inwestycji odgrywają środki unijne\footnote{Model można jednak uogólnić na okres, w którym środki unijne przestaną być istotne.}. Jednostka samorządu terytorialnego jest w niniejszej pracy rozumiana jako gmina lub miasto na prawach powiatu, w tym Warszawa. 

Województwa i powiaty ziemskie nie są więc brane pod uwagę. Wynika to z ,,silnego zróżnicowania potencjału finansowego pomiędzy rodzajami JST'' (Sierak i in., 2013). Przykładowo, udział wydatków majątkowych w wydatkach ogółem jest wyraźnie mniejszy w powiatach ziemskich niż w gminach, natomiast odwrotna sytuacja ma miejsce w województwach. W niniejszej pracy wykorzystywane są dane empiryczne dotyczące gmin i miast na prawach powiatu, dlatego zdecydowano się zawęzić obszar badań do najniższego szczebla jednostek samorządowych. Należy zarazem podkreślić, że samorządy wojewódzkie i powiatowe ziemskie mają stosunkowo małe znaczenie - łącznie ich wydatki ogółem w każdym roku z okresu 2005-2014 były około cztery razy mniejsze niż łącznie wydatki gmin i miast powiatowych. W 2015 r. łączne wydatki samorządów województw i powiatów wyniosły 40,6 mld zł, natomiast gmin, Warszawy i miast na prawach powiatów wyniosły 155,8 mld zł (RIO, 2015)\nocite{RIO_2015}. 

\subsection{Preferencje}

Problem decyzyjny samorządowców można zinterpretować następująco. Po wygranych wyborach, które odbywają się na koniec roku zerowego, nowe władze samorządowe mają przed sobą cztery lata kadencji. Decydenci owi zastanawiają się, ile środków przeznaczyć na wydatki bieżące i inwestycje w roku pierwszym, drugim, trzecim i czwartym.\footnote{W wyżej opisany sposób można zinterpretować problem optymalizacyjny z rozdziału \ref{rozdzial_model_czteroletni}. Nieco inaczej należy opisać problem z rozdziału \ref{rozdzial_model_dwuletni}. Władze samorządowe dokonują tam decyzji po zakończeniu drugiego roku - planują wydatki jedynie na rok trzeci i czwarty.} W pierwszym dniu roku piątego odbywają się kolejne wybory, podczas których mieszkańcy danej gminy lub miasta oceniają dotychczasowe władze pod kątem strumienia wydatków bieżących z czterech ostatnich lat i zasobu infrastruktury na moment bieżący, a także w trzech zeszłych latach.

Mieszkańcy obszaru zarządzanego przez daną JST czerpią użyteczność z wydatków bieżących w roku $t$ oznaczonych jako $c_{t}$ (tj. przeznaczonych na bieżącą działalność, świadczenia społeczne, zasiłki i stypendia oraz inne podmioty, m.in. uczelnie, szkoły, przedszkola, instytucje kultury, zakłady opieki zdrowotnej, Izby Rolnicze i inne JST; w tej kategorii nie uwzględnia się natomiast odsetek od kredytów i pożyczek, gdyż zostały one zdefiniowane oddzielnie) oraz z zasobu szeroko rozumianej infrastruktury z roku $t+1$, tj. $k_{t+1}$  (m.in. dróg, szkół, przedszkoli, domów kultury, obiektów sportowych, oczyszczalni ścieków, pojazdów transportu zbiorowego). Maksymalizowana jest suma zdyskontowanych rocznych strumieni użyteczności z $c_{t}$ i $k_{t+1}$ wyrażonych za pomocą kombinacji liniowej logarytmów tych zmiennych. 

Zakłada się tutaj tożsamość preferencji (z wyjątkiem horyzontu czasowego) władz i mieszkańców. Politycy starają się maksymalizować dokładnie znaną, logarytmiczną funkcję użyteczności mieszkańców po to, aby wygrać następne wybory. 

Optymalizacji podlega więc następująca funkcja:
\begin{equation}
\max_{ \{c_{t}\}, \{u_{t}\}, \{i_{t}\}, \{z_{t}\}} \sum_{t=1}^{4} \beta^{t} \left( \alpha \ln c_{t} + \left(1 - \alpha \right) \ln k_{t+1} \right).
\label{eq:uzytecznosc}
\end{equation}

Założenie logarytmicznej, separowalnej względem $c_{t}$ i $k_{t+1}$ funkcji użyteczności jest zgodne z postulatem dodatniej, malejącej krańcowej użyteczności czerpanej z wydatków bieżących i infrastruktury. Spośród wielu funkcji o dodatniej pierwszej pochodnej i ujemnej drugiej pochodnej, wybrano logarytm ze względu na możliwość uzyskania prostych rachunków (pochodną logarytmu zmiennej jest odwrotność zmiennej, a separowalność sprawia, że pochodne mieszane drugiego rzędu są równe zero). Co więcej, logarytmy są często używane przez ekonomistów w funkcjach użyteczności\footnote{O logarytmicznie modelowanej użyteczności pisał już w XVIII wieku matematyk Bernoulli, jego praca została przedrukowana w Econometrice (1954)\nocite{Bernoulli_1954}. Założył on, że ,,jakikolwiek wzrost majątku (...) będzie zawsze skutkował wzrostem użyteczności odwrotnie proporcjonalnym do ilości dóbr już posiadanych'', a funkcją spełniającą powyższy warunek jest właśnie logarytm.}. 

Czasowy horyzont planowania został ograniczony z tradycyjnie przyjmowanej w ekonomii nieskończoności do czterech lat kadencji władz samorządowych z dwóch powodów. 

Po pierwsze, zakłada się krótkowzroczność polityków - ich głównym celem jest zwycięstwo w kolejnych wyborach i dlatego zależy im na maksymalizacji użyteczności w ciągu bieżącej kadencji, a nie w długim okresie. W tym celu decydenci np. wolą zrealizować maksymalne wydatki dopuszczalne przez reguły fiskalne niż wziąć pod uwagę obciążenie długiem przyszłych pokoleń. Słabością przyjętego założenia jest abstrahowanie od możliwości reelekcji. Oznacza to, że wyborcy, mimo że zależy im na użyteczności w długim okresie, nie są w stanie dobrze prognozować wydatków w przyszłości, więc oceniają polityków wyłącznie przez pryzmat ostatniej kadencji. Ponadto odróżnienie funkcji celu wyborców od polityków oraz uwzględnienie niepełnej informacji, co zostało wspomniane w poprzednim rozdziale, należy do cech współczesnych teorii fiskalnego federalizmu. 

Po drugie, model zawiera kilka warunków ograniczających oraz zmiennych decyzyjnych, przez co rozwiązania optymalne mają złożoną postać i różnią się w zależności od przyjętego wariantu stanów początkowych. Skrócenie horyzontu czasowego do jednej kadencji umożliwia stosunkowo czytelny zapis i analizę rozwiązań.\footnote{Co więcej, dopiero potraktowanie dwóch pierwszych lat jako danych, czyli skrócenie horyzontu do roku trzeciego i czwartego umożliwia rozwiązanie analityczne modelu.} 

Warto wyjaśnić także występowanie w funkcji użyteczności zmiennej $k_{t+1}$ zamiast $k_{t}$. Przede wszystkim, gdyby użyto $k_{t}$, to optymalne inwestycje w ostatnim roku kadencji byłyby zerowe, gdyż zgodnie z równaniem (\ref{eq_kapital}) na poziom infrastruktury w przyszłym roku wpływają inwestycje z poprzedniego roku. W praktyce inwestycje samorządowe w ostatnim roku kadencji odgrywają istotną rolę w pozyskaniu głosów wyborców. Można nawet postawić hipotezę, że obywatele wynagradzają władze samorządowe bardziej za przyrost infrastruktury niż za jej poziom, który odziedziczyli po swoich poprzednikach. Jednak krańcowa użyteczność z infrastruktury - jak z każdego dobra - maleje, więc w funkcji użyteczności występuje poziom $k_{t+1}$, a nie zmiana. 

\subsection{Ograniczenia budżetowe}
  
JST podlegają w każdym roku ograniczeniu budżetowemu (wg terminologii Kornaia - twardemu). Założono, że suma wydatków i rozchodów równa się sumie dochodów i przychodów z zaciągniętych pożyczek i wyemitowanych obligacji. Jednak, zgodnie z art. 217 ust. 2 pkt 5-6 ustawy o finansach publicznych, deficyt budżetu JST może być dodatkowo sfinansowany przychodami pochodzącymi m.in. z: nadwyżki budżetu JST z lat ubiegłych lub wolnych środków jako nadwyżki środków pieniężnych na rachunku bieżącym budżetu JST, wynikających z rozliczeń wyemitowanych papierów wartościowych, kredytów i pożyczek z lat ubiegłych. 

Z dwóch powodów abstrahowano od nadwyżki zgromadzonej w latach ubiegłych. Po pierwsze, zakładając, że oprocentowanie długu jest większe niż depozytów, samorządom korzystniej byłoby zredukować wolne środki do zera oraz spłacić w tej samej kwocie dług. Po drugie, w rzeczywistości nadwyżka z lat ubiegłych stanowi średnio tylko $7\%$ przychodów gmin i miast powiatowych. W $57\%$ są to kredyty, pożyczki i wyemitowane papiery wartościowe, a w $33\%$ - wolne środki wynikające z rozliczeń kredytów, pożyczek i wyemitowanych papierów wartościowych z lat ubiegłych. Ta ostatnia kategoria występuje, jeżeli samorządy zaciągną kredyt w jednym roku (np. w grudniu) w celu wydania tych środków w roku następnym (np. w styczniu). W modelu zaciąganie pożyczek zachodzi dokładnie raz na rok, a popyt zgłaszany przez samorządy jest całkowicie zaspokajany po z góry określonej stopie procentowej. Dlatego modelowym decydentom nie opłacałoby się zadłużanie się z rocznym wyprzedzeniem. Wszystkie rozliczenia kredytów, pożyczek i papierów wartościowych odbywają się w roku bieżącym. W rezultacie, $90\%$ przychodów JST jest odwzorowane w modelu bez nadwyżki z lat ubiegłych.

Założono dwa źródła dochodów: bieżące i kapitałowe unijne (dalej, w skrócie: unijne). Przyjęto, że dochody bieżące, $y_{t}$ (dotacje i subwencje z budżetu państwa i środków unijnych, wpływy z podatków - PIT i CIT - opłaty i kary oraz dochody z majątku\footnote{Nie zdecydowano się na wprowadzenie równania objaśniającego dochody z majątku za pomocą infrastruktury $k_{t}$ ze względu na możliwe nadmierne skomplikowanie modelu.}) rosną w stałym tempie $\gamma$. W modelu szereg $y_{t} = y_{0} (1 + \gamma)^{t}$ jest więc góry ustalony, dlatego równanie na $y$ nie zostało podane jako jedno z ograniczeń w dalszej części rozdziału. W rzeczywistości dostęp do środków unijnych jest ograniczony, zatem w modelu zakłada się, że dochody unijne w relacji do dochodów bieżących $\frac{u_{t}}{y_{t}}$ nie mogą przekroczyć limitu przeznaczonego dla danego JST - $\upsilon$:
\begin{equation}
0 \leq \frac{u_{t}}{y_{t}} \leq \frac{U_{t}}{y_{t}} = \upsilon. \nonumber
\end{equation}

Źródłem przychodu netto $z_{t}$ jest zaciągnięta pożyczka albo kredyt w roku t lub też, zgodnie z inną interpretacją, wpływ z wyemitowanych obligacji. Zmienna $z_{t}$ może przyjmować wartości ujemne, co należy interpretować jako spłatę netto części zadłużenia. Początkowy stan zadłużenia $b_{0}$ powiększony o skumulowane pożyczki z kolejnych lat stanowi zadłużenie w roku t: 
\begin{equation}
b_{t+1} = b_{0} + \sum_{\tau=0}^{t} z_{\tau}. \nonumber
\end{equation}

Wydatki mogą być przeznaczone na cztery cele. Z góry ustalone są odsetki od zadłużenia w wysokości iloczynu stałej stopy procentowej i długu $r b_{t}$. Decyzji podlega kwota przeznaczona na wydatki bieżące $c_{t}$ (wszystkie oprócz odsetek i wydatków majątkowych), a także inwestycje zwykłe $i_{t}$ oraz unijne $(1+\theta)u_{t}$. Współczynnik $\theta > 0$ reprezentuje część finansowania inwestycji ze środków własnych JST (tzw. współfinansowanie). 

Wydatki mogą być finansowane z dochodów bieżących, unijnych lub zaciągniętych pożyczek. Podsumowując, ograniczenie budżetowe JST przedstawia się następująco: 
\begin{equation}
(1+\theta) u_{t} + i_{t} + c_{t} + r b_{t} = u_{t} + y_{t} + z_{t}. \nonumber
\end{equation}

Inwestycje powodują przyrost infrastruktury $k_{t}$, która ulega corocznej deprecjacji o frakcję $\delta$. Parametr ten obejmuje także wpływ inflacji, tj. opisuje zmianę nominalnej wartości infrastruktury wynikającą m.in. ze zmian cen. Warto zauważyć, że w pierwszej kolejności optymalną decyzją wydaje się realizowanie inwestycji unijnych, gdyż są one częściowo finansowane ze środków zewnętrznych\footnote{W większości przypadków rzeczywiście tak powinno być, ale nie jest to pewne ze względu na występowanie dochodów unijnych w mianownikach indywidualnego wskaźnika zadłużenia (IWZ, szczegóły kilka akapitów niżej). Nie można wykluczyć, że w pewnych wyjątkowych sytuacjach korzystne mogłoby być zmniejszenie w danym roku (inne rozłożenie w czasie) inwestycji unijnych, a w konsekwencji: zmniejszenie dochodów unijnych, zmniejszenie mianownika IWZ i wreszcie - zwiększenie przestrzeni fiskalnej.}. Nie jest jednak wykluczone, że optymalny łączny poziom inwestycji powinien przekroczyć $(1+\theta)u_{t}$ i wówczas jedynym wyjściem jest realizowanie również bardziej kosztownych inwestycji zwykłych:
\begin{equation}
\label{eq_kapital}
k_{t} = k_{t-1}(1-\delta) + (1+\theta)u_{t-1} + i_{t-1}. \nonumber
\end{equation}

Zmiennymi decyzyjnymi w tym modelu są szeregi czasowe: wydatków bieżących, inwestycji unijnych i zwykłych, a także kwoty zaciągniętego długu. Wszystkie te zmienne, oprócz ostatniej, mogą przyjmować tylko wartości nieujemne: 
\begin{IEEEeqnarray}{rCl}
c_{t} & \geq & 0; \nonumber \\
u_{t} & \geq & 0;  \nonumber \\
i_{t} & \geq & 0.  \nonumber
\end{IEEEeqnarray}

\subsection{Reguły fiskalne zapobiegające eksplozji długu}

Tak wyspecyfikowany model nie miałby rozwiązania optymalnego. W ostatnim roku warto byłoby bowiem zaciągać jak największy (teoretycznie - nieskończenie wielki) dług $z_{4}^{*}$. Jego część ($r z_{4}^{*}$) przeznaczono by na odsetki, natomiast pozostała część ($ \left(1 - r \right) z_{4}^{*}$) zwiększałaby wydatki bieżące $c_{4}$, które w sposób nieograniczony zwiększałyby użyteczność. Wprawdzie odsetki ponoszone z tytułu takiego długu stanowiłyby wielkie obciążenie budżetu w przyszłych latach, ale z uwagi na czteroletni horyzont planowania, użyteczność z tych lat nie byłaby w ogóle brana pod uwagę. W rzeczywistości politycy również stoją przed pokusą prowadzenia nadmiernie ekspansywnej polityki budżetowej. Warto tu ponownie przywołać ustalenia Besleya i Coate'a (2003) o zawyżaniu wydatków publicznych przez rządy uwzględniające interesy wszystkich regionów. 

Dlatego samorządy podlegają regułom fiskalnym zapisanym w ustawie o finansach publicznych. Włączenie tych reguł do modelu sprawia, że eksplodujące zadłużenie przestaje być rozwiązaniem dopuszczalnym. Istnieją dwie reguły fiskalne nałożone na budżety samorządów zarówno \textit{ex ante}, jak i \textit{ex post}: reguła nadwyżki operacyjnej oraz indywidualny limit zadłużenia. 

Pierwsza reguła nałożona na jednostki samorządu terytorialnego została zapisana w art. 242 ustawy o finansach publicznych. Głosi ona, że zarówno planowane, jak i wykonane wydatki bieżące nie mogą być wyższe niż dochody bieżące powiększone o nadwyżkę budżetową z lat ubiegłych i wolne środki. Artykuł jest interpretowany tak, że jeśli skumulowany wynik za ubiegłe lata był ujemny, to dochody bieżące nie są pomniejszane, a jeśli dodatnie, to są powiększane. Dokładne wytłumaczenie sposobu obliczenia tej kategorii podał Bitner (2014)\nocite{Bitner_2014}. W niniejszym modelu nadwyżka z lat ubiegłych nie jest modelowana, zatem opisywaną tu regułę można zapisać w następujący sposób: 
\begin{eqnarray}
c_{t} + rb_{t} \leq y_{t}. \nonumber
\end{eqnarray}

Od 2014 r., zgodnie z art. 243 ustawy o finansach publicznych, samorządy obowiązuje także przestrzeganie indywidualnych wskaźników zadłużenia, wyrażonych wzorem:     
\begin{equation}
\frac{\chi'_{t} b_{t} + r_{t} b_{t}}{y_{t} + k'_{t} + u_{t}} \leq \frac{1}{3} \sum_{\tau=t-3}^{t-1} \frac{y_{\tau} + k'_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + k'_{\tau} + u_{\tau}},  \nonumber
\end{equation}

gdzie: $\chi'$ - planowana na rok budżetowy łączna kwota z tytułu spłat rat kredytów i pożyczek\footnote{(...) oraz wykupów papierów wartościowych przeznaczonych na finansowanie planowanego deficytu budżetu, spłatę wcześniej zaciągniętych zobowiązań, wyprzedzające finansowanie działań  finansowanych ze środków pochodzących z budżetu UE, a także na finansowanie przedsięwzięć inwestycyjnych.}; $k'$ - dochody ze sprzedaży majątku. W powyższej nierówności występują także zmienne, których definicje z niniejszego modelu są bardzo zbliżone do definicji ustawowych. W celu zachowania przejrzystości - pozostawiono ich oznaczenia bez zmian. Niemniej jednak należy zaznaczyć, że $rb$ w ustawie zdefiniowano jako planowane na rok budżetowy odsetki od kredytów i pożyczek\footnote{(...) zaciągniętych na pokrycie występującego w
ciągu roku przejściowego deficytu budżetu, finansowanie planowanego deficytu budżetu, spłatę wcześniej zaciągniętych zobowiązań, wyprzedzające finansowanie działań finansowanych ze środków pochodzących z budżetu UE oraz na finansowanie przedsięwzięć inwestycyjnych, a także odsetki i dyskonto od papierów wartościowych emitowanych na te cele oraz spłaty kwot wynikających z udzielonych poręczeń i gwarancji.}; $y + k' + u$ - dochody ogółem budżetu w danym roku budżetowym; $y$ - dochody bieżące; $c$ - wydatki bieżące.       

W rozważanym tutaj modelu uwzględniono uproszczony wzór na limit zadłużenia, rezygnując ze zmiennej $k'$ - dochodów ze sprzedaży majątku. Uznano bowiem, że sprzedaż majątku należy traktować jako działanie wyjątkowe - jednorazowe, zatem nie może stanowić stałego źródła finansowania wydatków. Ponadto możliwość sprzedaży majątku wymagałaby podziału tej zmiennej na poszczególne (niejednorodne) typy, gdyż w przeciwnym razie, zakładając inwestycje (czyli zwiększenie jednorodnego majątku) jednoczesna sprzedaż (zmniejszenie jednorodnego majątku) nie miałaby sensu. Co więcej, z danych JST wynika, że udział tej kategorii dochodów jest niski. 

Uściślenia wymaga też kwestia dochodów. W statystyce samorządów, dochody ogółem składają się z dochodów bieżących: krajowych i unijnych (nazwanych tak dla uproszczenia, w prawie zostały one określone w art. 5 ust. 1 pkt 2 i 3 ustawy o finansach publicznych, w szczególności mogą pochodzić z Norweskiego Mechanizmu Finansowego lub Szwajcarsko-Polskiego Programu Współpracy) oraz majątkowych: ze sprzedaży majątku i pozostałych majątkowych - krajowych i unijnych. W modelu występuje tylko jedna kategoria dochodów unijnych - należy je traktować jako tylko majątkowe, gdyż w przeciwnym razie musiałyby wystąpić w liczniku nierówności (\ref{regula243}). Wobec tego, dochody bieżące modelowanej gminy, $y_{t}$, zawierają w sobie kształtowane egzogenicznie dochody bieżące: krajowe i unijne. W modelu nie występują też pozostałe dochody majątkowe, które mają dość niski udział w dochodach ogółem, oraz dochody ze sprzedaży majątku, co zostało wyjaśnione w poprzednim akapicie. Jedyne zatem dochody majątkowe to $u_{t}$.     

Ponadto, zastąpiono spłatę rat kredytów $z'$ stałym odsetkiem zadłużenia, które zapada w danym roku $\chi \cdot b_{t}$. Należy zaznaczyć, że modelowany jest przyrost netto wartości zadłużenia (podobnie jak majątku), a nie poszczególne transakcje. Stała jest również stopa procentowa $r$. Poniższa nierówność uniemożliwia nieograniczone zaciąganie długu w ostatnim roku:
\begin{equation}
\label{regula243}
\frac{(\chi+r) b_{t}}{y_{t} + u_{t}} \leq \frac{1}{3} \sum_{\tau=t-3}^{t-1} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}}.
\end{equation}

\section{Rozwiązanie modelu}
\label{rozwiazanie_modelu}
\subsection{Zapis rozwiązania modelu za pomocą warunków Karusha-Kuhna-Tuckera}
\label{zapis_rozwiazania}

Warunki konieczne, które musi spełniać rozwiązanie optymalne modelu, wynikają z twierdzenia Karusha, Kuhna i Tuckera (KKT), które brzmi następująco (Chong, Żak, 2001, s. 397-398)\nocite{Chong_Zak_2001}:

Rozważmy problem optymalizacyjny:

$$ \min f(\bm{x}) $$
p.w. $$ \bm{h}(\bm{x}) = \bm{0},$$
$$\bm{g}(\bm{x}) \leq \bm{0},$$
gdzie $f: \mathbb{R}^{n} \rightarrow \mathbb{R}$,  $\bm{h}: \mathbb{R}^{n} \rightarrow \mathbb{R}^{m}$, $m \leq n$ i $\bm{g}: \mathbb{R}^{n} \rightarrow \mathbb{R}^{p}$. Niech:  $J(\bm{x}^{*}) = \left\{j : g_{j}(\bm{x}^{*}) = 0 \right\}$. Niech $\bm{x}^{*}$ będzie punktem regularnym, tzn. takim, że wektory:
$$\nabla h_{i}(\bm{x^{*}}), \nabla g_{j}(\bm{x^{*}}), 1 \leq i \leq m, j \in J(\bm{x^{*}})$$
są liniowo niezależne. $C^{1}$ oznacza zbiór funkcji ciągłych i różniczkowalnych w sposób ciągły\footnote{Założenia twierdzenia KKT można nieco osłabić, ale dla funkcji wykorzystanych w niniejszym modelu nie ma to znaczenia (Palczewski, 2014, s. 57-58)\nocite{Palczewski_2014}}.

Niech $f, \bm{h}, \bm{g} \in C^{1}$. Niech $\bm{x}^{*}$ będzie punktem regularnym, stanowiącym ekstremum lokalne $f$, pod warunkiem że $\bm{h(x)} = \bm{0}$, $\bm{g(x)} \leq \bm{0}$. Wtedy istnieje $\bm{\lambda}^{*} \in \mathbb{R}^{m}$ (tzw. wektor mnożników Lagrange'a) i $\bm{\mu}^{*} \in \mathbb{R}^{p}$ (tzw. wektor mnożników KKT), takie że:
\begin{enumerate}
\item $\bm{\mu}^{*} \geq \bm{0}$;
\item $ Df(\bm{x}^{*}) + \bm{\lambda}^{*T}D \bm{h}(\bm{x}^{*}) + \bm {\mu}^{*T}D \bm{g}(\bm{x}^{*}) = \bm{0}^{T} $;
\item $\bm{\mu}^{*T} \bm{g}(\bm{x}^{*}) = 0$.
\end{enumerate}

Dowód można znaleźć np. we wspomnianym podręczniku do optymalizacji autorstwa Chonga i Żaka (2001, s. 399-401).

Model decyzyjny władz samorządowych z warunkami w postaci KKT należy zapisać w następujący sposób:

\begin{equation}
\label{problem_maks}
\max_{\{c_{t}\}, \{u_{t}\}, \{i_{t}\}, \{z_{t}\}}  f(\bm{x}) =  \sum_{t=1}^{4} \beta^{t} \left( \alpha \ln c_{t} + \left(1 - \alpha \right) \ln k_{t+1} \right)
\end{equation}

$\mbox{p.w. } \forall t \in {1, 2, 3, 4}$
\begin{IEEEeqnarray}{lCl}
h_{1t}(\bm{x}): \theta u_{t} + i_{t} + c_{t} + r b_{t} - y_{t} - z_{t} & = 0\nonumber \\
h_{2t}(\bm{x}): b_{t+1} - b_{1} - \sum_{\tau=1}^{t} z_{\tau} & = & 0  \nonumber \\
h_{3t}(\bm{x}): k_{t+1} - (1-\delta)k_{t} - i_{t} - (1+\theta)u_{t} & = & 0 
\nonumber \\
g_{1t}(\bm{x}): -u_{t} & \leq & 0
\nonumber \\
g_{2t}(\bm{x}): u_{t} - U_{t} & \leq & 0
\nonumber \\
g_{3t}(\bm{x}): -c_{t} & \leq & 0 
\nonumber \\
g_{4t}(\bm{x}): -i_{t} & \leq & 0
\nonumber \\
g_{5t}(\bm{x}): \frac{(\chi + r) b_{t+1}}{y_{t+1} + u_{t+1}} - \frac{1}{3} \sum_{\tau=t-2}^{t} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}} & \leq & 0 
\label{IWZ}
\\
g_{6t}(\bm{x}): c_{t} + rb_{t} - y_{t} & \leq &  0
\label{regula_bez_nadwyzki}
\\
\mbox{dane: } b_{-1}, b_{0}, b_{1}, k_{1}, c_{-1}, c_{0}, u_{-1}, u_{0}, u_{5}. & & \nonumber
\end{IEEEeqnarray}

Rozwiązanie modelu polega na znalezieniu wartości składowych wektora: $$\bm{x}^{*} = [c_{1}^{*} c_{2}^{*} c_{3}^{*} c_{4}^{*} u_{1}^{*} u_{2}^{*} u_{3}^{*} u_{4}^{*} i_{1}^{*} i_{2}^{*} i_{3}^{*} i_{4}^{*} z_{1}^{*} z_{2}^{*} z_{3}^{*} z_{4}^{*}]^{T},$$ spełniających warunki z twierdzenia KKT. Wymaga to policzenia pochodnych funkcji $f(\bm{x}) + \bm{\lambda} h(\bm{x}) + \bm{\mu} g(\bm{x})$. Jednocześnie, w przypadku każdego warunku $g_{j}$: jeżeli $g_{j}(x) <0$, to $\mu_{j} = 0$ i analogicznie: jeżeli $\mu_{j} > 0$, to $g_{j}(x) = 0$. Wynika to z faktu, że oba czynniki $g_{j}(x)$ i $\mu_{j}$ nie mogą być jednocześnie niezerowe, gdyż taki iloczyn mógłby być tylko ujemny (co wynika z pierwszego warunku KKT i tego, że $g_{j} \leq 0$), a wówczas suma ujemnych i ewentualnie zerowych iloczynów dałaby liczbę ujemną, a nie zerową, co wymaga trzeci warunek KKT. 

Warunki Kuhna-Tuckera są warunkami koniecznymi tylko wtedy, gdy spełnione są warunki tzw. kwalifikowalności\footnote{Szczegółową dyskusję na ten temat można znaleźć np. w podręczniku do ekonomii matematycznej Chianga (1994).}. Mogą istnieć bowiem rozwiązania optymalne, które nie spełniają warunków KKT, ale musiałyby one znajdować się w specyficznie określonych punktach brzegowych. W przykładzie z podrozdziału \ref{rozdzial_szescienne} pokazano, że rozwiązanie analityczne modelu może sprowadzać się do znalezienia, przy ustalonej strukturze warunków ograniczających, optymalnego poziomu inwestycji zwykłych ($i_{t}^{*}$). O poziomie tym założono w omawianym przykładzie, że nie jest zerowy, a zatem z góry przyjęto, że nie może znaleźć się w punkcie brzegowym. 

Teoretycznie ekstremów lokalnych spełniających warunki KKT mogłoby być więcej niż jeden i wówczas należałoby wybrać spośród nich ekstremum (ewentualnie ekstrema) globalne. Jednak ,,żaden punkt wewnętrzny zbioru rozwiązań dopuszczalnych, nie spełniający warunków KKT, nie może być rozwiązaniem optymalnym'' (Chiang, 1994). Oznacza to, że jeżeli ekstremum globalne istnieje  w punkcie wewnętrznym oraz jeżeli zbiór punktów spełniających warunki KKT jest jednoelementowy, to punkt należący do tego zbioru jest ekstremum globalnym. W dalszej części pracy (w szczególności w porozdziale \ref{rozdzial_szescienne} oraz części B i C aneksu) pokazano, że punkty spełniające warunki KKT dla pewnego podzbioru zbioru rozwiązań dopuszczalnych stanowią rozwiązanie równania sześciennego. Spośród trzech takich rozwiązań, dwa stanowią liczby zespolone, a tylko jeden należy do zbioru liczb rzeczywistych. Oznacza to, że punkt ten musi być globalnym rozwiązaniem optymalnym w ramach omawianego podzbioru.

Wyznaczenie pełnego rozwiązania analitycznego takiego modelu jest niewykonalne ze względu na ogromną złożoność zagadnienia. Już nawet rozwiązanie dla trzeciego i czwartego roku (patrz podrozdział \ref{rozdzial_szescienne}) wymaga bardzo żmudnych i czasochłonnych rachunków, które prowadzą do równania sześciennego. Dlatego w kolejnych podrozdziałach zostaną wyznaczone, metodą analityczną, fragmentaryczne rozwiązania modelu, dla $t = 3,4$ (dla z góry ustalonych wartości zmiennych decyzyjnych z lat $t=1,2$), a następnie, metodą numeryczną, pełne rozwiązanie modelu, dla $t = 1,2,3,4$. Innymi słowy, w kolejnych podrozdziałach przedstawione zostaną rozwiązania analityczne problemu (\ref{problem_maks}) na pewnych podzbiorach pełnego zbioru rozwiązań dopuszczalnych. Rozwiązania takie co do zasady nie będą stanowiły globalnego maksimum problemu (\ref{problem_maks}), jednak pozwolą zbudować cenną intuicję odnośnie do funkcjonowania modelu. Pełne rozwiązanie modelu zostanie wyznaczone metodą numeryczną w rozdziale \ref{analiza_wrazliwosci}, po kalibracji modelu w rozdziale \ref{rozdzial_dane}. Jak się okaże, struktura warunków ograniczających w rozwiązaniu optymalnym z dużym prawdopodobieństwem będzie zgodna z tą, którą założono  na potrzeby rozwiązania analitycznego w rozdziale \ref{rozwiazanie_modelu}. Pozwala to potwierdzić praktyczną użyteczność przedstawionych tu analiz.


```{r, echo = FALSE, eval=TRUE}
library(nleqslv)
library(optimx)
```

```{r, echo=FALSE, eval=TRUE}
szescienne1<-function(a,b,c,d){
  h<-as.complex(as.complex(27*(a^2)*(d^2) + (4*(b^3) - (18*a*b*c))*d + (4*a*(c^3)) - (b^2 * c^2))^(1/2))
  i<-(2*3^(3/2))*a^2
  j<-27*(a^2)*d - (9*a*b*c) + 2*(b^3)
  k<-54*a^3
  e<-as.complex(h/i - j/k)
  f<-(3*a*c - b^2)
  g<-(9*a^2)*((h/i - j/k)^(1/3))
  return( e^(1/3) - f/g - b/(3*a) )
}


glowna<-function(arg){

wyniki<-0*c(1:21)  

################################################################
#Deklaracje wartości parametrów i startowych poziomów zmiennych#
################################################################

alpha<-0.4
beta<-0.1   
gamma<-arg[1]
delta<-arg[2]
theta<-arg[3]
r<-arg[4]
chi<-arg[5] 
y1<-1
y2<-y1*(1+gamma)
y3<-y2*(1+gamma)
y4<-y3*(1+gamma)
y5<-y4*(1+gamma)
b1<-arg[6]*y1
b2<-arg[6]*y2
b3<-arg[6]*y3
c1<-arg[7]*y1
c2<-arg[7]*y2
k3<-arg[8]*y3
upsilon<-arg[9]

u1<-upsilon*y1
U1<-upsilon*y1
u2<-upsilon*y2
U2<-upsilon*y2
u3<-upsilon*y3
U3<-upsilon*y3
u4<-upsilon*y4
U4<-upsilon*y4
u5<-upsilon*y5
U5<-upsilon*y5

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

############################################
# Deklaracja funkcji użyteczności          #
############################################

uzyt<-function(p){
  c3<-p[1]
  u3<-p[2]
  i3<-p[3]

  z3<-(1+theta)*u3 + i3 + c3 + r*b3 - u3 - y3
  b4<-b3+z3
  k4<-(1-delta)*k3+(1+theta)*u3+i3

  u4<-U4
  c4<-(
    (((alpha*(y5+u5)/(chi+r)*1/3)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
     *(y3-c3 - r*b3)/(y3+u3))
    +(((alpha*(y5+u5)/(chi+r)*1/3)
       /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
      *(((y2-c2 - r*b2)/(y2+u2))+((y4 - r*b4)/(y4+u4))))
    -(alpha*((1+r)*b4)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
    +(alpha*(y4 + (1-delta)*k4 + u4)
      /(1+ 1/3*((y5+u5)/(chi+r))/(y4+u4)))
  )
  k5<-(
    (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 +
      (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4))
                 -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
  )
  i4<-k5-(1-delta)*k4-(1+theta)*u4

  kara<-0*c(1:6)
  kara[1]<-(c3<0)*9999 + (c4<0)*9999
  kara[2]<-(i3<0)*9999 + (i4<0)*9999
  kara[3]<-(u3<0)*9999 + (u3>U3)*9999
  kara[4]<-((c3+r*b3)>y3)*9999
  kara[5]<-(((chi+r)*b4)/(y4+u4) > 1/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-c3-r*b3)/(y3+u3)))*9999
  kara[6]<-((c4+r*b4)>y4)*9999
  return(-(- abs(sum(kara)*which.max(abs(c(c3,c4,u3,i3,i4))))
           + alpha*log(c3) + (1-alpha)*log(k4) + beta*alpha*log(c4)
           + beta*(1-alpha)*log(k5)))
}


####################################################
# Podsumowanie rozwiązania z równania sześciennego #          
####################################################
# 
# cat(c3, u3, i3)
# cat(c4, u4, i4)
# uzyt(c(c3-0.000001,u3,i3))
# 

 wyniki[1:7]<-c(c3, u3, i3, c4, u4, i4, uzyt(c(c3-0.000001,u3,i3)))


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
k4<-(1-delta)*k3+(1+theta)*u3+i3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 + 
    (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4)) 
               -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
)
i4<-k5-(1-delta)*k4-(1+theta)*u4
z3<-(1+theta)*u3 + i3 + c3 + r*b3 - u3 - y3
b4<-b3+z3

############################################
# Sprawdzenie z warunkami I rzędu          #
############################################

lew<-(
  +(alpha/c3) 
  +(alpha*beta*
      ((-(y5+u5)/(chi+r)/3*(1/(y3+u3)+r/(y4+u4))) - (1+r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
  ) 
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3))+(r/(y4+u4)))-(1+r))/k5
)  

praw<-(
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

spr<-(
  -lew/((chi+r)/(y4+u4) + 1/(3*(y3+u3)))
  +praw/((chi+r)/(y4+u4))
)
spr

####################################################
# Podsumowanie rozwiązania metodami iteracyjnymi   #          
####################################################

# cat(c3, u3, i3)
# cat(c4, u4, i4)
# uzyt(c(c3-0.00000001,u3,i3))

wyniki[8:14]<-c(c3, u3, i3, c4, u4, i4, uzyt(c(c3-0.000001,u3,i3)))

spr3<-function(pomoc){
  c3<-pomoc
  u3<-U3
  u4<-U4
  b4<-(y4+u4)/(chi+r)/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-c3-r*b3)/(y3+u3))
  z3<-b4-b3
  i3<- z3 - (1+theta)*u3 - c3 - r*b3 + u3 + y3
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
  k4<-(1-delta)*k3+(1+theta)*u3+i3
  k5<-(
    (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 +
      (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4))
                 -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
  )
  i4<-k5-(1-delta)*k4-(1+theta)*u4

  lewa<-(
    +(alpha/c3)
    +(alpha*beta*
        ((-(y5+u5)/(chi+r)/3*(1/(y3+u3)+r/(y4+u4))) - (1+r))
      /(
        ((y5+u5)/(chi+r)/3)
        * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
        -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
        +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
      )
    )
    +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3))+(r/(y4+u4)))-(1+r))/k5
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
  return(c(pomo))
}


##############################################
# Rozwiązanie bazujące na warunkach I rzędu  #  
##############################################



rozw<-c(nleqslv(c(0.5), spr3)$x)
rozw[]<-rozw[]
b4<-(y4+u4)/(chi+r)/3*((y1-c1-r*b1)/(y1+u1) + (y2-c2-r*b2)/(y2+u2) + (y3-rozw-r*b3)/(y3+u3))

z3<-b4-b3
i3<-( z3 - (1+theta)*u3 - rozw - r*b3 + u3 + y3)
p<-c(rozw-0.000001, u3, i3)

c3<-p[1]
u3<-p[2]
i3<-p[3]

u4<-U4
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
k4<-(1-delta)*k3+(1+theta)*u3+i3
k5<-(
  (1-alpha)*(1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + (1-alpha)*u4 + 
    (1-alpha)*((y5+u5)/(chi+r)/3*((y2-c2-r*b2)/(y2+u2) + (y3- c3-r*b3)/(y3+u3) + (y4 -r*b4)/(y4+u4)) 
               -     (1+r)*(b3+ theta*u3 + i3 + c3 + r*b3 - y3) + y4)
)
i4<-k5-(1-delta)*k4-(1+theta)*u4


####################################################
# Sprawdzenie                                      #          
####################################################

lewa<-(
  +(alpha/c3) 
  +(alpha*beta*
      ((-(y5+u5)/(chi+r)/3*(1/(y3+u3)+r/(y4+u4))) - (1+r))
    /(
      ((y5+u5)/(chi+r)/3)
      * ((y3-c3-r*b3)/(y3+u3)+((y2-c2-r*b2)/(y2+u2))+((y4-r*b4)/(y4+u4)))
      -(((1+r)*(b3+theta*u3 + c3 + i3 + r*b3 - y3)))
      +(y4 + (1-delta)*((1-delta)*k3 + (1+theta)*u3 + i3) + u4)
    )
  ) 
  +beta*(1-alpha)*(1-alpha)*(-(y5+u5)/(chi+r)/3*((1/(y3+u3))+(r/(y4+u4)))-(1+r))/k5
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

####################################################
# Podsumowanie rozwiązania z warunków I rzędu      #          
####################################################

# cat(c3, u3, i3)
# cat(c4, u4, i4)
# uzyt(c(c3-0.00000001,u3,i3))
# uzyt(c(c3,u3,i3))

wyniki[15:21]<-c(c3, u3, i3, c4, u4, i4, uzyt(c(c3-0.000001,u3,i3)))

return(wyniki)}


######################################################
# Analiza wyników                                    #
######################################################

macierz<-matrix(0*c(1:(23*10)), nrow=100, ncol=23)

wektor<-0*c(1:100)
for (iter1 in 1:10){
  for (iter2 in 1:10){
    wektor[iter2+ (iter1-1)*10]<-(0.02*iter1+0.28)    
  }
}

macierz[,1]<-as.vector(wektor)
macierz[,2]<-0.05*c(1:10)
macierz

for (iter2 in 1:100){
 macierz[iter2,3:23]<-glowna(macierz[iter2,1], macierz[iter2,2])  
 print(iter2)
}
macierz
View(macierz)
setwd("C:\\Dysk\\Nowe\\JST\\Skrypty w R")
write.csv(macierz, "macierz2.csv")

######################################################
# Analiza wrażliwości                                #
######################################################

gamma_arg<-0.043
delta_arg<-0.049
theta_arg<-0.62
r_arg<-0.038
chi_arg<-0.2
b_arg<-0.32
c_arg<-0.92
k_arg<-2.06
upsilon_arg<-0.25

library(triangle)

# rlnorm(1, f.ln.m, f.ln.sd)
# rgamma(1, f.g.s, f.g.r)
# rchisq(1, f.chi.df)
# rt(1, df)*sc + loc
# rnorm(1, f.mean, f.sd)
# rtriangle(1, low,up,mean)


losowanie<-function(){
gamma_arg<-rt(1, 2.919)*0.039 + 0.044
delta_arg<-(-0.15 + rgamma(1, 4.76, 21.213))
theta_arg<-rtriangle(1, 0.43, 1, 0.62)
r_arg<-rgamma(1, 6.417, 152.5)
chi_arg<-rgamma(1, 2.325, 9.608)
if (runif(1)<0.038){
  b_arg<-0}else{
  b_arg<-rgamma(1, 2.405, 6.984)
}
c_arg<-rt(1, 4.52)*0.045 + 0.9
k_arg<-rt(1, 6.58)*0.36 + 2.06
upsilon_arg<-rtriangle(1, 0.2, 0.35, 0.25)

arg_arg<-c(gamma_arg, delta_arg, theta_arg, r_arg, chi_arg, b_arg, c_arg, k_arg, upsilon_arg)
return(arg_arg)
}

n_iter<-400
macierz<-matrix(0*c(1:30), nrow=n_iter, ncol=30)

for (iter in 1:n_iter){
  losowanko<-losowanie()
  macierz[iter,1:9]<-losowanko
  macierz[iter,10:30]<-glowna(losowanko)  
  print(iter)
}
setwd("C:\\Dysk\\Nowe\\JST\\Skrypty w R\\Wyniki październik 2017")
write.csv(macierz, "wyniki9.csv")
```
