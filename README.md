# Monitor de Energia DC

## Descrição do projeto

O projeto consiste no desenvolvimento de um sistema embarcado para monitorar o consumo de uma carga DC utilizando o microcontrolador **STM32F411CEU6 (Black Pill)**.

O sistema será capaz de medir tensão, corrente, potência e energia consumida, exibindo os valores em tempo real em um display OLED.

## Alunos

Hardware: *Aluno A*

Firmware: Ítalo Gowbery Mota Vieira - 12311EAU013

Validação e documentação: Paulo Antônio Deoterônio Mesquita 12221EAU012

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

## Resultado esperado

Espera-se desenvolver uma placa capaz de monitorar o consumo de uma carga DC em tempo real, exibindo as grandezas elétricas em um display OLED e sinalizando situações de corrente elevada.

O projeto integrará hardware, firmware e comunicação digital em um sistema funcional de monitoramento de energia.
