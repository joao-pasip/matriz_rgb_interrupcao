# Projeto: Controle de Matriz de LEDs com Raspberry Pi Pico

## Descrição

Este projeto utiliza um Raspberry Pi Pico para controlar uma matriz de LEDs WS2812B. Ele permite a exibição de números de 0 a 9 na matriz, utilizando um buffer de pixels e uma máquina de estado programável (PIO). A mudança de números é feita através de dois botões.

## Componentes Utilizados

- Raspberry Pi Pico
- LEDs WS2812B (25 LEDs dispostos em matriz 5x5)
- Botões (para mudar os números exibidos)
- Resistor de pull-down (se necessário para os botões)

## Configuração de Hardware

- **LEDs WS2812B** conectados ao **pino 7** do Raspberry Pi Pico
- **Botão A** conectado ao **pino 5** (incrementa o contador)
- **Botão B** conectado ao **pino 6** (decrementa o contador)
- **LED Vermelho** conectado ao **pino 13**

## Funcionalidades

- **Controle de LEDs WS2812B** via PIO
- **Exibição de números** de 0 a 9 na matriz
- **Botões para mudar os números**
- **Interrupção GPIO** para leitura dos botões
- **Piscar LED vermelho** para indicar eventos

## Estrutura do Código

### Principais Elementos

- **`npInit()`**: Inicializa a PIO para controle dos LEDs.
- **`npSetLED()`**: Define a cor de um LED específico.
- **`npClear()`**: Limpa todos os LEDs.
- **`npWrite()`**: Atualiza os LEDs com as cores definidas no buffer.
- **`getIndex(x, y)`**: Converte coordenadas da matriz para índice do buffer.
- **Matriz `matrizes[10][5][5][3]`**: Define padrões de cores para exibição dos números.
- **`gpio_irq_handler()`**: Trata eventos dos botões e altera o contador.

## Como Usar

1. **Monte o circuito** conforme descrito.
2. **Compile e grave o código** no Raspberry Pi Pico.
3. **Pressione os botões** para alterar os números exibidos na matriz.
4. O LED vermelho piscará ao pressionar um botão.

## Requisitos

- SDK do Raspberry Pi Pico
- Biblioteca PIO para controle de LEDs WS2812B
- Compilador GCC para ARM

## Autor

[João Paulo Silva Piauhy](https://www.linkedin.com/in/joaopasip/)

## Licença

Este projeto foi desenvolvido como atividade da Residência em Sistemas Embarcados - Embarca Tech.
