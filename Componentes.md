# Componentes: Stateful vs Stateless

## Stateful: 
Usa states; Geralmente criado usando classes mas não é obrigatório. 
Agora com React Hooks states podem ser usados em funções;

## Stateless: 
Não usa states; Geralmente construído usando funções.
Componentes que apenas renderizam coisas na tela.

## Hooks
Com a presença dos Hooks, a nomenclatura passou a ser: 

* Class Components
* Function Componentes

# Dumb Components
- Se preocupa com a apresentação, não tem regra
- Recebe valores via props
- Não possue dependência com o restante da aplicação (desacoplado)
- Não especifica como dados são carregados ou sofrem mutações
- Recebe valores e callbacks exclusivamente via props
- Raramente possuem estado; Quando precisam é para controlar a interface, não os dados do usuário. Não é um estado que intefere no restante da aplicação.
- Só renderiza e não faz mais nada.
- Não possuem regras específicas. 

Exemplos: Button, Card, Sidebar, Footer, List, Menu.


# Smart Components
- Se preocupa como as coisas vão funcionar, não só aparência delas.
- Pode conter smart e dumb components.
- Providenciam dados e padrões de apresentação ou outros containers.
- Costumam possuir estados e chamar outros fluxos do sistema.
- Possuem regras específicas. Dificilmente pode ser reutilizado em outro contexto.

Exemplos: userGallery, userPage, filterBook, followersSidebar, listCards.
