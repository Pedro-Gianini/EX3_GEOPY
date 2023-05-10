## Solução dos exercícios da terceira aula do curso GeoPY
## Geocodificação e concatenação espacial

Bibliotecas usadas:
gdal-bin python-gdal python3-gdal ; python3-rtree ; geopandas==0.10.0 ; descartes ; io ; pandas ; geopandas ; matplotlib.pyplot/patheffects ; contextily

Funções aprendidas:
apt.update() ; apt.upgrade() ; apt.install() ; files.upload(); read_csv();  geocode () ; io.StringIO() ; .merge(); .to_crs(); .plot(); buffer="nome do arquivo".buffer(tamanho do buffer em metros); .shape; .title('título de escolha'); sjoin("tabela1","tabela2",how='inner',predicate='within') ; .sum()

Conteúdos abordados :
# Exercício 1 # 
O código tem como objetivo geocodificar endereços de áreas verdes em São José dos Campos e exportá-las como um shapefile. Primeiramente, o código lê um arquivo de texto com os endereços e apelidos das áreas verdes. Em seguida, utiliza a biblioteca GeoPandas para geocodificar os endereços utilizando a API Nominatim, da OpenStreetMap. A ferramenta merge é usada para juntar o resultado da geocodificação com a tabela original de endereços, e a projeção das geometrias é alterada para WGS84 UTM Zona 23S. Por fim, o resultado é exportado como um shapefile com o nome "areas_verdes.shp".

# Exercício 2 # 
O código é uma sequência de comandos em Python que tem como objetivo criar buffers ao redor de áreas verdes geocodificadas. Primeiramente, é necessário criar um arquivo .txt com os endereços das áreas verdes e seus respectivos apelidos. Em seguida, é feita a geocodificação desses endereços e os resultados são armazenados em um GeoDataFrame. Depois, é realizado o reprojeto das geometrias para o sistema de coordenadas WGS84 UTM Zona 23S. 
Na parte 2 do código, é criada uma nova coluna no GeoDataFrame para armazenar o buffer. É utilizada a função buffer da Geopandas para criar buffers de 1 km ao redor de cada área verde. Em seguida, é criada uma cópia do GeoDataFrame original e as geometrias de ponto são substituídas pelos buffers gerados. Por fim, é exportado um shapefile com o nome "areas_verdes.shp" contendo os buffers gerados.

# Exercício 3 # 
O código é uma implementação em Python de um processo de análise espacial para calcular a quantidade de pessoas que vivem em um raio de 1km de áreas verdes. O processo inclui a importação de dados de geoprocessamento em formato shapefile, a concatenação espacial entre os buffers (áreas verdes) e os setores censitários, o agrupamento dos dados pelo nome de cada área verde, o cálculo da soma da população vivendo à 1km para cada área verde e a inserção da população total no GeoDataFrame do buffer. Além disso, o código plota os dados em um mapa e cria uma legenda resumida. O código também faz uso das bibliotecas geopandas, contextily e mapclassify.
