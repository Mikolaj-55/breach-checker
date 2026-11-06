ZADANIE 1
<missing>      19 hours ago     LABEL maintainer=NGINX Docker Maintainers <d…   0B        buildkit.dockerfile.v0
{"autor":"Mikołaj Bembnista","data":"2026-11-06","maintainer":"Mikolaj-55@users.noreply.github.com"}
Widać moją wartość dockerfile ponieważ nadpisuje ona wartość dziedziczoną z obrazu mbazowego, 0B mają metadane. 


ZADANIE 2
Fri Nov  6 13:57:05 UTC 2026
Fri Nov  6 13:57:05 UTC 2026
CONTAINER ID   IMAGE                   COMMAND                  CREATED         STATUS         PORTS                                     NAMES
8999761f154b   mikolaj-frontend:zad2   "/docker-entrypoint.…"   2 minutes ago   Up 2 minutes   0.0.0.0:8022->80/tcp, [::]:8022->80/tcp   zad2b
bfd46be679de   mikolaj-frontend:zad2   "/docker-entrypoint.…"   3 minutes ago   Up 3 minutes   0.0.0.0:8021->80/tcp, [::]:8021->80/tcp   zad2

Ponieważ został dodany w RUN, który wykonuje się tylko przy budowaniu obrazu.


ZADANIE 3
root   /usr/share/nginx/html;

Ponieważ nginx szuka pliku index.html właśnie w tym konkretnym miejscu, czyli jego domyślnym katalogu głównym (root).


ZADANIE 4
PS C:\Users\Student_PL\Documents\MB\breach-checker> docker exec zad4 ls /usr/share/nginx
html
index.html
script.js
style.css
zadanie03.md
PS C:\Users\Student_PL\Documents\MB\breach-checker> docker exec zad4 ls /usr/share/nginx/html
50x.html
build.txt
index.html

htmlhint sprawdził plik z /nginx/html, ponieważ tak napisaliśmy w Dockerfile. build przeszedł ponieważ htmlhint nie wyrzucił błędu, tzn. plik był poprawny. Widzimy stronę główną nginx ponieważ nginx sprawdza katalog /nginx/html, w którym jest domyślny index.html, podczas gdy nasz jest w /nginx


ZADANIE 5
PS C:\Users\Student_PL\Documents\MB\breach-checker> docker rmi breach-checker-frontend:latest
Untagged: breach-checker-frontend:latest
PS C:\Users\Student_PL\Documents\MB\breach-checker> docker rmi breach-checker-frontend:v2
Untagged: breach-checker-frontend:v2
Deleted: sha256:fbb955ff920dcf55ee5ed328821f46e690522c56c5a453fc9525c56e6c25603c

rmi usuwa obraz z dysku, kiedy zostaje tylko jeden tag tego obrazu, w przeciwnym wypadku usuwa tylko tag.