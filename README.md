# CodeRefactoring

1. Dług techniczny - należy zmniejszać najlepiej 10% nakładem pracy
2. Refactoring zmienia strukturę implementacji bez zmiany obserwowalnych zachowań
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
