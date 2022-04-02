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
