
## Descripción
Can you figure out how this program works to get the flag?

## Solución
nc chatelaine.cylabacademy.net 45927

3

func_table

func_table[:96]+'win'+' '*29

4

python3 -c "print(bytes(int(x,16) for x in input('Hex: ').split()).decode())"

academy{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_3e57e558}


## Notas Adicionales


## Referencias

