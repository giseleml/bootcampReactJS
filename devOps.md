# DevOps

Antigamente as áreas eram separadas e não colaboravam entre si: 

- Development
- IT Operations
- Quality Assurance - QA

DevOps busca integrar esses times, garantindo software de qualidade maior, mais rápido e confiável; São práticas que integram e automatizam os processos entre essas equipes. Colaboração e comunicação entre as equipes.

## CI/CD

### CI - Continuous Integration 
Construção => Teste Unitário => Análise da Qualidade => Empacotamento da release para deploy

O software é compilado e testado toda vez que um desenvolvedor envia código para a aplicação, ocorrendo várias vezes ao dia.

### CD - Continuous Delivery 
Precisa de alguém para aprovar o deploy.
integração contínua, testes automatizados e recursos de implantação automatizada permitem que o software seja desenvolvido e implementado de forma rápida, confiável e repetitiva com intervenção humana mínima.

### CD - Continuous Deployment 
O deploy é feito de modo automático, após o CI. 
cada alteração de código passa por todo o pipeline e é colocada em produção automaticamente, resultando em muitas implantações de produção todos os dias. Faz tudo o que a Entrega Contínua faz, mas o processo é totalmente automatizado, não há intervenção humana

Principais ferramentas: Travis CI, Jenkins, GitLab Cl, Azure Pipelines.

- O pipelining de software é um tipo de execução fora de ordem, exceto que a reordenação é feita por um compilador em vez do processador.
