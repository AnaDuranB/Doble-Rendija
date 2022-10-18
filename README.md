# Experimento de la Doble Rendija

“Este es un experimento realizado a principios del siglo XIX por Thomas Young con el objetivo de apoyar la teoría de que la luz era una onda y rechazar la teoría de que esta estaba formada por partículas. 

Young hizo pasar un haz de luz por dos rendijas y vio que sobre una pantalla se producía un patrón de interferencias, una serie de franjas brillantes y oscuras alternadas.

Este resultado es inexplicable si la luz estuviera formada por partículas porque deberían observarse sólo dos franjas de luz frente a las rendijas, pero es fácilmente interpretable asumiendo que **la luz es una onda y que sufre interferencias. “ - BBC**

## Materiales
Para este experimento vamos a necesitar lo siguiente, sin embargo, puede ser realizado con distintos materiales.

- Un laser
- Papel aluminio
- Un cubreobjetos
- Marcador negro permanente
- Un visturí con buen filo.

### Gráficamente
![1parte](https://user-images.githubusercontent.com/87900830/196315329-abe8807d-87b8-46f9-b5c6-2f20ade32a11.png)
---
![Captura de pantalla 2022-10-17 203400](https://user-images.githubusercontent.com/87900830/196315346-b17f9186-8095-4438-b239-da40e34f838c.png)
---
![Captura de pantalla 2022-10-17 204017](https://user-images.githubusercontent.com/87900830/196315366-2c7f9e13-0be6-46be-8a02-d23e1ad76320.png)

Los fotones o partículas de materia (como un electrón) producen un patrón de onda cuando se usan dos rendijas.

## Procedimiento

1. Cubrir un lado del cubreobjetos con el aluminio, pegarlo en los alrededores para asegurar que este no se mueva.
2. Pintar el lado con aluminio con ayuda del marcador negro.
3. Con el bisturí recortar en el aluminio dos líneas rectas paralelas lo más cercanas posibles sin dañar el aluminio entre ellas, esta será nuestra rendija.
4. Ubicar la rendija entre luna pared y el puntero laser.

![WhatsApp Image 2022-10-17 at 8 55 48 PM](https://user-images.githubusercontent.com/87900830/196317822-ce1f9d20-b7ed-46b1-b9da-8b7e57fa6cdc.jpeg)

## Evidencias del experimento
![WhatsApp Image 2022-10-17 at 10 38 19 AM (1)](https://user-images.githubusercontent.com/87900830/196315608-a1fedb9f-4648-4069-be7a-792ac17f2096.jpeg)
---
## Simulación haciendo uso de la librería
Este experimento puede ser representado como sistemas probabilísticos, y de la misma forma, llevado a nuestra librería de la siguiente forma:

```python
def exp_3(matriz,v_inicial):
    print("Experimento Cuantico con 2 rendijas")
    matriz = [[(0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0)],
              [(1 / math.sqrt(2), 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0)],
              [(1 / math.sqrt(2), 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0), (0, 0)],
              [(0, 0), (-1 / math.sqrt(6), 1 / math.sqrt(6)), (0, 0), (1, 0), (0, 0), (0, 0), (0, 0), (0, 0)],
              [(0, 0), (-1 / math.sqrt(6), -1 / math.sqrt(6)), (0, 0), (0, 0), (1, 0), (0, 0), (0, 0), (0, 0)],
              [(0, 0), (1 / math.sqrt(6), -1 / math.sqrt(6)), (-1 / math.sqrt(6), 1 / math.sqrt(6)), (0, 0), (0, 0),
               (1, 0), (0, 0), (0, 0)],
              [(0, 0), (0, 0), (-1 / math.sqrt(6), -1 / math.sqrt(6)), (0, 0), (0, 0), (0, 0), (1, 0), (0, 0)],
              [(0, 0), (0, 0), (1 / math.sqrt(6), -1 / math.sqrt(6)), (0, 0), (0, 0), (0, 0), (0, 0), (1, 0)]]
    print("Matriz Asociada: ")

    for i in matriz:
        print(i)
    tics = 3

    X = [x[:] for x in matriz]
    for i in range(2, tics + 1):
        X = lc.productomatricesComplex(X, matriz)
    print("Estado inicial: ")
    v_inicial = [[(1, 0)], [(0, 0)], [(0, 0)], [(0, 0)], [(0, 0)], [(0, 0)], [(0, 0)], [(0, 0)]]

    print("Numero de tics:", tics)
    for i in v_inicial:
        print(i)
    posicion = lc.accmatriz_vectorcplx(X, v_inicial)

    print("Vector Final")
    probabilidades = []
    for i in range(len(posicion)):
        probabilidades += [(lc.modulocplx(posicion[i])) ** 2]
    for i in probabilidades:
        print(i)
    lc.graficas(lc.n_tics(matriz), probabilidades)
```
Lo que nos va a retornar,

![192081749-336ee4d3-4ff9-42b8-ab1d-dce9ef788e5a3](https://user-images.githubusercontent.com/87900830/196323924-e62e480f-cef3-40a1-bb5e-19726088336b.png)

![192081718-dbed7709-65f0-449d-b533-8c853cee2132](https://user-images.githubusercontent.com/87900830/196323026-e8c00e8d-a3c7-4803-b66a-8ea7879e36eb.png)



## Autores
- Laura Natalia Rojas
- Ana María Durán Burgos
- Felipe Eduardo Calvache
