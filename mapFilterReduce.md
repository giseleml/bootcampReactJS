# Desmitificando funções: map, filter e reduce.

## Filter: pega um array de elementos e os filtra de acordo com um teste lógico. 
Devolve um novo array.

const filterElements = arr.filter((item) => {})

O filter recebe uma função callback que será executada para cada elemento do array. Se o teste lógico der true, o elemento é colocado na nova array, do contrário não.

## Map: chama a função callback para cada elemento do array e retorna um novo array com a mesma quantidade de elementos do array inicial. O forEach funciona de forma similar, porém não retorna nada. Para fazê-lo retornar algo vai precisar colocar o forEach fora da variável que será agora um array vazio, e usar .push() para colocar os itens dentro dela. 

## Reduce: executa uma função pra cada elemento retornando um ÚNICO valor como resultado final.

const totalWeight = pets.reduce((total, pet) => {
  return total
, 0)

- parametro1 = total: valor acumulado a cada iteração

- parametro2 = pet: item a ser iterado

- parametro3 = 0: valor inicial da variavel total (parametro1)
