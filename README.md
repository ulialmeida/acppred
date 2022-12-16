# acppred

By Uli Almeida

a tool to predict anticancer peptides 

## Setup

```
$ make setup

```
acppred-train: Treina um modelo usando dados do usuário, nesse caso, predição de peptideos anticancer necessários três atributos, sendo eles:
    output: Define o diretório de saída da ferramenta (syntax: --output)
    positive_peptides: Entrada de dados com lista de peptídeos com potencial anticanerígeno (syntax: --positive_peptides)
    negative_peptides: Entrada de dados com lista de peptideos sem potencial anticancerigeno (syntax: -- negative_peptides)

acppred-predict: Predição de atividade anticancerigena de um peptideo, recebendo três parâmetros:
    input: Entrada de um arquivo em formato FASTA (syntax: --input)
    output: Saída de um arquivo em formato CSV (syntax: --output)
    model: Modelo de treinamento pré definido/treinado para ACPPred

python acppred/server: 
