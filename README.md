# Foto-Anita

Web stranica fotostudija Foto Anita, Valpovo.

## Struktura

- `index.html` — naslovnica (hero, o nama, usluge, carousel galerija, recenzije, kontakt)
- `galerije/` — stranice galerija, jedna po paru mladenaca
- `galerije/_template.html` — predložak za nove galerije
- `galerije/slike/<par>/` — optimizirane slike za web (max 1600px, q82)
- `Slike za Web/` — originali, **nisu u gitu** (5.8GB, ostaju lokalno)

## Dodavanje nove galerije

1. Ubaci originale u `Slike za Web/Ime & Ime/`
2. Optimiziraj ih u `galerije/slike/ime-ime/` kao `01.jpg`, `02.jpg`…:
   ```
   convert ulaz.JPG -auto-orient -resize "1600x1600>" -quality 82 -strip izlaz.jpg
   ```
3. Kopiraj `_template.html`, popuni naslov i `photos` niz
4. Dodaj karticu u carousel u `index.html`

## TODO lista

- [x] centrirati sekciju services
- [x] dodati vlastite slike
- [x] Napraviti stranice za galerije mladenaca
- [x] Napraviti Formspree racun i dodati endpoint da forma radi direktno
- [x] ~~radi sigurnosti dodati formspree endpoint u .env~~ — nije potrebno.
      Formspree endpoint je javan po dizajnu: mora biti u client-side kodu da
      bi ga preglednik mogao pozvati, pa ga svatko vidi u source-u. Nije tajna.
      Zloupotreba se sprječava u Formspree dashboardu (dozvoljene domene,
      reCAPTCHA, rate limiting) + honeypot polje koje forma već ima.

### Preostalo

- [ ] `og:image` u `index.html` treba apsolutni URL s pravom domenom
      (npr. `https://foto-anita.com/galerije/slike/kristiana-miroslav/15.jpg`)
- [ ] Zamijeniti placeholder recenzije pravima s Googlea
- [ ] Provjeriti je li kontakt mail `foto.anita96@gmail.com` ispravan
