ZAD 1
odp z przegladarki/curl: 
{"status":"ok"}
lini z backend logs: 
172.18.0.1 - - [13/Nov/2026 19:54:21] "GET /health HTTP/1.1" 200 -

ZAD 2
docker run --rm --network breach-net healthcheck-probe
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100     16 100     16   0      0    827      0                              0
{"status":"ok"}
backend: OK

docker run --rm healthcheck-probe
curl: (6) Could not resolve host: backend (Domain name not found)

docker stop backend
docker run --rm --network breach-net healthcheck-probe
curl: (6) Could not resolve host: backend (Domain name not found)

Ponieważ przez to że healthcheck-probe nie jest w sieci backendu, to nie zna adresu ip, ktory zostal przypisany do nazwy backend przez DNS tamtej sieci

ZAD 3
Po restarcie:
notatka
Po rm -f:
cat: /tmp/notatka.txt: No such file or directory

Fri Nov 13 19:55:41 UTC 2026
Fri Nov 13 19:55:53 UTC 2026

Ponieważ /tmp/ znajduje sie w systemie plików kontenera. historia.txt znajdowała się w woluminie. Lista wycieków to bind mount, więc przetrwałaby, ponieważ znajduje się w systemie plików hosta.