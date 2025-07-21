# Calculadora de IMC em Python

Este projeto calcula o Índice de Massa Corporal (IMC) com base no peso e altura fornecidos pelo usuário.

📚 Base de estudo

Curso: Curso de Python 3 do básico ao avançado - com projetos reais  
Instrutores: Luiz Otávio Miranda e Tales Calogi Malaquias  
Plataforma: Udemy  

Adaptei o projeto com minhas próprias palavras e estrutura para praticar lógica de programação.

## Como funciona

- O usuário informa peso (kg) e altura (m)
- O programa calcula o IMC com a fórmula `IMC = peso / altura²`


## Código principal

```python
peso = float(input("Digite seu peso (kg): "))
altura = float(input("Digite sua altura (m): "))

imc = peso / (altura ** 2)

print(f"Seu IMC é {imc:.2f}")

if imc < 18.5:
    print("Abaixo do peso.")
elif 18.5 <= imc < 25:
    print("Peso ideal.")
elif 25 <= imc < 30:
    print("Sobrepeso.")
else:
    print("Obesidade.")