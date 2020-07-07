# Performance Web

## Carregamento

- Minificar arquivos do front-end (HTML, CSS e JS).
|_ Usar cdn para bibliotecas de terceiros.
- Habilitar gzip: No servidor o módulo gzip pode ser habilitado para o tráfego dos arquivos entre navegador e servidor serem zipados, comprimindo os arquivos.
Com isso o tempo de request é diminuido.
- Lazy Loading: Evita requisitar coisas que não são necessárias no momento para o usuário. As informações são carregadas conforme o usuário realmente as acessa. Requisições sob demanda.
- Carregar de forma assíncrona: disparar várias requisições paralelamente, sem uma ter que esperar a outra.
- Tratar carregamento do iframe. Precisa ser renderizado por último na página.
- Tratar imagens: imagens não deve ser redimensionada pelo CSS, está mandando bytes desnecessários para o browser. Comprimir, abaixar qualidade e usar tamanhos corretos.
- Liberar o carregamento da página e carregar o resto depois (Above The Fold): entregar conteúdo visto primeiro antes do resto.

## Execução
- setTimeout: determina que algo será executado daqui x tempo, em milisegundos. 
---------------------------
# Promises
Fluxo assíncrono.

- Código síncrono: fluxo linear. 
Exemplo:
const arr = [1, 2, 3]
const length = arr.length
const double = arr.map(num = num * 2)
return double

Uma linha depende da outra para ser executado. Aproximadamente 9s para executar esse código.

- Código assíncrono: recursos independentes podem ser carregados de forma paralela.
Exemplo:
Requests HTTP
Leitura de arquivos 
I/O
Acesso a serviço externo 

Ao invés do fluxo linear, as requisições são executadas ao mesmo tempo e o tempo total será o da maior promise (maior requisição), diminuindo o tempo de execução do código.

## Event Loop em Node.js

- Event Loop: um loop infinito que roda no Node.js recebendo suas requisições e armazenando o que precisa ser executado.

Ao fazer a requisição ela vai pro Event Loop, e também uma função de callback que fica registrada numa fila. Quando essa fila acabar ela executará seu callback:

Request => Event Loop (single thread) =>
Intensive Operation => 
Operation Complete => Event Loop => Trigger Callback => Requests

## Criando uma promise

Uma promise é inicializada usando a keyword new, recebe como parâmetro resolve e reject, e retorna os métodos then e catch.

const randomPromise = new Promise((res, rej) => {
	.then(resposta)
	.catch(erro)
})
