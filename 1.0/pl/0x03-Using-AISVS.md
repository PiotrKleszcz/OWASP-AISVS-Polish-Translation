# Korzystanie z AISVS

Standard weryfikacji bezpieczeństwa sztucznej inteligencji (AISVS) definiuje wymagania bezpieczeństwa dla nowoczesnych aplikacji i usług AI, koncentrując się na aspektach pozostających w gestii programistów aplikacji.

AISVS jest przeznaczony dla wszystkich, którzy tworzą aplikacje AI lub oceniają ich bezpieczeństwo, w tym dla programistów, architektów, inżynierów bezpieczeństwa i audytorów. W tym rozdziale przedstawiono strukturę AISVS i sposób korzystania z niego, w tym poziomy weryfikacji, zamierzone przypadki użycia oraz miejsce AISVS wśród innych standardów bezpieczeństwa.

## Jak czytać ten standard

### Struktura rozdziałów

Każdy z 12 rozdziałów z wymaganiami ma ten sam układ:

* **Cel kontrolny.** Krótkie określenie celu bezpieczeństwa danego rozdziału.
* **Sekcje.** Wymagania są pogrupowane w powiązane ze sobą sekcje, z których każda zawiera krótki opis celu obrony.
* **Tabele wymagań.** Poszczególne wymagania są przedstawione w tabelach z następującymi kolumnami:

| Kolumna | Znaczenie |
| --- | --- |
| **#** | Unikalny identyfikator wymagania (np. 1.1.1, 9.3.2). |
| **Opis** | Treść wymagania, zawsze rozpoczynająca się od „Zweryfikuj, że”, aby podkreślić jego testowalność. |
| **Poziom** | Poziom weryfikacji (1, 2 lub 3) wskazujący wymagany poziom pewności; zob. poziomy weryfikacji poniżej. |

### Załączniki

Wymagania podstawowe uzupełniają trzy załączniki:

* **Załącznik A (Glosariusz)** definiuje kluczowe terminy i skróty używane w całym standardzie.
* **Załącznik B (Inwentarz mechanizmów bezpieczeństwa AI)** to zestawienie odsyłaczy obejmujące każdą technikę obrony występującą w AISVS, uporządkowane według kategorii mechanizmów bezpieczeństwa (uwierzytelnianie, autoryzacja, szyfrowanie, walidacja danych wejściowych itd.), z powiązaniami z konkretnymi identyfikatorami wymagań.
* **Załącznik C (Bezpieczne programowanie wspomagane przez AI)** zawiera mechanizmy dotyczące bezpiecznego korzystania z narzędzi AI do programowania w procesie wytwarzania oprogramowania.

## Poziomy weryfikacji bezpieczeństwa sztucznej inteligencji

AISVS definiuje trzy rosnące poziomy weryfikacji bezpieczeństwa. Każdy kolejny poziom zwiększa głębokość i złożoność weryfikacji, umożliwiając organizacjom dostosowanie poziomu bezpieczeństwa do poziomu ryzyka ich systemów AI.

Organizacje mogą zacząć od Poziomu 1 i stopniowo wdrażać wyższe poziomy w miarę wzrostu dojrzałości bezpieczeństwa i narażenia na zagrożenia. Poziomy AISVS są powiązane z poziomami [ASVS](https://owasp.org/www-project-application-security-verification-standard/) i powinny być stosowane łącznie z odpowiadającym im poziomem ASVS (zob. „Powiązanie z poziomami ASVS” poniżej).

### Definicja poziomów

Każde wymaganie w AISVS v1.0 jest przypisane do jednego z następujących poziomów:

#### Wymagania Poziomu 1

Poziom 1 obejmuje najbardziej krytyczne i fundamentalne wymagania bezpieczeństwa. Koncentrują się one na zapobieganiu powszechnym atakom, które nie zależą od innych warunków wstępnych ani podatności. Większość mechanizmów Poziomu 1 jest albo prosta we wdrożeniu, albo na tyle istotna, że uzasadnia wymagany nakład pracy.

#### Wymagania Poziomu 2

Poziom 2 dotyczy bardziej zaawansowanych lub rzadziej spotykanych ataków, a także wielowarstwowych zabezpieczeń przed powszechnymi zagrożeniami. Wymagania te mogą obejmować bardziej złożoną logikę lub być ukierunkowane na konkretne warunki wstępne ataków.

#### Wymagania Poziomu 3

Poziom 3 obejmuje mechanizmy, które są zazwyczaj trudniejsze we wdrożeniu lub mają zastosowanie tylko w określonych sytuacjach. Często są to mechanizmy obrony w głąb lub środki ograniczające niszowe, ukierunkowane albo bardzo złożone ataki.

## Powiązanie z poziomami ASVS

Poziomy AISVS są powiązane z poziomami [ASVS](https://owasp.org/www-project-application-security-verification-standard/). Weryfikacja aplikacji AI pod kątem Poziomu _N_ AISVS zakłada, że aplikacja została już lub jest weryfikowana pod kątem Poziomu _N_ ASVS. Oba standardy zaprojektowano tak, aby stosować je łącznie na odpowiadających sobie poziomach:

| Poziom AISVS | Odpowiadający poziom ASVS | Typowe zastosowanie |
| :---: | :---: | --- |
| 1 | 1 | Podstawowy poziom bezpieczeństwa dla każdej aplikacji AI, która przetwarza niezaufane dane wejściowe lub operuje na danych o dowolnym stopniu wrażliwości. |
| 2 | 2 | Aplikacje AI przetwarzające wrażliwe dane biznesowe lub dane podlegające regulacjom albo działające w kontekstach adwersarialnych. |
| 3 | 3 | Aplikacje AI o wysokim poziomie pewności, np. podejmujące decyzje mające wpływ na życie i zdrowie, obsługujące infrastrukturę krytyczną lub przetwarzające szczególnie wrażliwe dane osobowe. |

Jeśli wymaganie AISVS wydaje się pokrywać z wymaganiem ASVS, jego wersja w AISVS została sformułowana ponownie wyłącznie dlatego, że obejmuje szczegóły implementacji, powierzchnię ataku lub dowody specyficzne dla AI, które audytor musi oceniać w inny sposób.

## Zakres AISVS

Zakres AISVS jest celowo wąski. Standard definiuje wyłącznie wymagania bezpieczeństwa specyficzne dla systemów AI i ML lub takie, w których ogólne mechanizmy bezpieczeństwa mają specyficzne dla AI niuanse uzasadniające ich ponowne sformułowanie. Nie jest to samodzielny program bezpieczeństwa dla aplikacji AI. AISVS zakłada, że aplikacja bazowa, infrastruktura i praktyki organizacyjne zostały już zweryfikowane pod kątem uznanych standardów ogólnego przeznaczenia, i dodaje do nich warstwę specyficzną dla AI.

Poniższe obszary są celowo wyłączone z zakresu i nie są powielane w rozdziałach AISVS:

* **Ogólne bezpieczeństwo aplikacji.** Uwierzytelnianie, zarządzanie sesją, autoryzację, bezpieczeństwo transmisji, obsługę danych wejściowych i wyjściowych w elementach niezwiązanych z AI, zarządzanie sekretami, obsługę przesyłania plików, obsługę błędów i podobne mechanizmy definiuje [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard/).
* **Ogólne bezpieczeństwo łańcucha dostaw oprogramowania.** Skanowanie zależności, przypinanie wersji, wymuszanie plików blokad (lockfile), pochodzenie buildów, powtarzalne buildy, ogólne generowanie SBOM i integralność potoku CI/CD definiują [OWASP Software Component Verification Standard (SCVS)](https://owasp.org/www-project-software-component-verification-standard/), [SLSA](https://slsa.dev/) i [CIS Controls](https://www.cisecurity.org/controls).
* **Ogólne utwardzanie infrastruktury i platform.** Bazowe utwardzanie kontenerów, hostów, sieci, chmury i Kubernetesa definiują [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks), [NIST SP 800-53](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final), [NIST SP 800-190](https://csrc.nist.gov/pubs/sp/800/190/final) i [NIST Cybersecurity Framework (CSF)](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20).
* **Ogólna ochrona danych i operacje w zakresie prywatności.** Klasyfikację danych, szyfrowanie danych w spoczynku i w tranzycie, harmonogramy retencji, bezpieczne usuwanie danych z konwencjonalnych nośników, niezmienność logów audytowych oraz obsługę platform zarządzania zgodami definiują ASVS, [ISO/IEC 27001](https://www.iso.org/standard/27001) i obowiązujące przepisy o ochronie prywatności, takie jak RODO.
* **Ogólne logowanie i monitorowanie.** Kontrolę dostępu do magazynów logów, retencję, kopie zapasowe, szyfrowanie, redagowanie, ochronę przed manipulacją, integrację z SIEM i telemetrię operacyjną definiują ASVS i standardowe praktyki obserwowalności.
* **Zarządzanie AI i zarządzanie ryzykiem.** Organizacyjne zarządzanie AI, oceny wpływu AI, dokumentację dotyczącą sprawiedliwości (fairness) i etyki, karty modeli (model cards), publiczne raporty przejrzystości i projektowanie procesów zarządzania ryzykiem definiują [ISO/IEC 42001](https://www.iso.org/standard/81230.html), [ISO/IEC 23894](https://www.iso.org/standard/77304.html) i [NIST AI RMF](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10).
* **Wytyczne specyficzne dla dostawców.** AISVS jest neutralny wobec dostawców. Określa, co należy zweryfikować, a nie którego produktu użyć.

Podczas weryfikacji aplikacji AI pod kątem AISVS należy równolegle weryfikować odpowiadający poziom tych standardów bazowych.

## Odsyłacze wewnątrz AISVS

Rozdziały AISVS są uporządkowane według rodzin mechanizmów kontroli, a nie według ataków czy komponentów. W rezultacie obrona przed danym zagrożeniem AI zwykle wymaga łącznego zastosowania wymagań z kilku rozdziałów. Na przykład obrona przed wstrzyknięciem polecenia w aplikacji agentowej łączy wymagania z C2 (walidacja danych wejściowych), C7 (zachowanie modelu), C9 (orkiestracja i bezpieczeństwo agentowe), C10 (mechanizmy specyficzne dla MCP), C11 (odporność na ataki adwersarialne) i C12 (wykrywanie i logowanie).

Stosując AISVS, traktuj standard jako całość i korzystaj z Załącznika B (Inwentarz mechanizmów bezpieczeństwa AI), aby uzyskać przekrojowy obraz tego, gdzie występuje każda technika obrony.

## Wymagania AISVS a zakres ocen

Wymagania często można ocenić za pomocą połączenia testów technicznych i dokumentacji dostawców, np. kart modeli AI. Inną możliwością jest oznaczenie wymagań pozostających poza kontrolą organizacji jako wyłączonych z zakresu.
