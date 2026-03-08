# INTERA-AO_CLASS_POR_IDADE
TRABALHO UNIDADE 4

#EXERCICIO DE ALTERAÇÃO DE REPOSITORIO ...


import tkinter as tk
from tkinter import messagebox


def classificar_faixa_etaria():
  
    idade_str = idade_input.get()
    
    try:
       
        idade = int(idade_str)
        
        resultado_texto = ""

        
        if idade < 0:
            resultado_texto = "Idade Inválida (Negativa)"
            
        elif idade <= 20:
            resultado_texto = "Jovem"
            
        elif idade <= 40:
            
            resultado_texto = "Meia Idade"
            
        elif idade < 60:
            
            resultado_texto = "Coroa"
             
        else:
            
            resultado_texto = "Velho"
            
        
        messagebox.showinfo(
            "Resultado da Classificação",
            f"A idade é: {idade} anos\nClassificação: **{resultado_texto}**"
        )
        
        print(f"Idade {idade} classificada como: {resultado_texto}")

    except ValueError:
        
        messagebox.showerror(
            "PQP deu erro",
            "E So idade seu burro."
        )



janela = tk.Tk()
janela.title("descubra se você é novo, coroa, ou velho")
janela.geometry("350x200") 


idade_input = tk.StringVar()


label_idade = tk.Label(janela, text="IDADE AQUI:")
label_idade.pack(pady=10)


entrada_idade = tk.Entry(janela, textvariable=idade_input, width=10, font=("Arial black", 12))
entrada_idade.pack(pady=5)

entrada_idade.focus_set() 


entrada_idade.bind('<Return>', lambda event: classificar_faixa_etaria())



botao_executar = tk.Button(
    janela,
    text="Clique aqui",
    font=("Arial", 20, "bold"),
    bg="#2196F3",  
    fg="orange",
  
    command=classificar_faixa_etaria
)


botao_executar.pack(pady=40)


janela.mainloop()
