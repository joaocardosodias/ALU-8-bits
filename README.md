# CPU & ALU 8-bits

Uma Unidade Central de Processamento (CPU) e Unidade Lógica e Aritmética (ULA / ALU) de 8 bits desenvolvida no software [Digital](https://github.com/hneemann/Digital). 

O projeto consiste na implementação de uma arquitetura computacional completa, partindo de uma ULA modularizada até a construção de uma CPU funcional, utilizando circuitos combinacionais e sequenciais.

## Demonstração em Vídeo

- [Construção da ALU 8-bits](https://www.youtube.com/watch?v=E_-aaRJddRo)
- [CPU de 8 bits e Arquitetura](https://youtu.be/6Q5b-3ydh-A)

## Ferramentas Utilizadas

- **[Digital](https://github.com/hneemann/Digital)**: Software de simulação de circuitos lógicos digitais, utilizado para desenhar, testar e validar o funcionamento de toda a arquitetura.

## Arquitetura da CPU

Além da ULA, o projeto evoluiu para a implementação de CPUs de 8 bits com diferentes níveis de complexidade:

- **CPU 8-bits (`CPU8bits.dig`)**: Versão inicial da CPU integrando a ALU e registradores.
- **CPU 8-bits HARDCORE (`CPU8bitsHARDCORE.dig`)**: Versão avançada com controle refinado e maior capacidade de processamento.
- **CPU 8-bits HARDCORE Bus (`CPU8bitsHARDCOREbus.dig`)**: Implementação baseada em barramento (bus) para uma comunicação mais eficiente entre os componentes internos.

## Componentes e Operações

O projeto modulariza as funções, contendo subsistemas agrupados nas seguintes categorias:

### Operações Aritméticas
- **Soma (`soma8bits.dig`)**: Adição de valores de 8 bits usando cascata de somadores completos (`soma1bit.dig`). Foi adicionado também um somador maior em `somador16bits.dig`.
- **Subtração (`subtrator8bits.dig`)**: Subtração de valores acoplando o uso de complemento de 2.
- **Multiplicação (`multiplicador8bits.dig`)**: Circuito multiplicador para valores binários de 8 bits.
- **Divisão**: Circuito genérico divisor de 8 bits.
  - Há abstrações variadas do divisor: versão **otimizada** (`divisor8bits_otimizado.dig`), **não otimizada** (`divisor8bits_nao_otimizado.dig`) e a junção principal em `divisor8bits.dig`.

### Operações Lógicas
- **NAND (`nand8bits.dig`)**: Operação lógica bit a bit Não-E (NAND).
- **XOR (`xor8bits.dig`)**: Operação lógica bit a bit Ou-Exclusivo (XOR).

### Operações de Deslocamento (Shift)
- **Shift Left 8-bits (`shift_left8bits.dig`)**: Deslocamento lógico de bits para a esquerda.
- **Shift Right 8-bits (`shift_right8bits.dig`)**: Deslocamento lógico de bits para a direita.
- **Shift Left 16-bits (`shift_left16bits.dig`)**: Deslocador de 16 bits à esquerda (utilitário para extensões como multiplicação e divisão).

### Outros Utilitários
- **Complemento de 2 (`complemento2.dig`)**: Inversão algébrica de sinal a partir da inversão de bits somada de 1.
- **Células Auxiliares (`celula.dig`)**: Componentes de abstração ou bloco elementar de memória/processamento usado em arranjos matriciais.
- **ALU Principal (`ALU8bits.dig`)**: Componente central (nível de topo/Top Level) que multiplexa e une todos os módulos matemáticos e lógicos operando sob o controle de um sinal seletor (opcode).

