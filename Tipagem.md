# React com TypeScript

## TypeScript
- Superset criado pela Microsoft que adiciona tipos estáticos e outras abstrações (OOP). 

- Por que usar checagem de tipos?
Tipos ajudam a definir bem as camadas e relações entre módulos e aplicações. Ajudam a validar se as funções são chamadas da forma certa e com retorno esperado. 

## PropTypes vs TypeScript
- PropTypes é uma biblioteca que deve ser importado e definido nos componentes. 
- A checagem é feita em tempo de execução, não em compilação como o TypeScript. Mesmo que o componente tenha recebido tipo errado, ele é renderizado. 
- Mensagem de erro é vista no console. 
- O TypeScript não precisa ser importado e sua checagem de tipos é feita em tempo de compilação. Em caso de erro a aplicação não é executada. 