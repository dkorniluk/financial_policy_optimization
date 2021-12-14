---
title: "Optimization of financial policy"
author: "Dominik Korniluk, PhD"
output: rmarkdown::github_document
---


## Optimization

Celem bieżącej części rozprawy jest sformułowanie optymalnej polityki finansowej samorządów w zakresie wydatków bieżących oraz inwestycyjnych gmin i miast powiatowych w ciągu czteroletniej kadencji władz samorządowych. Zgodnie z ustaleniami zawartymi w powiązanej literaturze, przyjęto założenie, że optymalna polityka powinna uwzględniać regułę zrównoważonego wyniku bieżącego i indywidualny wskaźnik zadłużenia. Powinna też zależeć od: parametrów określających preferencje samorządów, stopy procentowej, zapadalności długu, tempa wzrostu dochodów bieżących, stopy amortyzacji, początkowych wskaźników zadłużenia, wydatków bieżących oraz poziomu infrastruktury, a także limitu funduszy przeznaczonych na inwestycje unijne i udziału środków unijnych w finansowaniu inwestycji.    

Przedstawiony w niniejszej pracy doktorskiej model opisuje problem, przed którym stoją decydenci jednostki samorządu terytorialnego (wójt, burmistrz gminy lub prezydent miasta) w okresie, w którym istotną rolę w finansowaniu inwestycji odgrywają środki unijne\footnote{Model można jednak uogólnić na okres, w którym środki unijne przestaną być istotne.}. Jednostka samorządu terytorialnego jest w niniejszej pracy rozumiana jako gmina lub miasto na prawach powiatu, w tym Warszawa. 

Województwa i powiaty ziemskie nie są więc brane pod uwagę. Wynika to z ,,silnego zróżnicowania potencjału finansowego pomiędzy rodzajami JST'' (Sierak i in., 2013). Przykładowo, udział wydatków majątkowych w wydatkach ogółem jest wyraźnie mniejszy w powiatach ziemskich niż w gminach, natomiast odwrotna sytuacja ma miejsce w województwach. W niniejszej pracy wykorzystywane są dane empiryczne dotyczące gmin i miast na prawach powiatu, dlatego zdecydowano się zawęzić obszar badań do najniższego szczebla jednostek samorządowych. Należy zarazem podkreślić, że samorządy wojewódzkie i powiatowe ziemskie mają stosunkowo małe znaczenie - łącznie ich wydatki ogółem w każdym roku z okresu 2005-2014 były około cztery razy mniejsze niż łącznie wydatki gmin i miast powiatowych. W 2015 r. łączne wydatki samorządów województw i powiatów wyniosły 40,6 mld zł, natomiast gmin, Warszawy i miast na prawach powiatów wyniosły 155,8 mld zł (RIO, 2015). 

# Preferencje

Problem decyzyjny samorządowców można zinterpretować następująco. Po wygranych wyborach, które odbywają się na koniec roku zerowego, nowe władze samorządowe mają przed sobą cztery lata kadencji. Decydenci owi zastanawiają się, ile środków przeznaczyć na wydatki bieżące i inwestycje w roku pierwszym, drugim, trzecim i czwartym.\footnote{W wyżej opisany sposób można zinterpretować problem optymalizacyjny z rozdziału \ref{rozdzial_model_czteroletni}. Nieco inaczej należy opisać problem z rozdziału \ref{rozdzial_model_dwuletni}. Władze samorządowe dokonują tam decyzji po zakończeniu drugiego roku - planują wydatki jedynie na rok trzeci i czwarty.} W pierwszym dniu roku piątego odbywają się kolejne wybory, podczas których mieszkańcy danej gminy lub miasta oceniają dotychczasowe władze pod kątem strumienia wydatków bieżących z czterech ostatnich lat i zasobu infrastruktury na moment bieżący, a także w trzech zeszłych latach.

Mieszkańcy obszaru zarządzanego przez daną JST czerpią użyteczność z wydatków bieżących w roku <img src="https://render.githubusercontent.com/render/math?math=t"> oznaczonych jako $c_{t}$ (tj. przeznaczonych na bieżącą działalność, świadczenia społeczne, zasiłki i stypendia oraz inne podmioty, m.in. uczelnie, szkoły, przedszkola, instytucje kultury, zakłady opieki zdrowotnej, Izby Rolnicze i inne JST; w tej kategorii nie uwzględnia się natomiast odsetek od kredytów i pożyczek, gdyż zostały one zdefiniowane oddzielnie) oraz z zasobu szeroko rozumianej infrastruktury z roku $t+1$, tj. $k_{t+1}$  (m.in. dróg, szkół, przedszkoli, domów kultury, obiektów sportowych, oczyszczalni ścieków, pojazdów transportu zbiorowego). Maksymalizowana jest suma zdyskontowanych rocznych strumieni użyteczności z $c_{t}$ i $k_{t+1}$ wyrażonych za pomocą kombinacji liniowej logarytmów tych zmiennych. 

Zakłada się tutaj tożsamość preferencji (z wyjątkiem horyzontu czasowego) władz i mieszkańców. Politycy starają się maksymalizować dokładnie znaną, logarytmiczną funkcję użyteczności mieszkańców po to, aby wygrać następne wybory. 

Optymalizacji podlega więc następująca funkcja:
<img src="https://render.githubusercontent.com/render/math?math=\max_{ \{c_{t}\}, \{u_{t}\}, \{i_{t}\}, \{z_{t}\}} \sum_{t=1}^{4} \beta^{t} \left( \alpha \ln c_{t} + \left(1 - \alpha \right) \ln k_{t+1} \right)">

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

\subsection{Analityczne rozwiązanie dla czwartego roku z napiętym warunkiem IWZ}
\label{podrozdzial_napiety_IWZ_bez_nadwyzki}

Uprośćmy teraz problem, znajdując ,,na skróty'' optymalne wartości dla zmiennych z roku czwartego. W tym celu warunek $h_{14}(\bm{x})$ należy przekształcić do postaci:

\begin{IEEEeqnarray}{rCl}
\theta u_{4} + i_{4} + c_{4}   & = &  z_{4} + y_{4} - rb_{4}. \nonumber
\end{IEEEeqnarray}

Zmienne $y_{4}$, $b_{4}$ są z góry ustalone w roku czwartym. Widać zatem, że suma wydatków bieżących i inwestycyjnych zależy dodatnio od wielkości zaciągniętego długu w czwartym roku. Optymalnie byłoby zatem powiększyć dług jak najbardziej to możliwe, czyli na tyle, na ile pozwalają reguły fiskalne. Z analizy rozwiązań optymalnych uzyskanych za pomocą metod numerycznych (rozdz. \ref{rozdz_numeryczna_metoda}) wynika, że prawie zawsze napięty jest warunek indywidualnego wskaźnika zadłużenia (IWZ, patrz równanie (\ref{IWZ})), a bardzo rzadko - zrównoważonego wyniku bieżącego (ZWB, patrz równanie (\ref{regula_bez_nadwyzki})). Dlatego dalej założono, że IWZ jest warunkiem napiętym, a ZWB - luźnym. 

Z napiętego warunku IWZ można wyprowadzić wzór na optymalny deficyt w roku czwartym: 
\begin{IEEEeqnarray}{rCl}
\frac{(\chi+r) b_{5}^{*}}{y_{5} + u_{5}^{*}} & = & \frac{1}{3} \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}} \Rightarrow \nonumber \\
%b_{5}^{*} & = & \frac{{y_{5} + u_{5}^{*}} }{\chi + r} \left( \frac{1}{3} \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}} \right) \nonumber \\
%z_{4}^{*} & = & b_{5}^{*} - b_{4} \nonumber \\
\Rightarrow z_{4}^{*} & = & \frac{y_{5} + u_{5}^{*}}{\chi+ r} \left( \frac{1}{3} \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}}  \right) - b_{4}. \nonumber
\end{IEEEeqnarray}

Następnie można przekształcić ograniczenie budżetowe tak, aby po lewej stronie występowały tylko zmienne decyzyjne (ponieważ powinny przyjąć optymalne wartości, to zostały oznaczone gwiazdkami), a po prawej stronie -  zmienne z góry ustalone w roku czwartym (ich suma to $\phi= \mbox{const}\lvert_{t=4}$). Wyjątek stanowi zmienna $u_{5} \leq U_{5}$, której wartość jest określana dopiero przez następne władze samorządowe, co wykracza poza omawiane tu zagadnienie optymalizacyjne. Na potrzeby rozwiązania można założyć, że w roku piątym kwota inwestycji unijnych opiewa na maksymalny limit, tj. $u^{*}_{5} = U_{5}$.   

{\footnotesize
\begin{IEEEeqnarray}{rCl}
\theta u_{4}^{*} + i_{4}^{*} + c_{4}^{*} + r b_{4} & = &  z_{4}^{*} + y_{4} \Rightarrow \nonumber \\
%
%\theta u_{4}^{*} + i_{4}^{*} + c_{4}^{*} & = &  \frac{y_{5} + U_{5}}{\chi+ r} \left( \frac{1}{3}  \sum_{\tau=2}^{4} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}}  \right) - (1+r) b_{4} + y_{4} \nonumber 
%\\
%\theta u_{4}^{*} + i_{4}^{*} + c_{4}^{*}\left( 1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + u_{4}^{*}} & = & \frac{y_{5} + U_{5}}{\chi+ r} \frac{1}{3} \sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}}  - (1+r ) b_{4} + y_{4} \nonumber
%\\
%\theta u_{4}^{*} + i_{4}^{*} + c_{4}^{*}\left( 1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4} }{y_{4} + u_{4}^{*}} & = & \frac{y_{5} + U_{5}}{\chi+ r} \frac{1}{3} \sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - rb_{\tau}}{y_{\tau} + u_{\tau}}  - (1+r) b_{4} + y_{4} \nonumber
%\\
\label{eq_ograniczenie_t4}
\Rightarrow \theta u_{4}^{*} + i_{4}^{*} + c_{4}^{*}\left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + u_{4}^{*}} & = & \phi
\end{IEEEeqnarray}
}

Czynnik dyskontujący $\beta^{4}$ można w funkcji celu pominąć, gdyż w tym rozdziale brany pod uwagę jest tylko jeden rok. Model optymalizacyjny można zapisać zatem w następujący sposób: 
\begin{equation}
\max_{c_{4}, u_{4}, i_{4}} \left( \alpha \ln c_{4} + \left(1 - \alpha \right) \ln k_{5} \right) \nonumber
\end{equation}
p.w.
\begin{IEEEeqnarray}{rCl}
\theta u_{4} + i_{4} + c_{4} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + u_{4}} - \phi& = & 0 \nonumber \\
-c_{4} & \leq & 0 \nonumber \\
-i_{4} & \leq & 0 \nonumber \\
-u_{4} & \leq & 0 \nonumber \\
u_{4} - U_{4} & \leq & 0 \nonumber \\
c_{4} + r b_{4} & = & y_{4}. \nonumber
\end{IEEEeqnarray}

Funkcja Lagrange'a i warunki konieczne (pierwszego rzędu) przedstawiają się następująco:
\begin{equation}
\begin{split}
\mathcal{L}(c_{4}, u_{4}, i_{4}) = \alpha \ln c_{4} + \left(1 - \alpha \right) \ln  \left( (1-\delta) k_{4} + (1+\theta)u_{4} + i_{4} \right) +\\
+ \lambda \left[ \theta u_{4} + i_{4} + c_{4}\left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + u_{4}} - \phi\right]\\ - \mu_{1}c_{4} - \mu_{2}i_{4} - \mu_{3}u_{4} + \mu_{4}(u_{4} - U_{4})
\nonumber
\end{split}
\end{equation}

\begin{equation} 
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} + \lambda \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) - \mu_{1}^{*} = 0 
\nonumber
\end{equation}

\begin{equation}
\frac {\partial \mathcal{L}}{\partial i_{4}} =  \frac{1-\alpha}{(1-\delta) k_{4} + (1+\theta)u_{4}^{*} + i_{4}^{*}} + \lambda^{*} - \mu_{2}^{*} = 0 
\nonumber
\end{equation}

\begin{equation}
\frac {\partial \mathcal{L}}{\partial u_{4}} = \frac{(1-\alpha)(1+\theta)}{(1-\delta) k_{4} + (1+\theta)u_{4}^{*} + i_{4}^{*}} + \lambda^{*} \left(\theta + (y_{4} - r b_{4} - c_{4}^{*}) \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{(y_{4} + u_{4}^{*})^{2}} \right) - \mu_{3}^{*} + \mu_{4}^{*} = 0.
\nonumber
\end{equation}   

Teoretycznie należałoby rozważyć szesnaście ($2^{4}$) zestawów potencjalnych rozwiązań optymalnych, gdyż każdy z czterech parametrów $\mu_{i}$ może przyjąć wartość zerową lub dodatnią. Poniżej przeanalizowano jednak tylko cztery wybrane warianty. Przede wszystkim założono, że $c^{*}_{4}>0$, co implikuje $\mu_{1} = 0$, a jednocześnie pozwala uniknąć rozpatrywania ośmiu wariantów. Trudno bowiem wyobrazić sobie samorząd, nawet o bardzo złym stanie infrastruktury, w którym nie poniesiono by żadnych wydatków bieżących. Zrezygnowano także z dwóch nierealistycznych scenariuszy: zerowych inwestycji zwykłych i unijnych dokładnie równych limitowi oraz dodatnich inwestycji zwykłych i zerowych unijnych, a także dwóch sprzecznych scenariuszy, które zakładałyby zerowe i zarazem równe limitowi inwestycje unijne (przy zerowych lub dodatnich inwestycjach zwykłych). Poniżej wyróżniono zatem cztery rodzaje rozwiązań, z których ostatnie zasługuje na szczególną uwagę. 

Zbieżność poniższych rozwiązań, uzyskanych metodą analityczną, z rozwiązaniami otrzymanymi dzięki numerycznym metodom optymalizacyjnym, zaprezentowano szczegółowo w aneksie \ref{Aneks_kody}. Wyjątek stanowi wariant trzeci, który nie został uwzględniony w aneksie (jest mało realny), lecz metoda postępowania w jego przypadku byłaby analogiczna do wariantu drugiego. 

Wariant I

Jeżeli wartość $(1-\delta)k_{4}$ jest odpowiednio wysoka, to największą użyteczność przynosi przeznaczenie całych dostępnych funduszy na wydatki bieżące. Warunek (\ref{eq_warunek}) oznacza, że krańcowa użyteczność z wydatków bieżących sfinansowanych z całego dostępnego budżetu jest wyższa niż z dowolnie małego powiększenia infrastruktury: 
\begin{IEEEeqnarray}{rCl}
\frac {\partial f}{\partial c_{4}} & > &  \frac {\partial f}{\partial k_{5}} \mbox{ dla } k_{5} = (1-\delta) k_{4} \label{eq_warunek} \\
\frac{\alpha \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}} \right)}{\phi+ \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r}} & > & \frac{1- \alpha}{(1-\delta)k_{4}}. \nonumber
\end{IEEEeqnarray}
%
\begin{IEEEeqnarray}{rCl}
u^{*}_{4} & =  &0 \nonumber \\ 
i^{*}_{4} & = & 0  \nonumber\\
c^{*}_{4} & = & \frac{\phi+ \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{y_{4} - r b_{4}}{y_{4}}}{1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4}}}. \label{eq_tylko_c4}
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
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} + \lambda^{*} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) = 0 
\label{eq_3_wariant_krotki}
\end{equation}

\begin{equation}
\frac{\partial \mathcal{L}}{\partial u_{4}} = \frac{(1-\alpha)(1+\theta)}{(1-\delta) k_{4} + (1+\theta)u_{4}^{*}} + \lambda^{*} \left(\theta + (y_{4} - r b_{4} - c_{4}^{*}) \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{(y_{4} + u_{4}^{*})^{2}} \right) = 0 
\label{eq_3_wariant_dlugi}
\end{equation}

\begin{equation}
\theta u_{4}^{*} +  c_{4}^{*} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + u_{4}^{*}} = \phi.
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
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} + \lambda^{*} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) = 0 
\\
\frac {\partial \mathcal{L}}{\partial i_{4}} =  \frac{1-\alpha}{(1-\delta) k_{4} + (1+\theta)u_{4}^{*} + i_{4}^{*}} + \lambda^{*}  = 0  
\\  
\frac {\partial \mathcal{L}}{\partial u_{4}} = \frac{(1-\alpha)(1+\theta)}{(1-\delta)k_{4} + (1+\theta) u_{4}^{*} + i_{4}^{*}} + \lambda^{*} \left(\theta + (y_{4} - r b_{4} - c_{4}^{*}) \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{(y_{4} + u_{4}^{*})^{2}} \right) = 0
\\
\theta u_{4}^{*} + i_{4}^{*} +  c_{4}^{*}\left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + u_{4}^{*}} \right) - \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + u_{4}^{*}} = \phi.
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
\frac {\partial \mathcal{L}}{\partial c_{4}} =  \frac{\alpha}{c_{4}^{*}} + \lambda^{*} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}} \right) = 0 \Rightarrow  c_{4} = -\frac{\alpha}{\lambda^{*} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}} \right)}\\
%
\frac {\partial \mathcal{L}}{\partial i_{4}} =  \frac{1-\alpha}{(1-\delta) k_{4} + (1+\theta)U_{4} + i_{4}^{*}} + \lambda^{*}  = 0  \Rightarrow  i_{4}^{*} = -\frac{1 - \alpha}{\lambda^{*}} - (1-\delta)k_{4} - (1+\theta)U_{4} \nonumber
\end{split}
\end{equation}

\begin{equation}
\begin{split}
\theta U_{4} -\frac{1 - \alpha}{\lambda^{*}} - (1-\delta)k_{4} - (1+\theta)U_{4} - \\
- \frac{\alpha}{\lambda^{*} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}} \right)} \left(1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}} \right) - \frac{y_{5}+U_{5}}{\chi+r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4}+U_{4}} = \phi \nonumber 
\\
\theta U_{4} -\frac{1 - \alpha}{\lambda^{*}} - (1-\delta)k_{4} - (1+\theta)U_{4}  -\frac{\alpha}{\lambda^{*}} - \frac{y_{5}+U_{5}}{\chi+r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + U_{4}} = \phi \nonumber 
\\
- U_{4} -\frac{1}{\lambda^{*}} - (1-\delta)k_{4} - \frac{y_{5}+U_{5}}{\chi+r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + U_{4}} = \phi\nonumber 
\\
\lambda^{*}  = -\frac{1}{\phi+ \frac{y_{5}+U_{5}}{\chi+r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + U_{4}} + u_{4}^{*} + (1-\delta)k_{4}}  \nonumber
\end{split}
\end{equation}

\begin{IEEEeqnarray}{rCl}
c_{4}^{*} & = & \frac{\alpha (\phi+ \frac{y_{5}+U_{5}}{\chi+r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + U_{4}} + (1-\delta)k_{4} + U_{4})}{1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}}} \label{eq_c4_wariant4} \\
i_{4}^{*} & = & (1 - \alpha) \left(\phi+ \frac{y_{5}+U_{5}}{\chi+r} \frac{1}{3} \frac{y_{4} - r b_{4}}{y_{4} + U_{4}} \right) - \alpha (1-\delta)k_{4} - (\theta + \alpha) U_{4}. \label{eq_i4_wariant4}
\end{IEEEeqnarray}

Optymalny poziom wydatków bieżących zależy dodatnio od: parametru $\alpha$ opisującego preferencje samorządów w odniesieniu do $c$, stałej $\phi_{0}$ oraz dochodów $y_{4}$, które wyznaczają przestrzeń fiskalną, infrastruktury $k_{4}$ (im większa, tym mniej potrzebne są inwestycje) oraz limitu $U_{4}$ (im większy, tym wystarczy realizować mniej inwestycji zwykłych). Z kolei optymalny poziom inwestycji zwykłych również zależą dodatnio od $\phi_{0}$ i $y_{4}$, a ujemnie od: $\alpha$, $k_{4}$, $U_{4}$, a także $\theta$. 

\subsection{Analityczne rozwiązanie dla trzeciego roku z napiętym warunkiem IWZ}
\label{rozdzial_szescienne}

Po znalezieniu optymalnych wartości zmiennych decyzyjnych z roku czwartego, można przejść do poszukiwania rozwiązań dla roku trzeciego. W tym celu problem decyzyjny został najpierw przeformułowany w warunkach roku trzeciego, a następnie rozwiązany za pomocą warunków KKT. Funkcja celu tego problemu ma następującą postać: 
\begin{equation}
\max_{c_{3}, u_{3}, i_{3}, z_{3}}  f(\bm{x_{3}}) = \beta^{3} \left( \alpha \ln c_{3} + (1 - \alpha) \ln k_{4} \right) + \beta^{4} \left( \alpha \ln c_{4}^{*} + (1-\alpha) \ln k_{5}^{*} \right).  \nonumber
\end{equation}
 
Zakłada się, że w czwartym roku realizowany jest wariant czwarty z podrozdziału \ref{podrozdzial_napiety_IWZ_bez_nadwyzki}, t.j. z inwestycjami unijnymi na maksymalnym poziomie. Wariant ten wydaje się być najbardziej realistyczny, gdyż z symulacji opisanych w podrozdziale \ref{podrozdz_struktura} wynika, że w zdecydowanej większości przypadków taki wariant jest optymalny. Ponadto, można domniemywać, że inwestycje w czwartym roku mogą być wyjątkowo wysokie z uwagi na ignorowanie przez decydentów przyszłego zadłużenia oraz IWZ dotyczących przyszłych lat. Wartość funkcji można dla uproszczenia podzielić przez $\beta^{3}$:

{\footnotesize
\begin{equation}
\begin{split}
f(\bm{x_{3}}) & = \alpha \ln c_{3} + (1 - \alpha) \ln ((1-\delta) k_{3} + (1+\theta) u_{3} + i_{3}) + \\
&+ \beta \alpha \ln \left( \frac{\alpha \left(  \frac{y_{5} + U_{5}}{\chi+ r} \frac{1}{3} \left(\sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - r b_{\tau}}{y_{\tau} + u_{\tau}} + \frac{y_{4} - r b_{4}}{y_{4} + U_{4}}  \right) - (1+r) b_{4} + y_{4} + (1-\delta)((1-\delta)k_{3} + (1+\theta)u_{3} + i_{3}) + U_{4} \right) }{1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}}}  \right) + 
\\
&+ \beta  (1-\alpha) \ln ( (1-\alpha) (1-\delta) ((1-\delta) k_{3} + (1+\theta) u_{3} + i_{3}) + (1+\theta) U_{4} +\\
%
&+   (1 - \alpha) \left(\frac{y_{5} + U_{5}}{\chi+ r} \frac{1}{3} \left( \sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - r b_{\tau}}{y_{\tau} + u_{\tau}}  + \frac{y_{4} - r b_{4}}{y_{4} + U_{4}} \right) - (1+r) b_{4} + y_{4}\right)  - (\theta + \alpha) U_{4})    \nonumber
\end{split}
\end{equation}
}
\begin{IEEEeqnarray}{lCl}
\mbox{p.w.} \nonumber
\\
& & \nonumber
\\
h_{13}(\bm{x_{3}}): \theta u_{3} + i_{3} + c_{3} + r b_{3} - y_{3} - z_{3} & = & 0
\label{h13}
\\
h_{23}(\bm{x_{3}}): b_{4} - b_{3} - z_{3} & = & 0
\label{h23}
\\
g_{13}(\bm{x}_{3}): -u_{3} & \leq & 0 \nonumber
\\
g_{23}(\bm{x_{3}}): u_{3} - U_{3} & \leq & 0 \nonumber
\\
g_{33}(\bm{x}_{3}): -c_{3} & \leq & 0 \nonumber
\\
g_{43}(\bm{x}_{3}): -i_{3} & \leq & 0 \nonumber
\\
g_{53}(\bm{x}_{3}): \frac{(\chi + r) b_{4}}{y_{4} + U_{4}} - \frac{1}{3} \left( \frac{y_{1} - c_{1} - r b_{1}}{y_{1} + u_{1}} + \frac{y_{2} - c_{2} - r b_{2}}{y_{2}+u_{2}} + \frac{y_{3} - c_{3} - r b_{3}}{y_{3}+u_{3}} \right)  & \leq & 0 
\label{g53}
\\
g_{63}(\bm{x}_{3}): c_{3} + r b_{3} - y_{3} & \leq & 0. \label{g63}
\end{IEEEeqnarray}

Powyższy problem można uprościć poprzez wyeliminowanie zmiennych $b_{4}$ i $z_{3}$, których wartości mogą zostać obliczone rezydualnie, po znalezieniu optymalnych wartości pozostałych zmiennych decyzyjnych $u_{3}$, $i_{3}$ i $c_{3}$: 

\begin{equation} 
%\theta u_{3} + i_{3} + c_{3} + r b_{3} - y_{3} - z_{3} = 0\\
z_{3} = \theta u_{3} + i_{3} + c_{3} + r b_{3} - y_{3}, 
\end{equation}

\begin{equation} 
b_{4} = b_{3} + \theta u_{3} + i_{3} + c_{3} + r b_{3} - y_{3}. 
\end{equation}

Dzięki powyższym przekształceniom, problem ogranicza się do trzech zmiennych decyzyjnych: $u_{3}$, $i_{3}$ i $c_{3}$. Wyeliminowane zostają też warunki ograniczające (\ref{h13}) i (\ref{h23}), które zostaną wykorzystane dopiero w celu obliczenia $b_{4}$ i $z_{3}$. Modyfikacji ulegnie także warunek (\ref{g53}):

{\footnotesize
\begin{equation}
g_{53}(\bm{x}): \frac{(\chi + r) \left(b_{3} + \theta u_{3} + i_{3} + c_{3} + r b_{3} - y_{3} \right)}{y_{4} + U_{4}} - \frac{1}{3} \left( \frac{y_{1} - c_{1} - r b_{1}}{y_{1} + u_{1}} + \frac{y_{2} - c_{2} - r b_{2}}{y_{2}+u_{2}} + \frac{y_{3} - c_{3} - r b_{3}}{y_{3}+u_{3}} \right) \leq  0. 
\nonumber
\end{equation}
}

Wydatki bieżące wynikają z napiętego warunku IWZ.

Poniżej założono także, że warunek (\ref{g53}) jest bardziej rygorystyczny od warunku (\ref{g63}). Z analizy zaprezentowanej w podrozdziale \ref{podrozdz_struktura} wynika, że warunek IWZ jest napięty prawie zawsze, a reguła zrównoważonego wyniku bieżącego - rzadko. Co więcej, JST występują przeciwko regule IWZ\footnote{,,Wprowadzony w 2014 r. indywidualny wskaźnik zadłużenia samorządów wymaga zmiany lub wręcz likwidacji, bo dusi inwestycje i nie pozwoli wykorzystać środków unijnych - przekonywali uczestnicy piątkowej debaty zorganizowanej przez Serwis Samorządowy PAP.'' (PAP, 2015)\nocite{PAP_2015} ,,Samorządowcy wskazują, że gorset, który wskaźnik nakłada na JST, jest zbyt ciasny.'' (Portal Samorządowy, 2016)\nocite{Portal_2016}}, a nie zrównoważonego wyniku bieżącego, z czego można wnioskować, że mają większe problemy z wypełnieniem IWZ. W związku z tym założono, że w rozwiązaniu optymalnym $c_{3} + r b_{3} < y_{3}$. 

Dodatkowo można założyć, że $c_{3} > 0$, ponieważ dla $c_{3} = 0$ użyteczność z krańcowego przyrostu wydatków bieżących byłaby nieskończenie wielka. Podobnie, jak w roku czwartym, dla roku trzeciego można także założyć maksymalne możliwe finansowanie inwestycji ze środków unijnych (patrz podrozdział \ref{podrozdz_dopasowywanie}). W związku z tym mnożniki KKT $\mu_{13} = 0$, $\mu_{33} = 0$, natomiast $u_{3} = U_{3}$, zatem $u_{3}$ przestaje być zmienną decyzyjną. Pozostają zatem niewiadome wartości dwóch zmiennych decyzyjnych: $c_{3}$ oraz $i_{3}$, a także jednego mnożnika KKT: $\mu_{53}$. Tym trzem niewiadomym odpowiadają trzy równania. Dwa równania stanowią warunki pierwszego rzędu, a jedno - związane jest ze spełnieniem reguły IWZ z równością. 

W następstwie poczynienia powyższych założeń utworzono funkcję Lagrange'a w postaci:  

{\scriptsize
\begin{IEEEeqnarray}{rCl}
\mathcal{L}(\bm{x}, \bm{\lambda}, \bm{\mu}) & = & f(\bm{x}) + \sum_{j=1}^{5} \mu_{j3} g_{j3}(\bm{x}) = \nonumber \\
& = &  \alpha \ln c_{3} + (1 - \alpha) \ln ( (1-\delta) k_{3} + (1 + \theta) U_{3} + i_{3}) + \nonumber \\
& + & \beta \alpha \ln (\frac{ \alpha ( \frac{y_{5} + U_{5}}{\chi+ r} \frac{1}{3} \left(\sum_{\tau=2}^{3} \frac{y_{\tau} - c_{\tau} - r b_{\tau}}{y_{\tau} + u_{\tau}} + \frac{y_{4} - r (b_{3} + \theta U_{3} + c_{3} + i_{3} + rb_{3} - y_{3})}{y_{4} + U_{4}}  \right) - (1+r)(b_{3} + \theta U_{3} + c_{3} + i_{3} + rb_{3} - y_{3}))}{1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}}}+ \nonumber \\
& + & \frac{ \alpha ( y_{4} + (1-\delta)((1-\delta)k_{3} + (1+\theta)U_{3} + i_{3}) + U_{4} ) }{1 + \frac{1}{3} \frac{y_{5} + U_{5}}{\chi + r} \frac{1}{y_{4} + U_{4}}}) + \nonumber \\
& + & \beta (1-\alpha) \ln ((1-\alpha) (1-\delta) ((1-\delta) k_{3} + (1+\theta) U_{3} + i_{3}) + (1-\alpha) U_{4} +\nonumber \\
 & + & (1 - \alpha) (\frac{y_{5} + U_{5}}{\chi+ r} \frac{1}{3} \left(  \frac{y_{2} - c_{2} - r b_{2}}{y_{2} + u_{2}} + \frac{y_{3} - c_{3} - r b_{3}}{y_{3} + U_{3}} + \frac{y_{4} - r (b_{3} + \theta U_{3} + c_{3} + i_{3} + rb_{3} - y_{3})}{y_{4} + U_{4}} \right) \nonumber \\
&-& (1+r) (b_{3} + \theta U_{3} + i_{3} + c_{3} + r b_{3} - y_{3}) + y_{4}))  + \nonumber \\
& + &  \mu_{53} \left( \frac{(\chi + r) \left(b_{3} + \theta U_{3} + i_{3} + c_{3} + r b_{3} - y_{3} \right)}{y_{4} + U_{4}} - \frac{1}{3} \left( \frac{y_{1} - c_{1} - r b_{1}}{y_{1} + u_{1}} + \frac{y_{2} - c_{2} - r b_{2}}{y_{2} + u_{2}} + \frac{y_{3} - c_{3} - r b_{3}}{y_{3} + U_{3}} \right) \right). 
\nonumber
\end{IEEEeqnarray}
}

Następnie wyprowadzono dwa warunki pierwszego rzędu, czyli obliczono pochodne funkcji Lagrange'a po $c_{3}$ i $i_{3}$ oraz przyrównano je do zera. Połączenie dwóch równań w jedno umożliwiło wyeliminowanie mnożnika $\mu_{53}$ o nieznanej wartości. Po pewnych przekształceniach wykorzystano równanie na napięty warunek IWZ. Dzięki niemu można było wyznaczyć $c_{3}$ jako funkcję $i_{3}$. Ostatecznie zatem w rachunkach pozostanie jedna zmienna decyzyjna - $i_{3}$ i jedno (skomplikowane) równanie. W celu łatwiejszego wykonania obliczeń, zastąpiono długie i złożone wyrazy (niezależne od zmiennej decyzyjnej $i_{3}$) w poszczególnych ułamkach tego równania, pojedynczymi symbolami pomocniczymi i uzyskano w ten sposób proste równanie. Dalsze przekształcenia prostego równania doprowadziły do uzyskania równania sześciennego. Istnieją trzy możliwe rozwiązania równania sześciennego w dziedzinie liczb zespolonych. Szczegółowe obliczenia zaprezentowano w części \ref{zmudne_rachunki} aneksu.

Ze wszystkich symulacji wynika, że spośród trzech wyżej wymienionych rozwiązań równania sześciennego, tylko jedno (\ref{rozw_jedyne}) należy do zbioru liczb rzeczywistych. Pozostałe należą do zbioru liczb zespolonych i nie mają interpretacji ekonomicznej. Poprawność wyniku została zweryfikowana dzięki zgodności rozwiązania numerycznego z rozwiązaniem (\ref{rozw_jedyne}) wyprowadzonym analitycznie. Numeryczny algorytm optymalizacyjny startujący z arbitralnych (dowolnych) wartości zmiennych wielokrotnie odnajdywał bowiem te same rozwiązania optymalne, co wynikające ze wzoru (\ref{rozw_jedyne}). Z drugiej strony, algorytmy numeryczne mogą znajdywać ekstrema lokalne, a nie globalne. Jeśli jednak rozwiązanie analityczne jest takie samo, to dowodzi to globalności danego ekstremum (przy założeniu danej struktury warunków ograniczających). Porównanie wyników osiąganych za pomocą metody analitycznej i numerycznej znajduje się w części B aneksu.  


\section{Dobór wartości parametrów strukturalnych modelu}
\label{rozdzial_dane}
%
Aby rozwiązać problem optymalizacyjny, przed którym stoi samorząd, należy podstawić wartości liczbowe pod parametry strukturalne: $\alpha$, $\beta$, $\upsilon$, $\theta$, r, $\chi$, $\gamma$, $\delta$ oraz wartości startowe pod zmienne: $b_{t}$, $c_{t}$ i $k_{t}$. W niniejszym rozdziale opisano sposób, w jaki określono wartości średnie parametrów oraz zdefniowano ich rozkłady, które posłużyły następnie do analizy wrażliwości wyników bazowych na zmiany parametryzacji. 

\subsection{Kalibracja parametrów i wartości startowych modelu w oparciu o dane empiryczne dla Polski}
\label{podrozdz_dopasowywanie}

\subsubsection{Limit dochodów unijnych}

Przeciętny poziom limitu dochodów pochodzących z funduszy unijnych w relacji do dochodów bieżących, $\upsilon$ i przedział, z którego limit ten może przyjmować wartości w analizie wrażliwości, zostały oszacowane na podstawie szeregu czasowego z Banku Danych Lokalnych (BDL). Szereg nosi nazwę ,,finansowanie i współfinansowanie programów i projektów unijnych: dochody razem'', odnosi się  do gmin i miast powiatowych i obejmuje lata 2010-2015. Do 2009 r. Główny Urząd Statystyczny opracowywał szereg o nazwie ,,środki gmin i miast powiatowych z budżetu UE przeznaczone na inwestycje w latach 2006-2009''. Jednak, z uwagi na różnice metodologiczne, zrezygnowano z uwzględniania tego archiwalnego szeregu. 

Tabela \ref{tabela_unijne} zawiera trzy statystyki podsumowujące każdy rok objęty obserwacją - średnią i medianę dochodów unijnych w relacji do dochodów bieżących powiększone o dwa odchylenia standardowe oraz wartość 95 percentyla. Ostatecznie przyjęto domyślną wartość parametru $\upsilon$ w wysokości $25\%$, a na potrzeby analizy wrażliwości losowano $\upsilon$ z rozkładu trójkątnego o wierzchołkach w punktach: $20\%$, $25\%$ i $35\%$. Szerokość przedziału odzwierciedla niepewność towarzyszącą definicji zmiennej oraz zróżnicowanie tej zmiennej w różnych gminach oraz latach. 

\begin{table}[!ht]
\caption{Dochody przeznaczone na inwestycje unijne w relacji do dochodów ogółem gmin i miast powiatowych}
\label{tabela_unijne}
\centering
\begin{tabular}[c]{l r r r r r r}
\hline 
\mbox{rok} & 2010 &	2011 & 2012 &	2013 &	2014	& 2015 \\
\hline 
\hline
\mbox{średnia}  $+ 2 \sigma$ & 	$28,8\%$ & 	$35,0\%$ & 	$27,7\%$ & 	$22,2\%$ & 	$23,1\%$ & 	$23,4\%$   \\
\mbox{mediana}  $+ 2 \sigma$ & 	$25,3\%$ & 	$31,5\%$ & 	$25,0\%$ & 	$19,9\%$ & 	$20,8\%$ & 	$20,7\%$   \\
\mbox{95 perc.} & $27,7\%$ & 	$31,7\%$ & 	$26,2\%$ & 	$20,6\%$ & 	$20,2\%$ & 	$23,6\%$   
\\ \hline
\end{tabular}
\\		Źródło: Bank Danych Lokalnych GUS
\end{table}

\begin{figure}[!ht]
\centering
  \caption{Rozkłady: dochodów unijnych w relacji do dochodów bieżących w gminach i miastach powiatowych w latach 2010-2015} 
\label{unijne_do_zwyklych}
		\includegraphics[width=1.00\textwidth]{C:/Dysk/Nowe/JST/Wykresy/unijne_do_zwyklych.png}
Źródło: Bank Danych Lokalnych GUS
 \end{figure}

\subsubsection{Udział finansowania własnego inwestycji unijnych}

Wartość parametru $\theta$, oznaczającego kwotę finansowania własnego na każdego złotego przypadającego z finansowania unijnego, została określona na podstawie danych przytoczonych przez Sieraka (2015), według którego ,,analiza projektów zamieszonych w bazie SIMIK wykazała w obecnej perspektywie następujący faktyczny poziom dofinansowania środkami unijnymi:
\begin{itemize}
\item dla gmin - 58,35\%;
\item dla powiatów - 64,68\%;
\item dla województw - 70,26\%;
\item średnio dla jednostek samorządu terytorialnego - 62,05\%''. 
\end{itemize}
Oznacza to, że jako wartość bazową należy przyjąć $\theta = 0,62$. Wtedy bowiem $\frac{1}{\theta + 1} \approx 0,62$ (zbieżność liczb przypadkowa), czyli dla tak określonej wartości $\theta$ poziom dofinansowania środkami unijnymi w modelu jest spójny z poziomem przeciętnym dla JST oraz zwykłą średnią dla gmin i powiatów (województwa wyłączono, gdyż nie są rozpatrywane w niniejszej pracy). Zakładając, że udział finansowania unijnego może się wahać od $50\%$ do $70\%$, to $0,43 < \theta < 1$ - krańce niniejszego przedziału oraz $0,62$ stanowią wierzchołki opisujące rozkład trójkątny, wykorzystywany w analizie wrażliwości. 

Wszystkie następnie omawiane w tym rozdziale parametry, z wyjątkiem $\delta$ i $k$, zostały skalibrowane w oparciu o dane pochodzące z wieloletnich prognoz finansowych jednostek samorządu terytorialnego. Dane te są zamieszczone na stronie Ministerstwa Finansów (www.mf.gov.pl / Działalność / Finanse publiczne / Budżety JST / Sprawozdania budżetowe / Wieloletnia prognoza finansowa JST). Najwcześniejsze pliki pochodzą z 2013 r. i zawierają informacje o wykonaniu budżetów począwszy od roku 2010. Dane za poszczególne lata były pozyskiwane z możliwie najnowszych plików, maksymalnie z pliku pochodzącego z 5 sierpnia 2016 r. Szeregi czasowe za lata 2010-2015 obejmują 2477 gmin i miast powiatowych. Nie zostały uwzględnione jedynie: gmina wiejska Zielona Góra (funkcjonująca do 2014 r.) i gmina Choszczno (brak w danych z 2013 r.), gdyż w przeciwnym razie próba byłaby niezbilansowana.  

\subsubsection{Stopa procentowa i stopa zapadalności długu}

Rozkłady empiryczne parametrów związanych z długiem: stopy procentowej $r$ i odsetka zapadającego długu $\chi$, cechowały się wyraźną asymetrią, więc w celu dopasowania rozkładu teoretycznego wzięto pod uwagę rozkłady: logarytmiczno-normalny i gamma. Rozkłady teoretyczne parametru r szacowano na podstawie rozkładu empirycznego ilorazu wydatków na obsługę długu i kwoty długu z roku poprzedniego, przy czym spośród 11890 historycznie zaobserwowanych wartości, pozostawiono 11735 pochodzących z przedziału $(0, 1)$. Za wartość domyślną $r$ do symulacji przyjęto medianę z ww. przedziału, tj. $0,039$. Z wykresu \ref{histogram_r} wynika, że oba rozkłady teoretyczne charakteryzują się podobnym stopniem dopasowania. Ostatecznie wybrano rozkład gamma ze względu na nieco niższą statystykę testu Kołmogorowa-Smirnowa (KS) (0,047) w porównaniu z rozkładem log-normalnym (0,050).  

\begin{figure}[H]
\centering
  \caption{Histogram wydatków na obsługę długu w relacji do poziomu długu z roku poprzedniego gmin i miast powiatowych - tj. stopy procentowej $r$ - w latach 2011-2015 w porównaniu z dopasowanymi rozkładami log-normalnym i gamma} 
\label{histogram_r}
		\includegraphics[width=\textwidth]{C:/Dysk/Nowe/JST/Wykresy/histogram_r.png}
Źródło: MF i obliczenia własne
 \end{figure}

Wartość p statystyki KS w obu przypadkach była bardzo bliska zeru. Przy każdym konwencjonalnym poziomie istotności należy zatem odrzucić hipotezę, że wartości empiryczne pochodzą z któregoś z powyższych rozkładów teoretycznych.\footnote{Klasyczny test KS zakłada, że rozkład teoretyczny jest z góry ustalony. W wyżej omawianym przypadku założenie to nie zostało spełnione, ponieważ parametry rozkładu teoretycznego były szacowane w oparciu o rozkład empiryczny. W takich sytuacjach wartości p są zawyżone, co sprzyja nieodrzucaniu hipotezy zerowej. Aby uzyskać nieobciążone wartości p, należy przeprowadzić tzw. ,,bootstrapowy'' test KS. Polega on na losowaniu z rozkładu teoretycznego z oszacowanymi parametrami wielu (tutaj przyjęto liczbę 1 tysiąca) prób, o liczebności równej liczebności próby empirycznej. Dla każdej próby losowej wylicza się statystykę testu KS. Następnie oblicza się, ile procent statystyk przyjęło większą wartość niż statystyka odpowiadająca próbie empirycznej. Ów procent stanowi nieobciążone oszacowanie wartości p testu KS. W przypadku parametru r, bootstrapowe wartości p dla rozkładu gamma i log-normalnego wyniosły 0.} Uznano jednak, że rozkład gamma jest wystarczająco podobny dla celów symulacji. 

Rozkłady teoretyczne parametru $\chi$ estymowano w oparciu o rozkład empiryczny spłaty rat kapitałowych kredytów i pożyczek oraz wykupu papierów wartościowych w relacji do kwoty długu z roku poprzedniego. Z 11890 obserwacji (niemal pełna populacja gmin w latach 2011-15) wyeliminowano te, które wykraczały poza przedział $(0, 1)$, po czym zostało 11520 liczb. Mediana, $0,2$, stanowi wartość bazową dla $\chi$ w symulacjach. Ponownie zdecydowano się na wybór rozkładu gamma (statystyka KS równa 0,033), a nie log-normalnego (0,053), patrz wykres \ref{histogram_chi}. Ponownie również bootstrapowe wartości p testu KS wyniosły 0.  

\begin{figure}[H]
\centering
  \caption{Histogram spłaty rat kapitałowych kredytów i pożyczek oraz wykupu papierów wartościowych w relacji do poziomu długu z roku poprzedniego gmin i miast powiatowych, $\chi$, w latach 2011-2015 w porównaniu z dopasowanymi rozkładami log-normalnym i gamma} 
\label{histogram_chi}
		\includegraphics[width=1.00\textwidth]{C:/Dysk/Nowe/JST/Wykresy/histogram_chi.png}
Źródło: MF i obliczenia własne
 \end{figure}

Dla porównania, w tabeli \ref{tabela_zadluzenie} można zaobserwować odpowiedniki parametrów r i $\chi$ we wszystkich JST ogółem - zaprezentowane tam wartości nie odbiegają silnie od oszacowanych. 

\begin{table}[!ht]
\caption{Dane dotyczące zadłużenia JST ogółem w mln zł}
\label{tabela_zadluzenie}
\centering
\begin{tabular}[c]{l r r r r r r r r r}
\hline 
rok	&	2007	&	2008	&	2009	&	2010	&	2011	&	2012	&	2013	&	2014	&	2015 \\ \hline
\hline
spłata rat	&	7349	&	6452	&	6132	&	7164	&	9615	&	10105	&	11839	&	8001	&	8292	\\
obsługa długu	&	994	&	1316	&	1400	&	1852	&	2711	&	3490	&	2820	&	2424	&	2021	\\
zadłużenie	&	25876	&	28775	&	40294	&	55094	&	65756	&	67835	&	69159	&	72110	&	71635	\\ \hline
$\chi(\mbox{rok})$	&	$28,4\%$	&	$22,4\%$	&	$15,2\%$	&	$13,0\%$	&	$14,6\%$	&	$14,9\%$	&	$17,1\%$	&	$11,1\%$	&	$11,6\%$	\\
r(rok)	&	$3,8\%$	&	$4,6\%$	&	$3,5\%$	&	$3,4\%$	&	$4,1\%$	&	$5,1\%$	&	$4,1\%$	&	$3,4\%$	&	$2,8\%$  \\ \hline
\end{tabular}
Źródło: Sprawozdanie z działalności regionalnych izb obrachunkowych i wykonania budżetu przez jednostki samorządu terytorialnego w 2015 roku (oraz sprawozdania z lat poprzednich) i obliczenia własne
\end{table}

\subsubsection{Wskaźnik zadłużenia}

Medianowy wskaźnik zadłużenia w całej populacji wyniósł 0,32 i wartość ta została przyjęta jako bazowa dla parametru $b = \frac{b_{t}}{y_{t}}$. Co ciekawe, w iloczynie 2477 gmin i miast powiatowych i 6 lat (2010-2015), zanotowano aż $3,8\%$ przypadków, dla których dług był zerowy. Uznano zatem, że rozkład teoretyczny powinien stanowić mieszankę rozkładu atomowego (0 z prawdopodobieństwem 0,038) i rozkładu ciągłego, który opisze 14280 obserwacji, dla których dług mieści się w przedziale (0, 2) dochodów bieżących. Owym rozkładem ciągłym okazał się gamma, którego odległość z testu KS była mniejsza (0,07) niż rozkładu log-normalnego (0,12). Nieco lepsze dopasowanie rozkładu gamma obrazuje także wykres \ref{histogram_b}. Niestety, wartości p wszystkich testów KS były zerowe lub bardzo zbliżone do zera.    

\begin{figure}[H]
\centering
  \caption{Histogram wskaźnika zadłużenia w relacji do dochodów bieżących gmin i miast powiatowych, $b$, w latach 2010-2015 w porównaniu z dopasowanymi rozkładami gamma i log-normalnym} 
\label{histogram_b}
		\includegraphics[width=1.00\textwidth]{C:/Dysk/Nowe/JST/Wykresy/histogram_b.png}
Źródło: MF i obliczenia własne
 \end{figure}

Powyższe rezultaty można porównać ze statystykami opartymi na corocznych ,,Sprawozdaniach z działalności regionalnych izb obrachunkowych i wykonania budżetu przez jednostki samorządu terytorialnego''. Znajdują się tam statystyki łącznego zadłużenia (zobowiązań zaliczanych do długu publicznego) gmin, miasta Warszawy oraz innych miast powiatowych za lata 2010-2015 (tabela \ref{tabela_zadluzenie_gmin_miast}). Wynika z nich, że średnie zadłużenie ogółem ($43\% - 49\%$) jest nieco wyższe niż domyślna wartość parametru ($32 \%$). Zjawisko to można tłumaczyć wpływem wyższych wskaźników zadłużenia w większych miastach na średnią ważoną i brakiem tego wpływu na medianę.   

\begin{table}[!ht]
\caption{Dane dotyczące zadłużenia gmin i miast powiatowych w mln zł}
\label{tabela_zadluzenie_gmin_miast}
\centering
\begin{tabular}[c]{l r r r r r r}
\hline 
zadłużenie JST	&	2010	&	2011	&	2012	&	2013	&	2014	&	2015	\\ \hline \hline
gminy	&	21.930	&	25.990	&	26.168	&	25.772	&	26.463	&	25.429	\\
Warszawa	&	5.291	&	5.966	&	5.696	&	5.925	&	6.038	&	5.858	\\
miasta powiaty	&	18.146	&	22.108	&	23.883	&	24.959	&	26.409	&	27.352	\\ \hline
razem	&	45.367	&	54.065	&	55.747	&	56.656	&	58.910	&	58.639	\\ 
dochody	&	105.555	&	109.885	&	115.370	&	118.806	&	124.723	&	128.392	\\ \hline
wskaźnik $b$	&	0,43	&	0,49	&	0,48	&	0,48	&	0,47	&	0,46	\\ 
\hline
\end{tabular}
 \vspace{1ex}

     \raggedright{Źródło: Sprawozdania z działalności RIO i wykonania budżetu przez JST 2011-2015 oraz Bank Danych Lokalnych GUS}
\end{table}

\subsubsection{Dynamika dochodów bieżących}

\begin{figure}
\centering
  \caption{Histogram dynamiki dochodów bieżących gmin i miast powiatowych w latach 2011-2015 w porównaniu z dopasowanymi rozkładami t-Studenta i normalnego} 
\label{histogram_gamma}
		\includegraphics[width=1.00\textwidth]{C:/Dysk/Nowe/JST/Wykresy/histogram_gamma.png}
Źródło: MF i obliczenia własne
 \end{figure}

Następnym parametrem wykorzystywanym w symulacjach jest parametr $\gamma$ - dynamika dochodów bieżących. Mediana rozkładu empirycznego wyniosła 0,044, co stanowi wartość domyślną w symulacjach.     

Na powyższym histogramie można zaobserwować, że rozkład normalny dopasowany za pomocą metody największej wiarygodności znacząco różni się od rozkładu empirycznego. Efektywność MNW została obniżona na skutek występowania obserwacji odstających. Dlatego pod uwagę wzięto także inny rozkład normalny - o tej samej wartości oczekiwanej, co pierwotny, ale o mniejszym odchyleniu standardowym (0,05 zamiast 0,07). Wprawdzie wartości p zarówno z klasycznego i bootstrapowego testu KS dla obu rozkładów normalnych wynoszą odpowiednio prawie zero i zero, ale odległość KS jest 4-krotnie mniejsza w przypadku rozkładu z ekspercko dobranym odchyleniem standardowym. Tak czy inaczej, z histogramu parametru $\gamma$ wynika, że nawet ów drugi rozkład normalny gorzej od t-Studenta opisuje ogony rozkładu empirycznego. Tę obserwację potwierdzają wyniki testu KS: wartości p dla rozkładu t-Studenta wynoszą odpowiednio 0,346 i 0,338. W związku z tym w symulacjach użyto właśnie rozkładu t-Studenta.  

\subsubsection{Wskaźnik wydatków bieżących}

\begin{figure}
\centering
  \caption{Histogram wydatków bieżących bez kosztów obsługi długu gmin i miast powiatowych w relacji do dochodów bieżących, $c$, w latach 2010-2015 w porównaniu z dopasowanymi rozkładami t-Studenta i normalnym} 
\label{histogram_c}
		\includegraphics[width=1.00\textwidth]{C:/Dysk/Nowe/JST/Wykresy/histogram_c.png}
Źródło: MF i obliczenia własne
 \end{figure}

Mimo, że wydatki bieżące stanowią zmienną decyzyjną, w celu uzyskania rozwiązania analitycznego dla roku trzeciego, potrzebne są ich wartości dla roku pierwszego i drugiego. Dlatego także ta kategoria musi być - przynajmniej w części symulacji - generowana z rozkładu. Rozkład empiryczny $c$ został otrzymany poprzez odjęcie kosztów obsługi długu od wydatków bieżących i podzielenie przez dochody bieżące ($\frac{c_{t}}{y_{t}}$). Test KS i wizualna ocena histogramu z nałożonymi wykresami rozkładów teoretycznych ponownie wskazują na rozkład t-Studenta. Wartość p klasycznego testu KS wyniosła bowiem dla tego rozkładu 0,0002 (blisko 0 dla rozkładu normalnego), a bootstrapowego - 0,001 (0 dla normalnego). Wartość medianowa wyniosła 0,90.  

\subsubsection{Wskaźnik wartości infrastruktury}

Następnym analizowanym parametrem jest $k = \frac{k_{t}}{y_{t}}$, czyli wartość brutto środków trwałych w relacji do dochodów bieżących. Podstawowy problem związany z tą kategorią stanowi niejednorodność danych udostępnianych przez Bank Danych Lokalnych. Obecnie publikowana jest wartość brutto środków trwałych w gospodarce narodowej (zawierającej także sektor prywatny), tylko na szczeblu województw, w przeliczeniu na jednego mieszkańca. Tak zdefiniowana kategoria nie odpowiada zatem zmiennej wykorzystywanej w modelu opisywanym w niniejszej pracy. Wykorzystano więc o wiele bardziej odpowiedni szereg czasowy, tj. środki trwałe jednostek i zakładów budżetowych gmin, pogrupowanych w powiaty. Jednak był on opracowywany przez BDL jedynie do 2011 r. Ze względu na to, że mianownik parametru $k$ stanowią dochody bieżące, do jego obliczenia niezbędne są dochody unijne. Niestety, szereg ,,finansowanie i współfinansowanie programów i projektów unijnych'' jest publikowany w BDL dopiero od 2010 r. Oznacza to, że dysponowano szeregami jednocześnie licznika i mianownika na szczeblu gmin wyłącznie za lata 2010-2011. 

Na podstawie różnych kategorii z Banku Danych Lokalnych można pośrednio wnioskować o wzrostowym trendzie zmiennej $k$. Po pierwsze, w latach 2005-2008 średnia wartość środków trwałych jednostek i zakładów budżetowych gmin pogrupowanych w powiaty, w relacji do dochodów ogółem (czyli zawierających dochody unijne) oscylowała wokół 1,7, a następnie szybko wzrosła do 1,97 w 2011 r. Po drugie, średnia omawianego tutaj parametru $k$ (czyli tym razem mianownik stanowiły dochody bieżące) wzrosła z 2,00 w 2010 r. do 2,15 w 2011 r. W $85 \%$ powiatów wskaźnik ten był wyższy w 2011 r. niż w roku poprzednim. Po trzecie, dynamika środków trwałych w województwach w gospodarce narodowej, w latach 2008-2014 była wyższa od dynamiki dochodów własnych JST, a także od nominalnego tempa wzrostu PKB. Przy założeniu względnie stabilnej liczby ludności, implikuje to, że relacja środków trwałych do dochodów publicznych i prywatnych także rosła. Wnioskowanie na podstawie powyższych obserwacji nie jest ścisłe (obserwacja 1. ignoruje wahania dochodów unijnych, obserwacja 2. dotyczy tylko dwóch lat, obserwacja 3. - województw, sektora prywatnego oraz centralnego podsektora publicznego). Powyższe obserwacje mogą jednak stanowić podstawę do wysunięcia hipotezy o stopniowym wzroście $k$.  Ów wzrostowy trend środków trwałych w relacji do dochodów bieżących sprawia, że rozkład parametru $k$ nie jest stały w czasie. Pomimo tego, w dalszej części pracy wykorzystano rozkład z lat 2010-2011, gdyż ma on na tyle dużą wariancję (obserwacje odstające pochodzą spoza przedziału $1,0 - 3,0$, patrz wykres \ref{histogram_k}), że powinien obejmować także większość hipotetycznego rozkładu szacowanego dla lat po 2011 r.

Do rozkładu empirycznego $k$ rozważano dopasowanie dwóch teoretycznych rozkładów: t-Studenta i normalnego. Empiryczne poziomy istotności wynikające ze zwykłego testu KS wyniosły odpowiednio: 0,614 i 0,078 i tylko nieznacznie różniły się od otrzymanych w bootstrapowym teście KS, tj. 0,606 i 0,072. Wyniki te przesądziły o wykorzystaniu rozkładu t-Studenta w analizie wrażliwości oraz przyjęciu 2,06 jako wartości bazowej dla $k$.  Dopasowanie obu wykresów do rozkładu empirycznego można zaobserwować na wykresach histogramu oraz kwantylowych. 

\begin{figure}[H]
\centering
  \caption{Histogram wartości środków trwałych w relacji do dochodów bieżących jednostek i zakładów budżetowych gmin i miast powiatowych pogrupowanych w powiaty, $k$, w latach 2010-2011 w porównaniu z dopasowanymi rozkładami t-Studenta oraz normalnym} 
\label{histogram_k}
		\includegraphics[width=1.00\textwidth]{C:/Dysk/Nowe/JST/Wykresy/histogram_k.png}
Źródło: Bank Danych Lokalnych GUS 
 \end{figure}

\subsubsection{Stopa deprecjacji infrastruktury}

Najtrudniejszym do skalibrowania rozkładem, ze względu na brak odpowiednich danych, był rozkład parametru $\delta$. W celu uzyskania rozkładu teoretycznego, poczyniono silne założenie, że wartości parametrów $i$ (wydatków majątkowych w relacji do dochodów bieżących), $k$ i $\gamma$ są równe wartościom długookresowym z modelu o nieskończonym horyzoncie czasowym opisanym w części D aneksu. Wykorzystano także wyprowadzone w aneksie równanie (\ref{eq_delta}): $ \delta = \frac{i}{k} - \gamma$.

Rozkład parametru $\delta$ uzyskano, stosując podobną procedurę, co w wypadku parametrów: $r, \chi, b,$ $\gamma, c, k$. Do tego parametru dopasowano rozkład gamma(kształt: 2.218; skala: 9.709) oraz wartość bazową równą wartości medianowej 0,19. Następnie wylosowano 100 tysięcy trójek i, k i $\gamma$ z rozkładów teoretycznych i każdej z trójek przypisano odpowiednią wartość $\delta$, zgodnie z ww. wzorem (\ref{eq_delta}). Medianą z tak uzyskanego rozkładu $\delta$ była liczba 0,059. Ponieważ parametr $\delta$ często przyjmował wartości ujemne, w celu dopasowania rozkładu gamma, który przypisuje zerowe prawdopodobieństwo liczbom ujemnym, każdą wartość $\delta$ powiększono o 0,15. Ostatecznie, rozkład $\delta$ stanowi rozkład gamma (kształt: 4,760; skala: 21,213) pomniejszony o wspomniane 0,15 - tak, aby wartości ujemne miały niezerowe prawdopodobieństwo wystąpienia.   

\subsection{Analiza struktury warunków ograniczających}
\label{podrozdz_struktura}

Po skalibrowaniu rozkładów teoretycznych dla wszystkich parametrów modelu, z wyjątkiem $\alpha$ i $\beta$, wygenerowano 7200 symulacji modelu ograniczonego do lat 3-4 w celu zbadania struktur warunków ograniczających (czyli zbadania, które warunki były luźne, a które napięte) w rozwiązaniach optymalnych. Wartości większości parametrów (tj. niebehawioralnych) losowano z rozkładów teoretycznych. W zakresie parametrów behawioralnych przyjęto na tym etapie podejście agnostyczne - losowano $\alpha$ z rozkładu jednostajnego na przedziale $[0,1; 0,9]$, zaś $\beta$ - z rozkładu jednostajnego na przedziale $[0; 1]$. W związku z tak dowolnym określeniem wartości parametrów behawioralnych, należy traktować owe symulacje jako wstępne. 

Każdy z 200 zestawów wylosowanych parametrów zreplikowano 36-krotnie (stąd łączna liczba 7200) - tak, aby uzyskać wszystkie kombinacje: $u_{3}$ równe zero, równe limitowi lub równe innej kwocie pomiędzy ww. skrajnymi liczbami, $i_{3}$ równe zero lub liczbie dodatniej oraz te same opcje dla ww. zmiennych z roku czwartego (łącznie: $3 \cdot 2 \cdot 3 \cdot 2 = 36$ kombinacji). Następnie obliczono użyteczność dla każdego z 36 scenariuszy i wybrano ten o najwyższej użyteczności. Ostatecznie uzyskano wartości optymalne zmiennych decyzyjnych, optymalną strukturę warunków ograniczających i użyteczność dla 200 zestawów wylosowanych parametrów. Do tych wyników odnoszą się wszystkie zaprezentowane w tym podrozdziale statystyki opisowe.

\begin{table}[!ht]
\caption{Częstość występowania różnych optymalnych wartości zmiennych decyzyjnych}
\label{tabela_optymalne_zmienne}
\centering
\begin{tabular}[c]{l l | l l | l l}
\hline 
zmienna & częstość & zmienna & częstość & zmienna & częstość  \\
\hline 
\hline
$i_{3}^{*} = 0$ & $32,5\%$ & $i_{3}^{*} > 0$ & $67,5\%$ & & \\ 
$u_{3}^{*} = 0$ & $32,5\%$ & $0 < u_{3}^{*} < U_{3}$ & $19,5\%$ & $u_{3}^{*} = U_{3}$ & $48\%$ \\
$i_{4}^{*} = 0$ & $51,5\%$ & $i_{4}^{*} > 0$ & $48,5\%$ & & \\
$u_{4}^{*} = 0$ & $5\%$ & $0 < u_{4}^{*} < U_{4}$ & $23,5\%$ & $u_{4}^{*} = U_{4}$ & $71,5\%$ \\
\hline
\end{tabular}
\\		Źródło: obliczenia własne
\end{table}

Z tabeli \ref{tabela_optymalne_zmienne} wynika, że inwestycje unijne przeważnie powinny być realizowane na maksymalnym poziomie, natomiast inwestycje zwykłe - niespodziewanie często powinny być zerowe. Należy jednak mieć na uwadze, że wyniki te były podyktowane specyficznymi wartościami $\alpha$ bliskimi 0,9 i/lub $\beta$ bliskimi 0, co wpływało na niską użyteczność z infrastruktury i w efekcie - zaniżanie inwestycji.

\begin{table}[!ht]
\caption{Zestawy najpopularniejszych wartości optymalnych zmiennych decyzyjnych}
\label{tabela_zestawy_optymalnych_zmiennych}
\centering
\begin{tabular}[c]{l | l l l l | l}
\hline 
poz. & $u_{3}^{*}$ & $i_{3}^{*}$  & $u_{4}^{*}$  & $i_{4}^{*}$ & częstość \\
\hline 
\hline
1 &$=0$ & $>0$ & $=U_{4}$ & $>0$ & $19,5\%$ \\ 
2 &$=U_{3}$ & $>0$ & $=U_{4}$ & $>0$ & $17,5\%$ \\ 
3 &$=U_{3}$ & $>0$ & $=U_{4}$ & $=0$ & $10,5\%$ \\ 
4 &$=U_{3}$ & $=0$ & $>0$ & $=0$ & $7\%$ \\
5 &$> 0$ & $=0$ & $=U_{4}$ & $=0$ & $6,5\%$ \\ 
6 &$=U_{3}$ & $=0$ & $=U_{4}$ & $=0$ & $5\%$ \\ 
7 &$=0$ & $>0$ & $=U_{4}$ & $=0$ & $4\%$ \\ 
8 &$=0$ & $=0$ & $>0$ & $=0$ & $3\%$ \\
9 &$>0$ & $=0$ & $>0$ & $=0$ & $3\%$ \\ 
10 &$=U_{3}$ & $>0$ & $>0$ & $=0$ & $3\%$ \\
\hline
\end{tabular}
\\		Źródło: obliczenia własne
\end{table}

Tabela \ref{tabela_zestawy_optymalnych_zmiennych} prezentuje 10 najpopularniejszych kombinacji optymalnych wartości zmiennych decyzyjnych. Łącznie odpowiadają one za $79\%$ przypadków. Warto wspomnieć, że drugi najczęściej występujący wariant (z niewielką stratą do najczęściej występującego) został rozwiązany w sposób analityczny w niniejszej pracy.

Warunek IWZ jest prawie zawsze napięty. W $3,5\%$ przypadków dla roku trzeciego, luz w warunku wynosi między 0,07 a 0,0001. Wtedy $\alpha$ przyjmuje wysokie wartości, około 0,8. Mowa tu jednak o implikacji, a nie równoważności, gdyż często dla wysokich $\alpha$ warunek IWZ także bywa napięty. W pozostałych przypadkach luz nie przekracza 0,0001, co jest w praktyce nieodróżnialne od zera. Warunek IWZ dla roku czwartego jest napięty zawsze. Z kolei warunek na zrównoważony wynik bieżący (ZWB) jest napięty rzadko. W trzecim roku zdarza się to w $9\%$ przypadków, wówczas $\alpha$ jest wysoka, wydatki bieżące - wysokie, a inwestycje, zwłaszcza zwykłe - niskie. ZWB w czwartym roku napięty jest w $6\%$ przypadków, wtedy $\alpha$ jest bardzo wysoka, a inwestycje przeważnie zerowe. Podsumowując, założenie o napiętości IWZ i braku napiętości ZWB ma potwierdzenie w wynikach wstępnych symulacji.

W $19\%$ przypadków odchylenie między wartościami użyteczności z rozwiązania numerycznego i analitycznego nie przekraczało 0,0001. Podobnie często, w $17\%$ przypadków, optymalna wartość żadnej z sześciu zmiennych decyzyjnych (oprócz podanych w tabelach - dodatkowo $c^{*}_{3}$ i $c^{*}_{4}$) nie odchyla się od optymalnej wartości uzyskanej w rozwiązaniu analitycznym o więcej niż 0,02 (jednostkę stanowią dochody bieżące samorządu z danego roku). W $14\%$ przypadków odchylenie to nie przekracza 0,01. Odnotowane odstępstwa są przede wszystkim konsekwencją niespełnienia ograniczeń przyjętych jakodane w rozwiązaniu analitycznym dla dużego odsetka wariantów parametryzacji. 

Jeżeli jednak założyć strukturę warunków ograniczających odpowiadającą strukturze rozwiązań analitycznych, czyli inwestycje unijne w trzecim i czwartym roku na maksymalnym poziomie oraz dodatnie inwestycje zwykłe w obu tych latach ($17,5\%$ przypadków), to zbieżność rozwiązań uzyskanych metodami numeryczną i analityczną staje się dużo większa. W $86\%$ odchylenie między użytecznościami z obu metod nie przekracza 0,0001. W $75\%$ optymalna wartość żadnej z 6 zmiennych nie odchyla się o bardziej od optymalnej wartości uzyskanej w rozwiązaniu analitycznym niż 0,02, natomiast w $64\%$ - o bardziej niż 0,01. Generalnie oznacza to dużą zbieżność wyników osiąganych za pomocą obu metod. Odnotowane odstępstwa są konsekwencją niedoskonałości meta-algorytmu numerycznego, który nie odnajduje ekstremów globalnych, a jedynie ekstrema lokalne. Warto w tym miejscu podkreślić, że na meta-algorytm składają się niedoskonałe metody optymalizacji, których wyniki mogą być poprawne bądź nie w zależności od startowych wartości zmiennych (patrz części A i C.2 aneksu). Ta obserwacja pokazuje ponadto, jaka korzyść płynie z uzyskania rozwiązania analitycznego.  

\subsection{Kalibracja wartości parametrów behawioralnych $\alpha$ i $\beta$}
\label{podrozdz_kalibrowanie}

Parametry: $\alpha$, opisujący preferencje względem wydatków bieżących w porównaniu z infrastrukturą, i $\beta$, dyskontujący przyszłą użyteczność, różnią się od pozostałych parametrów modelu. Są one bowiem parametrami behawioralnymi, nieobserwowalnymi i dlatego nie można odczytać ich rozkładów empirycznych z danych. Teoretycznie każdy wójt, burmistrz czy prezydent mógłby ustalić dowolne wartości $\alpha \in (0, 1)$ oraz $\beta > 0$, a następnie uzyskać z modelu optymalne wartości wydatków bieżących i inwestycyjnych. W podrozdziale \ref{rozdzial_model_dwuletni} ograniczono się jednak do takich $\alpha$ i $\beta$, zgodnie z którymi struktura warunków ograniczających w optimum jest taka jak założona w rozdziale \ref{rozwiazanie_modelu}, czyli przede wszystkim: w 3 i 4 roku wykorzystuje się całą dopuszczalną kwotę środków unijnych, napięta jest reguła IWZ oraz realizuje się niezerowe wydatki bieżące i inwestycyjne. Aby ograniczyć możliwość, że rozwiązanie uzyskane metodą KKT stanowi tylko ekstremum lokalne, a nie globalne, model rozwiązywano także za pomocą metod numerycznych. Jeżeli rozwiązania uzyskane za pomocą tych metod różniły się, tj. użyteczność mogła być wyższa przy innej strukturze warunków ograniczających niż założona, wówczas ($\alpha, \beta$) prowadzące do takich rozwiązań były wyłączane ze zbioru rozważanych wartości.   

Zadanie optymalizacyjne rozwiązano dla wszystkich możliwych par $(\alpha, \beta) \in \mathcal{A} \times \mathcal{B}$, gdzie $\alpha \in$ $\{0,1; 0,2,$ $ ..., 0,9\}$, zaś $\beta \in \{0,1; 0,2; ...; 1,0\}$. Pozostałym parametrom przypisano natomiast wartości bazowe podane w poprzednim podrozdziale. Z iloczynu kartezjańskiego $\mathcal{A} \times \mathcal{B}$ wyodrębniono następnie podzbiór, który prowadził do rozwiązań optymalnych o strukturze ograniczeń zgodnej z założeniami (punkty 2, 3, 6 i 7 spośród wymienionych poniżej). Z owego podzbioru, jedynie wartości parametrów podane w punktach 6 i 7 prowadziły do rozwiązań optymalnych zbliżonych do empirycznych, tj. istotnie wyższych wydatków bieżących niż inwestycyjnych. Ostatecznie zatem zawężono poszukiwania do obszaru zaprezentowanego w tabelach \ref{optymalne_3} i \ref{optymalne_4} i wybrano domyślną wartość $\alpha$ równą 0,4 oraz $\beta$ w wysokości 0,1. Wartości te wykorzystywano w symulacjach o z góry ustalonych wartościach $\alpha$ i $\beta$.   

\begin{enumerate}[label={\arabic*)}]
\item $\alpha = 0,1, \beta \neq 0,2 \Rightarrow u_{3}^{*}=0 \Rightarrow \mbox{zła struktura rozwiązania}$ 
\item $\alpha = 0,1, \beta = 0,2 \Rightarrow c_{3}^{*}, i_{3}^{*}, c_{4}^{*}, i_{4}^{*} > 0; u_{3}^{*} = U_{3}; u_{4}^{*} = U_{4} \\ \Rightarrow\mbox{dobra struktura rozwiązania, nierealistyczne wyniki}$
\item $\alpha = 0,2, \beta \in \{0,1; 0,3; 0,4; 0,5; 0,6\} \Rightarrow c_{3}^{*}, i_{3}^{*}, c_{4}^{*}, i_{4}^{*} > 0; u_{3}^{*} = U_{3}; u_{4}^{*} = U_{4} \\ \Rightarrow \mbox{dobra struktura rozwiązania, nierealistyczne wyniki}$
\item $\alpha = 0,2, \beta = 0,2 \Rightarrow u_{3}^{*} < U_{3} \Rightarrow \mbox{zła struktura rozwiązania}$ 
\item $\alpha = 0,2, \beta \in [0,7, 1,0] \Rightarrow u_{3}^{*}=0 \Rightarrow \mbox{zła struktura rozwiązania}$ 
\item $\alpha = 0,3 \Rightarrow c_{3}^{*}, i_{3}^{*}, c_{4}^{*}, i_{4}^{*} > 0; u_{3}^{*} = U_{3}; u_{4}^{*} = U_{4} \Rightarrow   \mbox{dobra struktura rozwiązania}$
\item $\alpha = 0,4, \beta \in [0,1, 0,4] \Rightarrow c_{3}^{*}, i_{3}^{*}, c_{4}^{*}, i_{4}^{*} > 0; u_{3}^{*} = U_{3}^{*}; u_{4}^{*} = u_{4}^{*}; c_{3}^{*} > i_{3}^{*}; c_{4}^{*} > i_{4}^{*} \\ \Rightarrow   \mbox{dobra struktura rozwiązania, wyniki zbliżone do wartości występujących w danych}$
\item $\alpha = 0,4, \beta \in [0,5, 1] \Rightarrow i_{4}^{*} < 0 \\ \Rightarrow \mbox{jeden warunek niespełnony, brak interpretacji ekonomicznej}$
\item $\alpha \geq 0,5 \Rightarrow i_{4}^{*} < 0 \Rightarrow \mbox{jeden warunek niespełnony, brak interpretacji ekonomicznej}$
\end{enumerate}

\begin{figure}[H]
	\centering
  \caption{Rozwiązania optymalne dla trzeciego roku w zależności od $\alpha$ i $\beta$} 
\label{optymalne_3}
		\includegraphics[trim=0cm 6cm 0cm 1cm, clip=true, width=1.35\textwidth]{C:/Dysk/Nowe/JST/Wykresy/c3_i3.pdf}
		Źródło: obliczenia własne
\end{figure}

\begin{figure}[H]
	\centering
  \caption{Rozwiązania optymalne dla czwartego roku w zależności od $\alpha$ i $\beta$} 
\label{optymalne_4}
		\includegraphics[trim=0cm 6cm 0cm 1cm, clip=true, width=1.35\textwidth]{C:/Dysk/Nowe/JST/Wykresy/c4_i4.pdf}
		Źródło: obliczenia własne
\end{figure}

Wartości $\alpha$ i $\beta$ były ostatnimi potrzebnymi do numerycznego rozwiązania modelu. Wszystkie wartości domyślne oraz rozkłady służące do analizy wrażliwości zostały zawarte w tabeli \ref{tabela_parametry}. 

\begin{table}[!ht]
\caption{Rozkłady wartości parametrów modelu}
\label{tabela_parametry}
\centering
\begin{tabular}[c]{l r l l}
\hline 
\mbox{parametr} & domyśl. & rozkład do analizy wrażliwości & źródło \\
\hline 
\hline
$\alpha$ & 0.4 & brak & własne \\
$\beta$ & 0.1 & brak & własne \\
$\upsilon$ & $0.25$ & trójkątny (0,2; 0,25; 0,35) & BDL \\
$\theta $ & 0,62 & trójkątny (0,43; 0,62; 1) & Sierak\nocite{Sierak_2015} \\
r  & 0,039 & gamma (kształt: 6,417 ; skala: 152,5) & MF \\
$\chi$ & 0,2  & gamma (kształt: 2,325 ; skala: 9,608) & MF \\
$\gamma$ & 0,044 & t-Studenta (położenie: 0,044; skala: 0,039; st. sw.: 2,919) & MF \\
$\delta$ & 0,059 & -0,15 + gamma(kształt: 4,760; skala: 21,213) & $\delta = \frac{i}{k} - \gamma$ \\
\hline
\end{tabular}
\end{table}

\begin{table}[!ht]
\caption{Rozkłady wartości startowych zmiennych modelu}
\label{tabela_startowe}
\centering
\begin{tabular}[c]{l r l l}
\hline 
\mbox{zmienna} & domyślnie & rozkład do analizy wrażliwości & źródło \\
\hline 
\hline
$b$ & 0,32 & 0 ($3,8\%$) lub gamma (kształt: 2,405; skala: 6,984)  & MF \\
$c$ & 0,90 & t-Studenta (położenie: 0,90; skala: 0,045; st. sw.: 4,52) & MF \\
$k$ & 2,06 & t-Studenta (położenie: 2,06; skala: 0,36; st. sw.: 6,58) & BDL \\
\hline
\end{tabular}
\end{table}

Podsumowując rozdział siódmy, należy stwierdzić, że niektóre omawiane w nim wyniki nie były zgodne z oczekiwaniami. Niespodziewanie często, w symulacjach z losowymi wartościami parametru preferencji $\alpha$ i czynnika dyskontowego $\beta$, optymalny poziom inwestycji okazywał się zerowy. Ponieważ rozkładów nieobserwowalnych parametrów $\alpha$ i $\beta$ nie da się oszacować na podstawie danych empirycznych, można założyć takie ich wartości, które implikują optymalne wartości zmiennych decyzyjnych zbliżone do empirycznych. Co więcej, można przyjąć wartości, które implikują strukturę warunków ograniczających zgodną z założoną w rozwiązaniu analitycznym. Tak skalibrowana wartość $\beta$ okazała się jednak na tyle niska, że oznacza niespotykaną w literaturze krótkowzroczność modelowanego decydenta. 

Ostatecznie, w następnym rozdziale, wykorzystywano skalibrowane rozkłady parametrów strukturalnych i wartości startowych, zaprezentowane w tabelach \ref{tabela_parametry} i \ref{tabela_startowe}. Z kolei w odniesieniu do parametrów behawioralnych, postępowano na dwa sposoby - losowano je z rozkładów jednostajnych (,,agnostycznych'') albo przyjmowano stałe wartości uzyskane w podrozdziale \ref{podrozdz_kalibrowanie}. 
 
\section{Rozwiązanie numeryczne modelu oraz analiza wrażliwości optymalnych poziomów wydatków bieżących i inwestycyjnych}
\label{analiza_wrazliwosci}

Niniejszy rozdział przedstawia rozwiązanie numeryczne pełnej, czterookresowej wersji modelu oraz opisuje wpływ wartości parametrów strukturalnych i behawioralnych modelu na optymalne wartości zmiennych decyzyjnych: wydatków bieżących $\frac{c_{t}^{*}}{y_{t}}$ oraz inwestycyjnych zwykłych $\frac{i_{t}^{*}}{y_{t}}$. Koncepcja obu podrozdziałów jest taka sama: polega na wylosowaniu wielu zestawów wartości parametrów i znalezieniu dla każdego zestawu optymalnych wartości zmiennych decyzyjnych. Następnie oszacowano liniowe metamodele\footnote{Przez metamodel rozumie się tu model, którego parametry estymowane są w oparciu o dane wygenerowane w procesie symulacji, a nie rzeczywiste dane empiryczne. Nie służy on więc weryfikacji zależności obserwowanych w danych, lecz wychwyceniu cech symulowanego procesu, trudnych do bezpośredniego dostrzeżenia ze względu na jego dużą złożoność.} ekonometryczne, w których zmienną objaśnianą była jedna ze zmiennych decyzyjnych, z konkretnego roku, a objaśniającymi - wartości parametrów. 

Należy zastrzec, że przyjęto liniową specyfikację modeli, mimo że w rzeczywistości efekty mogą być nieliniowe (a czasem wręcz niemonotoniczne), co widać w rozwiązaniach analitycznych modelu. Oszacowanie modeli liniowych pozwala znaleźć efekty przeciętne w całej przestrzeni parametrów (nie tylko lokalne wokół bazowych wartości parametrów), ale nie wychwyci nieliniowości. Przeanalizowanie pełnego wpływu ewentualnych zmian wartości wybranych parametrów w przypadku konkretnej gminy jest możliwe w oparciu o wykorzystywane tutaj narzędzia, ale wykracza poza zakres niniejszej rozprawy.

Warto też zaznaczyć, iż zrezygnowano z podawania statystycznej istotności zmiennych objaśniających w modelach. Wynika to z faktu, że w praktyce możliwe jest wygenerowanie tak dużej liczby obserwacji, aby uczynić każdy parametr istotnym (wszak każdy parametr znajdował się w rozwiązaniu analitycznym). Dlatego w niniejszym rozdziale uwagę skupiono na sile i kierunku wpływu poszczególnych parametrów. W rezultacie, pod uwagę brano oszacowania standaryzowanych współczynników regresji (równych zwykłym współczynnikom pomnożonym przez odchylenie standardowe danej zmiennej objaśniającej), a nie zwykłych współczynników. Łatwiej bowiem porównywać wpływ różnych parametrów, zakładając ich wzrost o jedno odchylenie standardowe, a nie o jednostkę.

Pierwszy podrozdział ogranicza się do modelu dwóch ostatnich lat kadencji władz samorządowych oraz do założonych wartości parametrów behawioralnych i struktury warunków ograniczających w rozwiązaniu optymalnym. Dzięki temu rozwiązanie metodą numeryczną mogło zostać sprawdzone za pomocą metody analitycznej. Drugi podrozdział nie zawiera powyższych ograniczeń. Dotyczy on pełnego modelu czteroletniego, nie zakłada ani określonych wartości parametrów behawioralnych, ani struktury warunków ograniczających. Jednak w tym przypadku rozwiązanie można uzyskać jedynie metodą numeryczną. W celach porównawczych, przeprowadzono też symulacje w oparciu o model czteroletni o z góry ustalonych wartościach parametrów behawioralnych.    

\subsection{Wyniki analizy wrażliwości dla scenariusza rozwiązanego analitycznie z ustalonymi: strukturą warunków ograniczających oraz $\alpha$ i $\beta$}
\label{rozdzial_model_dwuletni}

W celu wykonania analizy wrażliwości dla modelu dwuletniego, wylosowano 2247 zestawy wartości parametrów z rozkładów teoretycznych zaprezentowanych w tabeli \ref{tabela_startowe}, przyjmując wartość parametru preferencji $\alpha = 0,4$ i czynnika dyskontowego $\beta = 0,1$. Następnie pozostawiono dokładnie tysiąc zestawów, w których optymalne wartości zmiennych decyzyjnych były takie same według metody analitycznej (warunków KKT) oraz metody numerycznej (meta-algorytmu optymalizacyjnego). W kolejnym kroku, klasyczną metodą najmniejszych kwadratów, oszacowano liniowe modele ekonometryczne w oparciu o tysiąc zestawów liczb. W modelach tych zmiennymi objaśniającymi były wartości parametrów strukturalnych, a objaśnianymi - optymalne wartości kolejno: $\frac{c_{3}^{*}}{y_{3}}, \frac{c_{4}^{*}}{y_{4}}, \frac{i_{3}^{*}}{y_{3}} \mbox{i} \frac{i_{4}^{*}}{y_{4}}$, czyli optymalnych wydatki bieżących albo optymalnych inwestycji zwykłych w relacji do dochodów bieżących w roku odpowiednio trzecim i czwartym.  

Oszacowania standaryzowanych współczynników stojących przy zmiennych objaśniających ze wszystkich modeli zostały zebrane w tabeli \ref{optymalne_2_lata}.

\begin{table}[!ht]
  \caption{Oszacowania standaryzowanych współczynników modeli opisujących optymalne wartości zmiennych decyzyjnych dla modelu dwuletniego z określoną strukturą warunków ograniczających oraz $\alpha$ i $\beta$} 
\label{optymalne_2_lata}
\centering
\begin{tabular}[c]{r r r r r r r r r}
\hline 
	&	$\frac{c_{3}^{*}}{y_{3}}$	&	$\frac{c_{4}^{*}}{y_{4}}$	&	$\frac{i_{3}^{*}}{y_{3}}$	&	$\frac{i_{4}^{*}}{y_{4}}$	\\
\hline 
\hline
$\gamma$	&	-0,004	&	-0,015	&	0,044	&	0,099	\\
$\delta$	&	-0,026	&	-0,057	&	0,057	&	0,153	\\
$\theta$	&	0,000	&	-0,001	&	-0,034	&	-0,034	\\
$r$	&	0,004	&	0,000	&	-0,091	&	-0,034	\\
$\chi$	&	0,045	&	0,039	&	-0,385	&	-0,152	\\
$b$	&	-0,033	&	-0,016	&	-0,185	&	0,052	\\
$c$	&	-0,022	&	0,002	&	-0,131	&	0,094	\\
$k$	&	0,048	&	0,026	&	-0,102	&	-0,063	\\
$\upsilon$	&	0,004	&	0,006	&	-0,030	&	-0,039	\\
\hline
$R^2$	&	0,887	&	0,771	&	0,912	&	0,817	\\
\end{tabular}
\\		Źródło: obliczenia własne
\end{table}


Z wyżej przedstawionych modeli płynie wiele istotnych wniosków dla polityki gmin i miast powiatowych. 

Wydatki bieżące w relacji do dochodów bieżących w pierwszym i drugim roku (c = $\frac{c_{1}}{y_{1}}$ = $\frac{c_{2}}{y_{2}}$) wpływają: umiarkowanie negatywnie na $\frac{c_{3}^{*}}{y_{3}}$, nieznacznie na $\frac{c_{4}^{*}}{y_{4}}$ , silnie negatywnie na $\frac{i_{3}^{*}}{y_{3}}$ oraz silnie pozytywnie na $\frac{i_{4}^{*}}{y_{4}}$. Najprawdopodobniej wyższe wydatki bieżące w przeszłości, poprzez małą przestrzeń w IWZ, ograniczają wydatki ogółem w 3 roku, ale oszczędności te mogą zostać, przynajmniej częściowo, wykorzystane na wzrost wydatków w 4 roku. 

Dynamika dochodów bieżących  ($\gamma$) wpływa ujemnie na wydatki bieżące $\frac{c_{3}^{*}}{y_{3}}$ oraz $\frac{c_{4}^{*}}{y_{4}}$, natomiast dodatnio - na wydatki inwestycyjne $\frac{i_{3}^{*}}{y_{3}}$ oraz $\frac{i_{4}^{*}}{y_{4}}$.  Być może działa tu zasada zapobiegliwości. Ponadprzeciętnie wysoki wzrost dochodów należy przeznaczyć na inwestycje, które zwiększają użyteczność także w przyszłości, natomiast wydatki bieżące działają antycyklicznie, jako automatyczny stabilizator - w dobrych czasach rosną wolniej niż baza dochodowa, a w złych - szybciej. Należy podkreślić, że zmienne objaśniane stanowią kategorie w relacji do dochodów bieżących, zatem szybsza dynamika dochodów w roku t, $\gamma_{t}$ powinna pośrednio zwiększyć optymalne wartości liczników ($c_{t}^{*}$, $i_{t}^{*}$) oraz bezpośrednio - mianowników ($y_{t}$), więc końcowy efekt nie był oczywisty ex ante.

Zgodnie z rozwiązaniami analitycznymi (\ref{eq_c4_wariant4}) i (\ref{eq_i4_wariant4}), wpływ stopy procentowej $r$ i poziomu zadłużenia $b$ na obie kategorie wydatków optymalnych $c_{4}^{*}$ i $i_{4}^{*}$ jest ujemny. Wnioski z analizy wrażliwości są jednak nieco inne. Wpływ stopy procentowej $r$ na $\frac{c_{4}^{*}}{y_{4}}$ jest neutralny, a długu $b$ na $\frac{i_{4}^{*}}{y_{4}}$ - dodatni. Tę ostatnią, nieoczekiwaną zależność można wytłumaczyć tym, że początkowy stan zadłużenia $b$ ujemnie oddziałuje na $c_{3}^{*}$ oraz $i_{3}^{*}$, co obniża poziom długu $b_{4}$ i stwarza przestrzeń na inwestycje w ostatnim roku $i_{4}^{*}$. Poza tym, w rozwiązaniu analitycznym uwzględniony jest wpływ $\frac{b_{4}}{y_{4} + U_{4}} \approx \frac{b_{4}}{y_{4}} \approx b$, zaś w metamodelach opisywanych w niniejszym podrozdziale - $\frac{b_{3}}{y_{3}}$.

Jako zastanawiający należy ocenić również wpływ stopy zapadalności długu $\chi$. Jest on dodatni w odniesieniu do wydatków bieżących $\frac{c_{t}^{*}}{y_{t}}$, a ujemny - do inwestycji $\frac{i_{t}^{*}}{y_{t}}$. Biorąc pod uwagę IWZ, wydawać by się mogło, że wyższa stopa zapadalności $\chi$ powoduje wyższe koszty obsługi długu (lewa strona nierówności (\ref{regula243})), więc wymaga większej przestrzeni fiskalnej (prawa strona), którą mogą zapewnić niższe wydatki bieżące. Widocznie mechanizm wpływu parametru $\chi$ jest jednak bardziej złożony. Wyższa stopa zapadalności długu implikuje niższe wydatki ogółem (potwierdzają to wielokrotnie większe co do modułu oszacowania w modelach opisujących inwestycje niż wydatki bieżące), aby maksymalnie zredukować deficyt, a w konsekwencji dług i dzięki temu ograniczyć w przyszłych latach wydatki na spłatę długu, które z perspektywy funkcji użyteczności są czystą stratą. Krótko mówiąc, wysoka stopa zapadalności długu premiuje niskie zadłużenie. Efekt ten zadziałałby niezależnie od obowiązywania IWZ. Z kolei niski poziom długu wpływa na zmniejszenie wielkości lewej strony nierówności w regule fiskalnej, co pozwala na odpowiedni wzrost wydatków bieżących do momentu spełnienia reguły.

Poziom infrastruktury $k = \frac{k_{3}}{y_{3}}$ i limit dochodów unijnych $\upsilon$ oddziałują dodatnio na wydatki bieżące $\frac{c^{*}_{t}}{y_{t}}$ oraz ujemnie na inwestycyjne $\frac{i^{*}_{t}}{y_{t}}$. Ta konkluzja wysnuta z rozwiązania analitycznego została potwierdzona przez oszacowania metamodeli. Zgadza się ona także z intuicją - potrzeba mniej inwestycji zwykłych $i$, jeżeli infrastruktura $k$ jest już rozwinięta lub jeżeli można uzyskać większe finansowanie ze środków unijnych $\upsilon$. Zgodny z oczekiwaniami jest również wpływ wysokości stopy deprecjacji infrastruktury $\delta$. Im jest ona większa, tym należy więcej inwestować, aby odbudować poziom infrastruktury $k_{t}$, a przez to - trzeba realizować niższe wydatki bieżące $c^{*}_{t}$. Z kolei konieczność ponoszenia większego wkładu własnego w finansowanie inwestycji unijnych $\theta$ implikuje niższe kwoty inwestycji $\frac{i_{t}^{*}}{y_{t}}$, ale nie ma wpływu na kwoty wydatków bieżących $\frac{c_{t}^{*}}{y_{t}}$. 

Ostatnią wartą rozważenia kwestią jest siła wpływu poszczególnych parametrów na wartości zmiennych decyzyjnych, tzn. na który parametr szczególną uwagę powinni zwrócić decydenci. 

Na inwestycje zwykłe $\frac{i^{*}_{t}}{y_{t}}$, szczególnie w 3 roku, najsilniej oddziałuje stopa zapadalności długu $\chi$. W 3 roku dużą rolę odgrywają także startowe wartości zadłużenia $b$ i wydatków bieżących $c$, które mają, zgodnie z intuicją, mniejsze znaczenie w kontekście roku 4. W ostatnim roku znaczenia nabiera natomiast stopa deprecjacji infrastruktury $\delta$. 

W odniesieniu do wydatków bieżących $\frac{c^{*}_{t}}{y_{t}}$, miary przeciętnego wpływu są co do modułu niższe i mniej zróżnicowane. Największe znaczenie ma również stopa zapadalności długu $\chi$. Podobnie jak w przypadku inwestycji, w trzecim (lecz nie czwartym) roku istotną rolę odgrywały wartości startowe parametrów: $b$, $c$ i $k$. Natomiast w czwartym roku stosunkowo silny wpływ wywarła stopa deprecjacji infrastruktury $\delta$.

Parametry związane z inwestycjami unijnymi ($\theta$ i $\upsilon$) mają bardzo małe znaczenie w przypadku wszystkich czterech zmiennych objaśnianych. Nie dziwi to, gdyż w założonej strukturze warunków ograniczających, inwestycje unijne opiewają na maksymalną kwotę $u^{*}_{3} = U_{3}$ i $u^{*}_{4} = U_{4}$. 

\subsection{Rozwiązanie numeryczne pełnego modelu oraz wyniki analizy wrażliwości}
\label{rozdzial_model_czteroletni}

Z analizy przeprowadzonej w podrozdziale \ref{podrozdz_struktura} wynikało, że struktura warunków ograniczających przyjęta w rozwiązaniu analitycznym i założona w podrozdziale \ref{rozdzial_model_dwuletni} niekoniecznie musi być optymalna - będzie tak tylko przy pewnych, dość szczególnych założeniach co do wartości  parametru preferencji $\alpha$ i czynnika dyskontowego $\beta$. Dlatego w niniejszej części pracy zrezygnowano z narzucania struktury warunków ograniczających oraz przyjmowania określonych wartości $\alpha$ i $\beta$. Takie podejście ma swoją cenę - niemożność zweryfikowania wyników metody numerycznej za pomocą metody analitycznej.  

Przy założeniu domyślnych wartości parametrów, tj. zamieszczonych w tabeli \ref{tabela_parametry} i \ref{tabela_startowe}, optymalne wartości zmiennych decyzyjnych są następujące:   

\begin{table}[!ht]
\caption{Optymalne wartości zmiennych decyzyjnych w modelu czteroletnim, dla domyślnych wartości parametrów}
\label{optymalne_4_lata_centralne}
\centering
\begin{tabular}[c]{l l l l}
\hline 
\mbox{rok} & $c^{*}$ &  $u^{*}$ &  $i^{*}$ \\
\hline 
\hline
1 & 0,71 & 0,25 & 0,46 \\
2 & 0,80 & 0,26 & 0,26 \\  
3 & 0,71 & 0,25 & 0,50 \\ 
4 & 0,83 & 0,16 & 0,14 \\
\hline
\end{tabular}
\\ Źródło: obliczenia własne
\end{table}

W trzech pierwszych latach inwestycje unijne kształtują się na poziomie bliskim limitowi $u^{*}_{t} \approx U_{t}$. Można również zauważyć, że na przemian występują lata z wyższymi i niższymi inwestycjami zwykłymi $i^{*}_{t}$. W ostatnim roku inwestycje są najniższe - dlatego, że mają wpływ na użyteczność czerpaną z infrastruktury $k_{t}$ tylko w jednym roku, a nie rozkładają się na odpowiednio dłuższy okres, jak w przypadku inwestycji z lat poprzednich.   

W celu oszacowania wpływu parametrów strukturalnych i behawioralnych na wartości optymalne zmiennych decyzyjnych w latach 1-4, wylosowano tysiąc zestawów parametrów strukturalnych i, w przeciwieństwie do poprzedniego podrozdziału, także behawioralnych: $\alpha$ z rozkładu jednostajnego na odcinku $[0,1; 0,9]$ i $\beta$ z rozkładu jednostajnego na odcinku $[0,1]$. Następnie oszacowano klasyczną metodą najmniejszych kwadratów osiem metamodeli ekonometrycznych - dla zmiennych objaśnianych: $\frac{c^{*}_{t}}{y_{t}}$ oraz $\frac{i^{*}_{t}}{y_{t}}$, gdzie $t \in \{1,2,3,4\}$. Oszacowania współczynników stojących przy zmiennych objaśniających ze wszystkich modeli zostały zebrane w tabeli \ref{optymalne_4_lata}.

\begin{table}[!ht]
  \caption{Oszacowania standaryzowanych współczynników metamodeli opisujących optymalne wartości zmiennych decyzyjnych dla modelu czteroletniego z endogeniczną strukturą warunków ograniczających oraz losowymi $\alpha$ i $\beta$} 
\label{optymalne_4_lata}
\centering
\begin{tabular}[c]{r r r r r r r r r}
\hline 
	&	$\frac{c_{1}^{*}}{y_{1}}$	&	$\frac{c_{2}^{*}}{y_{2}}$	&	$\frac{c_{3}^{*}}{y_{3}}$ &	$\frac{c_{4}^{*}}{y_{4}}$	&	$\frac{i_{1}^{*}}{y_{1}}$	&	$\frac{i_{2}^{*}}{y_{2}}$	 &	$\frac{i_{3}^{*}}{y_{3}}$	&	$\frac{i_{4}^{*}}{y_{4}}$	\\
\hline 
\hline
$\alpha$	&	0,230	&	0,154	&	0,115	&	0,137	&	-0,648	&	-0,336	&	-0,165	&	-0,026	\\
$\beta$	&	-0,036	&	-0,028	&	0,011	&	0,055	&	0,008	&	0,073	&	0,014	&	-0,047	\\
$\gamma$	&	-0,008	&	0,000	&	0,010	&	0,001	&	0,108	&	0,081	&	0,044	&	0,020	\\
$\delta$	&	-0,005	&	-0,015	&	-0,017	&	-0,020	&	0,050	&	0,037	&	0,038	&	0,030	\\
$\theta$	&	-0,003	&	-0,007	&	-0,009	&	-0,007	&	-0,005	&	-0,010	&	0,004	&	-0,008	\\
$r$	&	-0,005	&	-0,013	&	-0,014	&	-0,010	&	-0,094	&	-0,023	&	-0,005	&	-0,009	\\
$\chi$	&	-0,014	&	-0,006	&	-0,006	&	-0,001	&	-0,397	&	-0,104	&	-0,053	&	-0,036	\\
$b$	&	-0,060	&	-0,014	&	-0,003	&	-0,027	&	-0,079	&	0,009	&	0,013	&	-0,007	\\
$c$	&	-0,026	&	0,022	&	0,021	&	-0,009	&	-0,077	&	0,029	&	0,016	&	-0,002	\\
$k$	&	0,032	&	0,017	&	0,012	&	0,023	&	-0,086	&	-0,031	&	-0,014	&	-0,011	\\
$\upsilon$	&	0,003	&	0,006	&	0,006	&	0,000	&	-0,021	&	-0,035	&	-0,029	&	-0,009	\\
\hline
$R^2$	&	0,873	&	0,713	&	0,508	&	0,540	&	0,605	&	0,540	&	0,222	&	0,067	\\
\end{tabular}
\\		Źródło: obliczenia własne
\end{table}

Z modeli objaśniających optymalne wartości wydatków bieżących w kolejnych czterech latach  kadencji władz samorządowych $\frac{c^{*}_{t}}{y_{t}}$ można wyciągnąć następujące wnioski. 

Zmienne objaśniane zależą dodatnio od parametru preferencji $\alpha$, co było do przewidzenia na podstawie samej definicji tego parametru. Parametr ten cechuje ponadto największa siła wpływu. Równie oczywista jest zaobserwowana dodatnia zależność między startowym poziomem infrastruktury $k$ a poziomem wydatków bieżących $\frac{c^{*}_{t}}{y_{t}}$ - bogata infrastruktura nie wymaga wysokich nakładów inwestycyjnych. Odwrotnie przedstawia się sytuacja w związku ze stopą deprecjacji infrastruktury $\delta$ - im wyższa, tym potrzeba większych inwestycji (odtworzeniowych), co ogranicza fundusze na  $\frac{c^{*}_{t}}{y_{t}}$.        

Zgodnie z oczekiwaniami, wyższy dług $b$ i stopa procentowa $r$ prowadziły przeważnie do zmniejszenia $\frac{c^{*}_{t}}{y_{t}}$. To samo dotyczyło stopy zapadalności długu $\chi$, co stanowi odwrotną obserwację niż w poprzednim podrozdziale. Warto jednak zaznaczyć, że wpływ $\chi$ był zasadniczo słaby. 

Czynnik dyskontowy $\beta$ z kolei wpływa na $\frac{c_{t}^{*}}{y_{t}}$ ujemnie w dwóch pierwszych latach, następnie zależność ta staje się dodatnia. Jest to najbardziej wpływowy parametr, po parametrze preferencji $\alpha$, w odniesieniu do wydatków bieżących $\frac{c^{*}_{t}}{y_{t}}$. Im większa wielkość $\beta$, tym decydenta cechuje większa dalekowzroczność. W pierwszym i drugim roku, dalekowzroczny decydent może wpłynąć na użyteczność z przyszłych lat jedynie za pomocą inwestycji $i^{*}_{1}$ i $i^{*}_{2}$, a więc zwiększa je, co wypiera aktualne wydatki bieżące $c^{*}_{1}$ i $c^{*}_{2}$. W ostatnim roku $\beta$ nie różnicuje już stosunku do $c^{*}_{4}$ i $i^{*}_{4}$, gdyż inwestycje $i^{*}_{4}$ mogą wpłynąć na poziom infrastruktury $k_{5}$, czyli tylko z jednego roku wchodzącego w zakres funkcji użyteczności. Pod tym względem inwestycje z 4 roku $i^{*}_{4}$ przypominają wydatki bieżące $c^{*}_{t}$ z każdego roku. 

Oszacowanie stojące przy parametrze $c$ także zmienia znak - z ujemnego na dodatni, a w czwartym roku wynosi prawie zero. Najpierw wyższe wydatki bieżące $c$ poniesione w latach poprzedzających modelowaną kadencję zacieśniają przestrzeń fiskalną, czyli wymuszają oszczędności, które w późniejszych latach można wykorzystać na zwiększone wydatki bieżące $\frac{c^{*}_{t}}{y_{t}}$. Podobna obserwacja została zresztą poczyniona także w poprzednim podrozdziale.

W odniesieniu do dynamiki dochodów bieżących $\gamma$, wpływ tej zmiennej na $\frac{c^{*}_{t}}{y_{t}}$ okazał się być bardzo niewielki, co trochę osłabia obserwacje poczynione w poprzednim podrozdziale (acykliczność zamiast antycykliczności w odniesieniu do $\frac{c_{t}}{y_{t}}$)

Ponownie parametry dotyczące inwestycji unijnych: $\theta$ i $\upsilon$ uzyskały oszacowania niewiele odbiegające od zera. Oszacowania parametrów w przypadku $\upsilon$ były zawsze ujemne, co można wytłumaczyć efektem substytucji - większe wydatki na inwestycje unijne $u^{*}_{t}$ są rekompensowane spadkiem kwot przeznaczanych na inwestycje zwykłe $i^{*}_{t}$.

Część obserwacji poczynionych w oparciu o oszacowania modeli opisujących inwestycje zwykłe $\frac{i^{*}_{t}}{y_{t}}$ pokrywa się z obserwacjami odnoszącymi się do modeli wydatków bieżących $\frac{c^{*}_{t}}{y_{t}}$. Parametr preferencji $\alpha$ wpływa ujemnie na wielkość zmiennych objaśnianych, gdyż bezpośrednio premiuje wydatki bieżące $\frac{c^{*}_{t}}{y_{t}}$, zwiększane kosztem inwestycji $\frac{i^{*}_{t}}{y_{t}}$. 

Wysokość stopy deprecjacji $\delta$ wywiera dodatni wpływ na poziom inwestycji $\frac{i^{*}_{t}}{y_{t}}$, ponieważ szybsza deprecjacja wymaga zwiększonych nakładów inwestycyjnych na odtworzenie infrastruktury. Zgodnie z oczekiwaniami, wystąpiło również  ujemne oddziaływanie stopy procentowej $r$ i stopy zapadalności długu $\chi$ na inwestycje $\frac{i^{*}_{t}}{y_{t}}$. Zwiększone wydatki związane z długiem powodują bowiem zawężenie przestrzeni finansowej. Warto zauważyć, że $\chi$ jest drugim w kolejności najbardziej wpływowym parametrem w odniesieniu do inwestycji $\frac{i^{*}_{t}}{y_{t}}$.    

Trzy parametry: $k$, $b$ i $c$ dotyczą wartości startowych modelu. W związku z tym ich wpływ na zmienne objaśniane maleje w czasie. Początkowy poziom infrastruktury $k$ wpływa ujemnie na inwestycje $\frac{i^{*}_{t}}{y_{t}}$. Wartość zadłużenia $b$ również wpływa na spadek inwestycji, ale już jedynie w pierwszym i czwartym roku. Wpływ wydatków bieżących w okresie przed modelowaną kadencją $c$ kształtuje się podobnie jak $b$.

Zależności związane z dwoma parametrami: $\gamma$ i $\beta$ zasługują na szczególną uwagę. Po pierwsze, oszacowania przy dynamice dochodów bieżących $\gamma$ okazały się dość wysokie (trzeci najbardziej wpływowy parametr w modelach opisujących inwestycje) i dodatnie. Oznacza to, że poziom inwestycji $i^{*}_{t}$ powinien rosnąć szybciej niż dochody bieżące $y_{t}$, co potwierdza zaobserwowany już efekt zapobiegliwości. Z kolei $\beta$ wpływa na dodatnio, z wyjątkiem ostatniego roku, na wysokość inwestycji, co zostało już objaśnione wcześniej w niniejszym podrozdziale na przykładzie dalekowzrocznego decydenta.  

Poniżej zaprezentowano oszacowania z modeli opartych na tysiącu zestawów wylosowanych parametrów strukturalnych, przy założeniu, że $\alpha = 0,4$, a $\beta = 0,1$ (co, należy podkreślić, jest bardzo niską wartością w porównaniu do występujących zwykle w literaturze). Z jednej strony, określenie stałych wartości parametrów behawioralnych mogło przyczynić się do zawężenia analizy do bardziej realistycznych, wiarygodnych scenariuszy. Z drugiej strony, taka analiza mogła pominąć część istotnych przypadków. Liczby z tabeli \ref{optymalne_4_lata_stale_alfa_beta} mogą zatem posłużyć do oceny wrażliwości wyników analizy na poczynione założenia odnośnie do $\alpha$ i $\beta$. 

\begin{table}[!ht]
  \caption{Oszacowania standaryzowanych współczynników modeli opisujących optymalne wartości zmiennych decyzyjnych dla modelu czteroletniego z endogeniczną strukturą warunków ograniczających oraz ustalonymi $\alpha = 0,4$ i $\beta = 0,1$} 
\label{optymalne_4_lata_stale_alfa_beta}
\centering
\begin{tabular}[c]{r r r r r r r r r}
\hline 
	&	$\frac{c_{1}^{*}}{y_{1}}$	&	$\frac{c_{2}^{*}}{y_{2}}$	&	$\frac{c_{3}^{*}}{y_{3}}$ &	$\frac{c_{4}^{*}}{y_{4}}$	&	$\frac{i_{1}^{*}}{y_{1}}$	&	$\frac{i_{2}^{*}}{y_{2}}$	 &	$\frac{i_{3}^{*}}{y_{3}}$	&	$\frac{i_{4}^{*}}{y_{4}}$	\\
\hline 
\hline
$\gamma$	&	-0,009	&	0,012	&	0,036	&	0,017	&	0,025	&	0,032	&	-0,017	&	-0,026	\\
$\delta$	&	-0,023	&	-0,013	&	-0,007	&	-0,023	&	0,011	&	0,039	&	0,012	&	0,010	\\
$\theta$	&	-0,007	&	-0,012	&	-0,010	&	-0,017	&	0,015	&	-0,004	&	-0,004	&	0,013	\\
$r$	&	0,002	&	-0,008	&	-0,007	&	-0,011	&	-0,016	&	-0,020	&	-0,014	&	-0,014	\\
$\chi$	&	0,028	&	-0,010	&	-0,004	&	0,012	&	-0,009	&	-0,060	&	-0,035	&	-0,008	\\
$b$	&	-0,064	&	-0,012	&	0,005	&	-0,022	&	-0,018	&	0,030	&	-0,010	&	-0,017	\\
$c$	&	-0,031	&	0,029	&	0,033	&	-0,016	&	-0,012	&	0,023	&	0,007	&	-0,011	\\
$k$	&	0,045	&	0,004	&	0,010	&	0,028	&	-0,005	&	-0,010	&	-0,009	&	-0,004	\\
$\upsilon$	&	0,001	&	-0,011	&	-0,021	&	-0,008	&	-0,010	&	0,001	&	0,016	&	-0,004	\\
\hline
$R^2$	&	0,731	&	0,178	&	0,188	&	0,161	&	0,019	&	0,136	&	0,037	&	0,022	\\
\end{tabular}
\\		Źródło: obliczenia własne
\end{table}

Z tabeli \ref{optymalne_4_lata_stale_alfa_beta} wynika, iż zawężenie się do domyślnych wartości parametrów behawioralnych może skutkować innymi wnioskami formułowanymi w odniesieniu do parametrów strukturalnych. Warto zauważyć, że w dwóch ostatnich latach inwestycje $i^{*}_{t}$ nie rosną szybciej niż dochody bieżące $y_{t}$. Można domniemywać, że bardzo niski poziom $\beta$ spowodował, że szczególnie na koniec kadencji inwestycje $i^{*}_{t}$ nie odgrywają istotnego znaczenia. Szybsza dynamika dochodów $\gamma$ zwiększa zatem wydatki bieżące $c^{*}_{t}$. Osłabł także dodatni wpływ poziomu infrastruktury $k$ na $\frac{c^{*}_{t}}{y_{t}}$. Ponownie niewielką rolę odgrywają parametry związane z finansowaniem inwestycji unijnych $\theta$ i $\upsilon$. 

Siły wpływu poszczególnych parametrów w modelach pozbawionych $\alpha$ i $\beta$ wśród regresorów charakteryzują się mniejszym zróżnicowaniem. W przypadku wydatków bieżących $\frac{c^{*}_{t}}{y_{t}}$ nieznacznie największy wpływ wywierają wartości startowe: $b$, $c$ i $k$. W odniesieniu zaś do inwestycji zwykłych $\frac{i^{*}_{t}}{y_{t}}$, zróżnicowanie jest nieco większe, ale niższe w porównaniu z modelem o zmiennych wartościach parametrów behawioralnych. Najbardziej wpływowe parametry to $\chi$ i $\gamma$.  

\newpage
\section*{Podsumowanie części II}
\addcontentsline{toc}{section}{\protect\numberline{}Podsumowanie części II}%

W pracy postawiono hipotezę, że optymalna polityka finansowa gmin i miast powiatowych uwzględnia wiele czynników:

\begin{enumerate}[label={(\alph*)}]
\item Dodatni wpływ na optymalny poziom wydatków bieżących w relacji do dochodów bieżących samorządów ma wzrost: wskaźnika wartości infrastruktury oraz limitu dofinansowania unijnego.
\item Ujemny wpływ na optymalny poziom wydatków bieżących w relacji do dochodów bieżących samorządów ma wzrost: czynnika dyskontowego, współczynnika deprecjacji infrastruktury, udziału dochodów własnych w inwestycjach unijnych, stopy procentowej, stopy zapadalności długu, wskaźnika zadłużenia oraz wskaźnika wydatków bieżących z lat poprzednich.
\item Dodatni wpływ na optymalny poziom zwykłych (tj. nie współfinansowanych ze środków UE) wydatków inwestycyjnych w relacji do dochodów bieżących samorządów ma wzrost: czynnika dyskontowego, współczynnika deprecjacji infrastruktury oraz udziału dochodów własnych w inwestycjach unijnych. 
\item Ujemny wpływ na optymalny poziom zwykłych wydatków inwestycyjnych w relacji do dochodów bieżących samorządów ma wzrost: stopy procentowej, stopy zapadalności długu, wskaźnika zadłużenia, wskaźnika wydatków bieżących z lat poprzednich, wskaźnika wartości infrastruktury oraz limitu dofinansowania unijnego.
\end{enumerate}

Potwierdzono hipotezę (2a) w zakresie tego, że większa wartość infrastruktury powoduje zwiększenie wydatków bieżących (gdyż inwestycje stają się wówczas mniej potrzebne). Nie można było natomiast potwierdzić takiej hipotezy w odniesieniu do maksymalnego limitu środków unijnych.  

Odnośnie do hipotezy (2b) pokazano, iż wzrost: stopy deprecjacji infrastruktury, zadłużenia w relacji do dochodów bieżących i, w mniejszym stopniu, udziału współfinansowania inwestycji unijnych wpływa negatywnie na poziom wydatków bieżących w relacji do dochodów bieżących. Oddziaływanie stopy procentowej zaś okazało się być, w zależności od modelu, ujemne lub neutralne. Zwiększenie czynnika dyskontowego wywiera różny efekt na wydatki bieżące w zależności od okresu. Na początku, im bardziej dalekowzroczny decydent, tym bardziej troszczy się o użyteczność z przyszłości, a może ją poprawić w bieżącym momencie tylko za pomocą inwestycji, które ograniczają przestrzeń na wydatki bieżące. W ostatnim roku modelowanego okresu, użyteczność z infrastruktury wliczana jest do użyteczności tylko raz, podobnie jak wydatki bieżące, dlatego inwestycje przestają być tak istotne. 

Nie można uogólnić obserwacji na temat oddziaływania wzrostu stopy zapadalności długu, gdyż w zależności od przyjętych założeń i roku kadencji, wpływ tego parametru może być dodatni, ujemny lub zerowy. To samo dotyczy dynamiki dochodów bieżących (przy czym tutaj trudno było postawić hipotezę na temat wpływu tej zmiennej z uwagi na jednoczesne oddziaływanie jej na licznik i mianownik zmiennej objaśnianej). Zasadniczo ten ostatni parametr nie ma silnego wpływu na optymalne wartości zmiennych decyzyjnych. Nieoczekiwany efekt zaobserwowano w odniesieniu do wskaźnika wydatków bieżących poniesionych w okresie poprzedzającym modelowany zakres czasowy kadencji. Wyższe przeszłe wydatki ograniczają przestrzeń na wydatki na początku badanego okresu, ale w kolejnym roku następuje efekt kompensacji, tj. uprzednie oszczędności umożliwiają większe wydatki w porównaniu ze scenariuszem bez oszczędności. 

Stwierdzono także, że zgodnie z hipotezą (2c), dodatni wpływ na inwestycje zwykłe w relacji do dochodów bieżących ma wzrost stopy deprecjacji infrastruktury oraz czynnika dyskontowego (z wyjątkiem ostatniego roku). Wpływ parametru współfinansowania inwestycji unijnych jest zaś w przybliżeniu neutralny. 

Potwierdzona została też hipoteza (2d) w zakresie ujemnego wpływu na inwestycje zwykłe w relacji do dochodów bieżących wzrostu: stopy procentowej, stopy zapadalności zadłużenia i wskaźnika infrastruktury. Pozytywnie zweryfikowano też hipotezę o ujemnym wpływie wzrostu limitu dochodów unijnych. 

W przypadku wskaźnika zadłużenia można ponownie doszukać się efektu kompensacji. Ujemny wpływ występuje na początku okresu (w trzecim roku w modelu dwuletnim oraz w pierwszym roku w modelu czteroletnim), następnie wpływ staje się dodatni, a w przypadku modelu czteroletniego - na koniec okresu - ponownie ujemny, ale bliski neutralnemu. Efekt kompensacji, podobny jak opisany powyżej, dla wskaźnika wydatków bieżących z lat przeszłych jako zmiennej objaśniającej i optymalnych inwestycji zwykłych w roli zmiennej objaśnianej okazał się silniejszy niż w przypadku optymalnych wydatków bieżących w roli zmiennej objaśnianej. Po początkowym ujemnym oddziaływaniu na wielkość inwestycji zwykłych, następowało silne odbicie. 

Wyższa dynamika dochodów bieżących wpływa generalnie na wzrost wskaźnika inwestycji, przy czym zależność ta jest silniejsza na początku okresu, co wynika z tzw. efektu zapobiegliwości. Optymalny poziom wydatków inwestycyjnych w relacji do dochodów bieżących w czasie co do zasady maleje, co jest konsekwencją przyjętej funkcji użyteczności, która premiuje inwestycje poczynione we wcześniejszym okresie, gdyż poprawiona w ten sposób infrastruktura jest uwzględniana wielokrotnie w użyteczności.  


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
