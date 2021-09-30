# 10&10 Headers of Request/Response

Гуляя по просторам интернета я решил зайти на свой любимый сайт: [https://www.poxuy.com/](https://www.poxuy.com/)

Мой запрос выглядел следующим образом:

```css
GET / HTTP/2
Host: www.poxuy.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:92.0) Gecko/20100101 Firefox/92.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: ru-RU,ru;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

Ну  тут вобщем то все понятно, Host - доман на который я ссылаюсь, так как некоторые сайты используют виртуальный хостинг. User-Agent сообщает серверу о том, что я не поисковый бот, а просто использую браузер Огненной Лисы. Заголовок **Accept** говорит серверу о том, какие типы контента браузер способен понять. **Accept-Language** - языки которыми пользователь владеет, **Accept-Encoding** - кодировки для браузера, Connection указывает что делать с соединением (закрывать или нет), с заголовком **Upgrade-Insecure-Requests** я долго не мог разобраться и, как я понял он используется для того что бы браузер запрашивал http через http, а не через https. Группа заголовков Sec-Fetch связанна c https.

На свой странный запрос я получил вполне прямой ответ:

```css
HTTP/2 200 OK
server: nginx
date: Thu, 30 Sep 2021 13:13:40 GMT
content-type: text/html; charset=UTF-8
link: <https://www.poxuy.com/wp-json/>; rel="https://api.w.org/"
x-ray: p987:0.314/wn894:0.280/wa894:D=288335
content-encoding: br
```

Ну тут вобщем то тоже всен понятно. server - название сервера. date - как ни странно показывает дату загрузки документа, content-type - тип контента, link указывает на какой то связанный сайт, x-ray - ренген, content-encoding - выбранный тип кодировки.
