## Ograniczenia budżetowe
  
JST podlegają w każdym roku ograniczeniu budżetowemu (wg terminologii Kornaia - twardemu). Założono, że suma wydatków i rozchodów równa się sumie dochodów i przychodów z zaciągniętych pożyczek i wyemitowanych obligacji. Jednak, zgodnie z art. 217 ust. 2 pkt 5-6 ustawy o finansach publicznych, deficyt budżetu JST może być dodatkowo sfinansowany przychodami pochodzącymi m.in. z: nadwyżki budżetu JST z lat ubiegłych lub wolnych środków jako nadwyżki środków pieniężnych na rachunku bieżącym budżetu JST, wynikających z rozliczeń wyemitowanych papierów wartościowych, kredytów i pożyczek z lat ubiegłych. 

Z dwóch powodów abstrahowano od nadwyżki zgromadzonej w latach ubiegłych. Po pierwsze, zakładając, że oprocentowanie długu jest większe niż depozytów, samorządom korzystniej byłoby zredukować wolne środki do zera oraz spłacić w tej samej kwocie dług. Po drugie, w rzeczywistości nadwyżka z lat ubiegłych stanowi średnio tylko 7\% przychodów gmin i miast powiatowych. W 57\% są to kredyty, pożyczki i wyemitowane papiery wartościowe, a w 33\% - wolne środki wynikające z rozliczeń kredytów, pożyczek i wyemitowanych papierów wartościowych z lat ubiegłych. Ta ostatnia kategoria występuje, jeżeli samorządy zaciągną kredyt w jednym roku (np. w grudniu) w celu wydania tych środków w roku następnym (np. w styczniu). W modelu zaciąganie pożyczek zachodzi dokładnie raz na rok, a popyt zgłaszany przez samorządy jest całkowicie zaspokajany po z góry określonej stopie procentowej. Dlatego modelowym decydentom nie opłacałoby się zadłużanie się z rocznym wyprzedzeniem. Wszystkie rozliczenia kredytów, pożyczek i papierów wartościowych odbywają się w roku bieżącym. W rezultacie, 90\% przychodów JST jest odwzorowane w modelu bez nadwyżki z lat ubiegłych.

Założono dwa źródła dochodów: bieżące i kapitałowe unijne (dalej, w skrócie: unijne). Przyjęto, że dochody bieżące, $y_{t}$ (dotacje i subwencje z budżetu państwa i środków unijnych, wpływy z podatków - PIT i CIT - opłaty i kary oraz dochody z majątku\footnote{Nie zdecydowano się na wprowadzenie równania objaśniającego dochody z majątku za pomocą infrastruktury $k_{t}$ ze względu na możliwe nadmierne skomplikowanie modelu.}) rosną w stałym tempie \gamma. W modelu szereg $y_{t} = y_{0} (1 + \gamma)^{t}$ jest więc góry ustalony, dlatego równanie na y nie zostało podane jako jedno z ograniczeń w dalszej części rozdziału. W rzeczywistości dostęp do środków unijnych jest ograniczony, zatem w modelu zakłada się, że dochody unijne w relacji do dochodów bieżących $\frac{u_{t}}{y_{t}}$   nie mogą przekroczyć limitu przeznaczonego dla danego JST - \upsilon:

$0 \leq \frac{u_{t}}{y_{t}} \leq \frac{U_{t}}{y_{t}} = \upsilon$ 

Źródłem przychodu netto $z_{t}$ jest zaciągnięta pożyczka albo kredyt w roku t lub też, zgodnie z inną interpretacją, wpływ z wyemitowanych obligacji. Zmienna $z_{t}$ może przyjmować wartości ujemne, co należy interpretować jako spłatę netto części zadłużenia. Początkowy stan zadłużenia $b_0$ 
 powiększony o skumulowane pożyczki z kolejnych lat stanowi zadłużenie w roku t: 

$$b_{t+1} = b_{0} + \sum_{\tau=0}^{t} z_{\tau}$$

Wydatki mogą być przeznaczone na cztery cele. Z góry ustalone są odsetki od zadłużenia w wysokości iloczynu stałej stopy procentowej i długu $r b_{t}$. Decyzji podlega kwota przeznaczona na wydatki bieżące $c_{t}$ (wszystkie oprócz odsetek i wydatków majątkowych), a także inwestycje zwykłe $i_{t}$ oraz unijne $(1+\theta)u_{t}$. Współczynnik $\theta > 0$ reprezentuje część finansowania inwestycji ze środków własnych JST (tzw. współfinansowanie). 

Wydatki mogą być finansowane z dochodów bieżących, unijnych lub zaciągniętych pożyczek. Podsumowując, ograniczenie budżetowe JST przedstawia się następująco: 

$(1+\theta) u_{t} + i_{t} + c_{t} + r b_{t} = u_{t} + y_{t} + z_{t}$. 

Inwestycje powodują przyrost infrastruktury $k_{t}$, która ulega corocznej deprecjacji o frakcję \delta. Parametr ten obejmuje także wpływ inflacji, tj. opisuje zmianę nominalnej wartości infrastruktury wynikającą m.in. ze zmian cen. Warto zauważyć, że w pierwszej kolejności optymalną decyzją wydaje się realizowanie inwestycji unijnych, gdyż są one częściowo finansowane ze środków zewnętrznych (W większości przypadków rzeczywiście tak powinno być, ale nie jest to pewne ze względu na występowanie dochodów unijnych w mianownikach indywidualnego wskaźnika zadłużenia (IWZ, szczegóły kilka akapitów niżej). Nie można wykluczyć, że w pewnych wyjątkowych sytuacjach korzystne mogłoby być zmniejszenie w danym roku (inne rozłożenie w czasie) inwestycji unijnych, a w konsekwencji: zmniejszenie dochodów unijnych, zmniejszenie mianownika IWZ i wreszcie - zwiększenie przestrzeni fiskalnej.). Nie jest jednak wykluczone, że optymalny łączny poziom inwestycji powinien przekroczyć $(1+\theta)u_{t}$ i wówczas jedynym wyjściem jest realizowanie również bardziej kosztownych inwestycji zwykłych:

$k_{t} = k_{t-1}(1-\delta)+(1+\theta)u_{t-1} + i_{t-1}$. 

Zmiennymi decyzyjnymi w tym modelu są szeregi czasowe: wydatków bieżących, inwestycji unijnych i zwykłych, a także kwoty zaciągniętego długu. Wszystkie te zmienne, oprócz ostatniej, mogą przyjmować tylko wartości nieujemne:  

$c_{t} \geq 0$. 

$u_{t} \geq 0$. 

$i_{t} \geq 0$. 
