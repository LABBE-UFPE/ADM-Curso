# MDA-Course
###### Day1
---
Se você estiver usando um sistema operacional Windows, lembre-se de salvar todos os arquivos na unidade USB externa, porque nós iniciaremos o Linux Ubuntu mais tarde e você precisará acessar os arquivos que estão na sua unidade USB.

Comece fazendo um diretório em seu drive USB chamado MDA-Course. Crie outro diretório dentro do MDA-Course chamado day1-Practical. Você pode fazer tudo isso em uma linha no terminal, se souber o nome da sua unidade USB. Substitua o nome da sua unidade USB nos locais apropriados abaixo.

Para criar um diretório no ubuntu faça:

`mkdir /media/ubuntu/"driver_name"/MDA-course && mkdir /media/ubuntu/"Driver_name"/MDA-course/day1-Practical`

`mkdir` = Make directory "Cria um novo diretório"

`&&` = adiciona uma nova tarefa

# Adquirindo Dados do GenBank
---
Vamos usar recursos publicamente disponíveis para recuperar dados de sequência para comparação com dados de sequência que coletamos para os quais temos uma hipótese sobre sua origem (ou seja, gênero).

A primeira coisa que vamos fazer é certificar-se de que sequenciamos o organismo correto, comparando-o às sequências que foram depositadas no GenBank, que é hospedado pelo *National Center for Biotechnology Information Search database* [NCBI](https://www.ncbi.nlm.nih.gov/).

O GenBank® é o banco de dados de sequências genéticas do NIH, uma coleção anotada de todas as seqüências de DNA publicamente disponíveis. O GenBank faz parte da Colaboração Internacional de Banco de Dados de Sequência de Nucleotídeos, que compreende o DNA DataBank do Japão (DDBJ), o European Nucleotide Archive (ENA) e o GenBank no NCBI. Essas três organizações trocam dados diariamente. Mais informações [GenBank](https://www.ncbi.nlm.nih.gov/genbank/)

### Usando o BLAST para consultar o Genbank

Para pesquisar o banco de dados do GenBank, precisamos ter alguns meios de comparar nossas sequências com as sequências mais semelhantes.

##### O que é o BLAST?

É um algoritmo para comparar sequências.

A Ferramenta de Pesquisa de Alinhamento Local Básico [BLAST](https://blast.ncbi.nlm.nih.gov/Blast.cgi) localiza regiões de similaridade local entre sequências. O programa compara sequências de nucleotídeos ou proteínas a bancos de dados de sequências e calcula a significância estatística das correspondências. O BLAST pode ser usado para inferir relações funcionais e evolutivas entre sequências, bem como ajudar a identificar membros de famílias de genes.

## Prática :computer:
---
Responda as seguintes questões:
- [ ] Qual é o comprimento da sequência?
- [ ] Quantos gêneros e espécies estão representados nos 10 melhores *hits*?
- [ ] Qual porcentagem da nossa sequência de consulta está alinhada com a correspondência superior?
- [ ] Qual porcentagem de nucleotídeos é idêntica à top match?
- [ ] Quantas das 10 melhores correspondências não são idênticas ao longo do comprimento da sequência de consulta?
- [ ] Qual é a probabilidade de você encontrar a mesma correspondência no banco de dados de sequências aleatórias do banco de dados atual do GenBank, dado o tamanho da sequência de consulta?
- [ ] Qual posição do nucleotídeo na seqüência de consulta é a incompatibilidade com Curvularia chiangmaiensis cepa CPC 28829?
- [ ] De qual hospedeiro foi coletada a cepa de Curvularia chiangmaiensis CPC 28829?
- [ ] Esta sequência é publicada? Onde?
- [ ] O top match é publicado? Onde?
