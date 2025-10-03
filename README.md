<h1 align="center"> Documentação Smart Factory: <br> Monitoramento Industrial em Tempo Real </h1>

<p align="center"> 
  <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/00%20-%20Logo%20Smart%20Factory.png" height="500" width="700"/> 
</p>

<h3> Equipe responsável: <br> Luis Barbosa, Maycon Siqueira, Yhan Phillipe </h3>
<h3> Instrutor: Fred Aguiar </h3>

<hr>

<h2 align="center"> Introdução </h2>

A empresa Smart Factory está desenvolvendo uma solução para monitoramento em tempo real de variáveis industriais em uma planta piloto. <br>
O cliente solicitou que a aplicação seja capaz de:

- Coletar dados de sensores conectados a um Arduino.
- Publicar esses dados em tópicos via protocolo MQTT.
- Exibir os valores em uma aplicação desktop (WPF).
- Trabalhar com 5 grandezas monitoradas. <br>

A turma deverá atuar como uma equipe única de desenvolvimento, simulando uma software house dividida em squads de responsabilidade.

<hr>

<h2 align="center"> Responsabilidades das Squads </h2>

<h2> Squad 1: Hardware & Coleta de Dados </h2>

<p align="justify"> 
  Squad composto pelos membros: <b>Danilo Santos, Luna Beatriz, Kaio Silva, Vinicius Gomes.</b> <br>
  Este Squad é responsável pela fonte dos dados e sua correta aquisição no nível do hardware.<br>
</p>

- <b>Integração de Sensores:</b> Selecionar, calibrar e conectar os 5 sensores físicos ao Arduino.
- <b>Firmware do Arduino:</b> Desenvolver o código (Sketch) para o Arduino que faça a leitura das 5 grandezas de forma contínua e confiável.
- <b>Comunicação de Saída:</b> Implementar a lógica para formatar os dados e enviá-los de forma serial ou via rede (Wi-Fi/Ethernet) para a próxima camada (o Publicador).

<b> Pontos Importantes </b>
- As ligações positivo e negativo (5V e GND) identificadas em vermelho e preto para padronização

<b> Dificuldades </b>
- Montagem e ligação dos sensores a protoboard/arduino sendo posição correta de conexão do sensor

<h3 align="center"> Esquema de Montagem do Aduino </h3>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%201/S1%200.jpg" height="600" width="600"/> </p>

<h3 align="center"> Montagem Protótipo </h3>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%201/S1%201.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%201/S1%202.jpg" height="500" width="500"/> </p>

<h3 align="center"> Código Arduino </h3>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%201/S1%203.png" width="990"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%201/S1%204.png" width="990"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%201/S1%205.png" width="990"/> </p>



<h2> Squad 2: Publicador WPF (Publisher) </h2>

<p align="justify">
  Squad composto pelos membros: <b>Alice Virgilia, Bruno Maia, Diulie Batista, Marilene Araujo.</b> <br>
  Este Squad tem a responsabilidade de receber os dados do Squad 1 e publicá-los no Broker MQTT. <br>
</p>

- <b>Interface de Coleta:</b> Criar a aplicação WPF que faz a leitura dos dados brutos enviados pelo Arduino via serial.
- <b>Protocolo MQTT:</b> Integrar e configurar uma biblioteca MQTT Client (ex: M2Mqtt, MQTTnet) na aplicação Publicadora.
- <b>Publicação de Dados:</b> Estruturar os dados lidos em uma mensagem MQTT e publicá-los nos tópicos definidos (Squad 3). Recomenda-se um tópico por grandeza ou um tópico único com payload estruturado (JSON).
- <b>Tratamento de Erros:</b> Implementar a lógica de reconexão automática ao Broker e o tratamento de falhas na leitura do Arduino.


<b> Dificuldades </b>
- Importação de plugins e bibliotecas para fazer o código em outros computadores



<h2> Squad 3: Broker & Infraestrutura </h2>

<p align="justify">
  Squad composto pelos membros: <b>Lucas Aquino, Miguel Duarte, Nicolas Oliveira, Pedro Moura.</b> <br>
  Este Squad é crucial para a conectividade e comunicação de toda a solução, sendo responsável pelo middleware MQTT. <br>
</p>

- <b>Instalação e Configuração do Broker:</b> Escolher, instalar e configurar um Broker MQTT (Mosquitto).
- <b>Gerenciamento de Rede:</b> Garantir que o Broker esteja acessível via rede para o Publicador (Squad 2) e o Cliente (Squad 4). Configuração de firewall e portas.
- <b>Definição de Tópicos:</b> Estruturar a hierarquia de tópicos MQTT de forma clara (ex: smartfactory/planta_piloto/temperatura, smartfactory/planta_piloto/pressao).
- <b>Segurança:</b> Implementar segurança básica (se necessário), como autenticação por usuário/senha e/ou certificados (TLS/SSL) para conexão ao Broker.
- <b>Testes de Infraestrutura:</b> Realizar testes de carga e latência para garantir a estabilidade do Broker.

<b> Dificuldades </b>
- Montagem de portas para a criação dos usuários e senhas, usadas para especificação dos tópicos abordados

[Documentação Broker](https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Documenta%C3%A7%C3%A3o%20Broker.txt)

<h3 align="center"> Comunicação MQTT </h3>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%203/S3%201.jpg"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%203/S3%202.jpg"/> </p>



<h2> Squad 4: Aplicação Cliente (Subscriber) </h2>

<p align="justify">
  Squad composto pelos membros: <b>Erick Silva, Otavio Soares.</b> <br>
  Este Squad é responsável pela experiência do usuário (UX) e a visualização dos dados em tempo real. <br>
</p>

- <b>Desenvolvimento da Interface WPF:</b> Criar a aplicação desktop WPF com layout e design intuitivos.
- <b>Assinatura (Subscription):</b> Integrar a biblioteca MQTT Client (a mesma do Squad 2) e configurar a assinatura aos tópicos definidos pelo Squad 3.
- <b>Processamento de Mensagens:</b> Implementar a lógica para receber e decodificar as mensagens MQTT publicadas.
- <b>Visualização em Tempo Real:</b> Desenvolver os componentes visuais que exibem as 5 grandezas e atualizam o valor automaticamente ao receber uma nova mensagem.
- <b>Indicadores de Status:</b> Incluir indicadores visuais para o status da conexão com o Broker (online/offline).

<h3 align="center"> Código Cliente (Subscriber) </h3>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%204/S4%201.jpg"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%204/S4%202.jpg"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%204/S4%203.jpg"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squad%204/S4%204.jpg"/> </p>

<b> Dificuldades </b>
- Recebimento dos dados para andamento do projeto.



<h2> Squad 5: Documentação & Testes </h2>

<p align="justify">
  Squad composto pelos membros: <b>Luis Barbosa, Maycon Siqueira, Yhan Phillipe.</b> <br>
  Esta Squad garante a qualidade, rastreabilidade e manutenibilidade de todo o projeto. <br>
</p>

- <b>Plano de Testes:</b> Elaborar e executar Testes de Integração (fim a fim: Arduino → WPF) e Testes Unitários (código do Arduino, parsing de JSON, etc.).
- <b>Documentação Técnica:</b> Compilar toda a documentação gerada pelos outros Squads (diagramas, código-fonte, configurações do Broker) em um repositório centralizado.
- <b>Documentação do Usuário:</b> Criar um Manual do Usuário para a Aplicação Cliente (WPF) e um guia de instalação (Deployment).
- <b>Gerenciamento de Versões:</b> Configurar o repositório de código-fonte (Git) e definir a política de branching e releases.
- <b>Gerenciamento de Requisitos:</b> Manter a lista de requisitos atualizada e garantir que todos os 5 requisitos do cliente foram atendidos e verificados.

<b> Dificuldades </b>
- Organização das informações coletadas
- Planejamento no recebimento das informações

<hr>



<h2 align="center"> Sensores Utilizados </h2>

<div align="center">
  <table>
    <thead>
      <tr>
        <th> :computer: Sensor </th>
        <th> ✅ Nome do Sensor </th>
        <th> :bulb: Descrição </th>
      </tr>
    </thead>
    <tbody align="center">
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/01%20-%20Arduino.jpg" height="300" width="300" /> </td>
        <td><b> Arduíno UNO </b></td>
        <td> A placa microcontroladora (o "cérebro" do projeto) usada para carregar e executar o código que controla os sensores e atuadores do circuito. </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/02%20-%20Sensor%20Ultrassonico%20HC-SR04.jpg" height="350" width="300"/> </td>
        <td><b> HC-SR04 Ultrassônico </b></td>
        <td> Sensor de distância que utiliza ondas ultrassônicas para medir a distância até um objeto, calculando o tempo de retorno do pulso sonoro.
 </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/03%20-%20Sensor%20de%20Chuva%20e%20Umidade%20HW-028.jpg" height="300" width="300"/> </td>
        <td><b> HW-028 Sensor de Chuva </b></td>
        <td> Placa sensora que detecta a presença de chuva ou umidade ao medir a mudança na resistência de suas trilhas de cobre quando molhadas.
 </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/04%20-%20Modulo%20HW-103V0.1.jpg" height="300" width="350"/> </td>
        <td><b> Módulo HW-103 V0.1 (conectado ao HW-028) </b></td>
        <td> Módulo de controle que converte o sinal analógico da placa de chuva em um sinal digital (presença/ausência de chuva) e um sinal analógico (intensidade da chuva).
 </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/05%20-%20Sensor%20Infravermelho%20HW-870.jpg" height="300" width="300"/> </td>
        <td><b> HW-870 Infravermelho </b></td>
        <td> Geralmente, um módulo sensor refletivo que usa luz infravermelha para detectar objetos ou rastrear linhas no chão, comumente usado em robótica.
 </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/06%20-%20Sensor%20de%20Temperatura%20Dallas%2018820%202034c4%2B817ab.jpg" height="300" width="300"/></td>
        <td><b> Dallas 18B20 de Temperatura </b></td>
        <td> Sensor de temperatura digital de alta precisão que se comunica usando a interface 1-Wire (apenas um pino de dados). </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/07%20-%20Sensor%20LDR.jpg" height="300" width="300"/></td>
        <td><b> LDR (Light Dependent Resistor) </b></td>
        <td> Resistor cuja resistência elétrica varia de acordo com a intensidade da luz; usado para medir luminosidade. </td>
      </tr>
    </tbody>
  </table>
</div>

<hr>

<h2 align="center"> Componentes Complementares </h2>

<div align="center">
  <table>
    <thead>
      <tr>
        <th> :computer: Componente </th>
        <th> :file_folder: Nome </th>
        <th> :bulb: Descrição </th>
      </tr>
    </thead>
    <tbody align="center">
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/08%20-%20Protoboard.jpg" height="250" width="250"/></td>
        <td><b> Protoboard </b></td>
        <td> Uma placa de montagem sem solda, essencial para montar e testar circuitos eletrônicos temporariamente.
 </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/09%20-%20Resistores.webp" height="250" width="250"/> </td>
        <td><b> Resistor </b></td>
        <td> Componente eletrônico passivo usado para controlar e limitar o fluxo de corrente elétrica no circuito, protegendo outros componentes. </td>
      </tr>
      <tr>
        <td> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/10%20-%20Jumpers%20de%20Conex%C3%A3o.jpg" height="250" width="250"/></td>
        <td><b> Jumpers de Conexão </b></td>
        <td> Fios com conectores nas pontas, utilizados para realizar as conexões elétricas entre o Arduino, a protoboard e os componentes. </td>
      </tr>
    </tbody>
  </table>
</div>

<hr>

<h2 align="center"> Fases de Testes e Planejamentos dos Squads </h2>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0009.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0010.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0011.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0012.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0015.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0016.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0017.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0018.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251001-WA0019.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251002-WA0003.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251002-WA0004.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251002-WA0005.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251002-WA0006.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251002-WA0007.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Documentos%20Smart%20Factory/Squads/IMG-20251002-WA0008.jpg" height="500" width="500"/> </p>

<hr>

<h2 align="center"> Conclusões dos Squads </h2>

<h3 align="center"> Squad 1 </h3>

<h3 align="center"> Squad 2 </h3>

<h3 align="center"> Squad 3 </h3>

<h3 align="center"> Squad 4 </h3>

<h3 align="center"> Squad 5 </h3>

<h3 align="center"> Conclusão Geral </h3>
