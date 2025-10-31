### Documentação do protótipo
Este protótipo consiste em um semáforo offline, feito em um protoboard, que posseu 3 leds, dentre eles, um vermelho, um amarelo e um verde. Cada led possue um resistor pois o resistir serve para limitar a corrente elétrica que passa pelo LED, protegendo-o de queimar por sobrecarga. Um LED é um componente sensível e pode ser danificado por excesso de corrente, mesmo com uma pequena mudança na tensão. Os jumpers fêmea-macho foram usados para interligar o Arduino à protoboard. Os leds ascedem em intervalos de tempo diferente, no caso do led vermelho, o progrmama mantém a luz dele ascesa por 6 segundos, no caso do amarelo a duração é de 2 segundos e o led verde ascende por 4 segundos, isso é um ciclo contínuo e automatizado pelo programa utilizado a função tempoMillis() usa o millis(), que conta o tempo desde que o Arduino foi ligado, para controlar a duração de cada fase sem bloquear o loop principal diferente do delay.


### Tabela de Avaliação entre Pares
#### Avaliador: Guilherme Schmidt
|Critério|  Contempla (Pontos)| Contempla Parcialmente (Pontos) |Não Contempla (Pontos) |Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores   |3  |   || |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo |3  |   | | |
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |  3|   |   | |
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |   |  0,5 |   | |
| | | | |Pontuação Total: 9,5|

### Tabela de Avaliação entre Pares
#### Avaliador: Lucas Lopes
|Critério|  Contempla (Pontos)| Contempla Parcialmente (Pontos) |Não Contempla (Pontos) |Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores   |3  |   || |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo |3  |   | | |
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |  3|   |   | |
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |   |  0,5 |   | |
| | | | |Pontuação Total: 9,5|

