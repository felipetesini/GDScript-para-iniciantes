# TÓPICO I — `print()` [depuração, output e etc...]
Sem enrolação, se você nunca pesquisou no navegador: **"O que é `print()`?"** então eu vou te mostrar o resultado robusto que você recebe:

> `print()` em GDScript é uma função fundamental para **depuração** (debugging), usada para exibir **mensagens**, **variáveis** ou o **estado do seu jogo no console de saída** (Output) da Godot Engine [...]

Parece maluquice, não? Depuração, função, console de saída, output... Mas relaxa! Isso tudo são apenas nomes chiques e estilosos, vamos quebrar a taça de vidro e organizar os cacos em ordem:

1. `print()` é como um comando que a própria Godot Engine criou e te permite usar. Com esse comando, você pode mostrar mensagens (informações) no **Output** da Godot.
-# Explicação de Output mais abaixo, continue lendo...

2. `Depuração` ou também chamado de `debug`, nada mais é que o processo de encontrar e corrigir erros (bugs) em um código. Então, quando você identifica um erro num código e começa a elaborar uma solução para ele, você **automaticamente** está fazendo uma __depuração__. Simples, não?

3. `Output`, vulgo **Console de Saída**, é literalmente a **Saída** de tudo o que acontecer com o seu código! Sejam: erros, avisos e mensagens no geral. Toda vez que você usar `print()` em seu código, o resultado sempre aparecerá na janela com o nome **Output** (muitos devem achar óbvio, mas é bom explicar).

### Wow...
Aprendemos termos novos, mas vamos avançar:
**"Por que `print()` é o primeiro tópico desse material didático?"**, você provavelmente não se perguntou, mas agora quer uma resposta, acertei?
Simples! Ele vai ser sua única ferramenta para brincar com seu código por um bom tempo, mas você nunca vai deixar de usá-lo mesmo após isso, além de que é o mais simples e intuitivo para iniciantes como eu e você!

### Direto ao ponto!
Enfim, eu disse que `print()` era um comando, e no mundo da programação, chamamos esses comandos que a própria Godot criou de: **funções embutidas** (também conhecidas como funções **built-in**).
Não entraremos em detalhes sobre funções embutidas agora, só tenha em mente que elas:
- Só precisam ser usadas, nada mais.
Pois todo o código que faz essa função embutida funcionar está todo escondido dentro da Engine, e não dá pra ver esse código, então não se preocupe com isso, apenas foque em usar a função.

## Prática & Exemplos

Vamos mexer com o `print()` no seu código! (espero que seu Godot esteja aberto)
Usaremos a função `print()` da seguinte forma:
```gdscript
print("Olá, mundo!")
```
Mas, se você foi apressado o suficiente para rodar o código antes que eu pedisse, então viu que digitar apenas isso não vai funcionar, pois nos deparamos com o seguinte erro:
```diff
- Error at (3, 1): Unexpected identifier "print" in class body.
```
Traduzindo literalmente: **Identificador inesperado "print" no corpo da classe.**
E santo Deus! Outro termo chique e estiloso para decifrarmos... Mas não vamos entrar em detalhes dessa questão agora, vamos aprofundar isso quando chegarmos no tópico de `FUNÇÕES`, então fica tranquilo!

Para contornarmos essa situação, digite o seguinte código:
```gdscript
extends Node
func _ready():
  print("Olá, mundo!")
```
E voilà! O código agora irá mandar a mensagem "Olá, mundo!" no seu **Output**.
Se você não sabe o porquê de termos adicionado `extends Node` e `func _ready():` para fazer o código funcionar, recomendo que leia o nosso **TÓPICO 0 — Engine** na qual eu explico minuciosamente como a Godot Engine lê e executa seu código, assim como os fundamentos importantes que um iniciante deve aprender para não ficar preso na primeira mensagem de erro que ele se deparar.

Agora, **"como manipular o texto na minha função?"** — você se perguntou, né? E isso é muito simples:
Como você já sabe, `print()` é uma **função embutida** que vai mostrar no **Output** da Godot a mensagem que você definir.
A mensagem que você quer colocar vai ficar dentro das "aspas", deu para entender? Por exemplo:
```gdscript
  print("Você vai escrever sua mensagem aqui dentro!")
  print("E toda vez que você quiser mandar um texto, PRECISA obrigatoriamente estar dentro de aspas!")
  print("E claro, as aspas precisam estar dentro dos parenteses, se não, a Engine não vai entender que isso faz parte do print()")
```
Intrigante, não? E além de você poder exibir qualquer tipo de mensagem (texto) no seu **Output**, você também consegue usar números, assim como fazer cálculos com eles apenas usando `print()`! Dê uma olhada:

```gdscript
  print("Olá, mundo! O resultado de 2+2 é: ",2+2)
```
Se você rodar o código acima, vai ver este resultado:
```gdscript
  Olá, mundo! O resultado de 2+2 é: 4
```
E não, a Engine não vai entender que você quer somar dois números se você fizer: `print("A soma de 2+2 é: 2+2")`, isso porque tudo o que estiver dentro das **"aspas"** será lido pela Engine como TEXTO, nada mais e nada menos, então, se você quer que uma expressão matemática dê um resultado, precisará SEPARAR o texto da expressão.
E se você é esperto, já deve ter notado que eu separei o texto da expressão usando uma VÍRGULA, sim, uma vírgula... Em casos como esse, ela serve para separar múltiplos valores (números, texto, boolean, variável, etc) para você exibir no **Output**, por isso, o correto a se fazer para mandar uma mensagem no **Output** com uma expressão matemática calculada é dessa forma:
```gdscript
  print("Oi! Meu nome é Felipe. Eu nasci em 2007, então eu tenho ",2025-2007," anos de idade.")
         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^    ^^^^^     ^^^^^^^^^^^^
                                 texto                             expressão      texto
```

## Vamos brincar!

Usando apenas o `print()`, podemos exibir diversas mensagens no nosso **Output**! Até mesmo podemos criar diálogos meramente didáticos para tornar o uso dessa **função embutida** mais divertida... Agora, como desafio para você, quero que você tente replicar esse resultado no seu **Output**:
```
  Maria: Oi! Meu nome é Maria! Como você se chama?
  João: Tudo bem, Maria? Eu me chamo João! Prazer em conhecê-la.
  Maria: Igualmente! Quantos anos você tem?
  João: Eu nasci em 2005, então tenho X anos, e você?
  Maria: Que legal! Eu sou um ano mais velha que você! Tenho X anos!
```
**Seu desafio é simples:** no seu código, subtraia o ano de nascimento do João pelo nosso ano atual, mas, usando a expressão matemática dentro de `print()`, para que dessa forma o diálogo seja corrigido e tenha o valor de X encontrado.
