<h1> US Baby Name </h1>

<h3>Descrição do Problema</h3>
Para mais informações: https://www.kaggle.com/kaggle/us-baby-names

<h3>Desafio</h3>
Todas as soluções foram implementadas na linguagem R utilizando os recursos disponíveis para coletar, manipular, análisar e visualizar as informações. 


<h3>Dependências</h3>
Para a execução dos algoritmos implementados é necessário instalar as seguintes bibliotecas.
* RSQLite: Biblioteca para realizar as consultas em SQL.
* ggplot2: Apresentar as visualizações dos dados.
* gridExtra: Possibilita a geração de vários gráficos na mesma tela.
* dplyr: Manipulação dos dataframes.
* maps: Fornece uma base de dados de alta resolução para exibição de mapas.
* ggmap: Exibição e a manipulação de imagens e utilizando coordenadas e afins.
* scales: Apresenta métodos para alterar a parte gráfica como eixos, rótulos e entre outros. 

Obs: Para instalar todas as pendências execute `init_packages()` no arquivo `util.R`

<h3>Considerações</h3>
1. Será exibida apenas as deduções e resultados. Todos os códigos estarão na pasta <i>/code</i>. 
2. Na pasta <i>/img</i> apresentamos algumas compilações de imagens.
3. Para algumas questões serão mostradas apenas os principais resultados. Todos os resultados estarão no formato <i>.csv</i> na pasta <i>/csv</i>.

<h3>Tabelas</h3>
Os datasets '<i>NationalNames</i>' e '<i>StateNames</i>' estão disponíveis nos formatos <i>.csv</i> e <i>.sqlite</i>. 

**NationalNames**

A tabela contém os dados de nomes dos bebês a nível Nacional dos EUA.


Id | Name | Year | Gender | Count
------ | ------ | ------ | ------ | ------:
1 | Mary | 1880 | F | 7065
2 | Anna | 1880 | F | 2604
3 | Emma | 1880 | F | 2003
`obs: 1.825.433 registros`

**StateNames**

A tabela contém os dados de nomes dos bebês a nível Estadual dos EUA.

Id | Name | Year | Gender | State | Count
------ | ------ | ------ | ------ | ------ | ------:
1 | Mary | 1910 | F | AK | 14
2 | Annie | 1910 | F | AK | 12
3 | Anna | 1910 | F | AK | 10
`obs: 5.647.426 registros`

<h3>Tabelas auxiliares</h3>

As tabelas auxiliares '<i>State</i>' e '<i>Generation</i>' estão disponíveis no arquivo `answer.R` no método `create_tables`.

**State**

A tabela `State` contém as informações de cada Estado.
- A inserção dos registros está no arquivo `util.R` no método `location_state`.
- As colunas `Lat`(Latitude) e `Lon`(Longitude) serão utilizados na plotagem em mapas.

State | Lat | Lon | Name
------ | ------ | ------ | ------ | ------ | ------:
AK | 64.20084 | -149.49367 | Alaska, USA
AL | 32.31823 | -86.90230 | Alabama, USA
AR | 35.20105 | -91.83183 | Arkansas, USA
`obs: 51 registros`

**Generation**

A tabela `Generation` contém as informações de cada geração.
- A inserção dos registros está no arquivo `util.R` no método `generations_american`.

Name | YearIni | YearEnd
------ | ------ | ------ | ------:
Lost Generation | 1883 | 1900
G.I. Generation | 1901 | 1924
Silent Generation | 1925 | 1942
`obs: 7 registros`

<h3>Respostas</h3>
<h3>Questão 1</h3>
Qual dos gêneros que há a maior variedade de nomes por ano e gênero em âmbito nacional?
![alt text][asked1]

* Por volta de 1915 há pequena explosão populacional, provávelmente ocasionada pela migração.
* Na década de 1970 houve um aumento significativo para ambos os gêneros até em meados de 2010. 
* Aparentemente, os casais são mais propensos a serem 'criativos' com os nomes femininos do que nomes masculinos. 

`Nota: Certos fatos serão explorados na Questão 3.`

<h3>Questão 2</h3>
Quais são os dez nomes mais populares de todos os tempos?

![alt text][asked2_1]

![alt text][asked2_2]

* A decaída de todos dos nomes populares nas últimas décadas é devido o aumento da variedade dos nomes inspirados na cultura POP e influências sociais.
* Grande parte dos nomes tiveram seu ápice entre 1955 à 1970 com picos de até 100.000 registros.
* No gênero masculino, cinco dos dez nomes estão entre os vinte nomes mais populares de 2014 que são William (5º),  Michael(7º), James(9º), David(18º) e Joseph (20º). No entanto no gênero Feminino, apenas Elizabeth (9º) está entre os nomes mais populares de 2014.

<h3>Questão 3</h3>
Exiba um gráfico com a quantidade total de registros por gênero a cada ano.
![alt text][asked3]


* Na década de 1910, os EUA começaram a receber refugiados de diversas partes do mundo que estavam fugindo de regimes ou de guerras a procura de melhores condições e oportunidades na vida, ocorrendo assim uma explosão população.
* Durante 1945-47 houve um aumento substancial nos nascimentos em um curto periodo de tempo que coincide com o fim da segunda guerra mundial (2 de setembro de 1945) e a volta dos soldados americanos. Em 1946, ocorreu o aumento mais significado durante o périodo de avaliação com aproximadamente 271.000 mil registros para ambos os gêneros.
* Em duas ocasições ocorreram os maiores déficits nos registros de bebês que foram em 1965-66 e 1971-73.

<h3>Questão 4</h3>
Existe alguma tendência nos nascimentos no decorrer dos anos?

`Teoria Geracional Strauss-Howe`

![alt text][asked4]

<h3>Questão 5</h3>
Qual o impacto do nomes dos presidentes em nomes de bebês?

<h3>Influência neutra</h3>

![alt text][asked5_1]

Os presidentes Chester Arthur, Benjamin Harrison, William McKinley e John Kennedy não apresentaram muitas váriações durante os seus respectivos mandatos. No caso de John Kennedy, o nome John era popular na época e nos casos dos outros presidentes, os seus nomes não tiveram influência nas escolhas dos nomes dos bebês na época de seus mandatos e apenas se popularizou posteriormente.

Outros exemplos: 
[Chester Arthur](https://github.com/wyassue/teste/blob/master/img/president/1881%201885-Chester%20Alan%20Arthur.png),
[Benjamin Harrison](https://github.com/wyassue/teste/blob/master/img/president/1889%201893-Benjamin%20Harrison.png) e
[William McKinley](https://github.com/wyassue/teste/blob/master/img/president/1897%201901-William%20McKinley.png).

<h3>Impacto positivo</h3>

![alt text][asked5_2.1]

![alt text][asked5_2.2]

Esses presidentes obtiveram uma grande influência nas escolhas dos nomes durante o periodo de candidatura até o mandato, em razão que em todos os casos apresentaram o 'pico máximo' no período. Há casos que os nomes continuaram a serem registros (Calvin) e em outros caíram em deuso.

Exemplo: Em 2007, o nome Barack obteve poucos registros. O aumento repentino no nome Barack foi ocasioado pelo anuncio de Barack Obama a presidência dos Estados Unidos. Avançando até 2009 com a vitória sobre o candidato republicano John McCain.

Outros exemplos: 
[Grover Cleveland](https://github.com/wyassue/teste/blob/master/img/president/1885%201889-Grover%20Cleveland.png),
[Woodrow Wilson](https://github.com/wyassue/teste/blob/master/img/president/1913%201921-Woodrow%20Wilson.png),
[Warren Harding](https://github.com/wyassue/teste/blob/master/img/president/1921%201923-Warren%20Gamaliel%20Harding.png),
[Calvin Coolidge](https://github.com/wyassue/teste/blob/master/img/president/1923%201929-Calvin%20Coolidge.png),
[Herbert Hoover](https://github.com/wyassue/teste/blob/master/img/president/1929%201933-Herbert%20Clark%20Hoover.png),
[Dwight Eisenhower](https://github.com/wyassue/teste/blob/master/img/president/1953%201961-Dwight%20David%20Eisenhower.png) e 
[Lyndon Johnson](https://github.com/wyassue/teste/blob/master/img/president/1963%201969-Lyndon%20Baines%20Johnson.png).


<h3>Impacto negativo</h3>

![alt text][asked5_3.1]

![alt text][asked5_3.2]

Esses presidentes apresentaram impacto negativo durante a candidatura até o mandato devido algumas particularidades. Muitos destes presidentes participaram de momentos de decisivos, de guerras ou por escândalos (Richard Nixon - Watergate).

Exemplo: Durante a campanha de George H.W. Bush (1989-1993), o nome George estava se popularizando até em 1990 quando subitamente houve o declinio devido a Guerra do Golfo causando antipatia com a população diante dos custos de guerra ataque à civis. 

Outros exemplos: 
[Harry Truman](https://github.com/wyassue/teste/blob/master/img/president/1945%201953-Harry%20S.%20Truman.png),
[Richard Nixon](https://github.com/wyassue/teste/blob/master/img/president/1969%201974-Richard%20Milhous%20Nixon.png),
[Gerald Ford](https://github.com/wyassue/teste/blob/master/img/president/1974%201977-Gerald%20Rudolph%20Ford.png) e 
[James Carter Jr.](https://github.com/wyassue/teste/blob/master/img/president/1977%201981-James%20Earl%20Carter%20Jr..png).



<h3>Questão 6</h3>

Quais são os nomes 'fogo de palha'?

**Feminino**

![alt text][trendF1]
![alt text][trendF2]
![alt text][trendF3]

Outros exemplos: [Katina](https://github.com/wyassue/teste/blob/master/img/person/F/Katina_F.png), [Khadijah](https://github.com/wyassue/teste/blob/master/img/person/F/Khadijah_F.png), [Marquita](https://github.com/wyassue/teste/blob/master/img/person/F/Marquita_F.png)...


**Masculino**

![alt text][trendM1]
![alt text][trendM2]
![alt text][trendM3]

Outros exemplos: [Harding](https://github.com/wyassue/teste/blob/master/img/person/M/Harding_M.png), [Levar](https://github.com/wyassue/teste/blob/master/img/person/M/Levar_M.png), [Talan](https://github.com/wyassue/teste/blob/master/img/person/M/Talan_M.png)...

<h3>Questão 7</h3>

Impacto do nome das pessoas famosas sobre os nomes dos bebês

**Feminino**

![alt text][famousF1]
![alt text][famousF2]
![alt text][famousF3]

**Masculino**

![alt text][famousM1]
![alt text][famousM2]
![alt text][famousM3]
![alt text][famousM4]

<h3>Questão 8</h3>

Quais são os nomes mais UNISEX?

![alt text][unisex1]
![alt text][unisex2]
![alt text][unisex3]

Posição | Nome | F | M | | Posição | Nome | F | M 
------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------:
1º|Krishna|1715|1713||6º|Shaya|745|727
2º|Michal|3620|3563||7º|Kris|13792|13437
3º|Lian|671|684||8º|Ivory|8186|8405
4º|Kerry|49417|48452||9º|Christan|1403|1366
5º|Delane|922|942||10º|Terryl|740|717

<h3>Questão 9</h3>

Quais são os principais nomes inspirados em flores?

`Nota: Está sendo considerado apenas os nomes femininos`

![alt text][asked9]

Posição | Nome | Total | | Posição | Nome | Total
------ |------ |------ |------ |------ |------ |------:
1º|Heather|523717||6º|Daisy|134828
2º|Rose|475178||7º|Lily|123182
3º|Alyssa|296309||8º|Violet|122727
4º|Jasmine|236389||9º|Marguerite|93157
5º|Myrtle|136435||10º|Iris|74409

<h3>Questão 10</h3>
A atual composição por gênero e distribuição populacional de cada estado.

![alt text][asked10]

<h3>Questão 11</h3>

A densidade demográfica das regiões dos EUA durante 1910 a 2010.

![alt text][asked11]

* Antes da colonização inglesa, os espanhóis já exploravam a região no que tornaria o território americano e se fixando nos estados de Flórida, Califórnia, Arizona, Utah, Novo México e Texas.
* Notavel a descentralização da população da costa leste e a migração para as regiões da costa oeste.


[asked1]: https://github.com/wyassue/teste/blob/master/img/%20answer1.png "Questão 1"
[asked2_1]: https://github.com/wyassue/teste/blob/master/img/%20answer2_F_v2.png "Questão 2"
[asked2_2]: https://github.com/wyassue/teste/blob/master/img/%20answer2_M_v2.png "Questão 2"
[asked3]: https://github.com/wyassue/teste/blob/master/img/%20answer3.png "Questão 3"
[asked4]: https://github.com/wyassue/teste/blob/master/img/%20answer4.png "Questão 4"
[asked5_1]: https://github.com/wyassue/teste/blob/master/img/president/1961%201963-John%20Fitzgerald%20Kennedy.png "Questão 5.1"
[asked5_2.1]: https://github.com/wyassue/teste/blob/master/img/president/1933%201945-Franklin%20Delano%20Roosevelt.png "Questão 5.2.1"
[asked5_2.2]: https://github.com/wyassue/teste/blob/master/img/president/2009%202014-Barack%20Hussein%20Obama.png "Questão 5.2.2"
[asked5_3.1]: https://github.com/wyassue/teste/blob/master/img/president/1969%201974-Richard%20Milhous%20Nixon.png "Questão 5.3.1"
[asked5_3.2]: https://github.com/wyassue/teste/blob/master/img/president/1989%201993-George%20Herbert%20Walker%20Bush.png "Questão 5.3.2"
[asked9]: https://github.com/wyassue/teste/blob/master/img/answer9.png "Questão 9"

[president1]: https://github.com/wyassue/teste/blob/master/img/Theodore_1901_1909.png "Questão 5.1"
[president2]: https://github.com/wyassue/teste/blob/master/img/Herbert_1929_1933.png "Questão 5.2"
[president3]: https://github.com/wyassue/teste/blob/master/img/Franklin_1933_1945.png "Questão 5.3"

[trendF1]: https://github.com/wyassue/teste/blob/master/img/person/F/Ashanti_F.png "Questão 6.1.1"
[trendF2]: https://github.com/wyassue/teste/blob/master/img/person/F/Deneen_F.png "Questão 6.1.2"
[trendF3]: https://github.com/wyassue/teste/blob/master/img/person/F/Iesha_F.png "Questão 6.1.3"

[trendM1]: https://github.com/wyassue/teste/blob/master/img/person/M/Arsenio_M.png "Questão 6.1.1"
[trendM2]: https://github.com/wyassue/teste/blob/master/img/person/M/Devante_M.png "Questão 6.1.2"
[trendM3]: https://github.com/wyassue/teste/blob/master/img/person/M/Jase_M.png "Questão 6.1.3"

[famousF1]: https://github.com/wyassue/teste/blob/master/img/famous/F/Bella_F.png "Questão 6.2.1"
[famousF2]: https://github.com/wyassue/teste/blob/master/img/famous/F/Britney_F.png "Questão 6.2.1"
[famousF3]: https://github.com/wyassue/teste/blob/master/img/famous/F/Rihanna_F.png "Questão 6.2.1"

[famousM1]: https://github.com/wyassue/teste/blob/master/img/famous/M/Beckham_M.png "Questão 6.2.1"
[famousM2]: https://github.com/wyassue/teste/blob/master/img/famous/M/Kanye_M.png "Questão 6.2.2"
[famousM3]: https://github.com/wyassue/teste/blob/master/img/famous/M/Neymar_M.png "Questão 6.2.3"
[famousM4]: https://github.com/wyassue/teste/blob/master/img/famous/M/Shaquille_M.png "Questão 6.2.4"

[unisex1]: https://github.com/wyassue/teste/blob/master/img/unisex/Delane.png "Questão 7.1"
[unisex2]: https://github.com/wyassue/teste/blob/master/img/unisex/Ivory.png "Questão 7.2"
[unisex3]: https://github.com/wyassue/teste/blob/master/img/unisex/Michal.png "Questão 7.3"

[asked10]: https://github.com/wyassue/teste/blob/master/img/questao9.png "Questão 8"
[asked11]: https://github.com/wyassue/teste/blob/master/img/questao8.png "Questão 9"
