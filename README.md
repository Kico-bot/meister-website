# webseiten-meister.de

Website von **Webseiten-Meister**: Webentwicklung für öffentliche Auftraggeber, Vereine und KMU.
Gebaut mit [Astro](https://astro.build) als statische Seite, ausgeliefert über **Cloudflare Pages**.

## Lokal entwickeln

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # erzeugt ./dist
```

## Inhalte pflegen

- Zentrale Angaben (Name, E-Mail, Telefon, Anschrift): `src/site.ts`
- Seiten: `src/pages/*.astro`
- Design: `src/styles/global.css`
- Sicherheits-Header für Cloudflare: `public/_headers`

## Cloudflare Pages anbinden (einmalig)

1. Cloudflare Dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
2. Repository `Kico-bot/meister-website` auswählen
3. Build-Einstellungen:
   - Framework preset: **Astro**
   - Build command: `npm run build`
   - Build output directory: `dist`
   - Umgebungsvariable `NODE_VERSION` = `22`
4. **Save and Deploy**. Danach wird jeder Push auf `main` automatisch veröffentlicht, jeder andere Branch bekommt eine Vorschau-URL.
5. **Custom domains** → `webseiten-meister.de` und `www.webseiten-meister.de` hinzufügen.
   Liegt die Domain bei einem anderen Registrar: Nameserver auf Cloudflare umstellen oder CNAME auf `<projekt>.pages.dev` setzen.

## Vor dem Livegang

- [ ] Anschrift (und optional Telefon, USt-IdNr.) in `src/site.ts` eintragen – Pflicht fürs Impressum
- [ ] Postfach `kontakt@webseiten-meister.de` einrichten (z. B. Cloudflare Email Routing)
- [ ] Preise unter `/pakete/` prüfen
- [ ] Referenzen ergänzen, sobald vorhanden
