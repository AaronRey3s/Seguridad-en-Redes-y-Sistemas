## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap). Recover the flag that was pilfered from the network.

## Solución
aaron-tank_3@aaron-tankVirtualBox:~/shark_on_wire_2$ sudo apt update
sudo apt install python3.14-venv -y
aaron-tank_3@aaron-tankVirtualBox:~/shark_on_wire_2$ cd ~/shark_on_wire_2
rm -rf venv
python3 -m venv venv
source venv/bin/activate
(venv) aaron-tank_3@aaron-tankVirtualBox:~/shark_on_wire_2$ pip install scapy
Collecting scapy
(venv) aaron-tank_3@aaron-tankVirtualBox:~/shark_on_wire_2$ cp shark-on-wire-2-capture.pcap capture.pcap
(venv) aaron-tank_3@aaron-tankVirtualBox:~/shark_on_wire_2$ nano solve.py
(venv) aaron-tank_3@aaron-tankVirtualBox:~/shark_on_wire_2$ python3 solve.py
academy{p1LLf3r3d_data_v1a_st3g0}
## Notas Adicionales


## Referencias