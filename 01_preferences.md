# Wprowadzenie

Celem bieżącej części rozprawy jest sformułowanie optymalnej polityki finansowej samorządów w zakresie wydatków bieżących oraz inwestycyjnych gmin i miast powiatowych w ciągu czteroletniej kadencji władz samorządowych. Zgodnie z ustaleniami zawartymi w powiązanej literaturze, przyjęto założenie, że optymalna polityka powinna uwzględniać regułę zrównoważonego wyniku bieżącego i indywidualny wskaźnik zadłużenia. Powinna też zależeć od: parametrów określających preferencje samorządów, stopy procentowej, zapadalności długu, tempa wzrostu dochodów bieżących, stopy amortyzacji, początkowych wskaźników zadłużenia, wydatków bieżących oraz poziomu infrastruktury, a także limitu funduszy przeznaczonych na inwestycje unijne i udziału środków unijnych w finansowaniu inwestycji.    

Przedstawiony w niniejszej pracy doktorskiej model opisuje problem, przed którym stoją decydenci jednostki samorządu terytorialnego (wójt, burmistrz gminy lub prezydent miasta) w okresie, w którym istotną rolę w finansowaniu inwestycji odgrywają środki unijne (Model można jednak uogólnić na okres, w którym środki unijne przestaną być istotne.). Jednostka samorządu terytorialnego jest w niniejszej pracy rozumiana jako gmina lub miasto na prawach powiatu, w tym Warszawa. 

Województwa i powiaty ziemskie nie są więc brane pod uwagę. Wynika to z ,,silnego zróżnicowania potencjału finansowego pomiędzy rodzajami JST'' (Sierak i in., 2013). Przykładowo, udział wydatków majątkowych w wydatkach ogółem jest wyraźnie mniejszy w powiatach ziemskich niż w gminach, natomiast odwrotna sytuacja ma miejsce w województwach. W niniejszej pracy wykorzystywane są dane empiryczne dotyczące gmin i miast na prawach powiatu, dlatego zdecydowano się zawęzić obszar badań do najniższego szczebla jednostek samorządowych. Należy zarazem podkreślić, że samorządy wojewódzkie i powiatowe ziemskie mają stosunkowo małe znaczenie - łącznie ich wydatki ogółem w każdym roku z okresu 2005-2014 były około cztery razy mniejsze niż łącznie wydatki gmin i miast powiatowych. W 2015 r. łączne wydatki samorządów województw i powiatów wyniosły 40,6 mld zł, natomiast gmin, Warszawy i miast na prawach powiatów wyniosły 155,8 mld zł (RIO, 2015). 

# Preferencje

Problem decyzyjny samorządowców można zinterpretować następująco. Po wygranych wyborach, które odbywają się na koniec roku zerowego, nowe władze samorządowe mają przed sobą cztery lata kadencji. Decydenci owi zastanawiają się, ile środków przeznaczyć na wydatki bieżące i inwestycje w roku pierwszym, drugim, trzecim i czwartym. Władze samorządowe dokonują tam decyzji po zakończeniu drugiego roku - planują wydatki jedynie na rok trzeci i czwarty.} W pierwszym dniu roku piątego odbywają się kolejne wybory, podczas których mieszkańcy danej gminy lub miasta oceniają dotychczasowe władze pod kątem strumienia wydatków bieżących z czterech ostatnich lat i zasobu infrastruktury na moment bieżący, a także w trzech zeszłych latach.

Mieszkańcy obszaru zarządzanego przez daną JST czerpią użyteczność z wydatków bieżących w roku $t$ oznaczonych jako $c_{t}$ (tj. przeznaczonych na bieżącą działalność, świadczenia społeczne, zasiłki i stypendia oraz inne podmioty, m.in. uczelnie, szkoły, przedszkola, instytucje kultury, zakłady opieki zdrowotnej, Izby Rolnicze i inne JST; w tej kategorii nie uwzględnia się natomiast odsetek od kredytów i pożyczek, gdyż zostały one zdefiniowane oddzielnie) oraz z zasobu szeroko rozumianej infrastruktury z roku <img src="https://render.githubusercontent.com/render/math?math=t%2B1">, tj. <img src="https://render.githubusercontent.com/render/math?math=k_{t%2B1}">  (m.in. dróg, szkół, przedszkoli, domów kultury, obiektów sportowych, oczyszczalni ścieków, pojazdów transportu zbiorowego). Maksymalizowana jest suma zdyskontowanych rocznych strumieni użyteczności z <img src="https://render.githubusercontent.com/render/math?math=c_{t}"> i <img src="https://render.githubusercontent.com/render/math?math=k_{t%2B1}"> wyrażonych za pomocą kombinacji liniowej logarytmów tych zmiennych. 

Zakłada się tutaj tożsamość preferencji (z wyjątkiem horyzontu czasowego) władz i mieszkańców. Politycy starają się maksymalizować dokładnie znaną, logarytmiczną funkcję użyteczności mieszkańców po to, aby wygrać następne wybory. 

Optymalizacji podlega więc następująca funkcja:
<img src="https://render.githubusercontent.com/render/math?math=\max_{ \{c_{t}\}, \{u_{t}\}, \{i_{t}\}, \{z_{t}\}} \sum_{t=1}^{4} \beta^{t} \left( \alpha \ln c_{t} %2B \left(1 - \alpha \right) \ln k_{t%2B1} \right)">

Założenie logarytmicznej, separowalnej względem <img src="https://render.githubusercontent.com/render/math?math=c_{t}"> i <img src="https://render.githubusercontent.com/render/math?math=k_{t%2B1}"> funkcji użyteczności jest zgodne z postulatem dodatniej, malejącej krańcowej użyteczności czerpanej z wydatków bieżących i infrastruktury. Spośród wielu funkcji o dodatniej pierwszej pochodnej i ujemnej drugiej pochodnej, wybrano logarytm ze względu na możliwość uzyskania prostych rachunków (pochodną logarytmu zmiennej jest odwrotność zmiennej, a separowalność sprawia, że pochodne mieszane drugiego rzędu są równe zero). Co więcej, logarytmy są często używane przez ekonomistów w funkcjach użyteczności (O logarytmicznie modelowanej użyteczności pisał już w XVIII wieku matematyk Bernoulli, jego praca została przedrukowana w Econometrice (1954) (Bernoulli, 1954). Założył on, że ,,jakikolwiek wzrost majątku (...) będzie zawsze skutkował wzrostem użyteczności odwrotnie proporcjonalnym do ilości dóbr już posiadanych'', a funkcją spełniającą powyższy warunek jest właśnie logarytm.). 

Czasowy horyzont planowania został ograniczony z tradycyjnie przyjmowanej w ekonomii nieskończoności do czterech lat kadencji władz samorządowych z dwóch powodów. 

Po pierwsze, zakłada się krótkowzroczność polityków - ich głównym celem jest zwycięstwo w kolejnych wyborach i dlatego zależy im na maksymalizacji użyteczności w ciągu bieżącej kadencji, a nie w długim okresie. W tym celu decydenci np. wolą zrealizować maksymalne wydatki dopuszczalne przez reguły fiskalne niż wziąć pod uwagę obciążenie długiem przyszłych pokoleń. Słabością przyjętego założenia jest abstrahowanie od możliwości reelekcji. Oznacza to, że wyborcy, mimo że zależy im na użyteczności w długim okresie, nie są w stanie dobrze prognozować wydatków w przyszłości, więc oceniają polityków wyłącznie przez pryzmat ostatniej kadencji. Ponadto odróżnienie funkcji celu wyborców od polityków oraz uwzględnienie niepełnej informacji, co zostało wspomniane w poprzednim rozdziale, należy do cech współczesnych teorii fiskalnego federalizmu. 

Po drugie, model zawiera kilka warunków ograniczających oraz zmiennych decyzyjnych, przez co rozwiązania optymalne mają złożoną postać i różnią się w zależności od przyjętego wariantu stanów początkowych. Skrócenie horyzontu czasowego do jednej kadencji umożliwia stosunkowo czytelny zapis i analizę rozwiązań. (Co więcej, dopiero potraktowanie dwóch pierwszych lat jako danych, czyli skrócenie horyzontu do roku trzeciego i czwartego umożliwia rozwiązanie analityczne modelu.) 

Warto wyjaśnić także występowanie w funkcji użyteczności zmiennej <img src="https://render.githubusercontent.com/render/math?math=k_{t%2B1}"> zamiast <img src="https://render.githubusercontent.com/render/math?math=k_{t}">. Przede wszystkim, gdyby użyto <img src="https://render.githubusercontent.com/render/math?math=k_{t}">, to optymalne inwestycje w ostatnim roku kadencji byłyby zerowe, gdyż zgodnie z równaniem (\ref{eq_kapital}) na poziom infrastruktury w przyszłym roku wpływają inwestycje z poprzedniego roku. W praktyce inwestycje samorządowe w ostatnim roku kadencji odgrywają istotną rolę w pozyskaniu głosów wyborców. Można nawet postawić hipotezę, że obywatele wynagradzają władze samorządowe bardziej za przyrost infrastruktury niż za jej poziom, który odziedziczyli po swoich poprzednikach. Jednak krańcowa użyteczność z infrastruktury - jak z każdego dobra - maleje, więc w funkcji użyteczności występuje poziom <img src="https://render.githubusercontent.com/render/math?math=k_{t%2B1}">, a nie zmiana. 

```{r setup, echo=FALSE}
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
```

