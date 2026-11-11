### Nome do aluno: Joseph Douglas Moura Batista 
### matrícula: 20230002504
### Link direto para o dataset utilizado: https://l1nk.dev/3bkcrq1  
### Breve descrição do projeto e dos objetivos: 

O projeto consiste em utilizar um conjunto de dados de pacientes hospitalares para desenvolver, treinar e avaliar redes neurais artificiais em PyTorch voltadas a tarefas de regressão e classificação. O trabalho abrange a seleção criteriosa de funções de perda, camadas de saída e métricas, a execução de um estudo controlado de hiperparâmetros para analisar a generalização e o comportamento frente ao overfitting e underfitting, e a manipulação correta de salvamento e carregamento de modelos para inferências reprodutíveis. Por fim, o projeto avalia a eficiência computacional das soluções considerando tempo de execução, uso de memória, quantidade de parâmetros, tamanho em disco e consumo energético culminando em uma discussão crítica sobre a viabilidade de sua implantação em um ambiente prático.

### Instruções claras de execução (ordem dos notebooks, dependências e versão do PyTorch): 

1.Baixe o dataset [stroke_risk](https://www.kaggle.com/datasets/mobeenfatimah/stroke-risk-prediction-dataset?resource=download) 

2.Entre no link do notebook online [Notebook_online](https://l1nk.dev/3bkcrq1)

3.Faça upload do dataset baixado no notebook online 

4.Rode o primeiro codigo onde está as bibliotecas 

5.Rode as partes do codigo que tenha o comentário 3 atividade logo no início

### Como carregar os modelos salvos e executar a inferência (exemplo de comando para src/inference.py):

1. Faça upload do dataset baixado no notebook online
  
2. Rode o primeiro codigo onde está as bibliotecas
 
3. Rode as partes do codigo que tenha o comentário 3 atividade logo no início
   
4. A inferência rode como um codigo normal do dataset, os arquivos que são gerados ficam na parte esquerda onde faz o upload de dataset
   
### Resumo dos principais resultados e da tabela-resumo final:

A analise da otimização de uma rede neural para a previsão de AVC, destaca que a taxa de aprendizado e o tamanho da camada oculta são hiperparâmetros críticos que exigem um equilíbrio cuidadoso para evitar *underfitting* ou *overfitting*, efeito este também controlado pelo termo de regularização. Embora a análise tenha sido feita variando um fator por vez, ressalta-se a forte interação prática entre esses parâmetros. Para uma avaliação realista em cenários desbalanceados, recomenda-se o uso de múltiplas sementes e o F1-score macro, monitorando o *gap* de generalização. Além disso, a reprodutibilidade exata exige salvar o *Pipeline* completo com pré-processamento, fixar sementes e converter estruturas de texto de forma adequada. Por fim, o modelo demonstra baixo custo computacional e alta velocidade de inferência, viabilizando o uso em tempo real na clínica, embora o estudo apresente limitações metodológicas como o tamanho reduzido do *dataset*.

**Tabela-Resumo final** 

|Problema                         |Hiperparâmetros Escolhidos        |Treino|Validação      |	Teste         |	Gap Gen. (Treino - Val)| 
|---------------------------------|----------------------------------|------|---------------|---------------|------------------------| 
|Previsão de Risco de AVC (Stroke)|{"learning_rate_init": 0.001,     |0.9120|0.8850 ± 0.0120|0.8790 ± 0.0140| 0.0270                 |
|                                 |"hidden_layer_sizes": "(100, 50)",|  
|                                 |  "alpha": 0.001}                 |

|Gap Gen. (Treino - Teste)|Tempo de Treino (s)|	Memória Pico (MB)	| Tempo Inf. (ms/amostra) | 
|-------------------------|-------------------|-------------------|-------------------------| 
|0.0330                   |1.45               | 12.4              |0.350                    |
