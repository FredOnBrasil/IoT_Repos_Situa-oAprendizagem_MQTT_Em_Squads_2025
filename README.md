<h1 align="center"> Smart Factory </h1>

<p align="center"> 
  <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/00%20-%20Logo%20Smart%20Factory.png" height="500" width="700"/> 
</p>

<h3> Equipe responsável pela documentação: <br>
  Luis Barbosa, Maycon Siqueira, Yhan Phillipe </h3>
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

<h2 align="center"> Squads </h2>

<h2> Squad 1: Hardware & Coleta de Dados </h2>

<p align="justify"> 
  Squad composto pelos membros: Danilo Santos, Luna Beatriz, Kaio Silva, Vinicius Gomes
</p>

<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/Squad%201/S1%201.jpg" height="500" width="500"/> </p>
<p align="center"> <img src="https://github.com/MaysCroft/Situacao-de-Aprendizagem-6/blob/main/Imagens%20Smart%20Factory/Squad%201/S1%202.jpg" height="500" width="500"/> </p>

<h2> Squad 2: Publicador WPF (Publisher) </h2>

<p align="justify">
  Squad composto pelos membros: Alice Virgilia, Bruno Maia, Diulie Batista, Marilene Araujo
</p>

<h2> Squad 3: Broker & Infraestrutura </h2>

<p align="justify">
  Squad composto pelos membros: Lucas Aquino, Miguel Duarte, Nicolas Oliveira, Pedro Moura
</p>

<h2> Squad 4: Aplicação Cliente (Subscriber) </h2>

<p align="justify">
  Squad composto pelos membros: Erick Silva, Otavio Soares
</p>

<h2> Squad 5: Documentação & Testes </h2>

<p align="justify">
  Squad composto pelos membros: Luis Barbosa, Maycon Siqueira, Yhan Phillipe
</p>

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

<h2> Testes </h2>

<hr>
