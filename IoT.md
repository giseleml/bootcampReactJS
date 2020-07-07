# IoT (Internet das Coisas)

Início da Internet: (Arpanet) Conectar computadores do centro de pesquisas para troca de informações

Surgimento de navegadores, emails, e-commerce, etc.
Utilizam uma rede mundial de computadores para conectar pessoas.

Surge a IoT quando há coisas (que não são pessoas) que começam utilizar essa rede mundial para trocar dados e enviar informações.

## Por que conectar as coisas?
- Colocar dispositivos/sensores embutidos em produtos do dia a dia (carros, eletrodomésticos, etc.) para coletar dados, possibilitando conhecer melhor essas Coisas facilitando tomar decisões, resolver problemas e simplificar as coisas do dia a dia.

## Conceitos Básicos de IoT

1. Things => Onde colocamos os sensores que coletarão dados
2. Cloud => Onde esses dados serão processados e armazenados
3. Intelligence => Processo de utilizar todos esses dados gerados e se beneficiar dessa rede de forma inteligente, para resolver problemas, otimizar processos, ter vantagem competitiva, etc.

## Exemplos de Uso

- Smart Buildings; Em um edifício é possível coletar várias informações. Possuem sistemas elétricos, controle de incêndio, sistemas de segurança, catracas eletrônicas, e muito mais componentes na infraestrutura de um edifício. Smart Building é a capacidade de coletar dados desses componentes e utilizá-los de forma inteligente para, por exemplo, melhorar a segurança do prédio ou do controle de incêndio.

- Smart Home; Controle de luzes, detector de movimento, monitoramento ao vivo, sensor de temperatura, fechadura eletrônica e muitos outros sensores. 

- Wearables; Componentes que podem ser usados no corpo (óculos, relógios, etc. também coletando dados. 

- Agricultura; Um sensor que mede a umidade do solo, informando se precisa aplicar mais ou menos irrigação em determinada área.

- Smart Transportation; Veículos passam a coletar dados de trânsito. Exemplo: Tesla, veículos autônomos que coletam dados de trânsito e comunicam com outros veículos ao redor. 

- Supply Chain; Surgimento da tecnologia RFID: etiqueta um produto e ao passar por scanners de radio frequência ele é detectado, sabendo que ele está passando por determinado lugar. Possibilita acompanhar o processo do produto desde fábrica até as lojas. 

- Energia Eficiente: com IoT é possível coletar dados de fontes geradoras e consumidoras de energia, criando uma rede de informações para tomada de decisões.

## Desafios IoT

- Privacidade e Segurança: equipamentos conectados à dados sensíveis. Ex: uma empresa chinesa produziu uma câmera que foi descoberto ter uma vulnerabilidade que permitiu hackers acessarem e terem audios e imagens da casa de pessoas.

- Quantidade exponencial de dispositivos conectados na rede: Nem todo mundo está acostumado a trabalhar com fontes geradoras de dados (como processar, armazenar e usar de forma inteligente corretamente?).

- Gerar valor a partir dos dados coletados: por que coletá-los e o que será feito com eles? 

## Arquitetura de IoT

- Things: arduino, embarcados (MCU - Microcontrolador de chip único), minicomputadores.

- MQTT: protocolo de comunicação para IoT dos dispositivos com a nuvem. Criado pela IBM, esta na base da pilha TCP/IP, protocolo de mensagem assícrona. 

Segue modelo Publish/Subscribe: É possível só publicar a mensagem (ex: um GPS capturando pontos geográficos e apenas mandando pra um middleware). Esse middleware é especializado em receber essa mensagem, o objetivo dele é receber a mensagem de uma ponta e entregar na outra, como um roteador de mensagens. Entrega para os clients que estão inscritos (subscribe) para receber aquele tipo de mensagem. MQTT Broker como middleware. O Broker tem um endereço na internet (DNS, host, etc.) que é usado para a publicação. 

### AWS Lambda: 
Uma função que recebe dados, executa um trabalho e então "morre". Ela pega os dados e alimenta uma area de cache. 