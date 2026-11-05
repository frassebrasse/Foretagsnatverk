# Labbjournal – företagsnätverk

## Syfte

Skapa en ny nätverksmiljö från grunden. Den här första topologin är ett **förslag** tills uppgiftsbeskrivningen har kontrollerats.

## Föreslagen adressplan

| Enhet | Nät | Adress | Route till annat nät |
| --- | --- | --- | --- |
| router | office + servers | 172.30.10.1/24 + 172.30.20.1/24 | Direktansluten |
| pc1 | office | 172.30.10.10/24 | via 172.30.10.1 |
| pc2 | office | 172.30.10.11/24 | via 172.30.10.1 |
| pc3 | servers | 172.30.20.10/24 | via 172.30.20.1 |
| server | servers | 172.30.20.20/24 | via 172.30.20.1 |

## Kontrollpunkter

- [ ] Kontrollera lärarens krav och anpassa topologin.
- [ ] Kör `docker compose config` utan fel.
- [ ] Bygg och starta containrarna.
- [ ] Kontrollera IP-adresser med `ip -br addr`.
- [ ] Kontrollera statiska rutter med `ip route`.
- [ ] Ping mellan pc1 och pc2 (samma nät).
- [ ] Ping från pc1 till servern (mellan näten).
- [ ] Ping från servern till pc1 (returväg).
- [ ] Dokumentera eventuella fel och lösningar.

## Testkommandon

```bash
docker compose exec router ip -br addr
docker compose exec router sysctl net.ipv4.ip_forward
docker compose exec pc1 ip route
docker compose exec pc1 ping -c 4 172.30.10.11
docker compose exec pc1 ping -c 4 172.30.20.20
docker compose exec server ping -c 4 172.30.10.10
```

## Testresultat (ej utförda)

| Datum | Från | Till | Förväntat | Faktiskt resultat |
| --- | --- | --- | --- | --- |
| – | pc1 | pc2 | Ping svarar | Ej testat |
| – | pc1 | server | Ping via router | Ej testat |
| – | server | pc1 | Ping via router | Ej testat |

## Slutsats

Fylls i efter praktisk verifiering i Codespaces.
