# slay-research-paper

Empiryczny raport badawczy wg standardu [slay-paper](https://github.com/slayerlabs/slay-paper).

## Struktura

```
paper/
├── main.tex                    ← wrapper (nie pisz tu treści)
├── formatka/slayer.sty         ← WYGLĄD (podmienialny)
└── tresc/
    ├── 00-strona-tytulowa.tex  ← tytuł + autor + wykres hero
    └── 10-tresc.tex            ← body: sekcje merytoryczne
.github/workflows/latex.yml     ← CI: .tex → PDF jako artefakt
```

## Gdzie pisać

Edytuj tylko `paper/tresc/*.tex`. Wyglądu nie ruszaj — jest w `paper/formatka/slayer.sty`.

## Obowiązkowe sekcje

1. **Streszczenie** — 3–5 zdań, empiria od razu
2. **Wprowadzenie** — teza + jak ją zweryfikujemy
3. **Metoda** — dane, przetwarzanie, definicje formalne
4. **Wyniki** — liczby, tabele, wykresy
5. **Warunek obalenia** — mierzalny test/próg (OBOWIĄZKOWY)
6. **Dyskusja** — ograniczenia, co dalej
7. **Podpis** — autor + data

## Twarde reguły

- Matematyka zawsze w LaTeX: `$\Delta$` nie Δ, `$\le$` nie ≤
- CI sprawdza ten warunek automatycznie (krok `Lint`)

## CI

Push na `paper/**` → GitHub Actions buduje PDF → artefakt `raport-pdf`.

## Kompilacja lokalnie

```bash
cd paper && latexmk -pdf main.tex
# lub: pdflatex main.tex (x2)
```
