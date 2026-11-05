# Labbjournal – företagsnätverk

## Bekräftat från tidigare övning

| Enhet | IP-adress | Status |
| --- | --- | --- |
| router | Ej verifierad | Förekom i labbmiljön |
| pc1 | 172.30.10.10/24 | Ping-test rapporterades fungera |
| pc2 | Ej verifierad | Förekom i labbmiljön |
| pc3 | Ej verifierad | Förekom i labbmiljön |
| server | Ej verifierad | Förekom i labbmiljön |

**Viktigt:** Tabellen är historiska anteckningar, inte ett aktuellt testresultat från GitHub.

## Första inventering i Codespaces

Kör dessa ofarliga läskommandon i arbetsytans terminal:

```bash
pwd
git status
git remote -v
ls -la
find . -maxdepth 3 -type f -not -path './.git/*' | sort
docker ps -a
```

Kontrollera att du är i rätt repo och att inga lokala ändringar skrivs över. Om labbfilerna finns här, dokumentera var Dockerfile, Compose-filen och eventuella skript ligger.

## Nätverkstester (när containrarna är igång)

Kontrollera först filnamn och faktiska containernamn innan du kör kommandon:

```bash
docker ps
docker exec pc1 ip -br address
docker exec pc1 ip route
docker exec pc1 ping -c 4 172.30.10.10
```

Det sista kommandot testar bara `pc1`s egen tidigare IP-adress, **inte** kontakt med servern eller routing. För ett verkligt anslutningstest: ersätt måladressen med en verifierad IP till en annan container.

## Att fylla i

- [ ] Hitta ursprungliga labbfiler.
- [ ] Dokumentera alla IP-adresser och nätmasker.
- [ ] Kontrollera standard-gateway på varje klient.
- [ ] Testa klient till klient.
- [ ] Testa klient till server.
- [ ] Kontrollera om kommunikation mellan subnät faktiskt passerar routercontainern.
- [ ] Skriv ned felsökningsresultat och slutsats.

## Resultatmall

| Datum | Källa | Mål | Kommando | Resultat | Kommentar |
| --- | --- | --- | --- | --- | --- |
| Ej testat | pc1 | annan enhet | ping | Ej testat | Fylls i efter verifiering |
