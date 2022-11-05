# TEXT-MINING-SENTIMENT-ANALYSIS-E-NLP

Tidytext e Tidydata • Hadley Wickham:
1. Cada variável é uma coluna
2. Cada observação é uma linha
3. Cada unidade observacional é a tabela • Um token por linha!


Token
TOKEN = Para mineração de texto organizada, o token armazenado em
cada linha geralmente é uma única palavra, mas também pode ser um ngrama, frase ou parágrafo.
Menor unidade que importa do texto!

Unnest Token
text <- c("Because I could not stop for Death -",
"He kindly stopped for me -",
"The Carriage held but just Ourselves -",
"and Immortality")
text_df <- tibble(line = 1:4, text = text)
text_df %>% unnest_tokens(word, text)

Unnest Token • Perceba como a função é útil:
1. Transforma todas as letras em minúscula;
2. Tira pontuação; • Outros pacotes – tem que fazer manualmente.

Bag of Words
• Muito interessante para compreender o texto
• Verifica a frequência dos termos e conta os mesmos ou variável binária que indica 
presença ou não
• Não é a abordagem em questão – podemos chegar em algo semelhante com dplyr
Bag-of-words (BoW) é um modelo de linguagem estatística usado para analisar texto e 
documentos com base na contagem de palavras. O modelo não leva em conta a ordem 
das palavras em um documento.


Bag of Words
• Essa contagem é muito útil para diversos problemas:
1. Verificar termos mais comuns;
2. Verificar termos menos comuns;
3. Verificar similaridade entre termos e sua quantidade no texto.
• Bag – desconsidera qualquer ordem
• Próxima aula iremos mostrar o TF-IDF


Data Cleaning
• Muitas palavras devem ser retiradas do texto a depender do que se está 
extraindo (data cleaning):
1. Números;
2. Emoji;
3. Caracteres especiais
4. Espaço em branco
5. etc


Stop Words
• Todas as palavras carregam sentido? Algumas carregam pouco ou
nenhum: stop words
• https://gist.github.com/alopes/5358189
• De, para, que, etc


Stop Words
• Grande quantidade de listas disponíveis: usar listas pré prontas


Stop Words
• Aceitável: lista pronta com ajustes
• Toda stop word tem de ser retirada?
• Anti join
Data_frame %>% anti_join(get_stopwords(source = "snowball"))


Stemming
• Stemming é o processo de reduzir palavras flexionadas (ou às vezes
derivadas) ao seu tronco (stem), base ou raiz, geralmente uma forma da
palavra escrita.


Token n-gram
•
O que é bigrama e n-grama?
R: São tokenizações com N palavras. Uni-gram: Token com uma palavra, Bi-Gram: Token com duas palavras, Tri-gram: Token com três palavras.

Correlação 
• Há como medir se duas palavras tendem a ocorrer simultaneamente em um
documento?
• Tidytext é muito útil para isso
• Correlação de pares – pairwise correlation
• Valor de phi – correlação de Pearson


Topic Modelling
• Modelo não supervisionado que permite aproximar partes de
documentos por tópicos semelhantes.
• Utilidade prática
• Método LDA

