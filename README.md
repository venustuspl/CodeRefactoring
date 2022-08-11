# CodeRefactoring

1. Dług techniczny - należy zmniejszać najlepiej 10% nakładem pracy
2. Refactoring zmienia strukturę implementacji bez zmiany obserwowalnych zachowań/
3. Aby rozpocząć refactoring należy najpierw poznać obserwowalne funkcje aplikacji
4. Refactoring powinien być bezpieczny
5. Jeśli mamy stabilne testy to refakturujemy produkcję
6. Jeśli mamy stabilną produkcję to robimy testy
7. Test powinien być tworzony na wysokim obserwowowalnym zachowaniu, np. trzeba znać cel funkcji żeby o niej opowiedzieć
8. Należy oddzielać cel od szczegółów implementacji
9. Refactoring to inwestycja, z reguły zwrot z inwestycji jest duży
10. Dobieramy rozwiązanie do klasy problemu
11. Start refactoringu - nazwanie problemu
12. Boilerplate - ciągłe dodawanie tego samego kodu
13. Event storming - opis systemu za pomocą następujących po sobie zdarzeń
14. W "big picture" opisuje się tylko istotne zmiany biznesowe
15. As is - stan obecny
16. To be - stan oczekiwany
17. Hot spots - punkty zapalne, ryzyka - np. powolny raport
18. Skupiamy się na celu refaktoringu a nie na narzędziu
19. DRY - nie duplikuj logiki a nie tylko kodu
20. Shotgun surgery - duplikująca się logika jest niebezpieczna, każda modyfikacja musi być przetestowana więc łatwo o pomyłkę
21. Powtarzający się kod najlepiej analizować staycznie
22. Nie robimy zmian jeśli będzie to "sztuka dla sztuki"
23. Powtarzający się kod najlepiej wrzucić w jedno miejsce pakiet klasę a nie kolejny utils
24. Należy zdiagnozować obserwowalne zachowania i tam wprowadzać zmiany
25. Bezpieczeństwo zapewniamy stworzeniem dla obserwowalnych przypadków testów integracyjnych
26. Obserwowalne zachowania nie dotykają elementów kluczowych systemu więc ich zmiana niewiele może zepsuć
27. Pisanie testów uczy zachowania systemu
28. Testy z wykorzystaniem metody isThrownBy assertThatExceptionOfType nie za głęboko podłączać zrefaktorowane klasy
29. Test integracyjny najlepiej zastępuje duplikujący się kod testów, a drobne przypadki sprawdza się testami jednostkowymi
30. Testujemy obserwowalne zachowania
31. Użycie technik i narzędzi dopasujemy do projektu i jego problemów i dalszych planowanych działań z danym kodem
32. Do operacji na pieniądzach zwykle stosuje się typ Integer, ale najlepsza byłaby np. klasa Money (value object)
33. Najlepiej mieć stabliny "interfejs" tak aby zmiany w kodzie były bezpieczniejsze
35. Fail fast - trudne na początku
36. Stabilny interfejs sprawia, że kod pod spodem jest usuwalny, a to równie ważne jak testowalność
37. Zielone testy przy refaktoringu to zapewnienie bezpieczeństwa
38. Value object to object, który nie ma stanów pobiera się go i zapisuje
39. Mechanizm refleksji powstaje np. gdy nazwy klas są budowane dynamicznie w kodzie
40. Testy integracyjne testują więcej niż testy jednostkowe
41. Testy jednostkowe można dzielić kontekstowo
42. Brak spójności danych występuje np. w tedy gdy kilka zależnych od siebie metod może się wywołać w innych miejscach systemu i zmienić zapisane dane
43. Refaktoryzacja to proces stopniowy - nie jest możliwe naprawienie wszystkiego na raz
44. Dane silnie związane to np. dane zmieniające się razem, to jest spójność
43. W systemie powinno być 1 miejsce zmieniające spójne dane a nie np. ciąg setterow
44. Gettery są mniej szkodliwe można zostawić w kodzie, gettery nie zmieniają stanu obiektu
45. Nazwy należy dobierać szybko i w razie coś szybko zmieniać za pomocą IDE
46. Refactoring - zapewnić bezpieczęstwo zmiany, przywrócić enkapsulację , zaobserwować efekt , przemyśleć następne zmiany
47. Jeśli jakiś problem nie ma określonych regół działania to będzie trudno go zrefaktorować
48. Techniki znajdowania blokującej transakcji bazodanowej: znajomość systemu, metryki, logi, debugowanie
49. Nazwij problem dobierz rozwiązanie
50. Może być blokowanie optymistyczne lub pesymistyczne dostępu do danych ORM mają optymistyczne 
51. Czasami dobrym rozwiązaniem będzie wyznaczenie okna technologicznego dla działań administracyjnych aby nie blokowały codziennych zadań 
52. Podział transakcji na węższe transakcje może być najlepszym pomysłem
53. Dane powiązane regułami powinny być trzymane razem 
54. Nie separujemy danych od reguł
55. Do osobnego bytu przenosimy daną, którą ciężko było zmieniać, tak żeby nie przeszkadzała innym danym
56. Zmienialne dane trzymamy w innej klasie
57. Refactoring etapy: a) ustalamy gdzie wprowadzić zmianę b) określamy wpływ zmiany c) zapewnieniamy bezpieczeństwo(testy) 
58. Podział obiektu: a) określenie sposobu podziału obiektu b) stworzenie obiektów c) podłączenie obiektów c) usunięcie danych ze starego obiektu d) sprawdzenie obesrwowalnych zachowań (green test)
59. Drobna zmiana może zadziałać jak dżwignia powodującą zdecydowanie lepsze działanie systemu
60. Patrzeć na zysk z refaktoringu w szerszym kontekście a nie np. w kontekście pojedynczych zapytań na bazę 
61. Strategią migracji danych może być stworzenie zdublowanej tabeli i zastąpię starej w momencie pewności działania nowej
62. Poprawianie błędów biznesowych przy refaktoryzacji nie jest oczywiste i należy taką sytuację przedyskutować
63. Rozbijać refaktoryzację na mniejsze kroki
64. Planować refaktoryzację
65. Mieć możliwość wycofania zmian lub rollbacku bazy
66. Fail fast - najtrudniejsze na początku
67. Przeglądanie stosu wywołań pozwala odnaleźć miejsce wykorzystania konceptu w systemie
68. Przed przystąpieniem do refaktoringu należy sprawdzić ciągłość logiki biznesowej i procesowej, np. prześledzić proces reklamacji czyli możliwych wydarzeń
69. Logika walidacyjna - opisuje ogólne sprawdzenie poprawności danych
70. Logika biznesowa - opisuje spójne przeprowadzenie zmiany stanu systemu
71. Jeśli logiki na siebie się nakładają to najlepiej blokować ustaloną część procesu podczas wykonywania na bazie
72. Osobne logiki należy enkapsulować do odobnych obiektów
73. Jeśli zwiększamy dostępność do plików to krócej blokujemy dostęp do danych
74. Logikę domenową należy zamknąć w dedykowanym obiekcie wtedy zmiany będą spójne 
75. Logikę procesową należy umieścić w warstwie wyższej, serwisie lub dedykowanym obiekcie
76. Mnogość reprezetacji to jeśli np. obiekt biznesowy może być ustawiany albo za pomocą flagi albo daty - np. ważność mil punktowych
77. Jeśli reguła jest rozpięta na wiele obiektów to najlepiej stworzyć stabilny interfejs
78. Aby nie mapować danych można je przechowywać w JSON
79. Wizualizacja przypadków może uprościć refaktoryzację
80. Warto odkryte słownictwo od razu zmieniać w systemie to zwiększy zrozumienie systemu legacy
81. VO - value object
82. Po refaktoryzacji funkcje stają się addytywne czyli można je łatwo dodać bez zmiany istniejącego kodu
83. Naprawa klas na niższym poziome pozwoli łatwiej naprawić kod na wyższym poziomie
84. Separuj to co zmienne od tego co stabilne
85. Zmienność kodu w metodzie można rozwiązać fabryką strategii
86. Do wyboru strategii najlepiej użyć wspólny parametr, który będzie je wyróżniał 
87. Aggregate wzorzec jednostki, która zawiera w sobie spójną zmianę systemu
88. Domain Driven Design to wzorzec agregatów
89. Event Storming może służyć do namierzania agregatów w systemie - jednostek spójnej zmiany
90. Przy modelowaniu reguł warto skupic się na elementach niezmiennych systemu 
91. Kod zaczynamy refaktorować lokalnie bo czasami ciężko zrozumieć całość
92. ORM w trybie Lazy nie robi zapytania o ile to nie jest potrzebne
93. Problem N+1 to najczęściej wąskie gardło każdej aplikacji
94. Eeager - wyciągnięcie dużej ilości danych, raport
95. Lazy - używamy gdy pobieramy wycinek danych
96. Warto czasem użyć bezpośrednio SQL zamiast ORM
97. Dto jest połączy kontraktem z encją 
98. Należy przemyśleć czy wszystkie dane muszą być transportowane poprzez Dto 
99. Docker run - uruchomienienie contenera np. pobranego z huba, zawsze warto przemapować porty aby kontener dziąłał lokalnie 
100. Podczas refaktoringu ważne jest wersjonowanie - api/v1/movies
101. Warto sprawdzać kod źródłowy używanych adnotacji
102. Zalecany jest update za pomocą setów
103. Nie dotykamy problematycznego kodu tylko go wymieniamy
104. Grennfield - nowy system
105. Brownfield - legacy
106. Podpięcie Greenfield w Brownfield podnosi morale
107. Da się przepisać system bez całościowego Rewrite, można nie zaczynać od zera
108. Napisanie nowego query bez frameworka może być łatwiejsze
109. Profilowanie aplikacji - mierzenie wydajności, warto wiedzieć co mierzymy i gdzie mierzymy
110. Utrzymywanie 2 modeli równoległych starego i nowego podczas refaktoryzacji jest najbezpieczniejsze 
111. Microcykle refaktoryzacji są bezpieczne 
112. Dużo łatwiej podłączyć drugi równoległy model jeśli ten pierwszy ma abstrakcję i dobre API
113. What are feature flags? Feature flags (also commonly known as feature toggles) is a software engineering technique that turns select functionality on and off during runtime, without deploying new code
114. Rekoncyliacja danych to ich porównanie systemowe
115. Asynchroniczne odpytanie modelu czyli drugi model nie czeka
116. Można oddzielać odczyty od zapisów w cache
117. Do szybszego odczytu danych można utworzyć dedykowany model odczytowy z szczegółowo wybranymi strukturami danych
118. W myśl zasady wszystko albo nic - oprócz zmian na bazie powinna być też zapisana przyczyna tych zmian
119. Warto dokumentować podejmowane decyzje
120. Jeśli mniejsze zmiany są możliwe to warto je wykonywać
121. Miej dane i patrz w dane
122. Obserwować nawet 5% danych
123. Należy obserwować dane nawet w długich odstępach
124. Zwizualizowane dane są najlepsze do obserwacji
125. Grafowa baza danych to baza, która używa grafu do zapisywania danych i połączeń między nimi
126. Pojawienie się rekurencji w kodzie powinno wzbudzić czujność, może to np. zwiększyć zużycie procesora
127. Command/Query Responsibility Segregation a potocznie po prostu CQRS to wzorzec projektowy, który jak sama nazwa na to wskazuje, wprowawdza pewną segregację odpowiedzialności:
- rozkazów (ang. command) – dla operacji które modyfikują dane
- zapytań (ang. query) – dla operacji które odczytują dane
128. Osoba techniczna nie powinna szeżyć defetyzmu
129. W zespole należy dopasować komunikację techniczną do nietechnicznej
130. Dopasować się do poziomu szczegółowości rozmówcy dopóki nie umyka sedno problemu
131. Zawsze należy się zastanowić się czy to będzie najlepszy moment na drążenie szczegółów
132. Ludzie dzielą się na wewnętrzne(decyzje podejmują w wyniku własnego doświadczenia) i zewnętrzne źródła referencji(decyzje podejmują po wysłuchaniu opinii innych)
133. Dla osób z wewnętrznym źródłem referencji proponujemy eksperyment
134. Dla osób z zewnętrznym źródłem referencji zbieramy dane uwiarygodniające, sterujemy pytaniami
135. IT i biznes są nastawione na wewnętrzne źródło referencji
136. Umiejętności komunikacyjne najlepiej ćwiczyć np. w scenkach
137. Najpierw opisujemy problem a później dopasujemy komunikację np. do osób do których piszesz (hr, biznes)
138. Są osoby nastawione na zasady i pracujące wg. zasad i procedur(głównie osoby techniczne)
139. Są też osoby nastawione na możliwości, ale one niechętnie trzymają się zasad
140. Plan działania powinien dopasowany do osób, które będą odbiorcami danego planu (np. osoby techniczne, osoby nastawione na możliwości, na cel, proaktywne, reaktywne)
141. Biznes jest nastawiony na komunikację: “oni”
