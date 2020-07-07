# Redux
Uma biblioteca que cria um container de states para aplicações JS. 
Ele mantém o state de toda a aplicação em uma única árvore imutável de states
que não podem ser modificados diretamente. Dessa forma, ao viés do state ser 
passado por props entre componentes tendo um fluxo único e seguindo sua hierarquia,
os states podem ser acessados por todos os componentes da aplicação, de acordo com
a necessidade deles.

## 3 Princípios Básicos: 
1. Single Source of Truth: a aplicação possui uma única store.
2. State é read-only.
3. Mudanças de state são feitas com pure functions, ou seja, o state é imutável.

## Básico

    * Actions: cargas de informação que mandam dados da aplicação para a store. São a única
    fonte informação para a store. São enviadas através do dispatch(); Retornam um objeto
    de action formatado. 
    * Reducers: especificam para a aplicação como o state muda em resposta às ações senviadas
    para a store. Actions apenas descrevem o que aconteceu, mas não como o state da aplicação
    mudou.
    * Store: objeto que contém a aplicação do state, permite acesso via getState(), permite que
    o statee seja atualizado por um dispatch(action), registra listeners por subscribe(listener).
    É importante lembrar que só haverá uma store na aplicação Redux. Quando a lógica dos dados 
    deve ser dividida deve ser usado uma composição de reducer ao invés de várias stores. 

## Fluxo do Redux

    Component => Action => Store => Reducer => Store => Component

## Providers, Métodos e Funções Redux
 
    * Provider: Embrulha a árvore de componentes, facilitando a conexão dos componentes filhos com a store.
    * connect(): Conecta um componente com a store.
    * Selector: Define quais estados do redux passar como props. 
    * mapStateToProps(state): Passamos qual o state da store que estamos associando e qual o state do
    nosso componente local esta associado a ele.
    Exemplo:
    
    function mapStateToProps(state) {
        return {
            count: state.count
        }
    }

# React 

## Fluxo React

Inicialização => Montagem (render) => Update (atualização + render) => Unmounting 
 
## Formulários

### Componentes Controlados
Mantém um state interno para os componentes controlados (input, textarea, select, etc.) e 
todos eles aceitam o atributo value. 

* onSubmit: O que será feito na submissão do formulário.
* value: Valor que é guardado num state.
* onChange: Cada alteração feita na DOM executa uma função passada pra ele.

- select: Value e onChange.
- checkbox: Não tem value, mas usa o atributo checked que deve ser guardado no state.
- radio: Value que precisa ser setado; O state é pego no checked. Pode receber função
em onChange também.

### Componentes Não-Controlados
* Componentes read-only dos quais o React só vai observar os estados e pegar suas referências.
Usando a função React.createRef() em uma variável, podemos atrubuíla ao ref do componente não-controlado.
Dessa forma conseguimos pegar seu state no envio.

Exemplo:
- input (upload de arquivos)