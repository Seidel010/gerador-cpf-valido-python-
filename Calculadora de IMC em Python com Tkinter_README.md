 Calculadora de IMC em Python com Tkinter

Este projeto foi criado para praticar o desenvolvimento de interfaces gráficas (GUI) em Python, utilizando a biblioteca nativa **tkinter**. O resultado é uma calculadora simples que determina o Índice de Massa Corporal (IMC) a partir do peso e da altura fornecidos pelo usuário.

## Base de estudo

Adaptação de um projeto pessoal para aplicar os conceitos da biblioteca **tkinter** na criação de aplicações desktop interativas.

## Como funciona

- Cria uma janela principal para a aplicação usando **tkinter**.
- Adiciona campos de entrada (`Entry`) para o usuário inserir o peso (em kg) e a altura (em metros).
- Um botão "Calcular" aciona a função de cálculo do IMC.
- A função obtém os valores dos campos de texto, converte-os para números e calcula o IMC com a fórmula:  
  \[
  \text{IMC} = \frac{\text{peso}}{\text{altura}^2}
  \]
- O resultado é exibido em um rótulo (`Label`) na mesma janela.
- Possui um tratamento simples de erro para caso o usuário insira um valor não numérico.

## Código principal

```python
import tkinter as tk
from tkinter import Frame, Label, Entry, Button

def calcula_imc():
    try:
        p = float(peso.get())
        a = float(altura.get())
        imc = p / (a ** 2)
        resultado['text'] = f'O seu IMC é {imc:.2f}'
    except ValueError:
        resultado['text'] = 'Por favor, insira números válidos.'

janela = tk.Tk()

frame = Frame(janela, padx=40, pady=40)
frame.grid(column=1, row=1)

Label(frame, text='Para saber seu IMC, digite os valores abaixo', pady=40).grid(column=1, row=1, columnspan=2)

Label(frame, text='Qual o seu peso {kg} ?').grid(column=1, row=2)
peso = Entry(frame)
peso.grid(column=2, row=2)

Label(frame, text='Qual a sua altura {m} ?').grid(column=1, row=3)
altura = Entry(frame)
altura.grid(column=2, row=3)

Button(frame, text='Calcular', command=calcula_imc).grid(column=2, row=4)

resultado = Label(frame, text='')
resultado.grid(column=1, row=5, columnspan=2)

janela.title('Calculadora de IMC')
janela.mainloop()