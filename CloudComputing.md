# Cloud Computing
Provedor ou serviço que faz o gerenciamento de hardware e software para o usuário. Antigamente havia uma sala/data center onde ficavam os servidores com profissionais checando-os todos os dias, sala refrigerada, backups, etc. sendo muito custoso para empresas. 

Já com o Cloud Computing elas não têm que custear com toda essa estrutura, sendo oferecida por outra empresa como Amazon.

O modelo de pagamento costuma ser pague pelo que consumir.

## IaaS - Infrastructure As A Service
O Cloud Computing nasceu aqui. Google Cloud, AWS, Microsoft Azure. Máquinas que podem ser alugadas e serem usadas para qualquer serviço necessário. Estrutura que não precisa ser provida pelo usuário, ele paga por ela. Não ter que construir sua infraestrutura física, redes, segurança, servers e bancos de dados.

## PaaS - Plataform As A Service
Não só máquinas disponíveis mas sim uma plataforma toda, permite escabilidade de máquinas, aumentar suas potências, etc. Provem serviços/plugins para essas máquinas. Terraform, CloudFormation. 

## BaaS - Backend As A Service
Backend ou Mobile Backend as a service. Redux a complexidade de construir o backend, tabelas, autenticação, etc. Firebase. Permite focar na aplicação e suas funcionalidades.

## SaaS - Software As A Service

O fornecedor do software se responsabiliza por toda a estrutura necessária à disponibilização do sistema, e o cliente utiliza o software via internet, pagando um valor pelo serviço.

## Kubernetes
Distribuição e escalamento de serviços, automatizando a implantação, dimensionamento e gestão de aplicações em containers. 

## Serverless
Arquitetura sem serviço "rodando"; Um serviço que conforme um evento é disparado ele executa um código do usuário. Assim o serviço nunca estará fora do ar (down time), já que não está rodando.
O custo é maior. 
Tudo é gerenciado pelo servidor, não tendo a preocupação de monitora-lo.
Geralmente há um número maior de lambdas, pois cada endpoint envocará uma. 

# Pooling
- Short pooling: novas requisições ao servidor em curto período de tempo para retornar dados novos ao usuário se disponíveis. Downside: muitas requisições.
- Long pooling: novas requisições ao servidor num espaço maior de tempo (30s), o servidor segura essa conexão por esse tempo e retorna ou não novos dados ao usuário. Downside: risco de ultrapassar a memória do servidor por ter que segurar muitas conexões ao mesmo tempo;

# Websocket
- Aplicação TCP que escuta uma porta de um servidor que segue um protocolo específico.
- Conexão única com o servidor que não é encerrada, é feita e fica escutando se o servidor tem algum dado pra passar e vice-versa. Conexão entre servidor e navegador é contínua.
- Canal de comunicação full-duplex.
- Usado em aplicaçes que requerem atualizações regulares e rápidas (chats, jogos multiplayer, etc.) mantém os dados sempre em tempo real.