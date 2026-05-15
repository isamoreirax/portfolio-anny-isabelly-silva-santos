# Traduzindo Logica para Python

> Projeto desenvolvido por Anny Isabelly Silva Santos  
> Curso: Análise e Desenvolvimento de Sistemas — UNICID

---

## Descrição

Quatro programas completos: processador de vendas, analisador de clima, sistema de notas e simulador de poupança com juros compostos.

---

## O que usei

- Funções, loops e condicionais
- Tipagem e conversão de dados
- Estruturas de decisão

---

## O que eu aprendi

- input() sempre retorna string — converter antes de operar matematicamente.
- range() não inclui o valor final: para ir de 1 até N, usar range(1, N + 1).

---

## Codigo

<details>
<summary>1. Processador de Vendas com Desconto</summary>

```python
def processar_vendas():
    total_compra = 0.0
    itens_comprados = 0
    quantidade_tipos = int(input("Quantos produtos diferentes foram comprados? "))
    contador = 0
    while contador < quantidade_tipos:
        nome = input("Nome do produto: ")
        preco = float(input("Preço unitário: "))
        qtd = int(input(f"Quantidade de '{nome}': "))
        if preco <= 0 or qtd <= 0:
            print(f"Valores inválidos para '{nome}'. Item ignorado.")
        else:
            subtotal = preco * qtd
            total_compra += subtotal
            itens_comprados += qtd
        contador += 1
    if total_compra > 500:
        total_final = total_compra * 0.90
        print("Desconto de 10% aplicado!")
    elif total_compra > 200:
        total_final = total_compra * 0.95
        print("Desconto de 5% aplicado!")
    else:
        total_final = total_compra
    print(f"\nResumo: {itens_comprados} itens. Total a pagar: R$ {total_final:.2f}")

processar_vendas()
```

</details>

<details>
<summary>2. Analisador de Clima Semanal</summary>

```python
def analisar_clima():
    soma_temperaturas = 0.0
    dias_quentes = 0
    alerta_extremo = False
    for dia in [1, 2, 3, 4, 5, 6, 7]:
        temp = float(input(f"Digite a temperatura do dia {dia}: "))
        soma_temperaturas = soma_temperaturas + temp
        if temp > 35.0:
            dias_quentes = dias_quentes + 1
        if temp > 45.0 or temp < -5.0:
            alerta_extremo = True
    media = soma_temperaturas / 7
    print("Média semanal:", media)
    print("Dias acima de 35°C:", dias_quentes)
    if alerta_extremo == True:
        print("CUIDADO: Condições climáticas perigosas detectadas!")
    else:
        print("Clima dentro da normalidade operacional.")

analisar_clima()
```

</details>

<details>
<summary>3. Sistema de Notas da Turma</summary>

```python
def sistema_notas_turma():
    total_alunos = int(input("Quantos alunos existem na turma? "))
    for j in range(total_alunos):
        aluno_nome = input("Nome do aluno: ")
        n1 = float(input("Nota 1: "))
        n2 = float(input("Nota 2: "))
        media_aluno = (n1 + n2) / 2
        if media_aluno >= 7.0:
            print(aluno_nome, ": Aprovado com média", media_aluno)
        elif media_aluno >= 5.0:
            print(aluno_nome, ": Recuperação (Média:", media_aluno, ")")
        else:
            print(aluno_nome, ": Reprovado")

sistema_notas_turma()
```

</details>

<details>
<summary>4. Simulador de Poupança</summary>

```python
def simulador_poupanca():
    saldo = float(input("Valor inicial do investimento: "))
    taxa = float(input("Taxa de juros mensal (em %): "))
    meses = int(input("Número de meses da simulação: "))
    m = 1
    while m <= meses:
        aporte = float(input(f"Quanto deseja depositar no mês {m}? (0 para nenhum) "))
        saldo = saldo + aporte
        juros = saldo * (taxa / 100)
        saldo = saldo + juros
        print("Mês", m, ": Saldo atualizado = R$", saldo)
        if saldo > 10000.0:
            print("Parabéns! Você atingiu a meta de 10k no mês", m)
        m = m + 1
    print("Resultado final após", meses, "meses: R$", saldo)

simulador_poupanca()
```

</details>

---

## Como Executar
1. Clone o repositório.
2. Instale as dependências: `pip install -r requirements.txt`.
3. Execute o arquivo principal: `python main.py`.

---
[Voltar ao início](https://github.com/isamoreirax/portfolio-Anny-Isabelly-Silva-Santos)

## Tecnologia

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
