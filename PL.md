# Filtr skrzynki z AI (Claude + Gmail)

Filtr spamu widzi tylko nadawcę. Claude może wiedzieć, nad czym pracujesz, bo mu to mówisz. Ten prompt każe Claude'owi posortować dwa tygodnie poczty według **twoich celów** i nigdy niczego nie usuwa.

Mój test na własnej skrzynce: 619 wątków z dwóch tygodni, 61 wymagało mnie, 396 to czysty szum.

## 1. Podłącz Gmaila (raz, ok. 30 s)
claude.ai → Customize → Connectors → Gmail → Connect. Działa też na darmowym planie.

## 2. Najpierw zmień to ustawienie
Na stronie konektora Gmail każde narzędzie ma trzy opcje: **Always allow / Needs approval / Block**.
Ustaw na **Block**:
- Send email message, Reply to email, Forward email
- Move message to Trash, Move thread to Trash
- Apply sensitive label (Trash or Spam), dla wiadomości i wątku
- Delete draft email, Delete label

„Add labels” zostaw na **Needs approval**, żeby Claude pytał, zanim cokolwiek oznaczy.

## 3. Prompt
Wpisz swoje trzy cele.

```
Przejrzyj wszystkie maile w mojej skrzynce Gmail z ostatnich 14 dni.

Moje trzy cele w tym miesiącu:
1) <cel 1, np. nowa praca: rekruterzy, rozmowy, odpowiedzi na aplikacje>
2) <cel 2, np. oddać projekt klienta na czas>
3) <cel 3, np. rozwinąć konto na Instagramie>

Wszystko od banku, sądu, urzędu skarbowego albo z fakturą zawsze trafia do NEEDS ME.

Przydziel każdy mail do dokładnie jednej z trzech kupek:
- NEEDS ME: muszę coś zrobić lub odpisać w tym tygodniu albo to przybliża któryś cel.
- READ LATER: przydatne, ale bez działania.
- NOISE: newslettery, promocje i powiadomienia, za którymi nie zatęsknię.

Niczego jeszcze nie usuwaj, nie archiwizuj ani nie oznaczaj. Najpierw pokaż mi:
1) ile maili sprawdziłeś i ile jest w każdej kupce,
2) tabelę wszystkich NEEDS ME: nadawca, temat i jedno zdanie, dlaczego,
3) nadawców z NOISE pogrupowanych, z liczbą przy każdym.

Dopiero gdy napiszę „go”, dodaj etykietę AI-noise do kupki NOISE. Nigdy niczego nie usuwaj.
```

Potem otwórz w Gmailu etykietę `AI-noise`, rzuć okiem, zaznacz wszystko i kliknij **Archiwizuj**. Zarchiwizowane to nie usunięte: wszystko zostaje w „Wszystkie”.

## Bonus: ten sam filtr na X i Instagramie
Zamiast scrollować, poproś asystenta, który umie przeszukiwać platformę (Grok dla X albo Claude/ChatGPT z wyszukiwaniem):

```
Moje cele w tym miesiącu: <cel 1>, <cel 2>, <cel 3>.
Znajdź 5 osób na <X / Instagramie>, które teraz publikują przydatne, praktyczne rzeczy o <temat>.
Pomiń tych, którzy głównie repostują, w każdym poście sprzedają kurs albo łowią zaangażowanie.
Dla każdej: nick, dlaczego warto obserwować (jedno zdanie) i jeden świeży post, który to pokazuje.
```
