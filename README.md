
## Projeto: Trabalhando com Machine Learning na Prática no Azure ML

Passo a passo do projeto Trabalhando com Machine Learning na Prática no Azure ML da DIO.

### Passo 1:

Inicialmente, foi necessário desenvolver um recurso de Machine Learning. Para realizar essa tarefa, cliquei na opção "Criar recurso" e, em seguida, busquei por Azure Machine Learning no marketplace. Após localizar o recurso desejado, procedi com a sua criação.

### Passo 2:

Na seção de Informações Básicas, mais especificamente em Detalhes do Recurso, coloca-se a assinatura para fins de cobrança no campo designado e, em seguida, especifica-se o Grupo de Recursos que abrangerá o novo recurso a ser criado.

Em seguida, na seção Detalhes da Área de Trabalho, são fornecidos os detalhes necessários para a criação do espaço de trabalho. Devido à natureza do laboratório, as configurações foram mantidas no mínimo. Finalmente, o recurso é criado ao clicar em Consultar + Criar. Após a aprovação da validação, é necessário clicar em "Criar".

Uma vez que o recurso é criado com sucesso, é possível acessar a página correspondente clicando no botão "Ir para o Recurso".

Nesta página, encontra-se o botão "Iniciar o Estúdio", que direciona para o Azure Machine Learning Studio.

### Passo 3:

No ambiente de trabalho, na página dedicada ao workspace que foi previamente estabelecido, naveguei até a opção correspondente ao ML automatizado no menu. Na página que se abriu, optei por iniciar um "Novo trabalho de ML automatizado".

Em relação às "Configurações básicas", completei os campos referentes a "Nome do trabalho", "Novo nome do experimento" e "Descrição". Posteriormente, prossegui para a próxima etapa.

Na etapa "Tipo de tarefa e dados", defini a tarefa como Regressão e, em seguida, ao selecionar os dados, optei por "Criar". No modal que surgiu, preenchi os campos em "Tipos de dados" com "Nome" e "Descrição", escolhendo "Tipo" como Tabular. Avancei para a etapa "Fonte de dados" e escolhi a opção "De arquivos da Web", prosseguindo novamente.

No passo "URL da Web", informei a URL https://aka.ms/bike-rentals para o conjunto de dados. Nas "Configurações", preenchi os detalhes do conjunto e, ao avançar para "Esquema", confirmei os tipos de dados. Finalmente, ao prosseguir, verifiquei as configurações estabelecidas para o ativo de dados e cliquei em "Criar".

Em relação às "Configurações de tarefas", selecionei o conjunto de dados importado. Posteriormente, na seção "Coluna de destino", designei a coluna "rentals" como alvo.

Nos campos referentes aos "Limites", fornecei os valores necessários e habilitei a opção de "Encerramento Antecipado".

Na fase de "Validar e testar", escolhi a "Divisão de validação de treinamento" como o tipo de validação. Ao avançar para a seção de "Computação", mantive os valores conforme apresentados na imagem.

Após avançar e revisar as configurações do trabalho, cliquei em "Enviar trabalho de treinamento". Ao concluir o treinamento, o modelo tornou-se acessível na opção do menu "Modelo".

### Passo 4:

Para verificar as métricas do modelo treinado, na página específica do modelo, cliquei no link indicado em "Criado pelo trabalho". Além disso, é viável acessar o trabalho mencionado na opção "Trabalhos" no menu.

Ao entrar na página do trabalho, naveguei até a aba de métricas.

### Passo 5:

Na página dedicada ao modelo, selecionei a guia "Pontos de extremidade". Alternativamente, é possível acessar por meio do menu lateral na opção "Pontos de extremidade". Escolhi o ponto de extremidade associado ao modelo gerado. Em seguida, dirigi-me à guia "Testar".

Para realizar o teste, empreguei o JSON a seguir:

    {
        "Inputs": { 
            "data": [
                {
                    "day": 1,
                    "mnth": 1,   
                    "year": 2022,
                    "season": 2,
                    "holiday": 0,
                    "weekday": 1,
                    "workingday": 1,
                    "weathersit": 2, 
                    "temp": 0.3, 
                    "atemp": 0.3,
                    "hum": 0.3,
                    "windspeed": 0.3 
                }
            ]    
        },   
        "GlobalParameters": 1.0
    }

A previsão gerada foi: 329.90

