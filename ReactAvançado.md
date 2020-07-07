# React Avançado

## Ciclo de Vida
Inicialização - Montagem - Atualização - Desmontagem

1) Inicialização: receber as props e o state
2) Montagem: render, componentDidMount
3) Atualização: shouldComponentUpdate, render
4) Desmontagem: componentWillUnmount

## Hooks (>=16.8)
Nova forma de escrever o ciclo de vida do React. Hooks recebem funções.

- Alguns hooks: useState, useEffect, useContext, useReducer, useCallback, useMemo, useRef, etc.

- Por ser usado em Função e não Classe, não tem this e nem render. 

useEffect(() => {
  console.log('Renderizei')
}, [])

- useEffect com array vazio: executa só 1 vez como componentDidMount.

useEffect(() => {
  console.log('valor alterado')
  }, [valor])

- useEffect com argumento: executa toda vez que o argumento passado for alterado, como componentDidUpdate.

useEffect(() => {
  return () => {
    console.log('Test')
  }
}, [])

- Return dentro de useEffect equivale ao componentWillUnmount.

- memo: cria componentes puros. Evita re-render desnecessários.

- useState

const [tweet, setTweet] = useState('title')

setTweet('tweet atualizado')

console.log('Novo tweet: ', tweet)

- Não utilizar hooks em funções JS, apenas em componentes React

## Context API

- useContext: quem for utilizar terá que chamar esse contexto. 
|_ CreateContext(padrão)
|_ ThemeContext.Provider: encapsula componentes que devem ouvir os valores do context. value={valores}
|_ Componente que consome o context deve importar: useContext e o arquivo do context. 

## Fragments
Permitem agrupar uma lista de filhos sem adicionar nós extras ao DOM. 

Aceita props:
<React.Fragment props={value}>
</React.Fragment>

Não aceita props:
<> 
</>

## Error Boundaries 
Um erro de JS em uma parte da UI não deve quebrar toda a aplicação, para isso foi introduzido no React +16 o conceito de erro boundary. 

É um componente que deve ser criado e que encapsula toda a aplicação (componente App.

Dentro desse componente:

Error: erro, errorInfo: objeto com informações do arquivo que deu erro
componentDidCatch(error, errorInfo) {
  console.log(error, errorInfo)
}

## Render Props
Compartilhar código entre componentes React passando uma prop cujo valor é uma função; Recebe uma função que retorna um elemento React.

Isso quer dizer que: Vamos passar uma função para dentro do render do nosso componente pai (wrapper, parent, container) uma função que vai ser responsável por renderizar o component UI desse container.

Isso vai nos permitir compartilhar os nossos métodos e props que desejarmos para UI passando apenas um nível para baixo.

## PropTypes
Captura de bugs com checagem de tipos nativa do React. A checagem é em tempo de execução, não de desenvolvimento (como TypeScript).

Deve ser importado:
import PropTypes from 'prop-types'

<nome-da-função/classe>.propTypes = {
  prop1: PropTypes.number,
  prop2: PropTypes.name.isRequired
}

### Definir propriedades padrão da aplicação. São executadas antes do PropTypes.

<nome-da-função/classe>.defaultProps = {
  cats: 0,
  customers: []
}

## Refs e DOM 
Com Refs é possível acessar a árvore do DOM ou elementos React. Com o ref pode acessar todos os métodos e propriedades do elemento referenciado. 

import React, { useRef } from 'react'

const inputRef = useRef()

const handleClick = () => {
	inputRef.current.focus()
}

<input ref={inputRef} />
<button onClick={handleClick}></button>
