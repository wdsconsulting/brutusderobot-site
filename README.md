# BrutusDeRobot — site

Statische site voor de **BrutusDeRobot Agent**: één pagina met een korte
beschrijving van de applicatie en het bijhorende privacybeleid.

Deze repo bestaat in de eerste plaats omdat **Google OAuth-verificatie** een
publiek bereikbare homepage én een privacybeleid vereist voor de OAuth-client.
Er staat bewust geen tracking, geen cookies en geen JavaScript in.

## Structuur

| Bestand | Doel |
| --- | --- |
| `index.html` | Homepage: wat de applicatie is, wie ze gebruikt, contactadres |
| `privacy.html` | Privacybeleid: welke Google-scopes, hoe data gebruikt/opgeslagen wordt |
| `CNAME` | Aangepast domein voor GitHub Pages (`brutusderobot.wds-consulting.be`) |

## Live

- **Primair:** <https://brutusderobot.wds-consulting.be>
- **GitHub Pages-URL:** <https://wdsconsulting.github.io/brutusderobot-site/>
  → stuurt door (301) naar het aangepaste domein

## GitHub Pages-configuratie

| Instelling | Waarde |
| --- | --- |
| Source | branch `main`, map `/` (root) |
| Build type | legacy (rechtstreeks uit de repo, geen build-stap) |
| Aangepast domein | `brutusderobot.wds-consulting.be` (via `CNAME`) |
| HTTPS | certificaat goedgekeurd, geldig t/m 16-12-2026 |
| HTTPS enforced | **uit** — de site is ook over HTTP bereikbaar |

Er is geen workflow of actie nodig: wat in `main` staat, is wat online staat.
Een push naar `main` publiceert dus meteen.

## Wijzigen

1. Pas `index.html` of `privacy.html` aan.
2. Commit en push naar `main`.
3. GitHub Pages herbouwt automatisch (meestal binnen een minuut).

```bash
git clone git@github.com:wdsconsulting/brutusderobot-site.git
cd brutusderobot-site
# ... aanpassen ...
git add -A && git commit -m "Update privacybeleid" && git push
```

## ⚠️ Aandachtspunten

- **Wijzig het domein niet zonder reden.** Dit adres staat geregistreerd bij de
  Google OAuth-consentconfiguratie. Verandert het, dan moet de verificatie
  opnieuw. Dat geldt ook voor het pad: `/privacy.html` is de opgegeven
  privacybeleid-URL.
- **Houd `privacy.html` in lijn met de werkelijkheid.** Als er Google-scopes
  bijkomen of verdwijnen (bv. Calendar, Drive), moet het beleid mee.
- **Geen secrets in deze repo.** De repo is publiek; er horen geen tokens,
  sleutels of persoonlijke gegevens in — enkel de teksten die publiek moeten zijn.

## Contact

Wouter De Saedeleer (WDS-Consulting) — wouterds.wds@gmail.com
