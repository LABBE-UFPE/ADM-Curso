# ADM-Curso
## Dia 2

---
Abra um navegador e cole o seguinte URL: https://www.ncbi.nlm.nih.gov/genbank/

Você verá uma barra de pesquisa com um menu suspenso à esquerda da barra de pesquisa. Veja o menu suspenso para ver todos os bancos de dados disponíveis para pesquisa. Nós procuraremos no banco de dados 'Nucleotide' por nossas sequências.

Comece colando os três primeiros números de acesso na barra de pesquisa:

Exploraremos alguns dos recursos dos resultados da pesquisa, incluindo os formatos de arquivo GenBank (gb) e fasta, conjuntos de dados de população (popset) e o banco de dados de taxonomia. Finalmente, veremos como exportar esses formatos de arquivo para um arquivo em nosso computador.

Voltaremos aos arquivos acima, mas vamos pensar novamente sobre a questão que estamos tentando responder. Queremos saber se o isolado que coletamos possui hospedeiro identificado e de que local do mundo ele foi isolado. Certamente, precisamos pesquisar na literatura para ver se alguma coisa foi publicada porém, também valeria a pena pesquisar no GenBank por qualquer sequência com tais informações.

Tente a seguinte pesquisa para limitar a sua pesquisa:

Exemplo: sequências de Colletotrichum em "*Cucumis melo*" no Japão: `Colletotrichum[organism] AND Japan[country] AND Cucumis[host]`

Você pode encontrar mais informações sobre campos de pesquisa [aqui](https://www.ncbi.nlm.nih.gov/books/NBK49540/) e os campos de pesquisa e qualificadores disponíveis [aqui](https://www.ncbi.nlm.nih.gov/entrez/query/static/help/Summary_Matrices.html#Search_Fields_and_Qualifiers).  

1. Quantas sequências esta consulta retorna?
2. Quantos genes diferentes são representados?

# Usando o *Entrez Efetch Utilities* para recuperar sequências
---
Agora vamos repetir o exercício acima usando E-utilities, a interface de programação de aplicativos (API) para o GenBank. Você pode ler mais sobre isso [aqui](https://www.ncbi.nlm.nih.gov/books/NBK179288/).  

Instalando `e-search` No terminal digite:

`sudo apt-get install ncbi-entrez-direct`

Recupere sequências do GenBank no formato fasta

O formato para pesquisar o banco de dados de nucleotídeos é o seguinte:

`esearch -db nucleotide -query "Números de Acesso Aqui" | efetch -format fasta`

Experimente:
`esearch -db nucleotide -query "Números de Acesso Aqui" | efetch -format fasta`

Agora, para redirecionar a saída do padrão para um arquivo com >>

`esearch -db nucleotide -query "Números de Acesso Aqui" | efetch -format fasta >> test.fasta`

Experimente-o recuperando sequências no formato GenBank:

`esearch -db nucleotide -query "Números de Acesso Aqui" | efetch -format gb`

Agora, para redirecionar a saída do padrão para um arquivo com >>

`esearch -db nucleotide -query "Números de Acesso Aqui" | efetch -format gb >> test.gb`

:computer: Agora recupere os mesmos números de acesso em ambos os formatos, fasta e GenBank, como você fez usando a interface online. Salve esses arquivos com os mesmos nomes de arquivos, exceto adicionar .esearch aos arquivos.

# Construindo seu próprio banco de dados BLAST local
---
Às vezes, você precisará recuperar dados locus individuais de sequências genômicas inteiras que estão disponíveis publicamente. Para fazer isso, você pode usar uma sequência homóloga para recuperar dados do genoma, configurando seu próprio banco de dados BLAST local.

Para instalar o `Blast` digite no terminal:

`sudo apt-get install ncbi-blast+`

Faça o download do(s) genoma(s) os quais vamos recuperar sequências por similaridade:

`wget ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/006/275/GCF_000006275.2_JCVI-afl1-v2.0/código.versão.isolado.genomic.fna.gz`

`gzip -d código.versão.isolado.genomic.fna.gz`

## Construa o banco de dados do BLAST
---
`makeblastdb -in código.versão.isolado.genomic.fna.gz -out "nomeDB -dbtype nucl`

A grande parte dos programas podem exibir os padrões de uso `usage`, para exibi-los digite o nome do programa em seguida `-h` ou `--help`

###### Exemplo:

`blastn --help`
