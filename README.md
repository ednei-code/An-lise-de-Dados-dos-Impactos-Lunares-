🚀 Análise de Dados dos Impactos Lunares 

Visão Geral

Este projeto de Ciência de Dados realiza uma análise exploratória (EDA) e estatística dos dados do programa NELIOTA (NEO Lunar Impacts and Optical Transients). O projeto investiga padrões temporais, características físicas e aspectos experimentais dos eventos de impacto registrados, além de preparar os dados para uma futura modelagem de classificação.




🛰️ Fonte dos Dados: O Programa NELIOTA

A base deste projeto são os dados abertos e validados do programa NELIOTA (NEO Lunar Impacts and Optical Transients). Este é um esforço da Agência Espacial Europeia (ESA) para monitorar a superfície lunar em busca de flashes ópticos de milissegundos, causados por micrometeoroides.

Os dados incluem registros de eventos captados por câmeras de alta velocidade em dois filtros (R e I), e são resultado da colaboração entre as seguintes instituições:

•
ESA – Agência Espacial Europeia

•
NOA – Observatório Nacional Helênico

•
IAASARS – Instituto de Astronomia, Astrofísica, Espaço e Tecnologia

Agradecimentos especiais à equipe científica NELIOTA, responsável pela detecção, validação e divulgação dos eventos observados.

🔗 Fonte Oficial dos Dados: https://neliota.astro.noa.gr/




🎯 Objetivos do Projeto

O projeto buscou responder a um conjunto de perguntas estruturadas:

Categoria
Perguntas Chave
Temporal
Em quais anos e meses ocorreram mais impactos? Existe sazonalidade?
Física
Onde se concentram os impactos mais brilhantes? Qual a relação entre duração e energia (magnitude)?
Experimental
O airmass ou o número de frames capturados influenciam a detecção e a confiabilidade do evento?
Classificação
Como padronizar os rótulos de especialistas (real, neo, suspected) para modelagem?


🛠️ Destaque Técnico: Feature Engineering Física

Um ponto crucial do projeto foi a conversão das magnitudes fotométricas (r_mag e i_mag) em variáveis físicas mais interpretáveis:

1.
Fluxo Luminoso: Conversão da escala logarítmica de magnitude para fluxo linear.

2.
Energia Cinética Estimada: Cálculo da energia do impactor, essencial para a análise física do fenômeno.

Essa etapa permitiu uma análise mais profunda da relação entre a duração do flash e a energia liberada.

🔍 Principais Descobertas (EDA)

•
Padrão Temporal: Identificação dos anos de maior atividade de registro e análise da distribuição mensal dos eventos.

•
Limpeza de Dados: Tratamento do valor -99.99 na coluna r_mag (indicando ausência de detecção no filtro R) e padronização dos mais de 30 rótulos de classificação de especialistas em 4 categorias limpas.

•
Confiabilidade Experimental: Demonstração de que o número de frames capturados está diretamente relacionado à confiabilidade do evento (eventos confirmados tendem a ter mais frames).

📂 Estrutura do Repositório

Plain Text


.
├── Lunar_Impacts_Analysis.ipynb # Notebook principal com o código e a análise
├── README.md
├── data/
│   └── impacto_lunar.csv      # Dataset utilizado no projeto
└── .gitignore


⚙️ Configuração e Dependências

O projeto foi desenvolvido em Python e requer as seguintes bibliotecas:

•
pandas

•
numpy

•
matplotlib

•
seaborn

•
datetime

•
scikit-learn (para a seção de Machine Learning)

Você pode instalar as dependências usando pip:

Bash


pip install pandas numpy matplotlib seaborn scikit-learn


⏭️ Próximos Passos (Machine Learning)

A etapa inicial de Machine Learning (Regressão Logística) apresentou baixa acurácia devido ao forte desbalanceamento de classes (real >> neo >> suspected).

O trabalho futuro deve focar em:

1.
Reamostragem: Aplicação de técnicas como SMOTE (Oversampling) ou NearMiss (Undersampling).

2.
Otimização de Métricas: Focar em F1-Score e Recall por classe, em vez de apenas Acurácia.

3.
Feature Engineering Avançada: Criação de features de razão (ex: frames_r / frames_i) e diferença de magnitude (i_mag - r_mag) para melhorar a separação das classes.




Autor: Ednei Vicente - Cientista de Dados Data: 2025

email - ednei.adgpo@gmail.com

linkedin - https://www.linkedin.com/in/ednei-cunha-vicente-551b64187/

blog - https://medium.com/@ednei_vicente

