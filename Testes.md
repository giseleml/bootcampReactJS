# Testes em React

## TDD (Test Driven Development)
Tem por objetivo escrever um teste antes mesmo de criar a funcionalidade, antecipando erros
a nível de desenvolvimento. 

### Ciclo de Vida:

1. RED: Escrever um teste que falha
2. GREEN: Criar uma função que passe no teste
3. REFACTOR: Refatorar e implementar a lógica dentro da aplicação.

### Tipos de Testes
* Unitários: Testar cada unidade da aplicação; Como funções, componentes, serviço, etc.
* End to End (E2E): Testar o fluxo da aplicação.

Para fazer estes testes existem várias bibliotecas, como:
- Jest (usa Jasmine)
- react-testing-library 
- Shallow, Enzyme
- Chai 
- Mocha

- Exemplo de criação de teste:

Função:
//soma.js
function soma (a, b) {
  return a + b 
}

Teste:
// soma.test.js
import { soma } from './soma

describe('Soma dois números', () => {
  it("A soma deve dar 3", () => {
    const res = soma(1, 2)
    expect(res).toBe(3)
  }
})

### Testando um Componente em React
* Instalar a biblioteca testing-library-react
* Instalar jest-dom (extende as capacidades do Jest para coisas relacionadas à React e sua testing-library).

- Exemplo:
const Basic = (props) => (
  <p>Meu nome é {props.name}</p>
)

export default Basic

Teste:
```javascript
import Basic from './basic'
import { render } from 'testing-library/react'
import 'jest-dom/extend-expect'

describe("Testando o Basic", () => {
  it("O componente deve renderizar corretament e", () => {
    const { baseElement } = render(<Basic name="Lilith" />)
    expect(baseElement).toHaveTextContent("Meu nome é Lilith")
  }
})
```

- Como usar testes com Redux?
Criar uma store (Provider) de testes para colocar em volta do componente. 

### BDD (Behaviour Driven Development)
Teste baseado em comportamento, prevê união do teste automatizado com a especificação
e a premissa do teste, para isso é necessária uma documentação dele.

## Sintaxe Gherkin: sintaxe de passos para definir cenários e descrever funcionalidades por feature (caso de uso).

- Exemplo:
//login.feature

Funcionalidade: Login
Cenário: Como um usuário válido, posso logar no sistema
Dado quando estou na tela de Login
Quando digita credenciais válidas
E clicar no botão de login
Então devo acessar a home do sistema

Cenário: Como um usuário inválido, devo visualizar uma mensagem de erro
(...)

## Bibliotecas mais utilizadas com React: 
- Jest-cucumber
- Chai
