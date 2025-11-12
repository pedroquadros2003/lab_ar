Grupo:
- Pedro Ulisses de Lima Quadros
- Iago Jacob de Souza Ramos
- Leonardo Fernandes Trevilato
- Rhuan dos Santos Vicente

O pêndulo invertido é um exercício famoso para o estudo de aprendizado por reforço. O jogo consiste em tentar equilibrar um pêndulo invertido em cima de um carrinho apenas exercendo duas forças horizontais, por meio dos botões 'z' e 'x'. Para jogar, apenas execute "$python3 main.py" em seu terminal. Utilizamos o algoritmo TD-Lambda causal para estimar os valores esperados da função valor em cada estado para a política nmanual (i.e. a estratégia utilizada pelo jogador).

***cost_values.txt:***  vetor das estimativas do valor esperado do ganho atualizado por Robins-Monro a cada vez que o jogo é jogado.

***custom_termination_wrapper.py:***    Wrapper para a customização das condições de falha do pêndulo, e.g. angulo máximo, distância da parede ao centro, etc.

***td-lambda.py:*** Classe que roda TD-lambda conforme controlamos o pêndulo. É instanciada em main.py.

***main.py:***  Rotina principal em que o jogo é jogado. Enquanto jogamos, os valores esperados de V são estimados por TD-lambda e, ao fim, são guardados em *cost_values.txt*.

    ***Quão difícil é controlar esse sistema?***
        Muito! Trata-se de um sistema caótico. Tente por si só e você verá ;

    ***Como o progresso no aprendizado do controle manual poderia ser estimado?***
        Registrando-se a função de valor conforme mais partidas são jogadas. Uma alta função de valor indica um melhor desempenho.


## Como Usar

Siga os passos abaixo para configurar o ambiente, treinar e testar o agente.

### 1. Configuração do Ambiente

É altamente recomendado usar um ambiente virtual (`venv`) para isolar as dependências do projeto.

```bash
# 1. Crie um ambiente virtual na pasta do projeto
python -m venv venv

# 2. Ative o ambiente virtual
# No Windows:
.\venv\Scripts\activate
# No macOS/Linux:
source venv/bin/activate

# 3. Instale as bibliotecas necessárias
pip install -r requirements.txt
```


### 2. Estimativa da função valor para uma política fixa

O usuário deve rodar o programa main.py da seguinte forma:

```bash
# No Windows:
python main.py

# No macOS/Linux:
python3 main.py
```

Depois de decidir e aplicar uma política fixa com o teclado por alguns episódios,o usuário deve apertar a tecla "ESC" duas vezes para sair e salvar a função valor no arquivo .txt .