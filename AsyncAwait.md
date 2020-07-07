# Async/Await
Syntax sugar de promises, buscando simplificar sua forma de uso. Por baixo dos panos a promise funciona igual, porém deixando o código mais legível e que até mesmo parece ser síncrono.

- Async: Informa pro compilador que dentro da função ocorrerão funções assíncronas. Faz com que o retorno da função seja automaticamente uma promise. 
Todo o código interno da função será envolvido por uma promise que será retornada. 

Exemplo:
const testFunc = async() => {
	const apiResponse = await fetch(<url>)
	.then(response => console.log(response)
	// OU console.log(await apiResponse)
}

O then recebe uma função com o resultado da promise. Aceita uma função callback de sucesso e de falha (resolve, reject).

É possível tratar erros:

try {
	const res = await promise
	console.log(res)
} catch (err) {
	console.error(err)
}

Funções como map, filter, etc. não podem usar 'await', pois não são assíncronas.

Outra forma de tratar erros:

promise.then(data => console.log(data)
	.catch(err => console.error(err))
	.then(() => console.log('end'))
)