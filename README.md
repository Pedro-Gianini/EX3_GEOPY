## Solução dos exercícios da TERCEIRA aula do curso GeoPY
## Geocodificação e concatenação espacial

Bibliotecas usadas: gdal-bin python-gdal python3-gdal ; python3-rtree ; geopandas==0.10.0 ; descartes ; io ; pandas ; geopandas ; matplotlib.pyplot/patheffects ; contextily

Funções aprendidas: files.upload(); read_csv(); import geocode; .merge(); .to_crs(); .plot(); buffer=~nome do arquivo~.buffer(tamanho do buffer em metros);
.shape; .title('título de escolha'); sjoin('~tabela1~','~tabela2~',how='inner',predicate='within') ; .sum()

Conteúdos abordados :
Instalação e atualização das bibliotecas; leitura de arquivos offline que estão no hd da máquina usando a função files.upload(); Em seguida o arquivo é lido e é feita a geocodificação dos mesmo , logo após é feita a junção da tabela original do arquivo com os novos dados geocodificados usando a função .merge(); Depois é feita a reprojeção do sistema de coordenada usando a função .to_crs() e são plotados os endereços com a função .plot(); por fim usamos a função to_file('areas_verdes.shp'), para salvar o arquivo desejado. 
No proximo exercício para armazenar os buffers é criada uma nova coluna vazia chamada 'buffer', depois usamos a função buffer=comb.buffer(1000), esta que adiciona um buffer de 1000 metros e plotamos por meio do .plot(); Depois fazemos a substituição dos dados antigos igualando a coluna 'geometry' com os dados do buffer;
No ultimo exercício usamos o arquivo que contém os dados da população e fazemos um spatial join, que une apenas os setores censitários que estão dentro do buffer usando a função : pop_join=gpd.sjoin(pop,copia_comb,how='inner',predicate='within'), depois disso verificamos o tamanho da tabela pela função .shape; Em seguida é criada uma tabela apenas com o nome do local e população , para combinarmos com a tabela a geometria do buffer e o endereço; Por fim com todas as informações reunidas na ultima tabela, plotamos o mapa usando as bilbiotecas matplotlib.pyplot e contextily; Depois foi feito um ajuste na layout do map para facilitar a visualização dos dados.
