# Anthony_EasyHome

## Objetivo do programa

Fará uma estimativa de orçamento para a construção de qualquer prédio/residência, baseado em dimensões e materiais desejados, tendo como grande vantagem a simplicidade existente para manipular o programa.
A motivação é uma obra que ainda está em andamento na minha casa que tomou muito tempo do meu pai pra determinar essa estimativa.
A linguagem utilizada será python e para a interface gráfica será utilizada a biblioteca Tkinter.


## Tutorial:

A começar, a interface gráfica que será utilizada é a Tkinter, que já vem, na maioria das vezes, nas instalações Python.
Para utilizá-la, é necessário importá-la, através do comando:
Como exemplo de tutorial, vamos criar uma caixa de texto dentro do container:
Exemplo 1:
    From Tinker import *

    class Application:
    def __init__(self, master=None):
          self.widget1 = Frame(master)
          self.widget1.pack()
          self.msg = Label(self.widget1, text="Primeiro widget")
          self.msg.pack ()
    root = Tk()
    Application(root)
    root.mainloop()

Exemplo 2: Para adicionar mais widgets à essa interface, como um botão "sair", poderíamos fazer:
    
    class Application:
        def __init__(self, master=None):
            self.widget1 = Frame(master)
            self.widget1.pack()
            self.msg = Label(self.widget1, text="Primeiro widget")
            self.msg["font"] = ("Verdana", "10", "italic", "bold")
            self.msg.pack ()
            self.sair = Button(self.widget1)
            self.sair["text"] = "Sair"
            self.sair["font"] = ("Calibri", "10")
            self.sair["width"] = 5
            self.sair["command"] = self.widget1.quit
            self.sair.pack ()

        root = Tk()
        Application(root)
        root.mainloop()

Exemplo 3: Para receber dados do usuário, usaríamos um código parecido com:
    from tkinter import *

    class Application:
        def __init__(self, master=None):
            self.fontePadrao = ("Arial", "10")
            self.primeiroContainer = Frame(master)
            self.primeiroContainer["pady"] = 10
            self.primeiroContainer.pack()

            self.segundoContainer = Frame(master)
            self.segundoContainer["padx"] = 20
            self.segundoContainer.pack()

            self.terceiroContainer = Frame(master)
            self.terceiroContainer["padx"] = 20
            self.terceiroContainer.pack()

            self.quartoContainer = Frame(master)
            self.quartoContainer["pady"] = 20
            self.quartoContainer.pack()

            self.titulo = Label(self.primeiroContainer, text="Dados do usuário")
            self.titulo["font"] = ("Arial", "10", "bold")
            self.titulo.pack()

            self.nomeLabel = Label(self.segundoContainer,text="Nome", font=self.fontePadrao)
            self.nomeLabel.pack(side=LEFT)

            self.nome = Entry(self.segundoContainer)
            self.nome["width"] = 30
            self.nome["font"] = self.fontePadrao
            self.nome.pack(side=LEFT)

            self.senhaLabel = Label(self.terceiroContainer, text="Senha", font=self.fontePadrao)
            self.senhaLabel.pack(side=LEFT)

            self.senha = Entry(self.terceiroContainer)
            self.senha["width"] = 30
            self.senha["font"] = self.fontePadrao
            self.senha["show"] = "*"
            self.senha.pack(side=LEFT)

            self.autenticar = Button(self.quartoContainer)
            self.autenticar["text"] = "Autenticar"
            self.autenticar["font"] = ("Calibri", "8")
            self.autenticar["width"] = 12
            self.autenticar["command"] = self.verificaSenha
            self.autenticar.pack()

            self.mensagem = Label(self.quartoContainer, text="", font=self.fontePadrao)
            self.mensagem.pack()

        #Método verificar senha
        def verificaSenha(self):
            usuario = self.nome.get()
            senha = self.senha.get()
            if usuario == "usuariodevmedia" and senha == "dev":
                self.mensagem["text"] = "Autenticado"
            else:
                self.mensagem["text"] = "Erro na autenticação"


        root = Tk()
        Application(root)
        root.mainloop()
        
Para utilização do programa:
1. No Windows 10:
    - Instalar uma IDE python3 como o PyCharm através do link:
         https://www.jetbrains.com/pycharm/download/
    - A biblioteca tkinter já vem instalada
    - Em seguida, no terminal do PyCharm, deve-se navegar até a pasta onde está o arquivo .py,tomando como base o diretório que está presente no terminal , usando os comandos:
        Entrar em um diretório:
            > ..
        Sair de um diretório:
            > cd ..
    - Ao entrar no diretório em que está o arquivo .py, executá-lo através do comando:
            >python Trabalho_provisorio.py
2. No linux:
    - Consulte se o Python já está instalado, através do comando
        $ python --version
                ou
        $ python3 --version
    - Se o Python 2 versão 2.7+ ou Python 3 versão 3.4+ ou posterior não estiver instalado, instale o Python com o gerenciador de pacote da distribuição. O comando e o nome do pacote varia de:
        No derivados do Debian, como Ubuntu, use apt. Verifique no repositório apt as versões do Python disponíveis para você. Depois, execute um comando semelhante ao seguinte, substituindo o nome do pacote correto:

            $ sudo apt-get install python3
        
        No Red Hat e derivados, use yum. Verifique no repositório yum as versões do Python disponíveis para você. Depois, execute um comando semelhante ao seguinte, substituindo o nome do pacote correto:

            $ sudo yum install python36
        
        No SUSE e derivados, use o zypper. Verifique no repositório as versões do Python disponíveis para você. Depois, execute um comando semelhante ao seguinte, substituindo o nome do pacote correto:

            $ sudo zypper install python3
    
        Abra um prompt de comando ou shell e execute o comando a seguir para verificar se o Python foi instalado corretamente.
            
            $ python3 --version
       
    - Instale a biblioteca tkinter através do comando:
            
            $apt-get install python-tk
       
    - Executar o programa no terminal através do comando
            $python3 Trabalho_provisorio.py
    
    A maioria das instalações Linux já vêm com a biblioteca Tkinter instalada


## Recursos do projeto
O menu principal terá 4 "etapas":
- Informar qual a área total da casa (Interna e externa) e a área da base
- Selecionar o tipo de azuleijo, com a possibilidade de selecionar um total de 4 tipos diferentes de um total de 8 possibilidades, informando a área total ocupada por cada tipo
- Selecionar o tipo de tijolo, podendo selecionar um de um total de 8 tipos diferentes
- Selecionar a marca de cimento que será utilizada, podendo escolher uma de um total de 4 possibilidades
- Por fim, será exibido o valor estimado para a obra

Um exemplo de utilização dele é demonstrado na figura a seguir:
![Tela do programa](https://i.screenshot.net/rkryzhg)

## Produtos disponíveis no programa
Azulejos:
    ![Azulejos](https://i.imgur.com/prEdkqj.png)
    
Tijolos:
    ![Tijolos](https://i.imgur.com/9YSPffX.png)
    
Cimentos:
    ![Cimentos](https://i.imgur.com/zyFxVuV.png)

