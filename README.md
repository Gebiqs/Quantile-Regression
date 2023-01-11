# Wpływ COVID-19 na zwroty z indeksów WIG





## 1. Motywacja badania 

Truizmem byłoby powiedzieć, że pandemia miała wpływ na Polską gospodarkę. Proste stwierdzenie, że „Pandemia wpłynęła na gospodarkę” nikogo nie dziwi. Prawdziwie zaskakujące mogą okazać się wnioski wyciągnięte z analizy przeprowadzonej przy użyciu bardziej zaawansowanych narzędzi. Odpowiednio dobrany zestaw narzędzi może określić nie tylko charakter wpływu, ale również może rozszerzyć perspektywę o kierunek wpływu, zależność między zmiennymi czy nawet rozbić problem na części pierwsze i umożliwić badanie struktury zjawiska. Regresja kwantylowa jest stosunkowo mało popularnym narzędziem regresji, lecz może okazać się przydatna w analizie złożoności wpływu zmiennych, czy właśnie struktury wpływu. W dalszej części niniejszego wywodu przybliżona zostanie po krótce teoria i przykładowe zastosowanie regresji kwantylowej.
Należy zauważyć, że notowania giełdowe są ważnym indykatorem powodzenia firm, a indeksy odzwierciedlają stan gospodarki. W tym samym momencie jednak ceny są wynikiem działania aktorów giełdowych, który przetwarzają dostępne informacje. Wartość akcji będzie zatem fluktuowała w czasie pod ich wpływem. Zatem motywatorem tego badania jest chęć analizy wpływu informacji o zakażeniach na polski rynek finansowy. W obszarze zainteresowania w szczególności leży pytanie, czy wpływ COVID-19 na zwroty z rynku akcji były zależne od ogonów rozkładu, a jeśli tak, to jaki dokładnie był ten wpływ. 





## 2. Cel badawczy

Celem pracy jest zbadanie zależności między zmianami zakażeń COVID a zmianami cen akcji polskich indeksów. W obszarze zainteresowania niniejszej pracy jest zbadanie struktury wpływu zmian zakażeń COVID na zmiany cen polskich indeksów giełdowych . Celem pracy jest również zweryfikowanie tezy o tym, że wpływ zmian zakażeń na zmiany cen jest zróżnicowany:
•	Ekstremalne dodatnie zmiany zakażeń współwystępują z ekstremalnie ujemnymi zmianami notowań indeksów. 
•	korelacja między wartościami środkowymi rozkładu (okolice mediany) jest mniejsza niż korelacja na krańcach rozkładu. 
•	Siła i kierunek relacji różni się między sektorami i kapitalizacją spółek. 





## 4. Metodologia

Badanie obejmuje dzienne dane notowań z przedziału czasu 4.01.2017-15.03.2022. Po wyczyszczeniu i dostosowaniu zbioru danych pozostało 1275 obserwacji. Dane dotyczące notowań pochodzą ze strony Stooq.com , dane dotyczące zakażeń COVID w Polsce zostały z kolei wyodrębnione z pliku dotyczącego dziennych zakażeń dostępnego w serwisie Github  jako ogólnodostępny, aktualizowany codziennie projekt open-source utrzymywany przez społeczność portalu.
Dla uproszczenia, indeks WIG będzie traktowany jako odpowiednia reprezentacja Polskiej giełdy. Z kolei wyszczególnione w Tabeli 2 indeksy: WIG20, mWIG40 oraz sWIG80 w ramach zgeneralizowane jako odpowiednio duże, średnie i małe spółki. Tabela 2 licząc od czwartego wiersza przedstawia notowania indeksów, które są reprezentacją kondycji poszczególnych sektorów Polskiej gospodarki. 
Za początek pandemii traktowana jest data 04.03.2020 kiedy to u 66-letniego Mieczysława Opałki zdiagnozowano pierwszy przypadek  COVID-19 w Polsce . Całkowita liczba zakażeń narastała w czterech głównych falach Z wykresu pod tytułem „Nowe zakażenia w czasie” widać, że pierwsza fala rozpoczęła się około 150 dni od pierwszego zakażenia, czyli na początku sierpnia 2020 roku. Z wykresu „Dzienna zmiana % zakażeń” możemy odczytać, że zmienność zakażeń znacząco wzrosła w końcu grudnia 2020 roku.


#### Wykresy 1-4. Analiza danych COVID-19
![alt text](https://github.com/Gebiqs/Quantile-Regression/blob/main/grafika_1.png)

Źródło: Opracowanie własne na podstawie https://github.com/owid/covid-19-data/tree/master/public/data


W badanym okresie średnia kapitalizacja indeksu WIG kształtowała się na poziomie 59tys. złotych. A przeciętna wartość zwrotów, liczonych jako logarytm naturalny przyrostu procentowego, był bliski zeru (0,025%), a odchylenie standardowe zwrotów wynosiło 0,012. Co ciekawe, przeciętne zwroty dla okresu przed pandemią COVID są niższe niż zwroty podczas trwania pandemii. Odchylenie standardowe z kolei na odwrót. Szczegółowe dane przedstawia tabela 1.

#### Tabela 1. Porównanie przedcovidowych i pocovidowych zwrotów WIG
![alt text](https://github.com/Gebiqs/Quantile-Regression/blob/main/grafika_2.png)

Źródło: opracowanie własne


#### Wykres 5. Notowania i zmienność indeksu WIG
![alt text](https://github.com/Gebiqs/Quantile-Regression/blob/main/grafika_3.png)

 Źródło: opracowanie własne na podstawie danych z portalu stooq.com


Sposób kształtowania się notowań indeksu WIG i jego zmienności przedstawiony jest na powyższym wykresie 5.
Do weryfikacji postawionych hipotez wybrany został model regresji kwantylowej uwzględniający dziesięć kwantyli, w których wysokie kwantyle reprezentują wysokie zwroty z indeksu a niskie kwantyle reprezentują niskie zwroty. Zmienną objaśniającą są notowania poszczególnych indeksów warszawskiej giełdy papierów wartościowych. Jako kontrolne zmienne objaśniające wybrane zostały: notowania indeksu DAX, ceny baryłki ropy Brent oraz zmienne zero-jedynkowe dla dni tygodnia. Kolejną zmienną objaśnianą, pozostającą w centrum zainteresowania autora są logarytmiczne zmiany kumulatywnej liczby zakażeń. 





#### Wykres 6. Zróżnicowanie zwrotów w zależności od dnia tygodnia
![alt text](https://github.com/Gebiqs/Quantile-Regression/blob/main/grafika_4.png)

Źródło: opracowanie własne na podstawie danych ze Stooq.com


Powodem wyboru tych zmiennych objaśniających była ich, według autora, potencjalna zdolność do wyjaśnienia poziomu zwrotów na polskiej giełdzie. Notowania indeksu DAX są niejako indykatorem kondycji gospodarczej najważniejszego partnera gospodarczego Polski. Ceny baryłki ropy Brent odnoszą się do ropy wydobywanej na morzu północnym i są uznawane za odpowiedni benchmark ceny ropy w Europie. Zmienne zero-jedynkowe reprezentujące dni tygodnia zostały wybrane ze względu na potrzebę uwzględnienia wpływu dnia tygodnia na poziom zwrotu. W modelu zaprezentowane są one jako wektor X’. Wszystkie zmienne objaśniające są opóźnione względem zmiennej objaśnianej o jeden okres (dzień). Ten zabieg ma na celu uwzględnienie opóźnienia reakcji inwestorów na informacje zewnętrzne. Model został sporządzony w postaci jak poniżej:


<img src="https://github.com/Gebiqs/Quantile-Regression/blob/main/grafika_5.png" width="660" height="225">





## 5. Rezultaty

Pozostające w interesie autora wyniki zostały wypisane w Tabeli 2. Wypisane zostały w niej współczynniki kierunkowe zmiany zakażeń COVID-19 i odchylenia standardowe dla siedmiu kwantyli na zwroty z jedenastu indeksów GPW.
Na łącznie 77 policzonych współczynników kierunkowych 20 charakteryzuje istotność statystyczna (25%). Wpływ zakażeń COVID-19 na zwroty giełdowe zgodnie z założeniami jest zróżnicowany. Co więcej, zgodnie z założeniami kierunek wpływu w zdecydowanej części indeksów jest negatywny. Wszystkie istotne statystycznie współczynniki z wyjątkiem tych dla indeksu WIG CHEMIA są negatywne. 
	Wpływ zmian zakażeń COVID na zwroty z indeksu okazał się być najistotniejszy dla spółek należących do indeksu WIG ODZIEŻ. Warto zaznaczyć, że wpływ jest negatywny. Przypuszczane jest, że powodem jest fakt, że spółki składowe charakteryzuje działalność w segmencie sprzedaży stacjonarnej – hurtowej lub franczyzowej. Są to segmenty, na które pandemia COVID, wraz z powszechnym zamknięciem gospodarki miała szczególny wpływ. Spośród spółek o największej kapitalizacji jedynie spółka CCC w trakcie pandemii prowadziła sprzedaż e-commerce (e-obuwie, modivo), lecz w badanym okresie jeszcze stosunkowo młode kanały internetowe nie były na tyle rozwinięte, aby mieć istotny wpływ.
	Spośród analizowanych indeksów pandemia COVID wywarła pozytywny wpływ na segment chemii. Do indeksu zalicza się spółki zajmujące się chemią: nawozami, chemią spożywczą, kosmetykami i materiałami budowlanymi. Domniemywane jest, że względnie pozytywny wpływ pandemii spowodowany był nieelastycznością popytu krajowego rynku, szczególnie w obszarze produkcji rolnej. Autorzy innych analiz wskazują, że dodatkowym czynnikiem napędzającym zyski polskich spółek z sektora chemii mogły być zerwane łańcuchy dostaw i trudności importu chemii z zagranicy .
	Teza, mówiąca o tym, że wpływ zmian dziennych zakażeń COVID-19 jest zróżnicowany między sektorami znalazła swoje poparcie w danych. Należy jednak podkreślić, że zróżnicowanie wpływu ze względu na poziom kapitalizacji spółek nie jest jasne. Wyniki dla indeksów WIG20 oraz mWIG40 nie cechują się wysoką istotnością statystyczną. Notowania indeksu sWIG80 okazały się zyskiwać przy zmianach zakażeń od trzeciego kwartyla w górę. 
	Ku zdziwieniu autora, wpływ zakażeń COVID na indeks WIG INFORMATYKA był negatywny. Technologie informatyczne używane były przez firmy i rządy jako remedium na zamknięcia gospodarki i ograniczenia w możliwościach interakcji międzyludzkiej. Prawdopodobne jest, że przyczyna negatywnych zwrotów w tym sektorze leży gdzieś indziej. Zdecydowanie jest to interesujący temat na przyszłe badania. 
	Wizualizacja tabeli 2, wraz z porównaniem wyników względem klasycznej metody regresji liniowej znajduje się w załączniku 1. Jest ono pewnym uszczegółowieniem wyników i ma na celu zaoferowanie możliwość oceny wpływu COVID-19 na indeksy w sposób wizualny. 

#### Tabela 2. Wpływ zmian zakażeń COVID-19 na indeksy giełdowe 
![alt text](https://github.com/Gebiqs/Quantile-Regression/blob/main/grafika_6.png)

Źródło: opracowanie własne na podstawie danych ze Stooq.com oraz github.com





## 6. Zakończenie 

W dzisiejszym świecie ekonometrii  model regresji kwantylowej nie cieszy się wielką popularnością. Ważnym celem pracy była popularyzacja tego narzędzia i pokazanie możliwości jego zastosowania w analizie szoków na rynku finansowym. Ważnym aspektem jest również zróżnicowanie wyników względem klasycznej metody OLS.
Sektory, które najbardziej cierpiały na wzrostach zakażeń COVID to był: sektor odzieżowy, sektor bankowy oraz sektor informatyki. Z kolei spółki zajmujące się szeroko pojętą chemią okazały się być jednymi z nielicznych beneficjentów pandemii.
Metoda regresji kwantylowej może być stosowana do dywersyfikacji i optymalizacji portfolio inwestycyjnego oraz zdaniem autora, powinna być brana pod uwagę przy jego konstrukcji.  









/
/
/
/
/
Źródła:

1.	https://discuss.dizzycoding.com/logarithmic-returns-in-pandas-dataframe/
2.	https://www.krus.gov.pl/fileadmin/moje_dokumenty/obrazki/kwartalnik/nr_73/73_Szajner_n.pdf [dostęp: 21.05.2022]
3.	Koenker R, Bassett JRG (1978) Regression quantiles Econometrical. Journal of the Econometric Society 46: 33-50.
4.	Huang Q, Zhang H, Chen J, He M (2017) Quantile Regression Models and Their Applications: A Review. J Biom Biostat 8: 354.
5.	Girma, Sourafel and Gorg, Holger, Foreign Direct Investment, Spillovers and Absorptive Capacity: Evidence from Quantile Regressions (July 2003). IIIS Discussion Paper No. 1; GEP Working Paper No. 2002/14
6.	Joachim Zietz & Emily N. Zietz & G. Stacy Sirmans., 2007. "Determinants of House Prices: A Quantile Regression Approach," Working Papers 200706
7.	T. C. Chiang, J. Li, Stock returns and risk: Evidence from quantile regression analysis / Journal of Risk and Financial Management 5(2012) 20-58
8.	  V. Shrotryia and H. Kalra, Analysis of Sectoral Herding through Quantile Regression: A Study of S&P BSE 500 Stocks, International Journal of Business and Economics, (2021)
9.	  Paresh Kumar Narayan, Qiang Gong & Huson Joher Ali Ahmed (2022) Is there a pattern in how COVID-19 has affected Australia’s stock returns?, Applied Economics Letters, 29:3, 179-182, DOI: 10.1080/13504851.2020.1861190
10.	  https://stooq.pl/q/d/?s=wig
11.	  https://github.com/owid/covid-19-data/tree/master/public/data [dostęp 16.03.2022]
12.	  https://www.medonet.pl/koronawirus/koronawirus-w-polsce,koronawirus-w-polsce--kim-byl-pacjent-zero--jak-sie-czuje-,artykul,21379457.html
