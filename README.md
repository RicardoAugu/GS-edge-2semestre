# GS-edge-2semestre

Em busca de aprimorar a qualidade de vida, nosso foco está naqueles que se dedicam diariamente a atividades físicas, como yoga, futebol, musculação, natação,
e muito mais. Estamos entusiasmados em apresentar nosso novo site, uma plataforma dedicada à melhoria esportiva e à prevenção de lesões.
Conduzimos uma análise minuciosa, levando em consideração o físico, nível de experiência no esporte e histórico de atividade física de cada atleta.
Esta abordagem personalizada é a base para o desenvolvimento de estratégias eficazes. Desenvolver planos nutricionais personalizados, adaptados às necessidades 
específicas de cada desportista. 
Estes planos visam não apenas otimizar o desempenho durante as atividades, mas também acelerar a recuperação pós exercício. Implementamos estratégias de 
fisioterapia preventiva para minimizar o risco de lesões e promover a saúde musculoesquelética a longo prazo. Nosso compromisso vai além do desempenho imediato, 
visando a sustentabilidade e o bem-estar a longo prazo. 

Com isso desenvolvemos um produto físico com tecnologia Arduino. Esse dispositivo avançado medirá a quantidade de peso dos alimentos,
registrará a ingestão diária de água e incorporará um sensor de movimento para monitorar a qualidade do sono. Esta inovação proporcionará um acompanhamento
em tempo real, permitindo uma compreensão abrangente dos hábitos diários e oferecendo insights valiosos para uma vida mais saudável.

Com código que é um firmware para um microcontrolador ESP32, desenvolvido em linguagem C++ utilizando a plataforma Arduino.
Ele tem o propósito de coletar dados de diferentes sensores e enviar essas informações para um servidor MQTT. Vamos entender as principais funcionalidades:

Configurações Iniciais:
Define as informações necessárias para a conexão Wi-Fi, como nome e senha da rede.
Configura os parâmetros do servidor MQTT, incluindo endereço, porta e tópicos de publicação.
Especifica os pinos utilizados para conectar os sensores (potenciômetro, PIR e HX711).
Define algumas constantes, como a escala do sensor HX711 e os intervalos de leitura do peso.

Inicialização:
Inicia a comunicação serial para permitir mensagens de depuração.
Configura o pino do sensor PIR como entrada.
Inicializa o módulo HX711 para a leitura do sensor de peso.

Loop Principal:
Verifica a conexão Wi-Fi e MQTT e reconecta, se necessário.
Atualiza os valores dos sensores a cada segundo.
Publica os valores lidos em tópicos MQTT específicos.

Funções de Atualização dos Sensores:
updatePotentiometerValue: Lê o valor do potenciômetro, converte para mililitros e publica no tópico MQTT "FIAP/CP/Agua".
updatePIRState: Lê o sensor PIR, imprime se há movimento detectado ou não e publica no tópico MQTT "FIAP/CP/PIR".
updateWeight: Lê o sensor de peso (HX711), converte o valor para quilogramas, limita o intervalo e publica no tópico MQTT "FIAP/CP/Weight".
Em resumo, este código cria um sistema que, ao ser carregado em um ESP32, conecta-se à Wi-Fi, estabelece uma comunicação MQTT e monitora sensores,
enviando continuamente os dados coletados para um servidor MQTT. Esses dados podem ser posteriormente utilizados em sistemas de automação ou monitoramento remoto.

Link para o projeto no Wokwi: https://wokwi.com/projects/381374487369705473




