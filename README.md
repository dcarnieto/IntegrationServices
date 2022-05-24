# IntegrationServices
Integration Services Studies


Carregamento dos dados do Excel via Visual Studio (SSIS)
- Abrir o projeto 'SSIS_CLIENTE' (nome)
- Criar um novo Package dentro do > SSIS Packages
- Criar um novo Data Flow Task dentro do pacote novo
- Em Other Resoures arrastar o Excel Resource
	- Dentro do Excel, New, escolher a planilha no caminho.
	- Em Name Of The Excel Sheet, escolher Planilha1$
- Clicar em Columns para verificar se foi carregada a estrutura da planilha e ok
- Em Other Destinations, arrastar OLE DB Destination
- Arrastar a seta Azul do Excel Source para o OLE DB Destination
- Dentro de OLE DB Destination, alterar a conexão OLE DB connection mannager para o banco correto
- Em Name of the table or the view, selecionar a tabela que será atualizada com os dados
- Clicar em Mappings onde será exibido a origem e destino das colunas ligadas

Antes de realizar a atualização, é necessário realizar o truncate na tabela para que os dados não fiquem duplicados, duas opções:
	1 - Realizar o truncate direto no banco
	2 - Criar uma tarefa de truncate direto no Visual Studio

Após o truncate, salvar o pacote e executar o mesmo com botão direito 'Execute Package'.

***OBS: Ocorreu um erro no momento de carregar os dados por incompatibilidade dos caracteres nos dados/campos do excel com a tabela, neste caso pode ser feito então a criação da tabela.
	- drop table 'tabela' direto no banco
	- em OLE DB Destination, Connection Manager, clicar em New na seção Name of the tabela or the view e copiar o create table alterando o nome OLE DESTINATION para o nome da tabela, salvar e executar o pacote.
