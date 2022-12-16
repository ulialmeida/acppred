# acppred

By Uli Almeida

a tool to predict anticancer peptides 

## Setup

```
$ make setup

```

__________________________________________________________________________________________________________________________________________________
acppred-train: Treina um modelo usando dados do usuário, nesse caso, predição de peptideos anticancer necessário quatro atributos, sendo eles:
    output: Define o diretório de saída da ferramenta (syntax: --output)
    positive_peptides: Entrada de dados com lista de peptídeos com potencial anticanerígeno (syntax: --positive_peptides)
    negative_peptides: Entrada de dados com lista de peptideos sem potencial anticancerigeno (syntax: -- negative_peptides)
    show report: mostra a classificação depois do treinamento (syntax: --show-report)
----------------------    
* Do módulo sklearn foi importado RandomForestClassifier, que ajusta diversos classificadores de árvore de decisão em diferentes subamostras do conjunto de dados e usa a média para melhorar a precisão preditiva, utilizado junto com a importação do módulo modelo.
* argparse facilita a criação de interfaces de linha de comando,o programa define quais argumentos requer, e o argparse vai descobrir como analisá-los, também gera automaticamente mensagens de ajuda, e uso emitirá erros quando os usuários derem ao programa argumentos inválidos, por isso é importante estar presente na fase teste.
argument_parser.add_argument() anexa especificações de argumentos individuais ao analisador (--negative-peptides' << filename, default='data/raw/positive.txt' << assume um valor e  help='a file containing anticancer peptides' << sinalização de ajuda)
__________________________________________________________________________________________________________________________________________________

acppred-predict: Predição de atividade anticancerigena de um peptideo, recebendo três parâmetros:
    input: Entrada de um arquivo em formato FASTA (syntax: --input)
    output: Saída de um arquivo em formato CSV (syntax: --output)
    model: Modelo de treinamento pré definido/treinado para ACPPred (syntax: --model)
    A utilização do argument_parser, required indica se o argumento é obrigatório, nesse caso, retornava True.
 ----------------------  
* Bio.SeqIO faz parte da biblioteca Biopython, possui interface simples para input e output de alinhamentos de sequência, SeqRecord lida com sequências como objetos 

__________________________________________________________________________________________________________________________________________________
acppred-models: Define uma previsão estimada potenciais peptídeos anticancerígenos;
  - estimator: scikit-learn conta com ferramentas para ajuste, seleção e avaliação de modelos, classification_reports desenvolve um relatório de texto mostrando as principais métricas de classificação.
  - positive_peptides: um arquivo contendo peptideos anticancer
  - negative_peptides: um arquivo contendo peptideos que não possuem ação anticâncer
__________________________________________________________________________________________________________________________________________________


