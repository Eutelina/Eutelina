# Trabalho de Bases de Programação

Nome Aluno: Eutelina Cristina Ramos Machado
Matrícula: 1230115563
e-mail: 14799768735@veigadealmeida.edu.br / eutelinacrm@gmail.com

Parabéns você foi contratado para trabalhar no projeto Terra2. Estamos montando um sistema de simulação da Terra nos mínimos detalhes.
Seu primeiro trabalho é projetar um sistema que trabalhe com informações geográficas. Para isso você precisa esboçar os seguintes algoritmos usando pseudocódigo.

## Resposta 1
1) crie uma função em portugol que leia coordenadas geográficas, latitude e longitude e converta de graus para radianos.

pseudocodigo aqui

```Função que converte de Gruas para Radianos ```
Função ConverterRadianos(latG, longG)
   
  PI = 3.14                      ```Constante do tipo Float utilizada na conversão ```
  latR = latG * PI / 180
  longR = longG * PI / 180
  Retornar (latR, longR)
  
Fim Função

---

## Resposta 2
2) Crie uma função em portugol que receba duas posições com latitude e longitude e calcule a distância entre elas. Deve usar a Formula de Harvesine.

pseudocodigo aqui

```Função que calcula a distância enrte dois pontos utilizando a formula de Harvesine```
Função CalcularDistanciaHaversine(lat1, long1, lat2, long2)

   R = 6371      ```Constate para o valor do raio da terra```

  ```Chama a função que converte de Graus para Radianos e atribui o valor para novas variáveis```
   lat1R, long1R = ConverterRadianos (lat1, long1)  
   lat2R, long2R = ConverterRadianos (lat2, long2)

    ``` Diferença entre as coordenadas ```
  difLat = lat2R - lat1R
  difLong = long2R - long1R
  
  ```Fórmula de Harversine```
  a = (sen(difLat / 2) * sen(difLat / 2)) + cos(lat1R) * cos(lat2R) *(sen(difLong / 2) * sen(difLong / 2))
  b = 2 * a * tan(2 * raiz (a), raiz (1 - a))

  ```Calculo da Distância```
  dist = R * b

  Retornar (dist)
  
Fim Função

---

## Resposta 3
3) crie um programa em portugol que calcule a antípoda de uma localidade informada com latitude e longitude. Além disso tem que calcular a distância entre as antipodas usando a função que você criaram.

pseudocodigo aqui

Função CalcularAntipoda(lat, long)
    ```Calcular a antípoda, são pontos que têm latitudes iguais em hemisférios opostos (norte – sul) e longitudes que diferem de 180∘ em hemisférios opostos (leste – oeste)```
    antipodaLat = -lat           
    antipodaLong = long + 180 

  Se antipodaLong > 180 Então
        antipodLong = antipodaLong - 360
  Fim Se
  
  Retornar (antipodaLat, antipodaLong)
    
Fim Função

```Programa principal```
Procedimento Principal
    Escrever("Digite a latitude: ")
    Ler(lat)
    Escrever("Digite a longitude: ")
    Leia(long)
    antipodaLat, antipodaLong = CalcularAntipoda(lat, long)
    distancia = CalcularDistanciaHaversine(lat, long, antipodaLat, antipodaLong)
    Escrever ("As coordenadas da antípoda são:")
    Escrever("Latitude: ", antipodaLat)
    Escrever("Longitude: ", antipodaLong)
    Escrever("A distância entre as coordenadas originais e suas antípodas em quilômetros, é: ", distancia)

Fim Procedimento




