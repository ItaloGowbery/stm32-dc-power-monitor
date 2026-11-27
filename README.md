# Monitor de Energia DC

## Descrição do projeto

O projeto consiste no desenvolvimento de um sistema embarcado para monitorar o consumo de uma carga DC utilizando o microcontrolador **STM32F411CEU6 (Black Pill)**.

O sistema será capaz de medir tensão, corrente, potência e energia consumida, exibindo os valores em tempo real em um display OLED.

## Alunos

Hardware: Paulo Antônio Deoterônio Mesquita - 12221EAU012

Firmware: Ítalo Gowbery Mota Vieira - 12311EAU013

Validação e documentação: Júlio Cézar Benetti Andrade Ortelan - 12311EAU016

## Componentes principais

- **STM32F411CEU6:** microcontrolador responsável pelo processamento.
- **INA219:** sensor de tensão e corrente com comunicação I2C.
- **OLED SSD1306:** display para exibição das medições.
- **Motor DC 12 V:** carga elétrica monitorada.
- **Fonte DC 12 V:** alimentação do motor.
- **LED verde:** indicação de funcionamento normal.
- **LED vermelho:** alerta de corrente elevada.
- **Botão:** alternância das informações exibidas no display.

## Funcionamento

A caraga por uma fonte externa, enquanto o STM32 será alimentado por USB.

O sensor INA219 medirá a tensão e a corrente consumida pelo motor e enviará os dados ao STM32 por meio do barramento I2C.

O microcontrolador calculará a potência e a energia consumida, apresentando os resultados no display OLED.

O LED verde indicará funcionamento normal, enquanto o vermelho será acionado caso a corrente ultrapasse um limite configurado.

O botão permitirá alternar entre as informações apresentadas no display e zerar a energia acumulada por meio de um pressionamento longo.

## Desenvolvimento

O projeto envolverá:

- Desenvolvimento de esquemático e PCB no Altium.
- Programação do STM32 em C, com configuração direta dos registradores, sem HAL/CubeMX para GPIO e I2C.
- Comunicação I2C com o INA219 e o OLED.
- Implementação dos LEDs e botão utilizando GPIO.
- Depuração utilizando ST-Link V2 e GDB.
- Validação das medições e da comunicação I2C com equipamentos de laboratório.

## Atendimento aos requisitos do projeto

| Requisito | Como será atendido |
|---|---|
| Microcontrolador | Utilização do STM32F411CEU6 (Black Pill). |
| Esquemático elétrico | Desenvolvimento do circuito utilizando o Altium Designer. |
| Layout da PCB | Desenvolvimento de uma placa personalizada para integração dos componentes. |
| GPIO | Controle dos LEDs de sinalização e leitura do botão. |
| Barramento de comunicação | Utilização do I2C para comunicação com o INA219 e o OLED SSD1306. |
| Configuração por registradores | Configuração direta dos periféricos GPIO e I2C, sem utilização de HAL ou CubeMX. |
| Dimensionamento do barramento | Dimensionamento dos resistores de pull-up e definição da frequência de comunicação. |
| Documentação do protocolo | Documentação dos endereços, formato dos quadros, temporização e taxa de comunicação I2C. |
| Integração dos periféricos | Acionamento dos LEDs conforme a corrente medida pelo INA219 e apresentação dos dados no OLED. |
| Firmware modular | Separação dos drivers GPIO, I2C, INA219 e SSD1306 da lógica da aplicação. |
| Depuração | Utilização do ST-Link V2 e GDB para breakpoints, inspeção de registradores e leitura de variáveis. |
| Validação do barramento | Captura dos sinais SDA e SCL utilizando um osciloscópio ou analisador lógico do laboratório. |
| Validação das medições | Comparação dos valores medidos pelo INA219 com instrumentos de referência. |
| Relatório | Documentação do esquemático, layout, testes, resultados e contribuição dos integrantes. |

### Diferenciais previstos

- Fabricação e montagem da PCB utilizando litografia.
- Utilização de timer para leitura periódica do sensor.
- Utilização de interrupção externa (EXTI) para o botão.
- Cálculo da energia acumulada ao longo do tempo.
- Monitoramento simultâneo de dois dispositivos no barramento I2C.

## Resultado esperado

Espera-se desenvolver uma placa capaz de monitorar o consumo de uma carga DC em tempo real, exibindo as grandezas elétricas em um display OLED e sinalizando situações de corrente elevada.

O projeto integrará hardware, firmware e comunicação digital em um sistema funcional de monitoramento de energia.
