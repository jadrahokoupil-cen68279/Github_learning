# GitHub Learning

Ucebni repozitar pro procviceni prace s Gitem a GitHubem: vetve, commity,
pull requesty, code review, merge a reseni konfliktu.

## Struktura repozitare

Kazda oblast obsahuje stejne tri zeme:

```text
models/
  CZE/
  AT/
  SLK/
data/
  CZE/
  AT/
  SLK/
strategies/
  CZE/
  AT/
  SLK/
```

- `models` obsahuje modely a jejich konfigurace.
- `data` obsahuje vstupni data nebo jejich ukazky.
- `strategies` obsahuje strategie zpracovani a rozhodovani.
- `CZE`, `AT` a `SLK` oddeluji jednotlive zeme.

## Doporucene cviceni s vetvemi

1. Naklonuj repozitar a vytvor novou vetev:

	```bash
	git clone <URL_REPOZITARE>
	cd Github_learning
	git switch -c feature/cze-model
	```

2. Udelej zmenu v `models/CZE/`, vytvor commit a odesli vetev:

	```bash
	git add models/CZE/
	git commit -m "Add CZE model example"
	git push -u origin feature/cze-model
	```

3. Na GitHubu otevri Pull Request do `main`. Projdi diff, pridej review a
	zkus nejprve vetv sloucit pres Pull Request.

4. Pro trenink lokalniho merge vytvor dve vetve, ktere upravi stejnou cast
	souboru:

	```bash
	git switch main
	git pull
	git switch -c feature/first-change
	# proved zmenu a commit
	git switch main
	git switch -c feature/second-change
	# proved konfliktni zmenu a commit
	git switch main
	git merge feature/first-change
	git merge feature/second-change
	```

5. Pri konfliktu uprav oznacene casti, over vysledek a dokonc merge:

	```bash
	git status
	git add <OPRAVENE_SOUBORY>
	git commit
	git log --oneline --graph --decorate --all
	```

## Navrh commit zpravy

Pouzivej kratke a konkretni zpravy v imperativu, napr.:

```text
Add AT strategy example
Update SLK sample data
Fix merge conflict in model configuration
```

Kazde cviceni muze byt samostatny Pull Request. Po slouceni muzes vetev
smazat a pokracovat dalsim cvicenim v nove vetvi.
