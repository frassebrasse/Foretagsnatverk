# Företagsnätverk – Linux- och nätverkslabb

Ett övningsprojekt för dator- och kommunikationsteknik med Linux, Docker och nätverksfelsökning.

> **Projektstatus:** GitHub-repot innehöll ursprungligen bara denna README. Den tidigare Codespaces-labben behöver kontrolleras och dess filer läggas till innan vi påstår att en Docker-miljö kan startas från repot.

## Tidigare labb (att verifiera)

I den tidigare övningen användes följande containernamn:

- `router`
- `pc1`
- `pc2`
- `pc3`
- `server`

För `pc1` användes adressen `172.30.10.10/24`. Ping-test fungerade under en tidigare session. Övriga IP-adresser, nätverk och konfigurationsfiler måste verifieras mot Codespaces-miljön.

## Kom igång

1. Öppna repot i GitHub Codespaces.
2. Kontrollera om dina tidigare labbfiler finns i arbetsytan eller i ett annat repo.
3. Kör `git status` och `ls -la` för att se vad som finns lokalt.
4. Om en Compose-fil finns, granska den innan du startar containrar.
5. Följ [labbjournalen](docs/labbjournal.md) för att dokumentera verkliga resultat.

**Obs:** Det finns ännu ingen verifierad Compose-konfiguration i detta repo. Kommandot `docker compose up` ska därför inte förväntas fungera här förrän den har lagts till.

## Mål

- Förstå adressering, nätmask, standard-gateway och routing.
- Använda Linux-kommandon för att inspektera nätverk.
- Testa och felsöka anslutning mellan värdar.
- Dokumentera inställningar, tester och slutsatser på ett reproducerbart sätt.

## Säkerhet

Använd bara tillåtna labbnät och testmiljöer. Lägg inte in lösenord, API-nycklar eller andra hemligheter i Git.

## Projektmaterial

- [Labbjournal och kontrollpunkter](docs/labbjournal.md)
- [Git-ignore](.gitignore)
