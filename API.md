# Comunicação entre Aplicações
No React há 3 bibliotecas populares para conectar a aplicação com um ou mais servidores HTTP;

## Fetch API
* Biblioteca nativa do browser. 
* Suporta service workers. 
* Não envia e nem recebe cookies (precisa definir na opção credentials). 
* Não rejeita o status do erro HTTP, apenas rejeita em caso de instabilidade de conexão.

Fetch por padrão é uma promise, de modo que os métodos .then() e .catch() podem ser utilizados nela.

- Exemplo de get:

fetch(apiURL).then(response => response.json())
.catch(error => alert(error))

- Exemplo de post:
const novoDado = {id: 2, nome: 'Jane Doe'}
fetch(apiURL, { 
  method: 'POST',
  body: JSON.stringify(novoDado)
})
.then(response => response.json())
.then(data => alert(data))
.catch(error => alert(error))

- Exemplo de delete: 
const novoDado = {id: 2, nome: 'Jane Doe'}
fetch(apiURL, { 
  method: 'DELETE'
})

- Exemplo de put: 
const novoDado = {id: 2, nome: 'Jane Doe'}
fetch(apiURL, { 
  method: 'PUT',
  body: JSON.stringify(novoDado)
})

## AJAX (Asynchronous JavaScript and XML)
Não é uma linguagem de programação, mas sim uma combinação do objeto
XMLHttpRequest (nativo do browser, usado para pedir dados de um web server),
JavaScript e HTML DOM (para usar ou exibir os dados).
Podem usar XML para transportar os dados, mas é igualmente comum transporta-los
como texto puro ou JSON.

- Exemplo de GET:
xhttp.open("GET", "demo_get.asp", true);
xhttp.send();

- Exemplo de POST:
xhttp.open("POST", "ajax_test.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Henry&lname=Ford");

## Axios 
* Biblioteca muito usada com React. 
* Cross-browser.
* Pode monitorar o progresso de um request.
* Melhor tratamento de erros e melhores testes.
* Suporte limitado para PWA.

- Exemplo de GET:
import axios from 'axios'

// A promise já vem resolvida então o dado já pode ser manipulado.

axios.get(apiURL)
.then(data => alert(data))
.catch(error => alert(error))

- Exemplo de POST:
import axios from 'axios'

// Pode ser passado JSON sem precisar de stringify.

axios.post(apiURL, {
 nome: 'Heleieth',
 area: 'Letras'
})
.then(data => console.log(data))

- Exemplo de DELETE:
import axios from 'axios'

axios.delete(apiURL/id para ser deletado)
.then(data => alert(data))

- Exemplo de PUT:
import axios from 'axios'

axios.put(apiURL, {
  nome: "Sonia",
  area: "Física"
})
