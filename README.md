# Sistema de Monitoramento Industrial

## Identificação

**Aluno:** Victor Rocha da Silva
**Disciplina:** Linguagem C
**Professora:** Profa. Karla Sartin
**Projeto:** Sistema de Monitoramento Industrial

## Objetivo

O objetivo do programa é fazer o monitoramento de temperaturas de um sistema. O usuário informa um limite de temperatura e depois coloca as temperaturas que serão analisadas pelo programa.

O programa verifica as temperaturas, identifica quando alguma está acima do limite e encerra o monitoramento automaticamente quando aparecem 3 temperaturas consecutivas acima do limite.

## Como o programa funciona

Primeiro, o programa pede o limite de temperatura. Esse valor precisa ser maior que 0.

Depois, o usuário informa as temperaturas uma por uma.

O programa verifica se o valor digitado é válido. Caso seja digitado algo que não seja um número, o programa informa que a entrada é inválida e pede novamente.

Para cada temperatura válida, o programa verifica se ela está acima do limite.

Quando a temperatura está acima do limite, o programa aumenta a quantidade de temperaturas acima do limite e também conta como uma temperatura consecutiva.

Quando a temperatura não está acima do limite, a contagem de temperaturas consecutivas volta para 0.

Quando são identificadas 3 temperaturas consecutivas acima do limite, o programa mostra um alerta e encerra o monitoramento.

Também é possível encerrar o programa manualmente digitando `000`.

No final, o programa apresenta:

* Total de leituras
* Média das temperaturas
* Maior temperatura
* Menor temperatura
* Quantidade de temperaturas acima do limite
* Percentual de temperaturas acima do limite

## Estruturas de repetição utilizadas

### do...while

O `do...while` foi utilizado para pedir o limite de temperatura e verificar se o valor informado é válido.

Essa estrutura foi utilizada porque o programa precisa pedir o valor pelo menos uma vez e só depois verificar se ele está correto.

### while

O `while` foi utilizado para continuar recebendo as temperaturas enquanto o monitoramento estiver acontecendo.

O programa pode sair desse processo quando o usuário digita `000` ou quando são identificadas 3 temperaturas consecutivas acima do limite.

