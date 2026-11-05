# Företagsnätverk – egen nätverkslabb

Det här projektet byggs **från grunden** för att öva på Linux, Docker, IP-adressering, routing och felsökning. Det återanvänder inte filer från en tidigare övning.

> **Första utkastet:** Topologin nedan är ett förslag, inte bekräftade lärarkrav. Konfigurationen har ännu inte körtestats i Codespaces.

## Topologi (förslag)

```text
 office 172.30.10.0/24              servers 172.30.20.0/24
 pc1 (.10) ─┐
 pc2 (.11) ─┼─ router (.10.1 / .20.1) ─┬─ pc3 (.10)
            │                         └─ server (.20)
```

Routercontainern är ansluten till båda näten och vidarebefordrar IPv4-paket. PC-klienterna och servern har statiska rutter till det andra subnätet via routercontainern. Docker-nätens gatewayadresser slutar på `.254`; dessa är inte vår labbrouter.

## Starta i Codespaces

Se till att Docker är tillgängligt. Från repots rot:

```bash
docker compose config
docker compose up -d --build
docker compose ps
```

Prova sedan:

```bash
docker compose exec pc1 ip -br addr
docker compose exec pc1 ip route
docker compose exec pc1 ping -c 4 172.30.10.11
docker compose exec pc1 ping -c 4 172.30.20.20
```

Det första ping-testet går inom samma subnät; det andra kräver routing. Om ett test misslyckas, dokumentera resultatet och felsök — det är en del av uppgiften.

Stoppa miljön med `docker compose down`.

## Filer

- `compose.yaml` – fem containrar och två isolerade labbnät.
- `Dockerfile` – Alpine Linux med `ip` och `ping`.
- `docs/labbjournal.md` – checklistor och testresultat.

## Nästa steg

Verifiera uppgiftens verkliga krav (antal enheter, IP-plan, tjänster, routing och eventuella säkerhetsregler). Justera därefter förslaget och kör testerna i Codespaces.

**Säkerhet:** Spara aldrig lösenord, tokens eller andra hemligheter i Git.
