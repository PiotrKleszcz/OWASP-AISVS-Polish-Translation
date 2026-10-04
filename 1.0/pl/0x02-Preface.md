# Przedmowa

Witamy w **Standardzie weryfikacji bezpieczeństwa sztucznej inteligencji (AISVS) w wersji 1.0**.

Wdrażając AISVS, organizacje mogą systematycznie oceniać i wzmacniać poziom bezpieczeństwa swoich systemów AI, budując fundament praktyk bezpiecznej inżynierii AI, który rozwija się wraz z samą technologią.

## Dlaczego powstał AISVS

Systemy AI wprowadzają ryzyka bezpieczeństwa, z myślą o których nie projektowano tradycyjnych standardów bezpieczeństwa aplikacji. Wstrzyknięcie polecenia (prompt injection) pozwala atakującym nadpisać instrukcje modelu za pomocą spreparowanych danych wejściowych, zamieniając model językowy w narzędzie do eksfiltracji danych, wykonywania nieautoryzowanych działań lub obchodzenia mechanizmów bezpieczeństwa (safety). Dane treningowe mogą zostać zatrute, aby umieścić w modelu backdoory lub pogorszyć jego zachowanie. Modele mogą zostać poddane ekstrakcji lub inwersji albo zmanipulowane za pomocą adwersarialnych danych wejściowych (adversarial inputs). Autonomiczni agenci mogą podejmować działania o realnych skutkach, kierując się wstrzykniętymi instrukcjami, których nie potrafią odróżnić od uprawnionych. Potoki wyszukiwania (retrieval) mogą zostać wykorzystane do wycieku informacji wrażliwych lub do wstrzyknięcia złośliwych treści do kontekstu modelu. Łańcuch dostaw modeli, zbiorów danych i frameworków stawia nowe wyzwania w zakresie integralności, których sama dotychczasowa analiza składu oprogramowania (SCA) nie jest w stanie rozwiązać.

AISVS stworzono, aby dać organizacjom uporządkowany, testowalny zestaw mechanizmów bezpieczeństwa zaprojektowanych specjalnie pod kątem tych ryzyk. Nie zastępuje on istniejących standardów – wypełnia lukę, której żaden z nich nie obejmuje.

## Zasady projektowe

AISVS jest podzielony na 12 rodzin mechanizmów kontroli. Każda rodzina dzieli się na wyspecjalizowane sekcje, które wspierają realizację jej celu kontrolnego. Każda sekcja zawiera wymagania weryfikacyjne. AISVS definiuje trzy poziomy weryfikacji, opisane w rozdziale „Korzystanie z AISVS”; sekcje nie muszą zawierać wymagań na każdym poziomie.

Każde wymaganie musi dotyczyć jednej kwestii, którą zwykle można zaimplementować i zweryfikować jako jeden mechanizm techniczny. Wymagania nie mogą powielać mechanizmów zdefiniowanych w innych miejscach AISVS. Wyższe poziomy pewności mogą wprowadzać surowsze kryteria, ale muszą one być sformułowane jako osobne wymagania. Wymagania powinny być formułowane jasnym, neutralnym technologicznie językiem, a konkretne technologie przywoływać wyłącznie jako przykłady, jeśli poprawia to przejrzystość.

Każde wymaganie AISVS opiera się na czterech zasadach projektowych wywodzących się z nazwy standardu:

* **Sztuczna inteligencja.** Wymagania muszą dotyczyć zasobów, przepływów pracy lub zachowania w czasie działania specyficznych dla AI/ML, w tym zbiorów danych, modeli, potoków treningowych i ewaluacyjnych, systemów wyszukiwania, agentów, narzędzi, pamięci oraz działania w czasie wnioskowania (inference). AISVS nie powiela ogólnych mechanizmów bezpieczeństwa aplikacji ze standardów takich jak ASVS, chyba że dany mechanizm wiąże się z kwestiami implementacji lub weryfikacji specyficznymi dla AI.
* **Bezpieczeństwo.** Wymagania muszą ograniczać możliwe do zidentyfikowania ryzyko w obszarze bezpieczeństwa (security), prywatności lub bezpieczeństwa (safety). Mechanizmy służące wyłącznie celom operacyjnym, zarządczym, związanym ze zgodnością lub biznesowym są poza zakresem.
* **Weryfikacja.** Wymagania muszą być obiektywnie weryfikowalne za pomocą testów, inspekcji lub audytu. Muszą istnieć wystarczające wskazówki implementacyjne lub narzędzia wspierające zarówno implementację, jak i weryfikację. Wytyczne czysto teoretyczne, subiektywne lub życzeniowe są wykluczone.
* **Standard.** Wymagania muszą mieć spójną strukturę, terminologię i semantykę poziomów pewności, aby AISVS pozostawał koherentny, łatwy w nawigacji i odpowiedni do powtarzalnych ocen.
