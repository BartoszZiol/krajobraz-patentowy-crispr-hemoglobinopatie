# Krajobraz patentowy technologii CRISPR/Cas9 w leczeniu hemoglobinopatii

**Zakres badania:** lata 2013-2026  
**Dziedziny:** prawo patentowe, biologia molekularna, edycja genomu, analiza danych.

Projekt przedstawia wybrane strategie ochrony patentowej rozwiązań związanych z edycją genomu w leczeniu anemii sierpowatokrwinkowej i beta-talasemii. Uwzględnia europejskie postępowania patentowe, konstrukcję opublikowanych zastrzeżeń, różnice między celami biologicznymi oraz statystyczny opis wyników wyszukiwania w bazie Espacenet.

## Najważniejsze wyniki

- **135** odrębnych rekordów publikacji uzyskanych z sześciu stron wyników Espacenet.
- **25** wstępnie wybranych publikacji do dalszego badania.
- **6** szczegółowo opracowanych przypadków dotyczących CRISPR i **1** technologii TALEN jako porównania.
- **2** wycofane europejskie zgłoszenia patentowe w badanej grupie: EP3887521A1 i EP3749767A1.
- **2** osobne zgłoszenia dotyczące *prime editing* promotorów HBG: EP4747377A1 (region -115) oraz EP4747376A1 (region -200).

**Ważne:** liczba 135 dotyczy publikacji, a nie 135 niezależnych rodzin patentowych. Nie ustalono pełnej liczby zweryfikowanych prostych rodzin DOCDB. Nie należy utożsamiać publikacji WO ani EP A1 z udzielonymi patentami.

## Wnioski z analizy

Zebrane publikacje wskazują na trzy odmienne cele interwencji: regulację ekspresji poprzez BCL11A, bezpośrednią edycję promotorów HBG1/HBG2 oraz korekcję HBB. Podobny cel terapeutyczny nie oznacza identycznego zakresu ochrony patentowej. W dokumentach występują różne kategorie zastrzeżeń, od RNA prowadzących i zestawów edycyjnych po komórki oraz zastosowania terapeutyczne. Dwa odrębne zgłoszenia prime editing dotyczą regionów -115 i -200, a zweryfikowane statusy EPO dowodzą konieczności rozróżniania publikacji, postępowania w toku i udzielonego patentu. Wnioski te szczegółowo omówiono w końcowych rozdziałach raportu.

## Pliki projektu

| Plik lub katalog | Zawartość |
| --- | --- |
| `Raport_krajobraz_patentowy_CRISPR_2013-2026_PL.pdf` | Raport w języku polskim, rozbudowane podsumowanie, analiza techniczna i prawna oraz cztery wykresy. |
| `Baza_krajobraz_patentowy_CRISPR_PL.xlsx` | Uporządkowany arkusz z 14 zakładkami, obejmujący wszystkie 135 publikacji, 25 kandydatów, przypadki, podstawy prawne i porównanie wybranych sekwencji D1/Editas. |
| `dane/publikacje_135.csv` | Dane bibliograficzne i ocena wstępna z polskimi nazwami kolumn. Oficjalne tytuły publikacji zachowano w oryginalnym brzmieniu. |
| `dane/kandydaci_25.csv` | Wybór publikacji do dalszej analizy. To nie jest lista potwierdzonych rodzin patentowych. |
| `dane/przypadki_7.csv` | Zestawienie analizowanych przypadków i ich źródeł. |
| `dane/zrodla.csv` | Adresy źródeł i odpowiednie przepisy EPC. |
| `dane/kontrola.json` | Podstawowe dane kontrolne i zakres ustaleń. |
| `wykresy/` | Cztery wykresy w języku polskim zapisane jako PNG. |
| `dokumentacja/` | Metodyka wyszukiwania, rejestr źródeł i zastrzeżenia dotyczące dowodów. |
| `skrypty/` | Skrypty umożliwiające ponowne wygenerowanie wykresów i PDF. |
| `materialy_zrodlowe/` | Oryginalne, niezmienione eksporty z Espacenet. |

## Podstawowa metodyka

Użyto wyszukiwania Espacenet Worldwide opartego na słowach `BCL11A` i `CRISPR` oraz określeniach chorób zawartych w tytule lub streszczeniu:

```text
(ftxt = BCL11A AND ftxt = CRISPR) AND (((ta = hemoglobinopathy OR ta = hemoglobinopathies) OR ta = "sickle cell") OR ta = thalassemia)
```

Przedmiotem analiz liczbowych są **rekordy publikacji**. Każdemu nadano wstępną kategorię: A (bezpośredni kandydat), B (zastosowanie terapeutyczne do sprawdzenia), C (technologia pokrewna) lub D (prawdopodobnie poza zakresem). Rozkład kategorii wynosi odpowiednio **35, 36, 37 i 27**.

Metodyka selekcji i hierarchia dowodów zostały dokładniej opisane w [`dokumentacja/metodyka.md`](dokumentacja/metodyka.md).

## Przykłady przeanalizowanych zgłoszeń

| Dokument | Główny cel | Stan lub uwaga |
| --- | --- | --- |
| EP3981876A1 (Editas) | Enhancer BCL11A | Wniosek o badanie; przeanalizowano zmiany zastrzeżeń z 2023 r. |
| EP3887521A1 (Editas) | HBG1/HBG2 | Wycofane przez zgłaszającego w grudniu 2024 r. |
| EP3749767A1 (Vertex) | BCL11A | Wycofane przez zgłaszającego w lutym 2025 r. |
| WO2025147212A1 | HBG, miejsca wiązania LRF | Nikazy Cas9; analizowano 42 zastrzeżenia WO. |
| WO2025017033A1 / EP4747377A1 | HBG, region -115 | Prime editing; wniosek o badanie; zmiany z 2026 r. |
| WO2025017030A1 / EP4747376A1 | HBG, region -200 | Prime editing; wniosek o badanie; zmiany z 2026 r. |
| WO2025181336A1 | HBB | TALEN/HDR, wyłącznie jako technologia porównawcza. |

## Odtwarzanie wykresów i raportu

Wymagany jest Python 3 z pakietami wskazanymi w `requirements.txt`:

```bash
python -m pip install -r requirements.txt
python skrypty/analiza.py
python skrypty/raport.py
```

Pierwszy skrypt przelicza dane z polskiego pliku CSV i generuje cztery wykresy. Drugi składa raport PDF z opisów i wykresów. Arkusz XLSX jest odrębnym opracowaniem analitycznym i nie jest odtwarzany przez wskazane dwa skrypty.

## Zakres odpowiedzialności za wnioski

Analiza ma charakter badawczy i nie stanowi opinii o ważności patentu, naruszeniu patentu ani oceny swobody prowadzenia działalności (FTO). Podstawą stwierdzeń o europejskim statusie są wyciągi z European Patent Register udokumentowane w listopadzie 2026 r. Dla EP4747376 i EP4747377 nie przeprowadzono analizy pełnych zastrzeżeń po zmianach z 15 stycznia 2026 r. Wycofanie zgłoszenia EP nie wyjaśnia samo przez się jego przyczyny ani sytuacji w innych jurysdykcjach.

Źródła urzędowe: [Espacenet](https://worldwide.espacenet.com/), [European Patent Register](https://register.epo.org/), [Konwencja o patencie europejskim](https://www.epo.org/en/legal/epc/) oraz [definicje rodzin patentowych DOCDB](https://www.epo.org/en/searching-for-patents/helpful-resources/first-time-here/patent-families/docdb).
