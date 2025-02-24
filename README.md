import tkinter as tk
import random
import string

# Função para gerar a senha
def gerar_senha():
    comprimento = int(entry_comprimento.get())  # Obtém o comprimento da senha
    caracteres = string.ascii_letters + string.digits + string.punctuation  # Define os caracteres permitidos
    senha = ''.join(random.choice(caracteres) for _ in range(comprimento))  # Gera a senha aleatória
    label_senha.config(text=senha)  # Exibe a senha gerada

# Criar a janela principal
root = tk.Tk()
root.title("Gerador de Senhas")

# Label para instruções
label_instrucoes = tk.Label(root, text="Digite o comprimento da senha:")
label_instrucoes.pack(pady=5)

# Caixa de entrada para comprimento da senha
entry_comprimento = tk.Entry(root)
entry_comprimento.pack(pady=5)

# Botão para gerar a senha
botao_gerar = tk.Button(root, text="Gerar Senha", command=gerar_senha)
botao_gerar.pack(pady=10)

# Label para exibir a senha gerada
label_senha = tk.Label(root, text="", font=("Arial", 14), fg="blue")
label_senha.pack(pady=20)

# Rodar a interface
root.mainloop()
