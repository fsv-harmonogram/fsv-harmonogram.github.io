# Harmonogram FSV UCM — návod na nasadenie cez GitHub Pages

Tento priečinok obsahuje kompletnú stránku pripravenú na bezplatný hosting cez GitHub Pages, vrátane vlastnej ikonky (logo veže FSV UCM) pre záložku prehliadača aj pre pridanie na plochu telefónu.

## Čo je v priečinku

- `index.html` — samotná stránka s harmonogramom
- `favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png` — ikonka pre záložku v prehliadači
- `apple-touch-icon.png` — ikonka pre pridanie na plochu iPhone/iPad
- `android-chrome-192x192.png`, `android-chrome-512x512.png` — ikonky pre Android
- `manifest.json` — umožňuje pridať stránku na plochu telefónu ako "appku"

## Krok 1: Založ si GitHub účet (ak ho ešte nemáš)

Choď na [github.com](https://github.com) a zaregistruj sa. Je to zadarmo.

## Krok 2: Vytvor nový repozitár

1. Po prihlásení klikni vpravo hore na **+** → **New repository**.
2. Daj mu názov, napr. `fsv-harmonogram`.
3. Nastav ho ako **Public** (musí byť verejný, aby GitHub Pages fungovali zadarmo).
4. Nezaškrtávaj žiadne ďalšie voľby (README, .gitignore) — necháme prázdny repozitár.
5. Klikni **Create repository**.

## Krok 3: Nahraj súbory

1. Na stránke novo vytvoreného repozitára klikni na odkaz **uploading an existing file** (alebo **Add file → Upload files**).
2. Pretiahni tam **všetky súbory z tohto priečinka** (index.html, favicon.ico, favicon-16x16.png, favicon-32x32.png, apple-touch-icon.png, android-chrome-192x192.png, android-chrome-512x512.png, manifest.json). README.md nemusíš nahrávať, je len pre teba.
3. Dole klikni **Commit changes**.

## Krok 4: Zapni GitHub Pages

1. V repozitári choď na **Settings** (hore v menu repozitára).
2. V ľavom menu klikni na **Pages**.
3. Pri **Source** vyber **Deploy from a branch**.
4. Pri **Branch** vyber `main` a priečinok `/ (root)`.
5. Klikni **Save**.
6. Počkaj minútu-dve — GitHub Pages vygeneruje adresu v tvare:

   `https://tvoj-github-username.github.io/fsv-harmonogram/`

   Túto adresu nájdeš znova v Settings → Pages hore, keď je nasadenie hotové (zobrazí sa zelený box "Your site is live at...").

## Krok 5: Over si ikonku

Otvor si vygenerovanú adresu v mobile aj desktope:

- V prehliadači by sa mala v záložke zobraziť oranžová ikonka s vežou FSV.
- Na iPhone: v Safari klikni na **Zdieľať → Pridať na plochu** — mala by sa ukázať tá istá ikonka namiesto screenshotu stránky.
- Na Androide: v Chrome cez menu **Pridať na plochu** rovnako.

## Ako neskôr aktualizovať obsah (nové akcie)

Zoznam akcií je v `index.html` v sekcii `<script>`, v poli `EVENTS`. Každá akcia je jeden riadok v tvare:

```js
{id:'e20', title:'Názov akcie', cat:'fsv', start:'2027-01-15'}
```

- `cat` môže byť `fsv`, `veltrh` alebo `iny`
- `end` je nepovinné pre viacdňové akcie
- `note` a `location` sú nepovinné doplňujúce texty
- `tbd:true` označí akciu bez presného dátumu (zobrazí sa "presný dátum bude upresnený")

Po úprave stačí v GitHub repozitári otvoriť `index.html` (ceruzka = Edit), zmeniť riadok a dať **Commit changes** — stránka sa do minúty aktualizuje na živej adrese.

## Poznámka k živému spoločnému editovaniu

Toto riešenie je statická stránka — úpravy robíš ty (alebo ktokoľvek s prístupom do GitHub repozitára) priamo v kóde. Ak by ste chceli, aby si doktorandi mohli sami pridávať akcie cez jednoduchý formulár priamo v appke (bez zásahu do kódu), treba k tomu pripojiť databázu (napr. Firebase) — to je ďalší krok, ktorý vieme dorobiť samostatne.
