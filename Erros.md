# Tratamento de Erros
Busca trazer mais resiliência ao software; "Ao falhar, o que será mostrado para o usuário?". Traz mais segurança. 

Exemplo:
const soma = (a, b) => a + b

- E se for passado uma string, undefined, etc?

- Tratamento de funções:

const soma = (a, b) => {
 if (typeof a === number && typeof b === number) {
   return a + b
  } else {
    return -1 
    }
}

- Tratamento em forms:

<form>
  <input type="text" required/>
</form>

É importante validar dados obrigatórios do form. 
Pode user CAPTCHA para evitar bots maliciosos; 

- Tratamento de Retorno de APIS:

fetch(apiURL)
.then(data => data.json())
.then(data => console.log(data))
.catch(error => {
  exibirMensagem(error.code);
})

exibirMensagem(codigo) {
  if (codigo === 401) {
    alert("Faça login para continuar")
  }
  if (codigo === 404) {
    alert("Recurso não encontrado")
  }
   if (codigo === 500) {
    alert("Erro interno do servidor")
  }
}
   
- Tratamento de Componentes
Em JS usamos PropTypes.
Podemos usar linguagens tipadas como TypeScript definindo interfaces.

Exemplo de Prop-Types:

const Basic = ({ name }) => (
  <p>Meu nome é {nome}</p>
)

Basic.propTypes = {
  name: PropTypes.string
}
