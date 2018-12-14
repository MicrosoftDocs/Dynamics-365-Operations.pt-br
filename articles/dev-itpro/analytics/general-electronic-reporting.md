---
title: "Relatório eletrônico (RE)"
description: "Este tópico oferece uma visão geral da ferramenta ER (Relatório eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 99c10649d7683265fcac86c1825c5a965bbdb415
ms.openlocfilehash: f27f228e48da653a9caf666f9053fe45a7c23745
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="electronic-reporting-er"></a>Relatório eletrônico (RE)

[!include [banner](../includes/banner.md)]

Este tópico oferece uma visão geral da ferramenta ER (Relatório eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER.

O ER é uma ferramenta que você pode usar para configurar formatos de documentos eletrônicos de entrada e de saída de acordo com os requisitos legais de vários países/regiões. ER permite que você gerencie esses formatos durante seu ciclo de vida. Por exemplo, você pode adotar novos requisitos normativos e gerar documentos de negócios no formato exigido para trocar informações, eletronicamente, com outras pessoas, bancos e órgãos do governo.

O mecanismo de ER se destina a usuários de negócios e não aos desenvolvedores. Como você configura formatos, em vez de códigos, os processos de criação e ajuste de formatos para documentos eletrônicos são mais rápidos e mais fáceis.

ER atualmente suporta os formatos de planilha texto, XML, documento do Microsoft Word e OPENXML. No entanto, uma interface de extensão oferece suporte a formatos adicionais.

## <a name="capabilities"></a>Capacidades
O mecanismo ER tem os seguintes recursos:

- Ele representa uma única ferramenta compartilhada para relatórios eletrônicos em domínios diferentes, e substitui mais de 20 mecanismos diferentes que fazem algum tipo de relatório eletrônico para o Microsoft Dynamics 365 for Finance and Operations.
- Isso torna o formato do relatório isolado da implementação atual do Finance and Operations. Em outras palavras, o formato é aplicável para versões diferentes do Finance and Operations.
- Ele suporta a criação de um formato personalizado que é baseado no formato original. Ele também inclui recursos para atualizar automaticamente o formato personalizado quando o formato original é alterado devido aos requisitos de localização/personalização.
- Ele se torna o padrão principal de suporte de requisitos de localização no relatório eletrônico para a Microsoft e parceiros da Microsoft.
- Ele oferece suporte à capacidade de formatos distribuídos para clientes e parceiros através do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Conceitos principais
### <a name="components"></a>Componentes

O ER dá suporte dois tipos de componentes **Modelo de dados** e **Formato**.

#### <a name="data-model-components"></a>Componentes do modelo de dados

Um componente de modelo de dados é uma representação abstrata de uma estrutura de dados. Ele é usado para descrever uma área específica de domínio corporativo com detalhes suficientes para atender aos requisitos de relatórios para o domínio. Um componente de modelo de dados é composto pelas seguintes partes:

- Um modelo de dados como um conjunto de entidades comerciais específicas de domínio, bem como a definição hierarquicamente estruturada de relações entre essas entidades.
- Um mapeamento de modelo que liga fontes de dados selecionadas do Finance and Operations a elementos individuais de um modelo de dados que especifica o fluxo de dados em tempo de execução e as regras de preenchimento de dados comerciais para o componente do modelo de dados.

Uma entidade comercial do modelo de dados é representada por um contêiner (registro). As propriedades da entidade comercial são representadas como itens de dados (campos). Cada item de dados tem um nome exclusivo, um rótulo, uma descrição e um valor. O valor de cada item de dados pode ser projetado para que seja reconhecido como cadeia de caracteres, inteiro, real, data, enumeração, booliano e assim por diante. Além disso, ele pode ser outro registro ou registros de lista.

Um único componente de modelo de dados pode conter várias hierarquias de entidades comerciais específicas de domínio. Também pode conter mapeamentos de modelo que oferecem suporte a um fluxo de dados específico do relatório em tempo de execução. As hierarquias são diferenciadas por um único registro que foi selecionado como uma raiz de mapeamento de modelo. Por exemplo, o modelo de dados da área de domínio de pagamento pode dar suporte aos seguintes mapeamentos:

- Empresa \> Fornecedor \> Transações de pagamento de domínio AP
- Cliente \> Empresa \> Transações de pagamento de domínio AR

Observe que as entidades de negócios, como transações de pagamento e de empresa, são projetadas uma vez. Mapeamentos diferentes, em seguida, reutilize-os.

Um mapeamento de modelo que oferece suporte a documentos eletrônicos de saída tem os seguintes recursos:

- Ele pode usar diferentes tipos de dados do Finance and Operations como fontes de dados para um modelo de dados. Por exemplo, ele pode usar tabelas, entidades de dados, métodos ou enumerações.
- Ele suporta parâmetros de entrada do usuário que podem ser definidos como fontes para um modelo de dados quando alguns dados devem ser especificados em tempo de execução.
- Ele oferece suporte à transformação dos dados do Finance and Operations em grupos necessários. Também permite filtrar, classificar e somar dados, além de acrescentar, com lógica calculada, campos que são criados por meio de fórmulas que se assemelham às do Microsoft Excel, conforme mostrado na ilustração a seguir. Para obter mais informações, consulte [Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md).

[![Designer de fórmulas](./media/ER-overview-01.png)](./media/ER-overview-01.png)

Um mapeamento de modelo que oferece suporte a documentos eletrônicos de entrada tem os seguintes recursos:

- Pode usar elementos de dados atualizáveis diferentes como metas. Esses elementos de dados incluem tabelas, entidades de dados e exibições. Os dados podem ser atualizados usando os dados dos documentos eletrônicos de entrada. Diversos destinos podem ser usados em um único mapeamento de modelo.
- Ele suporta parâmetros de entrada do usuário que podem ser definidos como fontes para um modelo de dados quando alguns dados devem ser especificados em tempo de execução.

Um componente do modelo de dados é criado para cada domínio corporativo que deve ser usado como fonte de dados unificada para relatórios que isole os relatórios da implementação física das fontes de dados. Ele representa conceitos e funcionalidades comerciais específicas de domínio de uma forma que torna o design inicial do formato de relatório e a manutenção adicional mais eficientes.

#### <a name="format-components-for-outgoing-electronic-documents"></a>Componentes de formato para documentos eletrônicos de saída

Um componente de formato é o esquema de saída do relatório que será gerado em tempo de execução. Um esquema é composto dos seguintes elementos:

- Um formato que define a estrutura e o conteúdo do documento eletrônico de saída gerado em tempo de execução.
- Fontes de dados, como um conjunto de parâmetros de entrada do usuário e um modelo de dados de domínio específico que usa um mapeamento de modelo selecionado.
- Um mapeamento de formato, como um conjunto de associações de fontes de dados do formato, com elementos individuais de formato que especificam, em tempo de execução, o fluxo de dados e as regras de geração de saída do formato.
- Uma validação de formato, como um conjunto de regras configuráveis que controla a geração de relatórios no tempo de execução, dependendo do contexto em execução. Por exemplo, pode haver uma regra que interrompe a geração de saída de pagamentos de um fornecedor e lança uma exceção quando os atributos específicos do fornecedor selecionado estão pendentes, como o número da conta bancária.

Um componente de formato suporta as seguintes funções:

- Criação de relatórios de saída como arquivos individuais em vários formatos, como texto, XML, Documento do Microsoft Word ou planilha.
- Criação de vários arquivos separadamente e o encapsulamento desses arquivos em arquivos zip.

Um componente de formato permite anexar arquivos específicos que podem ser usados na saída do relatório da seguinte maneira:

- Contendo pastas de trabalho da planilha do Excel como um modelo para saídas no formato de planilha OPENXML;
- Arquivos de Word contendo um documento que pode ser usado como modelo para saída no formato de documento do Microsoft Word;
- Os arquivos que podem ser incorporados na saída do formato como arquivos predefinidos

A ilustração a seguir mostra como os dados fluem para esses formatos.

[![Fluxo de dados para os componentes de formato de saída](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Para executar uma única configuração de formato ER e gerar um documento eletrônico de saída é preciso identificar o mapeamento da configuração de formato.

#### <a name="format-components-for-incoming-electronic-documents"></a>Componentes de formato para documentos eletrônicos de entrada
Um componente de formato é o esquema do documento de entrada que é importado em tempo de execução. Um esquema é composto dos seguintes elementos:

- Um formato que define a estrutura e o conteúdo do documento eletrônico de entrada que contém dados importados em tempo de execução. Um componente de formato é usado para analisar um documento de entrada em vários formatos, como texto e XML.
- Um mapeamento de formato que vincula os elementos de formato individuais aos elementos de um modelo de dados de domínio específico. Em tempo de execução, os elementos no modelo de dados especificam o fluxo de dados e as regras para importar dados de um documento de entrada e, em seguida, armazenar os dados em um modelo de dados.
- Uma validação de formato, como um conjunto de regras configuráveis que controla a importação de dados em tempo de execução, dependendo do contexto em execução. Por exemplo, pode haver uma regra que interrompe a importação de dados de um extrato bancário com os pagamentos do fornecedor e lança uma exceção quando os atributos de um fornecedor específico estão pendentes, como o código de identificação do fornecedor.

A ilustração a seguir mostra como os dados fluem para esses formatos.

[![Fluxo de dados para os componentes de formato de entrada](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Para executar uma única configuração de formato de ER para importar dados de um documento eletrônico de entrada, é preciso identificar o mapeamento desejado de uma configuração de formato, e também o ponto de integração de um mapeamento de modelo. Você pode usar o mesmo mapeamento de modelo e destinos juntamente com diferentes formatos para diferentes tipos de documentos recebidos.

#### <a name="component-versioning"></a>Controle de versão em componentes

Controle de versão tem suporte para componentes ER. O seguinte fluxo de trabalho é fornecido para gerenciar alterações em componentes ER:

1. A versão originalmente criada está marcada como uma versão **Rascunho**. Essa versão pode ser editada e está disponível para a execução do teste.
2. A versão **Rascunho** pode ser convertida em uma versão **Concluída**. Essa versão pode ser usada em processos de geração de relatórios locais.
3. A versão **Concluída** pode ser convertida em uma versão **Compartilhada**. Essa versão é publicada em LCS e pode ser usada em processos de relatórios globais.
4. A versão **Compartilhada** pode ser convertida em uma versão **Descontinuada**. Essa versão pode ser excluída.

As versões com o status **Concluída** ou **Compartilhada** estão disponíveis para outra troca de dados. As seguintes ações podem ser executadas em um componente que tem esse status:

- O componente pode ser serializado em formato XML e exportado como um arquivo no formato XML.
- O componente pode ser seriado novamente de um arquivo XML e importado para o Finance and Operations como uma nova versão de um componente de ER.

#### <a name="component-date-effectivity"></a>Efetivação de data de componente

Versão do componente ER com efetivação de data. Você pode definir a data **Efetiva a partir de** para que um componente ER especifique a data em que esse componente entra em vigor para os processos de relatório. A data da sessão do Finance and Operations é usada para definir se um componente é válido para execução. Se mais de uma versão é válida para uma data específica, a última versão é usada para processos de relatório.

#### <a name="component-access"></a>Acesso ao componente

O acesso aos componentes no formato ER depende da definição de códigos de país/região ISO. Quando essa configuração está em branco para uma versão selecionada de uma configuração de formato, um componente de formato pode ser acessado de qualquer empresa em tempo de execução. Quando essa configuração contiver códigos de país/região ISO, um componente de formato estará disponível das únicas empresas em que o endereço principal for definido para um dos códigos de país/região ISO do componente de formato.

Versões diferentes de um componente de formato de dados podem ter diferentes configurações de códigos de país/região ISO.

#### <a name="configuration"></a>Configuração

Uma configuração ER é o wrapper de um componente ER específico. Esse componente pode ser um componente de modelo de dados ou um componente de formato. Uma configuração pode incluir versões diferentes de um componente ER. Cada configuração é marcada como propriedade de um provedor de configuração específico. A versão **Rascunho** de um componente de uma configuração pode ser editada quando o proprietário de uma configuração for selecionado como o provedor ativo nas configurações ER do Finance and Operations.

Cada configuração de modelo contém um componente do modelo de dados. Uma nova configuração de formato pode ser derivada de uma configuração de modelo de dados específicos. Na árvore de configuração, a configuração de formato criada aparece como um filho da configuração do modelo de dados original.

A configuração de formato criada contém um componente de formato. O componente modelo de dados da configuração original de modelo é inserido automaticamente no componente formato da configuração de formato filho criada como uma fonte de dados padrão.

Uma configuração ER é compartilhada para empresas do Finance and Operations.

#### <a name="provider"></a>Provedor

O provedor de ER é a identificação de uma parte que é usada para indicar o autor (proprietário) de cada configuração de ER. ER permite que você gerencie a lista de provedores de configuração. As configurações de formato que são liberadas para documentos eletrônicos como parte da solução do Finance and Operations são marcadas como pertencentes ao fornecedor de configuração da **Microsoft**.

Para aprender a registrar um novo provedor de ER, execute a guia de tarefas **ER Criar um provedor de configuração e marcá-lo como ativo** (parte do processo comercial **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

#### <a name="repository"></a>Repositório

Um repositório armazena as configurações de RE. Quatro tipos de repositórios ER são atualmente compatíveis: **Recursos de operação**, **Projeto LCS (LCS)**, **Sistema de arquivo** e **Serviços de configuração regulatório (RCS)**.

Um repositório de **Recursos de operações** fornece acesso à lista de configurações que a Microsoft, como provedora de configuração do ER, libera como parte da solução Finance and Operations. Essas configurações podem ser importadas para a instância atual do Finance and Operations e usadas para relatórios eletrônicos. Elas também podem ser usadas para localizações e personalizações adicionais.

Um repositório de **projeto do LCS** fornece acesso à lista de configurações de projeto do LCS (biblioteca de ativos do projeto do LCS) que foi selecionado na fase de registro do repositório. O ER permite carregar configurações compartilhadas da instância atual do Finance and Operations para um repositório específico do **Projeto do LCS**. Você também pode importar configurações do repositório de um **Projeto LCS** na instância do Finance and Operations atual.

Um repositório do **Sistema de arquivos** fornece acesso à lista de definições que estão localizadas como arquivos xml na pasta específica do sistema de arquivos local do computador onde o serviço AOS está hospedado. A pasta necessária está selecionada no estágio de registro do armazenamento. Você também pode importar configurações de um repositório de **Sistema de arquivos** na instância do Finance and Operations atual. Note que esse tipo de armazenamento está acessível nos ambientes a seguir Dynamics 365 for Finance and Operations:
- ambientes armazenados em nuvem implantados para fins de desenvolvimento (contendo modelos de teste de pacotes integrados)
- ambientes localmente implantados (implantação LBD ou no local)

Visite a página [Configurações de Importação de relatório eletrônico (ER)](/electronic-reporting-import-ger-configurations.md) para obter mais detalhes sobre isso.

Um repositório de **Instância do RCS** fornece acesso à lista de configurações de uma instância RCS específica que foi selecionada na fase de registro do repositório. O ER permite a importação concluída ou configurações compartilhadas da instância selecionada de RCS na instância Finance and Operations e usado para relatório eletrônico.

Visite a página [Configurações de Importação de relatório eletrônico (ER) de Serviços de Configuração Regulatória (RCS)](/rcs-download-configurations.md) para obter mais detalhes sobre isso.

Os repositórios de **Projeto LCS**, **Sistema de arquivo** e **Serviços de configuração regulatória (RCS)** podem ser registrados individualmente para cada provedor de configuração da instância atual do Finance and Operations. Cada repositório pode ser dedicado a um provedor de configuração específico.

## <a name="supported-scenarios"></a>Cenários com suporte
### <a name="building-a-data-model"></a>Criação de um modelo de dados

O ER fornece um designer de modelo que você pode usar para criar um modelo de dados para um domínio comercial específico. Todas as entidades comerciais específicas de domínio e relações entre elas são apresentadas em um modelo de dados como uma estrutura hierárquica. A ilustração a seguir mostra um exemplo desse tipo de modelo de dados (o pagamento dados do modelo de domínio).

[![Modelo de dados de domínio de pagamento](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar modelo de dados de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="translating-data-model-content"></a>Traduzindo o conteúdo do modelo de dados

O conteúdo do modelo de dados (rótulos e descrições) pode ser traduzido para outros idiomas para os quais o Finance and Operations oferece suporte. Talvez você queira traduzir o conteúdo do modelo de dados pelos seguintes motivos:

- No momento da criação, para tornar um conteúdo mais inteligível para criadores de formato que falam outros idiomas, e que usarão o modelo de dados para mapeamento de dados de componentes de formato.
- No tempo execução, para tornar o conteúdo mais amigável, apresentando avisos e ajuda de parâmetros em tempo de execução, bem como mensagens de validação configuradas (erros e avisos), no idioma de preferência do usuário conectado.

A ilustração a seguir mostra um exemplo de onde o conteúdo do modelo de dados está traduzido do inglês para japonês.

[![Conteúdo de modelo de dados em Inglês](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Conteúdo de modelo de dados traduzido para japonês](./media/ER-overview-06.png)](./media/ER-overview-06.png)

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configurando mapeamentos de modelo de dados de documentos de saída

O ER fornece um designer de mapeamento do modelo que permite que os usuários mapeiem modelos de dados que eles criaram da fontes de dados específicas do Finance and Operations. Com base no mapeamento, os dados serão importados, em tempo de execução, das fontes de dados selecionadas para o modelo de dados. O modelo de dados é usado como uma fonte abstrata de dados de formatos ER que gera documentos eletrônicos de saída. O exemplo desse mapeamento de modelo de dados é mostrado na imagem a seguir (o mapeamento de modelo **Transferência de Crédito SEPA** do modelo de dados de domínio de pagamento).

[![Exemplo de mapeamento de modelo de dados](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Para familiarizar-se com este cenário em detalhes, execute os guias de tarefa **ER Definir o mapeamento do modelo e selecionar fontes de dados** e **ER Mapear modelo de dados para fontes de dados selecionadas** (parte do processo empresarial **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configurando mapeamentos de modelo de dados de documentos de entrada
ER fornece um designer de mapeamento do modelo que permite que os usuários mapeiem modelos de dados que eles criaram para destinos específicos. Por exemplo, os modelos de dados podem ser mapeados para os componentes de dados atualizáveis do Finance and Operations (tabelas, entidades de dados e exibições). Com base no mapeamento, os dados do Finance and Operations serão atualizados em tempo de execução usando os dados do modelo de dados. Como armazenamento abstrato do formato ER, o modelo de dados é preenchido com dados importados de um documento eletrônico de entrada. A ilustração a seguir mostra um exemplo desse tipo de mapeamento de modelo de dados. Neste exemplo, o mapeamento de modelo **Importar mapeamento para NETS** do modelo de dados de domínio de pagamento é usado para oferecer suporte à importação de extratos bancários no formato bancário NETS da Noruega.

[![Importar mapeamento para o exemplo do modelo de dados NETS](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Armazenamento do componente de modelo designado como uma configuração de modelo

O ER pode armazenar um modelo de dados designado, junto com os mapeamentos de dados associados, como uma configuração de modelo da instância atual do Dynamics 365 for Finance and Operations. A ilustração a seguir mostra um exemplo desse tipo de configuração do modelo de dados (o pagamento dados do modelo de configuração).

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Mapear modelo de dados para fontes de dados selecionadas** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Como criar um formato que usa um modelo de dados como base

O ER oferece suporte a um designer de formato que você pode usar para criar o formato de um documento eletrônico para o domínio comercial selecionado, escolhendo o componente modelo como base. O mesmo designer de formato de ER oferece a capacidade de mapear o formato criado para o mapeamento do modelo de dados do domínio selecionado como uma fonte de dados. A ilustração a seguir mostra um exemplo desse tipo de formato (a configuração de formato que oferece suporte a **BACS** formato de pagamento para o Brasil).

[![Exemplo de um formato que tem um modelo de dados como base](./media/ER-overview-09.png)](./media/ER-overview-09.png)

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar formato de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Criando uma configuração para gerar documentos eletrônicos em formato de planilha do OPENXML

O designer de formato ER pode ser usado para criar um documento eletrônico em formato de planilha do OPENXML. A ilustração a seguir mostra um exemplo desse tipo de formato (uma configuração de formato para gerar a planilha OPENXML com detalhes de um diário de pagamentos selecionado).

[![Pic-ER-format-Excel](./media/ER-overview-10.png)](./media/ER-overview-10.png)

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Criar uma configuração ER para gerar relatórios no formato OPENXML** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**). Como parte da etapa de guia de tarefas para importar um modelo, use o arquivo de Excel [Modelo de relatório de pagamento (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) como modelo.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Criando uma configuração para gerar documentos eletrônicos em formato de documento do Word
O designer de formato ER pode ser usado para criar um documento eletrônico em formato de documento do Word. A ilustração a seguir mostra um exemplo desse tipo de formato. Observe que esse formato reutiliza a configuração ER existente que foi originalmente criada para gerar a saída de relatório no formato OPENXML.

[![Pic-ER-format-Word](./media/ER-overview-11.png)](./media/ER-overview-11.png)

Para se familiarizar com os detalhes deste cenário, reproduza a guia de tarefas Criar uma configuração ER para gerar relatórios no formato Microsoft WORD (parte do processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)). Como parte da etapa de guia de tarefas para importar um modelo, use os seguintes arquivos de Word como modelos para o formato ER:

- [Modelo de relatório de pagamento (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Modelo limitado de relatório de pagamento (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Criar uma configuração para importar dados de documentos eletrônicos de entrada
O designer de formato ER pode ser usado para descrever um documento eletrônico planejado para importar dados em XML ou o formato de texto. O formato criado é usado para analisar um documento de entrada. O designer de mapeamento de formato ER pode ser usado para definir a associação dos elementos do formato criado com o modelo de dados. As ilustrações a seguir mostram um exemplo desse tipo de formato e mapeamento de formato. Neste exemplo, são importados extratos bancárias da NETS que incluem detalhes de pagamento do fornecedor no formato de texto.

[![ER-format-designer](./media/ER-overview-12.png)](./media/ER-overview-12.png)

[![ER-model-mapping-designer](./media/ER-overview-13.png)](./media/ER-overview-13.png)

Para se familiarizar com os detalhes deste cenário, reproduza a guia de tarefas Criar configurações ER necessárias para importar os dados de um arquivo externo (parte do processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)). Usar os seguintes arquivos para reproduzir esta guia:

- [Configuração de modelo de dados de ER (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Configuração de formato ER (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exemplo de documento de entrada no formato XML (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Exemplo de pasta de trabalho para gerenciar dados do documento de entrada (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Armazenamento do componente do formato designado na configuração de formato

O ER pode armazenar um formato designado junto com os mapeamentos de dados configurados como uma configuração de formato da instância atual do Finance and Operations. A ilustração anterior mostra um exemplo desse tipo de configuração de formato (**BACS (Reino Unido)**, que é um filho da configuração **Modelo de pagamento**). Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar formato de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="configuring-finance-and-operations-to-start-to-use-a-created-format-internally"></a>Configuração do Finance and Operations para começar a usar o formato criado internamente

O Finance and Operations pode ser configurado para começar a usar o formato criado para a geração de relatórios eletrônicos. A referência à configuração de formato criado deve ser definida em configurações específicas de um domínio. Por exemplo, para começar a usar uma configuração de formato de ER para pagamentos de fornecedores eletrônicos no formato BACS, a configuração de formato deve ser referenciada em métodos específicos de pagamento, conforme as ilustrações a seguir:

[![Configuração de formato BACS (Reino Unido)](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Referenciando o formato BACS (Reino Unido) em um método de pagamento](./media/ER-overview-15.png)](./media/ER-overview-15.png)

Execute a guia de tarefa **ER Usar formato para gerar documento eletrônico para pagamentos** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

## <a name="handling-er-components"></a>Manusear componentes ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Como publicar o componente de ER no LCS para oferecê-lo externamente (localização)

O proprietário de um componente criado é capaz de usar o ER para publicar a versão concluída de um componente de ER (modelo ou formato) para o LCS. Um repositório do tipo **Projeto de LCS** do provedor atual de configuração ER é necessário para isso. Quando o status da versão concluída de um componente mudar de **CONCLUÍDO** para **COMPARTILHADO**, esta versão será publicada no LCS. Quando um componente for publicado no LCS, o proprietário desse componente se tornará um prestador do serviço para dar suporte a esse componente. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico legalmente necessário (por exemplo, de acordo com o cenário de localização), esse serviço assumirá para manter esse formato compatível com as alterações legislativas e emitir novas versões deles sempre que as novas exigências legislativas precisarem de suporte. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Carregamento ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importação do componente de ER do LCS para usá-lo internamente

O ER permite importar componentes ER de LCS para a instância atual do Finance and Operations. Um repositório do tipo **Projeto de LCS** é necessário para isso. Quando um componente de ER for importado do LCS para a instância atual do Finance and Operations, o proprietário dessa instância se tornará um consumidor do serviço que é fornecido pelo proprietário (autor) de um componente importado. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico específico a partir do Finance and Operations em um formato específico de certo país/região (cenário de localização), supõem-se que o consumo deste serviço terá a capacidade de obter as atualizações desse formato para mantê-la compatível com as exigências legislativas. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Importar ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Como criar um formato selecionando outro formato como base (personalização)

Permite ER de criar (derivado) um novo componente da versão atual de um componente (base) que foi importado de LCS. Por exemplo, um usuário deseja derivar um novo formato para implementar alguns requisitos especiais para um documento eletrônico (por exemplo, um campo adicional ou uma descrição extensa) para oferecer suporte a um cenário de personalização. Execute a guia de tarefa **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Atualização de um formato selecionando uma nova versão do formato base (rebase)

O ER permite adotar automaticamente alterações na última versão do componente base na versão de rascunho atual do componente derivado. Esse processo é conhecido como *troca de base*. Por exemplo, as novas alterações de regulamentação (apresentadas na última versão do componente do formato importado do LCS) podem ser automaticamente adotadas na própria versão personalizada desse formato do documento eletrônico. As alterações que não podem ser mescladas automaticamente são consideradas conflitos. Esses conflitos são apresentados para resolução manual na ferramenta de designer para o componente apropriado. Reproduza o guia de tarefas **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.5.3 Adquirir/Desenvolver componente de solução/serviço de TI alterado (10683)**) para se familiarizar com este cenário em detalhes.

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-and-operations-solution"></a>Lista de configurações ER entregues na solução do Finance and Operations

| Configurações do modelo de dados específicos do domínio: título | Domínio                | Configurações dependentes do modelo de formato de data: título | Descrição                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Modelo de arquivo de auditoria                                 | Auditoria financeira       |                                                   |                                                                    |
|                                                  |                       | Arquivo de auditoria (NL)                                   | Formato de arquivo de auditoria para os Países Baixos                                  |
| Modelo BAS                                        | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | BAS (AU)                                          | Formato BAS da Austrália                                           |
| Modelo de Esquema do Setor de Construção               | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | Retorno mensal CIS (Reino Unido)                           | Formato de retorno mensal do CIS para o Reino Unido                   |
| Modelo de carta de cobrança                          | Faturas eletrônicas  |                                                   |                                                                    |
|                                                  |                       | Carta de cobrança OIOUBL (DK)                     | Formato de carta de cobrança OIOUBL da Dinamarca                        |
| Modelo de contabilidade eletrônicos (MX)          | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | Razão auxiliar XML (MX)                         | Transações do razão auxiliar por formato de relatório de conta para o México |
|                                                  |                       | Gráfico de contas XML (MX)                         | Gráfico do formato do relatório de conta para o México                          |
|                                                  |                       | Diários XML (MX)                                 | Formato do relatório de transações de diário para o México                      |
|                                                  |                       | Balancete XML (MX)                            | Formato de Relatório Balancete para o México                             |
| Modelo Elster                                     | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | Elster (DE)                                       | Formato da ELSTER para a Alemanha                                          |
| Modelo de lista de Vendas da UE                              | Relatório de troca       |                                                   |                                                                    |
|                                                  |                       | Lista de vendas da UE (DE)                                | Lista de vendas da UE formato TXT para Alemanha                               |
|                                                  |                       | Lista de vendas da UE (DK)                                | Lista de vendas da UE formato TXT para Dinamarca                               |
|                                                  |                       | Lista de vendas da UE (FR)                                | Lista de vendas da UE formato XML para França                                |
|                                                  |                       | Lista de vendas da UE (NL)                                | Formato XML de lista de vendas da UE para os Países Baixos                           |
|                                                  |                       | Lista de vendas da UE TXT (Reino Unido)                            | Formato TXT de lista de vendas da UE para o Reino Unido                    |
|                                                  |                       | Lista de vendas da UE XML (Reino Unido)                            | Formato XML de lista de vendas da UE para o Reino Unido                    |
|                                                  |                       | Lista de vendas da UE por relatório de colunas                   | Lista de vendas da UE por relatório de colunas                                    |
|                                                  |                       | Lista de vendas da UE por relatório de linhas                      | Lista de vendas da UE por relatório de linhas                                       |
| Modelo de contabilização FEC (FR)                        | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | Data Contábil FEC XML (FR)                      | Exportação de dados de estatísticas de FEC formato XML para a França                   |
| Arquivo de auditoria Alemão                                | Auditoria financeira       |                                                   |                                                                    |
|                                                  |                       | Saída do arquivo de auditoria Alemão                          | Fazer auditoria em arquivos de saída para a Alemanha e Áustria                          |
| Módulo intrastat                                  | Relatório de troca       |                                                   |                                                                    |
|                                                  |                       | Intrastat (DE)                                    | Formato da Intrastat para a Alemanha                                       |
|                                                  |                       | Intrastat (DK)                                    | Formato da Intrastat para a Dinamarca                                       |
|                                                  |                       | INTRACOM Intrastat (FR)                           | Formato INTRACOM Intrastat para a França                               |
|                                                  |                       | SAISUNIC Intrastat (FR)                           | Formato SAISUNIC Intrastat para a França                               |
|                                                  |                       | Intrastat (NL)                                    | Formato Intrastat para os Países Baixos                               |
|                                                  |                       | Intrastat (Reino Unido)                                    | Formato Intrastat para o Reino Unido                            |
|                                                  |                       | Relatório intrastat                                  | Relatório de controle de Excel Intrastat                                     |
| Modelo da fatura de cliente                           | Faturas eletrônicas  |                                                   |                                                                    |
|                                                  |                       | Nota de crédito do projeto OIOUBL (DK)                   | Formato de nota de crédito do projeto OIOUBL para Dinamarca                      |
|                                                  |                       | Fatura do projeto OIOUBL (DK)                       | Formato de fatura do projeto OIOUBL para Dinamarca                          |
|                                                  |                       | Nota de crédito das vendas OIOUBL (DK)                     | Formato de nota de crédito das vendas OIOUBL para Dinamarca                        |
|                                                  |                       | Fatura das vendas OIOUBL (DK)                         | Formato de nota fiscal de vendas OIOUBL para Dinamarca                            |
| Modelo de declaração OB                             | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | Declaração OB (NL)                               | Formato de declaração OB para os Países Baixos                          |
| Modelo de pagamento                                    | Pagamentos              |                                                   |                                                                    |
|                                                  |                       | Betalingsservice (DK)                             | Formato de pagamento Betalingsservice para a Dinamarca                        |
|                                                  |                       | Remessa de letra de câmbio (FR)                  | Formato de remessa de letra de câmbio da França                      |
|                                                  |                       | BTL91 (NL)                                        | Formato de pagamento de fornecedor BTL91 para os Países Baixos                    |
|                                                  |                       | CFONB Prelevements (FR)                           | Formato de pagamento de débito direto de CFONB para a França                       |
|                                                  |                       | Virements CFONB (FR)                              | Formato de pagamento de fornecedor doméstico de CFONB para a França                    |
|                                                  |                       | Fornecedor do Nordea (DK)                                | Formato de pagamento Nordea Corporate Netbank para Dinamarca         |
|                                                  |                       | Serviço de crédito direto ANZ (AU)                    | Formato para serviço de crédito direto da ANZ para Austrália                 |
|                                                  |                       | Serviço de crédito direto CBA (AU)                    | Formato para serviço de crédito direto da CBA para Austrália                 |
|                                                  |                       | Serviço de crédito direto NAB (AU)                    | Formato para serviço de crédito direto da NAB para Austrália                 |
|                                                  |                       | Serviço de crédito direto STG (AU)                    | Formato para serviço de crédito direto da STG para Austrália                 |
|                                                  |                       | Sistema de entrada direta WBC (AU)                      | Formato para Sistema de entrada direto da WBC para Austrália                   |
|                                                  |                       | DirectLink (NZ)                                   | Formato de DirectLink para Nova Zelândia                              |
|                                                  |                       | Arquivo de pagamento JBA (JP)                             | Formato de pagamento JBA para o Japão                                       |
|                                                  |                       | Transferência de Crédito ISO20022                          | Formato de transferência de crédito de SEPA da Europa                             |
|                                                  |                       | Transferência de Crédito ISO20022 (FR)                     | Formato de transferência de crédito de SEPA da França                             |
|                                                  |                       | Transferência de Crédito ISO20022 (DE)                     | Formato de transferência de crédito de SEPA da Alemanha                            |
|                                                  |                       | Transferência de Crédito ISO20022 (NL)                     | Formato de transferência de crédito SEPA dos Países Baixos                    |
|                                                  |                       | Débito direto ISO20022                             | Formato de débito direto SEPA da Europa                                |
|                                                  |                       | Débito direto ISO20022 (FR)                        | Formato de débito direto SEPA da França                                |
|                                                  |                       | Débito direto ISO20022 (DE)                        | Formato de débito direto SEPA da Alemanha                               |
|                                                  |                       | Débito direto ISO20022 (NL)                        | Formato de débito direto SEPA para os Países Baixos                       |
|                                                  |                       | BACS (REINO UNIDO)                                         | Formato de pagamento de fornecedor do BACS para o Reino Unido                  |
| Encargos revertidos                                   | Relatório de taxas         |                                                   |                                                                    |
|                                                  |                       | Lista de vendas de encargos revertidos                         | Formato de lista de vendas de encargos revertidos                                   |
| Modelo de integração XBRL Holandês                     | Relatório XBRL        |                                                   |                                                                    |
|                                                  |                       | XBRL Semansys (NL)                                | Formato de exportação Semansys XBRL para os Países Baixos                    |
| Modelo GAF (MY)                                   | Auditoria financeira       |                                                   |                                                                    |
|                                                  |                       | Arquivo GAF (MY)                                     | Formato de GAF para Malásia                                         |
| Relatório de classificação por vencimento de fornecedores (CN)                         | Análise de dados de fornecedores |                                                   |                                                                    |
|                                                  |                       | Formato de Relatório de classificação por vencimento de fornecedores (CN)                   | Formato de Relatório de classificação por vencimento de fornecedores para China                               |
| Modelo de Declaração de faturas do fornecedor                 | Análise de dados de fornecedores |                                                   |                                                                    |
|                                                  |                       | Declaração de faturas do fornecedor (IS)                   | Formato de declaração de fatura de fornecedor da Islândia                      |
|                                                  |                       | Relatório de declaração de faturas de fornecedor (IS)            | Relatório de declaração de fatura de fornecedor da Islândia                      |

## <a name="additional-resources"></a>Recursos adicionais

[Requisitos de localização – criar uma configuração de relatórios eletrônica](electronic-reporting-configuration.md)

[Gerenciar o ciclo de vida da configuração de relatório eletrônico](general-electronic-reporting-manage-configuration-lifecycle.md)

