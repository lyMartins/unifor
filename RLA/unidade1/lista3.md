
# UNIFOR
**Nome**: Carlyle Martins <br>
**Disciplina**: Raciocínio lógico algorítm

## Exercício exemplo 1
Implemente e teste um programa que imprima os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\num = 1\]
D --> E{num <= n}
E --FALSE--> I([FIM])
E --TRUE--> F{{"Num", num}}
F --> G[num =+ 1]
G --LOOP--> E
```

#### Pseudocódigo
```
ALGORITMO print_n_primeiros
DECLARE n, num: INTEIRO

INICIO

	ESCREVA “Digite um número: ”
	LEIA n			// variável de entrada n

	num ← 1			// variável num inicializada

	ENQUANTO num <= n FAÇA	// n iterações
		ESCREVA “Número ”, num

		num ← num + 1		// num =+ 1 (incremento)

	FIM_ENQUANTO
FIM
```

#### Teste de mesa
| it | n  | num | num <= n | Saída      | num =+ 1 |
| -- | -- | --  | --       | --         | --       |
| 1  | 10 | 1   | True     | Número 1   | 2        |
| 2  | 10 | 2   | True     | Número 2   | 3        |
| 3  | 10 | 3   | True     | Número 3   | 4        |
| 4  | 10 | 4   | True     | Número 4   | 5        |
| 5  | 10 | 5   | True     | Número 5   | 6        |
| 6  | 10 | 6   | True     | Número 6   | 7        |
| 7  | 10 | 7   | True     | Número 7   | 8        |
| 8  | 10 | 8   | True     | Número 8   | 9        |
| 9  | 10 | 9   | True     | Número 9   | 10       |
| 10 | 10 | 11  | True     | Número 10  | 11       |
| 11 | 10 | 11  | False    |            |          |

## Exercício exemplo 2
Implemente e teste um programa que some os n primeiros números.

#### Fluxograma
```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número: }}
B --> C[\n\]
C --> D[\soma = 0\]
D --> E[[i=1 ATÉ n PASSO 1]]
E --FALSE--> G([FIM])
E --TRUE--> F[soma =+ i]
F --LOOP--> E
```

#### Pseudocódigo
```
ALGORITMO	soma_n_numeros()
DECLARE	n, i, soma: INTEIRO

INICIO

	ESCREVA “Digite a quantidade de números: ”
	LEIA n		// variável de entrada n

	soma ← 0		// variável soma inicializada

	PARA i DE 1 ATÉ n PASSO 1 FAÇA

		soma ← soma + i	// soma =+ i (incremento)

	FIM_PARA

	ESCREVA “A soma é igual a ”, soma
FIM
```

#### Teste de mesa
| it | n  | soma | i  | soma =+ i |
| -- | -- | --   | -- | --        |
| 1  | 10 | 0    | 1  | 1         |
| 2  | 10 | 1    | 2  | 3         |
| 3  | 10 | 3    | 3  | 6         |
| 4  | 10 | 6    | 4  | 10        |
| 5  | 10 | 10   | 5  | 15        |
| 6  | 10 | 15   | 6  | 21        |
| 7  | 10 | 21   | 7  | 28        |
| 8  | 10 | 28   | 8  | 36        |
| 9  | 10 | 36   | 9  | 45        |
| 10 | 10 | 45   | 10 | 55        | 

## Lista de exercícios 03

### Exercício 01 (2.5 pontos)
Atualize o algoritmo para determinar se um número inteiro e positivo é par ou ímpar, usando uma laço condicional para aceitar apenas números maiores ou iguais a zero. 

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número}}
B --> C[\num,res\]
C --> D{num<=0}
D--loop-->B
D--TRUE-->E[res = num % 2]
E-->F{res == 0}
F--FALSE-->G{{esse número 'num' é impar}}
F--TRUE-->H{{esse número 'num' é par}}
H-->I([FIM])
G-->I
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO par ou impar
DECLARE num, res : inteiro

INICIO

	ESCREVA "Digite um número"
	LEIA  num

	ENQUANTO num < 0 FAÇA
		ESCREVA "Digite um número positivo"

	FIM_ENQUANTO

	SE num>=0 ENTAO
		res <- n%2 

			SE res == 0 ENTAO
				ESCREVA "esse número 'num' é par"

		
			SENAO
				ESCREVA "esse número 'num' é impar"

			FIM_SE
	SENAO
		ESCREVA "O número deve ser positivo!"

	FIM_SE

FIM
```

#### Teste de mesa (0.5 ponto)

| Iteração | num | res | Saída | 
| -- | -- | -- | -- | 
| 1 | 7 | 1 | "esse número 7 é impar" |
| 2 | 12 | 0 | "esse número 12 é par" |
| 3 | -5 | Não definido | "esse número 3 é impar" |   
| 4 | 3 | 1 | "esse número 3 é impar" |


### Exercício 02 (2.5 pontos)
Faça um algoritmo que exiba na tela uma contagem de 0 até 30, exibindo apenas os múltiplos de 3.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B[\num\]
B --> C[num = 0]
C --> D{num <=30}
D-->E{num % 3 = 0}
E-->F{{num}}
F-->G[num <- num + 3]
G-->H([FIM])
```

#### Pseudocódigo (1.0 ponto)

```
ALGORTIMO MultiploTres
DECLARE n: INTEIRO

INICIO

	// Variável n como dado de entrada
	ESCREVA "Digite a quantidade de números:"

	// Armazena o valor de entrada na variável "n"
	LEIA n

	//  Loop contado (loop for) executa as instruções a cada iteração dos valores de 'i' de 0 até n-1, incrementando 'i' em 3.
	PARA i DE 0 ATÉ n-1 PASSO 3 FAÇA

		// Exibe cada resultado das iterações feitas
		ESCREVA i

	FIM_PARA

FIM

```

#### Teste de mesa (0.5 ponto)

| it | n   | i  | saida | 
| -- | --  | -- | --    |    
| 1  | 7   | 0  | 0     |
| 2  | 7   | 3  | 3     |
| 3  | 7   | 6  | 6     |

### Exercício 03 (2.5 pontos)
Dada uma sequência de números inteiros, calcular a sua soma. 
Por exemplo, para a sequência {12, 17, 4, -6, 8, 0}, o seu programa deve escrever o número 35.

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a quantidade de números:"}}
B --> C[\n\]
C --> D[i = 1]
D --> E[soma = 0]
E --> F{i <= n}
F --FALSE--> G{{A soma dos número é, soma}}
G --> L([FIM])
F --TRUE--> H{{Digite o número, i,:}}
H --> I[\num\]
I --> J[soma = soma + num]
J --> K[i = i + 1]
K --LOOP--> F
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO SomaValores
DECLARE n,i: INTEIRO; soma,num: REAL

INICIO

	// Dado de entrada armezenado na variável n
	ESCREVA "Digite a quantidade de números:"

	// Armazena o valor de entrada na variável "n"
	LEIA n

	// Inicializa a variável "soma" em 0
	soma <- 0

	// Inicializa a variável "i" em 1
	i <- 1

	// Loop condicional (loop while) executa as instruções enquanto a condição "i <= n" for verdadeira
	ENQUANTO i <= n FAÇA

		// Exibe a mensagem solictando o número em cada iteração
		ESCREVA "Digite o número", i,":"

		// Armazena o valor de entrada na variável "num"
		LEIA num

		// Incrementa "num" na variável "soma" em cada iteração
		soma <- soma + num

		// Incrementa 1 na variável "num" em cada iteração
		i <- i + 1

	FIM_ENQUANTO

	// Exibe a mensagem concatenando aos caracteres "A soma dos número é" com a variável "soma".
	ESCREVA "A soma dos número é", soma

FIM
```

#### Tabela de testes (0.5 ponto)

| n  | soma | i  | i <= n | num | soma + num | i + 1   | saída                      |  
| -- | --   | -- | --     | --  | --         | --      | --                         |
| -1 | 0    | 1  | False  |     |            |         | A soma dos número é 0      |
| 0  | 0    | 1  | False  |     |            |         | A soma dos número é 0      |
| 3  | 0    | 1  | True   | 10  | 0+10 = 10  | 1+1 = 2 |                            |
| 3  | 10   | 2  | True   | 20  | 10+20 = 30 | 2+1 = 3 |                            |
| 3  | 30   | 3  | True   | 30  | 30+30 = 60 | 3+1 = 4 |                            |
| 3  | 60   | 4  | False  |     |            |         | A soma dos número é 60     |


### Exercício 04 (2.5 pontos)
Escreva um programa que leia a nota de diversos alunos, até que seja digitada uma nota negativa. 
Nesse momento, ele mostra a média aritmética de todas as notas lidas e quantas notas foram lidas. 
Ex. Foram lidas 14 notas. A média aritmética é 6.75!

#### Fluxograma (1.0 ponto)

```mermaid
flowchart TD
A([INICIO]) --> B[/soma/]
B --> C[/cont/]
C --> D{{"Digite a nota do aluno (nota negativa finaliza): "}}
D --> E{nota >= 0}
E --FALSE--> F{cont > 0}
F --FALSE--> Z([FIM]) 
F --TRUE--> G[media = soma / cont]
G --> H{{Foram lidas, cont, notas. A média aritmética é, media!}}
H --> Z
E --TRUE--> I[soma += nota]
I --> J[cont += 1]
J --> K{{"Digite a nota do aluno (nota negativa finaliza): "}}
K --LOOP-->  E
```

#### Pseudocódigo (1.0 ponto)

```
ALGORITMO CalculoMediaNotas
DECLARE nota, soma, contador: REAL

INICIO 
	 soma <- 0
	 contador <- 0

	ENQUANTO nota < 0 FAÇA
		ESCREVA "Digite a nota do aluno"
		LEIA nota

		SE nota >= 0 ENTAO
			soma <- soma + nota
			contador <- contador + 1
		FIM SE 
		FIM ENQUANTO

		SE contador > 0 ENTAO
			media <- soma/contador 
			ESCREVA "A média das notas é : ', edia'"
			ESCREVA "Foram digitadas ' , contador, " notas válidas."
		FIM SE
	FIM 
```


#### Tabela de testes

| it  | nota  | soma  | cont | nota >= 0 | soma + nota     | cont + 1 | nota    | cont > 0 | media          | saída                                            | 
| --  | --    | --    | --   | --        | --              | --       | --      | --       | --             | --                                               |
| 1   | -1.0  | 0.0   | 0    | False     |                 |          |         | False    |                |                                                  |

| it  | nota  | soma  | cont | nota >= 0 | soma + nota     | cont + 1 | nota    | cont > 0 | media          | saída                                            | 
| --  | --    | --    | --   | --        | --              | --       | --      | --       | --             | --                                               |
| 1   | 0.0   | 0.0   | 0    | True      | 0.0+0.0 = 0.0   | 0+1 = 1  | -1.0    |          |                |                                                  |
| 2   | -1.0  | 0.0   | 1    | False     |                 |          |         | True     | 0.0/1 = .0     | Foram lidas 1 nota(s). A média aritmética é 0.0! |

| it  | nota  | soma  | cont | nota >= 0 | soma + nota     | cont + 1 | nota    | cont > 0 | media          | saída                                            | 
| --  | --    | --    | --   | --        | --              | --       | --      | --       | --             | --                                               |
| 1   | 4.0   | 0.0   | 0    | True      | 0.0+4.0 = 4.0   | 0+1 = 1  | 8.0     |          |                |                                                  |
| 2   | 8.0   | 4.0   | 1    | True      | 4.0+8.0 = 12.0  | 1+1 = 2  | 6.0     |          |                |                                                  |
| 3   | 6.0   | 12.0  | 2    | True      | 12.0+6.0 = 18.0 | 2+1 = 3  | -8.0    |          |                |                                                  |
| 4   | -8.0  | 18.0  | 3    |           |                 |          |         | True     | 18.0/3.0 = 6.0 | Foram lidas 3 nota(s). A média aritmética é 6.0! |
