## Descripción
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.

To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!

Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.cylabacademy.net/library/cdf8425b82c6532c974b1a04fedc342a6d94dab1825f90cb223f67cb15193c15/myNetworkTraffic.pcap) and try to get the flag.

### Comando

```shell
tshark -r myNetworkTraffic.pcap -Y "tcp.len == 12 || tcp.len == 4" -T fields -e tcp.segment_data | xxd -p -r | base64 -d
```

#### 1. tshark

Herramienta de línea de comandos de Wireshark que permite analizar archivos de captura de red (.pcap).

#### 2. -r myNetworkTraffic.pcap

Indica el archivo de entrada que contiene el tráfico de red capturado.

#### 3. -Y "tcp.len == 12 || tcp.len == 4"


Filtro de visualización:

- tcp.len == 12 → paquetes con 12 bytes de datos
- tcp.len == 4 → paquetes con 4 bytes de datos
- || → operador OR

Se usan estos tamaños porque probablemente contienen fragmentos del mensaje.

#### 4. -T fields

Hace que la salida solo muestre campos específicos en lugar de todo el paquete.

#### 5. -e tcp.segment_data

Extrae el contenido del payload TCP en formato hexadecimal.

#### 6. |
Pipe que pasa la salida al siguiente comando.

#### 7. xxd -p -r

Convierte los datos:

- -p → formato hexadecimal plano
- -r → reverse (hexadecimal → binario)

#### 8. base64 -d

Decodifica el contenido en Base64 para obtener el mensaje original.

### Flujo del proceso

1. Leer archivo pcap
2. Filtrar paquetes específicos
3. Extraer datos TCP
4. Convertir de hex a binario
5. Decodificar Base64
6. Obtener el mensaje final