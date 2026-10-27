# Aula 16 - Variáveis Compostas - Tuplas:
## Relembrando variáveis

Variável é um espaço da memória dedicado à algo.

ex: “lanche = hamburguer”

Por padrão, cada variável recebe apenas 1 valor. Essas variáveis recebem o nome de “Variáveis simples”

## O que é uma Tupla?

Tuplas são uma forma de guardar mais de um valor no mesmo bloco de informação de uma variável, ou seja, é uma variável composta.
Outras variáveis compostas são:
- Listas,
- Dicionários.
Os elementos de uma tupla são identificados por índices [0, 1, 2, 3, ..]

![[Pasted image 20261026223109.png]]

Os elementos de uma tupla podem ser fatiados usando o mesmo método de fatiamento de strings (que na verdade são uma lista).

### Exemplos de fatiamento

#### Input

print (lanche [2])
#### Output
Pizza
___
#### Input

print (lanche [0:2])
#### Output

Hambúrguer, Suco
___
#### Input

print (lanche [1:])
#### Output
Suco, Pizza, Pudim
___
#### Input

print (lanche [-1])
#### Output

Pudim
___
### Outros comandos úteis

#### Input

len(lanche)
#### Output

4
___
#### Input

print(sorted (lanche))
#### Output

['Hambúrguer', 'Pizza', 'Pudim', 'Suco']
___
#### Input

print(lanche.index("suco"))
#### Output

1
___
## Outras funções nativas e métodos úteis

max(tupla) → Retorna o **maior** valor de uma variável composta.
min(tupla) → Retorna o **menor** valor de uma variável composta.
sum(tupla) → **Soma** todos os valores de uma variável composta.
tupla.count(valor) → Conta exatamente **quantas vezes** um determinado valor aparece dentro da tupla.
tupla.index(valor) → Retorna o número do **índice (a posição)** da primeira ocorrência daquele valor.

## Usos das variáveis compostas
As variáveis compostas também podem ser usadas com estruturas de repetição.
Por exemplo:
#### Input
for c in lanche:
print(c)
#### Output
hambúrguer
suco
pizza
pudim

## **Limitação:** **Tuplas são imutáveis.**
___
**Obs.** Em Python as variáveis compostas são representadas de formas diferentes dependendo dos seus tipos:
- ( ) - Tuplas
- [] - Listas
- { } - Dicionários
# Aula 17 - Variáveis compostas - Listas (Parte 01):
## O que é uma lista?
Uma lista é uma estrutura muito parecida com uma tupla, mas diferente delas, as listas são mutáveis.
![[Pasted image 20261026223634.png]]
## Manipulando listas

Para **criar** uma lista dentro do código podemos usar a função _list_ e combiná-la com _range_, por exemplo.
Para **adicionar** mais valores a uma lista usamos o método _append_ ou o método _insert_ e para **excluir** valores usamos o comando _del_, o método _remove_ que remove um item baseado no seu valor, ou o método _pop_.
Para remover um item **com segurança** usando o método _remove_ podemos usar a estrutura _if_ junto com o operador _in_ para verificar se o item em questão está na lista.
### Exemplos
#### Criar
valores = list(range(4,11))
![[Pasted image 20261026223659.png]]
#### Inserir
**lanche.append(‘Cookie’)** → Adiciona um 5º valor ao final da lista.
**lanche.insert(0,‘Cachorro Quente’)** → Adiciona um 5º valor na chave zero “empurrando” a numeração das chaves posteriores para frente.
![[Pasted image 20261026223733.png]]
#### Remover

**del lanche[3]** → É um comando, não um método.

**lanche.pop(3)** → Geralmente usado para apagar o último valor, mas pode ser usado indicando o índice.

**lanche.remove(‘Pizza’)** → Esse método remove o valor baseado no seu conteúdo e não no seu índice.

![[Pasted image 20261026223744.png]]

**lanche.pop()** → Remove o último ítem da lista.

![[Pasted image 20261026223752.png]]

**if ‘Pizza’ in lanche:**
lanche.remove(‘Pizza’)
## Cópias de listas

Ao fazer uma lista B receber os valores de outra lista A da forma convencional o Python cria uma ligação entre as duas listas, ou seja, alterando os valores de B, os valores de A são alterados também.
Para criar uma cópia dos valores de A em B, deve-se fazer com que B receba os valores de A.
### Criando uma ligação
#### Input
a = [2, 3, 4, 7]
b = a
b[2] = 8
print(f”Lista A: {a}”)
print(f”Lista B: {b}”)
#### Output
Lista A: [2, 3, 8, 7]
Lista B: [2, 3, 8, 7]
___
### Criando uma cópia
#### Input
a = [2, 3, 4, 7]
b = a[:]
b[2] = 8
print(f”Lista A: {a}”)
print(f”Lista B: {b}”)
#### Output
Lista A: [2, 3, 4, 7]
Lista B: [2, 3, 8, 7]
___
# Aula 18 - Variáveis compostas - Listas (Parte 02):
É possível adicionar uma lista dentro de outra lista.

| pessoas = []<br>dados = [‘Pedro’, 25]<br>pessoas.append(dados[:]) |
| ----------------------------------------------------------------- |

O que acontece nesse caso é que foi criada uma cópia da lista de dados dentro da posição 0 da lista pessoas.
![[Pasted image 20261026223942.png]]
Podemos declarar tudo isso de uma vez só com essa estrutura:
![[Pasted image 20261026223955.png]]
Pode-se buscar dados específicos dessa forma:
![[Pasted image 20261026224000.png]]
O método clear limpa uma lista.

| dado.append(‘Maria’)<br>dado.append(22)<br># dado == [‘Maria’, 22]<br>dado.clear()<br>#dado == [] |
| ------------------------------------------------------------------------------------------------- |
