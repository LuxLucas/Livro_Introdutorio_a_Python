# 2 - Como o Python vê o mundo

> Um comando muito utilizado é o `print()`. Ele escreve algo na saída padrão (no caso do Python, o console/tela)
> Formalmente o `print()` è:
> 
>  ```py
>   print(*objects, sep=' ', end='\n', file=sys.stdout)
>  ```
>  Onde:
> - _***objects:**_ lista de valores e/ou variáveis
> - _**sep = ' ':**_ caractere colocado entre cada valor escrito
> - _**end = '\n':**_ caractere usado no final da linha ('\n' pula a linha)
> - _**file = sys.stdout:**_ onde escrever as informações
>  
> Exemplos:  
> | PRINT | RESULTADO |
> | ----- | --------- |
> | print(1, 2, 3) | 1 2 3 |
> | print(1, 2, 3, sep=';') | 1;2;3 |

## Variáveis

O ato de declarar uma variável é: 
- (1) Reservar um espaço na memória RAM (Random Acess Memory).
- (2) Associar esse espaço a um identificador, ou seja, dar um nome a ele.

### Nomeação de variáveis
Assim como em outras linguagens, no Python, todo identificador:
- **Pode:**
  - **Começar com:** uma letra (caractere alfabético).
  - **Pode conter:** caracteres alfanuméricos (letra e números) e o "_" (underline).
  
- **Não pode:**
  - Espaço e caracteres especiais ("@", "-", "+", ".", "," ...).
  - _Palavras reservada_ (que possuem uso definido na linguagem), como: _for, if, int, print_ e entre outros.

O Python é case _sensitive_, ou seja, diferencia variáveis com letras minúsculas e maiúsculas. 
> Também, é aceito acentos em identificadores, mas não é recomendado para programadores.

```py
a = 1
A = 5
print('Variável a - Valor:', a)
print('Variável A - Valor:', A)
```

**Tabela 2.1.** Nome de Identificadores
| Identificadores Válidos | Identificadores Inválidos |
| :---: | :---: |
| A | 1A |
| Nota1 | 1Nota |
| Media_Final | Média Final
| Aluno | Aluno-Curso |
| a12b12 | a12/b12 |
| escreva | print |

### Tipos de variáveis
A linguagem Python é _Dinâmicamente Tipada_. Significa que toda variável possui seu tipo alterado durante a execução do _script_, sendo o interpretador que decide.
 ```py
 a = 1       # Inteiro
 a = 1.0     # Float
 a = "1"     # String
 a = True    # Booleano
 a = 3+12j   # Número complexo
 ```

> "#" (quadrilha) indica um comentário, tudo que o seguir, até o fim da linha, será ignorado pelo interpretador.  
> "\```" (crase) para comentar mais de uma linha, exemplo: \``` código ```.

**Tabela 2.2.** Tipos de Variáveis
| Tipo | Exemplo |
| --- | :---: |
| Booleano _(Bool)_ | True, False |
| Inteiro _(Int)_ | 1 |
| Ponto Flutuante _(Float)_ | 1.23 |
| Número complexo _(Complex)_ | 3+5x |
| String _(Str)_ | "12" |

### Operadores aritméticos

Para operações aritméticas simoles o Python possui:
| **Operador** | **Descrição** |
| :----------: | ------------- |
| + | Soma |
| - | Subtração |
| * | Multiplicação |
| / | Divisão |
| // | Divisor de inteiros | 
| % | Retorna o resto de uma  divisão de inteiros |
| ** | Exponenciação |

```py
a = 1.0         # a vale 1
b = a + 1       # soma
c = b - 3.0     # subtração
d = b / 2       # divisão
e = a % b       # resto de divisão (retorna o resto da divisão em inteiro)
f = b ** 2      # exponenciação (em outras linguagens é: b^2)
g = b * 7       # multiplicação
h = g // 3      # Divisão que retorna a parte inteira

print(a, b, c, d, e, f, g, h)
```

No _script_ 2.4, é exemplificado o uso das operações de divisão e resto para saber quantas notas de cada tipo são necessárias para um caixa dar troco, que, no caso, são R$ 135,00 reais. No exemplo há muitas parte que se repetem, peguemos a referente as notas de R$ 100,00:

- Na linha 3, é calculado a divisão entre o troco por 100 e pego a parte inteira dessa divisão, sendo ela, a quantidade de R$ 100,00 para serem entregues.
- Na linha 4, verifica-se o quanto sobrou para dar de troco, no caso, 35.

```py
 troco = 135
 
notas100 = troco // 100
troco = troco % 100
print("Entregar ", notas100, "notas de R$ 100,00")

notas50 = troco // 50
troco = troco % 50
print("Entregar ", notas50, "notas de R$ 50,00")

notas20 = troco // 20
troco = troco % 20
print("Entregar ", notas20, "notas de R$ 20,00")

notas10 = troco // 10
troco = troco % 10
print("Entregar ", notas10, "notas de R$ 10,00")
 
notas5 = troco // 5
troco = troco % 5
print("Entregar ", notas5, "notas de R$ 5,00")

notas2 = troco // 2
troco = troco % 2
print("Entregar ", notas2, "notas de R$ 2,00")
```

### Operadores lógicos
Os operadores lógicos comparam variáveis e retornam um _valor lógico_ (tipo booleano), ou seja, True ou False.

**Tabela 2.4:** Operadores Lógicos
| **Operador** | **Descrição** |
| :----------: | ------------- |
| == | Igual |
| != | Diferente |
| < | Menor |
| > | Maior | 
| <= | Menor igual |
| >= | Maior igual |
| not | Negação |
| and | Operador E |
| or | Operador OU |

Expressões lógicas podem ser conectadas pelos operadores _and_ (as expressões devem ser verdadeiras para retornar True) e _or_ (pelo menos uma expressão deve ser verdadeira para retornar True). O operador _not_ nega o resultado de uma expressão, retornando um valor contrário, se comparar True retorna False, se comparar False retorna True.

```py
A = 10
B = 15
C = 10

print("O valor da variável A é igual ao valor de B - ", A == B)
print("O valor da variável A é igual ao valor de C - ", A == C)
print("O valor da variável A é maior que o valor de C - ", A > C)
print("O valor da variável A não é igual ao valor de C - ", A != C)
print("O valor da variável A não é igual ao valor de C - ", not A == B)
print("O valor da variável A é igual ao valor de C e menor que B - ", A == C and A > B)
print("O valor da variável A é igual ao valor de C ou menor que B - ", A == C or A > B)
print("O valor da variável A + 5 é igual ou maior que B - ", A+5 >= B)
```

### Múltiplas atribuições
O python permite atribuir multiplos valores numa única linha.

```py
a, b = 2, 1
# a recebe 2
# b recebe 1

a, b = b, a   # Troca de valores
```

### Atribuições condicionais
Outra forma de atribuir valores a variáveis em Python é a atribuição condicional.

```py
# Atribui 1 para a variável a
a = 1

# Se a for maior que 0, atribui o valor 2 para a variável b. Senão, atribui 0
b = 2 if a > 0 else 0

# Atribui uma mensagem diferente para m conforme o valor de a
m = "Baixo" if a < 5 else "Alto"
```

## Entrada de dados

Programas normalmente possuem as etapas de _entrada_, _processamento_ e _saída de dados_. Um uso comum para entrada de dados em Python é usando a função `input`, que recebe um texto do teclado (num tipo de dado chamado _string_). 

Porém o tipo _string_ não é o ideal para certos processamentos, como operações aritméticas, para isso são usados métodos _tradutores_:
```py
idade = int(input("Qual sua idade? "))
print(idade)    # ex: 18

salario = float(input("Qual o seu salário? "))
print(salario)  # 1500.0

idade_string = str(idade)
print(idade_string) # "18"

numero_complexo = complex(idade + 1j)
print(numero_complexo)  # 18+1j

valor_bool = bool(numero_complexo)
print(valor_bool)   # True
```

## Strings
O tipo _string_ no Python é uma instância (um objeto) de uma classe chamada _string_. De forma simples, uma classe é uma estrutura computacional que possui dados e funções (atributos e métodos).

### Concatenação
Concatenação é juntar um ou mais strings ("juntar" texto), comumente usando o operador "+".

```py
artigo = 'A '
substantivo = 'floresta '
verbo = 'é '
adjetivo = 'harmoniosa'

frase = artigo + substantivo + verbo + adjetivo
print(frase)
```

### Substrings
_Substrings_ são "pedaços" de um texto maior, uma _string_. No python elas são representadas pelo operador [ ], com ele é possível acessar caracteres em conjunto de caracteres a partir de parâmetros de referência dentro do vetor.

O formato é `Parte = Todo[inicio : fim]`, onde _Todo_ é a _string_ original, _Parte_ o trecho selecionado de _Todo_, _inicio_ e _fim_ delimitam os trechos a serem extraídos. Tanto _inicio_ e _fim_ são valores numéricos e podem estar armazenados em variáveis, delimitam a parte da _string_ a ser extraída.

Quando os valores _inicio_ e _fim_ forem vazios, será atribuído a _inicio_ o valor zero e a _fim_ o maior ìndice da _string_. Quando esses parâmetros forem negativos a referência ou a ordem são determinados pelo tamanho da cadeia de caracteres **menos o valor de referência.**

Tenhamos o seguinte exemplo:
```py
Todo = "OCEANO ATLÂNTICO"
```
A palavra "OCEANO ATLÂNTICO" em Python possui 16 caracteres - lembre-se o espaço também é um caractere -, numerado de 0 até 15 - totalizando 16 números.
| Índice  | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  |
| ------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Palavra | O | C | E | A | N | O |  | A | T | L | Â | N | T | I | C | O |

```py
Todo = "OCEANO ATLÂNTICO"
print(Todo[0])      # O
print(Todo[:2])     # OC
print(Todo[2:])     # EANO ATLÂNTICO
print(Todo[-3:])    # ICO
print(Todo[:-5])    # OCEANO ATLÂ
print(Todo[2:9])    # EANO AT
print(Todo[5:1])    # Retorna nada, o início é maior que o fim
print(Todo[-3:-8])  # Retorna nada, o início é maior que o fim
```

### Métodos para trabalhar com string
O tipo _string_ em Python é um objeto advindo da instância de uma classe, no caso a _str_, um caso de lista no Python. Um objeto é formado por atributos - que guardam dados, como variáveis - e métodos, que manipulam os atributos. Há vários métodos para se trabalhar com _strings_, sendo acessados pelo nome da variável, um ponto, a função e seus parâmetros.

```py
texto = "são PAULo"
```

Alguns desses métodos são:

#### Capitalize()
Faz o primeiro caractere ficar em maiúsculo, o resto minúsculo.
```py
texto_cap = texto.capitalize()
print(texto_cap)    # São paulo
```

#### Center(x)
Faz o texto ficar centralizado em uma linha de largura "x" caracteres.
```py
texto_cent = texto.center(45)
print(texto_cent)   #                   são PAULo
```

#### Lstrip(x)
Remove os primerios caracteres da _string_ que forem iguais a "x".
```py
texto_remo = texto.lstrip("são")
print(texto_remo)   #  PAULo
```

#### Replace(x, y)
Substitui os caracteres "x" por "y".
```py
texto_troca = texto.replace("o", "_")
print(texto_troca)  # sã_ PAUL_
```

#### Upper() 
Faz o texto ficar todo em maiúsculo 
```py
texto_up = texto.upper()
print(texto_up)     # SÃO PAULO
```

#### Lower()
Faz o texto ficar todo em minúsculo |
```py
texto_low = texto.lower()
print(texto_low)    # são paulo
```

### Métodos relacionados com string
Também há métodos que lidam com _substrings_.
```py
palavra = "Paralelo"
```
#### Count(x)
Conta quantas vezes há "x" na _string_.
```py
cont_palavra = palavra.count("a")
print(cont_palavra)     # 2
```

#### Find(x)
Retorna o indice mais baixo da _substring_ "x" na_string_; -1 se "x" não é encontrado.
```py
find_palavra = palavra.find("l")
print(find_palavra)     # 4
```

#### Endswirth(x)
Retorna True caso a _string_ termine com "x".
```py
fim_palavra = palavra.endswith("o")
print(fim_palavra)      # True
```

#### Index(x)
Como o find(x), mas retorna ValueError se não existir.
```py
index_palavra = palavra.index("e")
print(index_palavra)    # 5
```

#### Rfind(x)
Como find(x), mas retorna o maior índice.
```py
rfind_palavra = palavra.rfind("P")
print(rfind_palavra)    # 0
```

#### Rindex(x)
Como o index(x) retorna, mas retorna o maior index.
```py
rindex_palavra = palavra.rindex("a")
print(rindex_palavra)   # 3
```

#### Split(x) 
Divide a string em palavras, sendo o  separador "x".
```py
split_palavra = palavra.split('l')
print(split_palavra)    # ['Para', 'e', 'o']
```

#### Len(x)
Retorna o número de caracteres _string_ "x".
```py
tamanho_palavra = len(palavra)
print(tamanho_palavra)  # 8
```
