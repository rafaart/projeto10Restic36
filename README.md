<h1 align="center"># :projeto10restic36:</h1>

# Projeto: Implementação e Análise do Algoritmo de K-means com o Dataset Human Activity Recognition

# Objetivo do nosso projeto:🎯

Este notebook contempla a criação de um modelo preditivo não supervisionado usando o algoritmo K-means para segmentar grupos e classificalos dentro de um data set de dominio público.

link para o dataset: https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones

link para o artigo: https://www.esann.org/sites/default/files/proceedings/legacy/es2013-84.pdf


# Instalação▶️
Você pode fazer um fork do repositório e iniciar edições no arquivo por conta própria, abaixo o link para o notebook que pode ser rodado em Jupiter notebook ou até mesmo em uma IDE Python de sua escolha

[![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rafaart/projeto10Restic36/blob/develop/K_MEANS_UNID_10.ipynb)

O notebook foi originalmente feito no Google Coolab e você pode iniciar as edições fazendo uma cópia do arquivo original no link abaixo

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DjoKKDo27wydZiRLmYIWOLCZQHBtJAgy?usp=sharing)

# Sobre a base de dados🎲

Os experimentos foram realizados com um grupo de 30 voluntários com idades entre 19 e 48 anos. Cada pessoa realizou seis atividades (CAMINHADA, SUBINDO ESCADAS, DESCENDO ESCADAS, SENTADO, EM PÉ, DEITADO) usando um smartphone (Samsung Galaxy S II) preso à cintura. Utilizando o acelerômetro e o giroscópio integrados, foram capturadas aceleração linear tri-axial e velocidade angular tri-axial a uma taxa constante de 50 Hz. Os experimentos foram gravados em vídeo para etiquetar manualmente os dados. O conjunto de dados foi aleatoriamente dividido em dois grupos, onde 70% dos voluntários foram selecionados para gerar os dados de treinamento e 30% para os dados de teste.

Os sinais dos sensores (acelerômetro e giroscópio) foram pré-processados aplicando filtros de ruído e depois amostrados em janelas deslizantes de largura fixa de 2,56 segundos com sobreposição de 50% (128 leituras/janela). O sinal de aceleração do sensor, que contém componentes de gravidade e movimento corporal, foi separado usando um filtro passa-baixa de Butterworth em aceleração corporal e gravidade. A força gravitacional foi considerada composta apenas por componentes de baixa frequência, por isso foi usado um filtro com frequência de corte de 0,3 Hz. De cada janela, foi obtido um vetor de características calculando variáveis nos domínios do tempo e da frequência. Consulte 'features_info.txt' para mais detalhes.

## Para cada registro são fornecidos:
======================================

- Aceleração tri-axial do acelerômetro (aceleração total) e a aceleração corporal estimada.
- Velocidade angular tri-axial do giroscópio.
- Um vetor de 561 características com variáveis dos domínios do tempo e da frequência.
- O rótulo da atividade.
- Um identificador do sujeito que realizou o experimento.

## O conjunto de dados inclui os seguintes arquivos:
=========================================

- 'README.txt'

- 'features_info.txt': Mostra informações sobre as variáveis utilizadas no vetor de características.

- 'features.txt': Lista todas as características.

- 'activity_labels.txt': Relaciona os rótulos das classes com seus respectivos nomes de atividade.

- 'train/X_train.txt': Conjunto de treinamento.

- 'train/y_train.txt': Rótulos de treinamento.

- 'test/X_test.txt': Conjunto de teste.

- 'test/y_test.txt': Rótulos de teste.

Os seguintes arquivos estão disponíveis para os dados de treinamento e teste. Suas descrições são equivalentes.

- 'train/subject_train.txt': Cada linha identifica o sujeito que realizou a atividade para cada amostra de janela. O intervalo vai de 1 a 30.

- 'train/Inertial Signals/total_acc_x_train.txt': O sinal de aceleração do eixo X do acelerômetro do smartphone em unidades padrão de gravidade 'g'. Cada linha mostra um vetor de 128 elementos. A mesma descrição se aplica aos arquivos 'total_acc_y_train.txt' e 'total_acc_z_train.txt' para os eixos Y e Z.

- 'train/Inertial Signals/body_acc_x_train.txt': O sinal de aceleração corporal obtido subtraindo a gravidade da aceleração total.

- 'train/Inertial Signals/body_gyro_x_train.txt': O vetor de velocidade angular medido pelo giroscópio para cada amostra de janela. As unidades são radianos/segundo.

## Notas:
======
- As características estão normalizadas e limitadas entre [-1,1].
- Cada vetor de características é uma linha no arquivo de texto.
- As unidades utilizadas para as acelerações (total e corporal) são 'g' (gravidade terrestre -> 9,80665 m/s²).
- As unidades do giroscópio são rad/s.
- Um vídeo do experimento, incluindo um exemplo das seis atividades registradas com um dos participantes, pode ser visto no seguinte link: [YouTube](http://www.youtube.com/watch?v=XOEN9W05_4A).

Para mais informações sobre este conjunto de dados, entre em contato: activityrecognition '@' smartlab.ws.

## Licença:
========
O uso deste conjunto de dados em publicações deve ser reconhecido referenciando a seguinte publicação [1]:

[1] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra e Jorge L. Reyes-Ortiz. *A Public Domain Dataset for Human Activity Recognition Using Smartphones*. 21º Simpósio Europeu em Redes Neurais Artificiais, Inteligência Computacional e Aprendizado de Máquina, ESANN 2013. Bruges, Bélgica, 24-26 de abril de 2013.

Este conjunto de dados é distribuído "TAL COMO ESTÁ", e nenhuma responsabilidade, implícita ou explícita, pode ser atribuída aos autores ou suas instituições pelo seu uso ou mau uso. Qualquer uso comercial é proibido.


# Uso da base: 🛠️

O conjunto de dados pode ser usado para:

Esse tipo de conjunto de dados é usado para entender tendências nas mídias sociais, analisar o comportamento dos influenciadores e ajudar marcas a identificar os perfis mais adequados para campanhas de marketing.


Sobre este arquivo:

Neste arquivo, basicamente há 10 atributos. Ele foi ordenado com base na classificação que foi decidida com base em "seguidores".

| nome da coluna | Descrição |
| ------------ | ------------ |
| rank: | Classificação do Influenciador com base no número de seguidores que ele tem |
| channel_info | Nome de usuário do Instagrammer |
| influence score | Pontuação de influência dos usuários. É calculado com base em menções, importância e popularidade |
| posts |  Número de posts que eles fizeram até agora |
| followers | Número de seguidores do usuário|
| avg_likes | Média de curtidas em posts do Instagrammer (total de curtidas/total de posts) |
| 60_day_eng_rate | Taxa de engajamento dos últimos 60 dias do Instagrammer como facção de engajamentos que eles fizeram até agora |
| new_post_avg_like | Média de curtidas que eles têm em novos posts |
| total de curtidas | Total de curtidas que o usuário obteve em seus posts. (em bilhões) |
| country | País ou região de origem do usuário. |


# Tecnologias Utilizadas: 🚀
Os códigos no notebook foram escritos na linguagem Python, a primeira célula de código encontrará os imports com todas bibliotecas e modulos necessários para reproduzir o projeto.
versão do Python: + 3.12 https://www.python.org/downloads/

Os códigos foram implementados através de um notebook na plataforma google coolab: [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1DjoKKDo27wydZiRLmYIWOLCZQHBtJAgy?usp=sharing)

## Bibliotecas necessárias
======
- Pandas
- Numpy
- sci-kitlearning
- matplotlib
- seaborn
- OS
- drive

# Autores: 😎😎
Rafael Santos Souza :octocat: : https://github.com/rafaart

& 

Yuri Oliveira dos Santos :octocat: : https://github.com/YuriGith

# Outras Publicações Relacionadas:
===========================
[2] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra, Jorge L. Reyes-Ortiz. *Energy Efficient Smartphone-Based Activity Recognition using Fixed-Point Arithmetic*. *Journal of Universal Computer Science*. Edição Especial em Ambientes Assistidos: Cuidados em Casa. Volume 19, Edição 9. Maio de 2013.

[3] Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra e Jorge L. Reyes-Ortiz. *Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine*. 4º Workshop Internacional de Ambientes Assistidos, IWAAL 2012, Vitoria-Gasteiz, Espanha, 3-5 de dezembro de 2012. *Lecture Notes in Computer Science* 2012, pp 216-223.

[4] Jorge Luis Reyes-Ortiz, Alessandro Ghio, Xavier Parra-Llanas, Davide Anguita, Joan Cabestany, Andreu Català. *Human Activity and Motion Disorder Recognition: Towards Smarter Interactive Cognitive Environments*. 21º Simpósio Europeu em Redes Neurais Artificiais, Inteligência Computacional e Aprendizado de Máquina, ESANN 2013. Bruges, Bélgica, 24-26 de abril de 2013.

==================================================================================================  
Jorge L. Reyes-Ortiz, Alessandro Ghio, Luca Oneto, Davide Anguita e Xavier Parra. Novembro de 2013.
