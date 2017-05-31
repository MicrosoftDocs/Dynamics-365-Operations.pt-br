---
title: "Visão geral do relatório eletrônico"
description: "Este artigo fornece uma visão geral ferramenta ER (Relatório eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: caa9f4c73f4c6b5b7637b5b012bd9ed3b7dd6392
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="electronic-reporting-overview"></a>Visão geral do relatório eletrônico

[!include[banner](../includes/banner.md)]


Este artigo fornece uma visão geral ferramenta ER (Relatório eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER.

Relatório eletrônico (ER) é uma ferramenta que você pode usar para configurar formatos para documentos eletrônicos de acordo com os requisitos legais de vários países/regiões. ER permite que você gerencie esses formatos durante seu ciclo de vida. Por exemplo, você pode adotar novos requisitos normativos e pode gerar documentos de negócios no formato exigido eletronicamente e trocar informações com outras pessoas, bancos e órgãos do governo. O mecanismo de ER se destina a usuários de negócios e não aos desenvolvedores. Como você configura formatos, não códigos, os processos de criação e ajuste de formatos para documentos eletrônicos são mais rápidos e mais fáceis. ER atualmente suporta os formatos de planilha texto, XML e OPENXML. No entanto, uma interface de extensão oferece suporte a mais formatos.

## <a name="capabilities"></a>Capacidades
O mecanismo ER tem os seguintes recursos:

-   Ele representa uma única ferramenta comum para relatórios eletrônicos em domínios diferentes, e substitui mais de 20 mecanismos diferentes que fazem algum tipo de relatório eletrônico para o Microsoft Dynamics 365 for Operations.
-   Isso torna o formato do relatório isolado da implementação atual do Dynamics 365 for Operations. (Em outras palavras, o formato é aplicável para versões diferentes do Dynamics 365 for Operations).
-   Ele suporta a criação de um formato personalizado que é baseado no formato original. Ele inclui recursos para atualizar automaticamente o formato personalizado quando ocorrem alterações no formato original porque os requisitos de localização/personalização são introduzidos.
-   Ele se torna o padrão principal de suporte de requisitos de localização no relatório eletrônico para a Microsoft e parceiros da Microsoft.
-   Ele oferece suporte à capacidade de formatos distribuídos para clientes e parceiros através do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Conceitos
### <a name="components"></a>Componentes

O ER dá suporte dois tipos de componentes **Modelo de dados** e **Formato**.

#### <a name="data-model-components"></a>Componentes do modelo de dados

Um componente do modelo de dados é uma representação abstrata da estrutura de dados a ser usada para descrever uma área de domínio comercial com detalhamento suficiente para atender aos requisitos de relatórios neste domínio. Um componente de modelo de dados é composto pelas seguintes partes:

-   Um modelo de dados como um conjunto de entidades comerciais específicas de domínio, bem como a definição hierarquicamente estruturada de relações entre essas entidades
-   Um mapeamento de modelo que liga fontes de dados selecionadas do Dynamics 365 for Operations a elementos individuais de um modelo de dados que especifica o fluxo de dados em tempo de execução e as regras de preenchimento de dados comerciais para o componente do modelo de dados.

Uma entidade comercial do modelo de dados é representada por um contêiner (registro). As propriedades da entidade comercial são representadas como itens de dados (campos). Cada item de dados tem um nome exclusivo, um rótulo, uma descrição e um valor. O valor de cada item de dados pode ser projetado para que seja reconhecido como cadeia de caracteres, inteiro, real, data, enumeração, booliano e assim por diante. Além disso, ele pode ser outro registro ou registros de lista. Um único componente do modelo de dados pode conter várias hierarquias de entidades comerciais específicas de domínio, bem como mapeamentos de modelo para dar suporte a um fluxo de dados específico de relatório em tempo de execução. As hierarquias são diferenciadas por um único registro que foi selecionado como uma raiz de mapeamento de modelo. Por exemplo, o modelo de dados da área de domínio de pagamento pode dar suporte aos seguintes mapeamentos:

-   Empresa -&gt; Fornecedor -&gt; Transações de pagamento de domínio AP
-   Cliente -&gt; Empresa -&gt; transações de pagamento de domínio AR

Observe que as entidades de negócios (por exemplo, transações de pagamento e de empresa) são projetadas uma vez. Mapeamentos diferentes, em seguida, reutilize-os. Um mapeamento de modelo tem os seguintes recursos:

-   Ele pode usar diferentes tipos de dados do Dynamics 365 for Operations como fontes de dados para um modelo de dados. Por exemplo, ele pode usar tabelas, entidades de dados, métodos ou enumerações.
-   Ele suporta parâmetros de entrada do usuário que podem ser definidos como fontes para um modelo de dados quando alguns dados devem ser especificados em tempo de execução.
-   Ele oferece suporte a transformação dos dados do Dynamics 365 for Operations em grupos necessários, filtragem, classificação e soma de dados, além de acrescentar com lógica calculada, campos que são criados por meio de fórmulas do Microsoft Excel (para obter mais detalhes, consulte [Designer de fórmulas no relatório eletrônico](general-electronic-reporting-formula-designer.md)).

[![Editor de fórmulas do Excel](./media/pic-formula-1024x615.png)](./media/pic-formula.png) Um componente do modelo de dados é criado para cada domínio comercial a ser usado como uma fonte de dados unificados para relatórios que isolam relatórios da implementação física de fontes de dados do Dynamics 365 for Operations e representa conceitos de negócios e funcionalidades específicas de domínio em um formato que torna o design inicial e a manutenção de formatos de relatórios mais eficazes.

#### <a name="format-components"></a>Componentes de formato

Um componente de formato é o esquema de saída do relatório que será gerado em tempo de execução. Um esquema é composto dos seguintes elementos:

-   Um formato que define a estrutura e o conteúdo do documento de relatório eletrônico que é gerado em tempo de execução
-   Fontes de dados como um conjunto de parâmetros de entrada do usuário e modelo de dados específicos que usam domínio com o mapeamento de modelo selecionado;
-   Um mapeamento de formato como um conjunto de associações de fontes de dados do formato com elementos individuais de formato que especificam o tempo de execução do fluxo de dados e as regras de geração de saída do formato
-   Uma validação de formato como um conjunto de regras configuráveis que controlam a geração de relatórios em tempo de execução, dependendo do contexto de execução (por exemplo, uma regra que interrompe a geração de saída de pagamentos do fornecedor e lança uma exceção quando atributos específicos do fornecedor selecionado estão ausentes, como o banco de número de conta).

Um componente de formato suporta as seguintes funções:

-   Criação de relatórios de saída como arquivos individuais em vários formatos: texto, XML ou planilha
-   Criação de vários arquivos separadamente e também o encapsulamento desses arquivos em arquivos zip

Um componente de formato permite anexar determinados arquivos que podem ser usados na saída do relatório da seguinte maneira:

-   Contendo pastas de trabalho da planilha do Excel como um modelo para saídas no formato de planilha OPENXML;
-   Os arquivos que podem ser incorporados na saída do formato como arquivos predefinidos

#### <a name="component-versioning"></a>Controle de versão em componentes

Controle de versão tem suporte para componentes ER. O seguinte fluxo de trabalho é fornecido para gerenciar alterações em componentes ER:

-   A versão é originalmente criada está marcada como uma versão **RASCUNHO**. Essa versão pode ser editada e está disponível para a execução do teste.
-   A versão **RASCUNHO** pode ser convertida em uma versão **CONCLUÍDA**. Essa versão pode ser usada em processos de geração de relatórios locais.
-   A versão **CONCLUÍDA** pode ser convertida em uma versão **COMPARTILHADA**. Essa versão é publicada em LCS e pode ser usada em processos de relatórios globais.
-   A versão **COMPARTILHADA** pode ser convertida em uma versão **DESCONTINUADA**. Essa versão pode ser excluída.

As versões com status** CONCLUÍDO** ou **COMPARTILHADO** estão disponíveis para outra troca de dados. Um componente que tem esse status pode ter essas ações executadas neles:

-   Pode ser serializado em formato XML e exportado do Dynamics 365 for Operations como um arquivo no formato XML.
-   Eles podem ser seriados novamente de um arquivo XML e importados para o Dynamics 365 for Operations como uma nova versão de um componente de ER.

#### <a name="component-date-effectivity"></a>Efetivação de data de componente

Versão do componente ER com efetivação de data. A data**Efetiva a partir de**pode ser definida para que um componente ER especifique a data em que esse componente entra em vigor para os processos de relatório. A data da sessão do Dynamics 365 for Operations é usada para definir se um componente é válido para execução. Se mais de uma versão é válida para uma data específica, a última versão é usada para processos de relatório.

#### <a name="component-access"></a>Acesso ao componente

O acesso aos componentes no formato ER depende da definição de códigos de país/região ISO. Quando essa configuração está em branco para uma versão selecionada de uma configuração de formato, um componente de formato pode ser acessado de qualquer empresa do Dynamics 365 for Operations em tempo de execução. Quando esta definição contém códigos de país/região ISO, um componente de formato fica disponível somente para empresas do Dynamics 365 for Operations que têm um endereço principal definido para um dos códigos de país/região ISO do componente de formato. Versões diferentes de um componente de formato de dados podem ter diferentes configurações de códigos de país/região ISO.

#### <a name="configuration"></a>Configuração

A configuração de ER é o wrapper de determinado componente ER: **Modelo de dados** ou **Formato**. Uma configuração pode incluir versões diferentes de determinado componente ER. Cada configuração é marcada como propriedade de um fornecedor de configuração específico. A versão **RASCUNHO** de um componente de uma configuração pode ser editada quando o proprietário de uma configuração for selecionado como o provedor ativo nas configurações ER do Dynamics 365 for Operations. Cada configuração de modelo contém um componente do **Modelo de dados**. Uma nova configuração de formato pode ser originada (derivada) de uma configuração de modelo de dados específico. A configuração de formato criada será apresentada na árvore de configuração como um filho da configuração do modelo de dados original. A configuração de formato criada contém um componente de **Formato**. O componente **Modelo de dados** da configuração original de modelo será inserido automaticamente no componente **Formato** da configuração de formato filho criada como uma fonte de dados padrão. Uma configuração de ER é compartilhada para empresas do Dynamics 365 for Operations.

#### <a name="provider"></a>Provedor

O provedor de ER é a identificação de uma parte que é usada para indicar o autor (proprietário) de cada configuração de ER. ER permite que você gerencie a lista de provedores de configuração. As configurações de formato que são lançadas para documentos eletrônicos como parte da solução do Dynamics 365 for Operations são marcadas como pertencentes ao fornecedor de configuração da **Microsoft**.

#### <a name="repository"></a>Repositório

Um repositório armazena as configurações de RE. Os seguintes tipos de repositórios de ER têm suporte no momento: **Recursos de operações** e **projeto de LCS**. Um repositório de ** Recursos de operações** fornece acesso à lista de configurações que são entregues como parte da solução do Dynamics 365 for Operations pelo Microsoft como um provedor de configuração do ER. Essas configurações podem ser importadas para a instância atual do Dynamics 365 for Operations e usadas para relatórios eletrônicos. Elas também podem ser usadas para localizações/personalizações adicionais. Um repositório de **projeto do LCS** fornece acesso à lista de configurações de projeto do LCS (biblioteca de ativos do projeto do LCS) que foi selecionado na fase de registro do repositório. O ER permite carregar configurações compartilhadas da instância atual do Dynamics 365 for Operations para um repositório específico do **projeto do LCS**. Você também pode importar configurações de um repositório de **projeto LCS** específico na instância do Dynamics 365 for Operations atual. Os repositórios do **projeto do LCS** necessários podem ser registrados individualmente para cada provedor de configuração da instância atual do Dynamics 365 for Operations. Cada repositório pode ser dedicado a um provedor de configuração específico.

## <a name="supported-scenarios"></a>Cenários com suporte
### <a name="building-a-data-model"></a>Criação de um modelo de dados

O ER fornece um designer de modelo que você pode usar para criar um modelo de dados para um domínio comercial específico. Todas as entidades comerciais específicas de domínio e relações entre elas são apresentadas em um modelo de dados como uma estrutura hierárquica. A ilustração a seguir mostra um exemplo desse tipo de modelo de dados (o pagamento dados do modelo de domínio). [![Exemplo de um modelo de dados](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) Para se familiar com os detalhes deste cenário, execute o guia de tarefas **ER Projetar modelo de dados de domínio específico** (parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="translating-data-model-content"></a>Traduzindo o conteúdo do modelo de dados

O conteúdo do modelo de dados (rótulos e descrições) pode ser traduzido para outros idiomas para os quais o Dynamics 365 for Operations oferece suporte. Talvez você queira traduzir o conteúdo do modelo de dados pelos seguintes motivos:

-   No momento da criação, para tornar um conteúdo mais inteligível para criadores de formato que falam apenas outro idioma, e que usarão um modelo de dados para mapeamento de dados de componentes de formato
-   No tempo de execução, para tornar o conteúdo mais fácil para o usuário, apresentando prompts e ajuda para parâmetros do tempo de execução e também mensagens de validação configuradas (erros e advertências), no idioma preferido do usuário registrado atualmente no Dynamics 365 for Operations.

A ilustração a seguir mostra um exemplo de como modelo de dados de conteúdo pode ser traduzido do inglês para japonês. [![Conteúdo do modelo de dados em inglês](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png) [![Conteúdo do modelo de dados em japonês](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Configuração de mapeamentos do modelo de dados

O ER fornece um designer de mapeamento do modelo que permite que os usuários mapeiem modelos de dados que eles criaram da fontes de dados específicas do Dynamics 365 for Operations. O exemplo desse mapeamento de modelo de dados é mostrado na imagem a seguir (o mapeamento de modelo **Transferência de Crédito SEPA** do modelo de dados de domínio de pagamento). [![Exemplo de um mapeamento de modelo de dados ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png) Para familiarizar-se com os detalhes deste cenário, execute as guias de tarefas de **ER Definir o mapeamento do modelo e selecionar fontes de dados** e de **ER Mapear modelo de dados para fontes de dados selecionadas** (parte do processo de negócios **7.5.4.3 Adquirir/desenvolver componentes de serviço/solução de TI (10677)**).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Armazenamento do componente de modelo designado como uma configuração de modelo

O ER pode armazenar um modelo de dados designado junto com os mapeamentos de dados associados como uma configuração de modelo da instância atual do Dynamics 365 for Operations. A ilustração a seguir mostra um exemplo desse tipo de configuração do modelo de dados (o pagamento dados do modelo de configuração). [![Exemplo de um modelo de dados ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png) Para se familiar com os detalhes deste cenário, execute o guia de tarefas **ER Mapear modelo de dados para as origens de dados selecionadas** (parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Como criar um formato que usa um modelo de dados como base

O ER oferece suporte a um designer de formato para criar um formato de um documento eletrônico específico para o domínio comercial selecionado, escolhendo o componente modelo como base. O mesmo designer de formato de ER oferece a capacidade de mapear o formato criado para o mapeamento do modelo de dados do domínio selecionado como uma fonte de dados. A ilustração a seguir mostra um exemplo desse tipo de formato (a configuração de formato que oferece suporte a **BACS** formato de pagamento para o Brasil). [![Exemplo de um formato que tem um modelo de dados como base](./media/pic-format-1024x690.png)](./media/pic-format.png) Para se familiar com os detalhes deste cenário, execute o guia de tarefas **ER Projetar formato de domínio específico** (parte do processo de negócios **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Criando uma configuração para gerar documentos eletrônicos em formato de planilha do OPENXML

Designer de formato ER pode ser usado para criar um determinado documento eletrônico em formato de planilha do OPENXML. A ilustração a seguir mostra um exemplo deste tipo de formato (uma configuração de formato para gerar a planilha de OPENXML com detalhes de um diário de pagamento selecionado):[![Pic-ER-format-Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) Para se familiarizar com os detalhes desse cenário, execute o guia de tarefas **ER Criar uma configuração para relatórios no formato OPENXML** (parte do processo comercial **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**). Use a referência mencionada abaixo do arquivo de Excel como um modelo de formato ER para projetar e concluir a etapa da importação do modelo um formato deste guia de tarefa: [Modelo do Relatório de Pagamento (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Armazenamento do componente do formato designado na configuração de formato

O ER pode armazenar um formato designado com os mapeamentos de dados configurados como uma configuração de formato da instância atual do Dynamics 365 for Operations. A ilustração anterior mostra um exemplo desse tipo de configuração de formato (**BACS (Reino Unido)**, que é um filho da configuração **Modelo de pagamento**). Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar formato de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Configuração do Dynamics 365 for Operations para começar a usar o formato criado internamente

O Dynamics 365 for Operations pode ser configurado para começar a usar o formato criado para a geração de relatórios eletrônicos. A referência à configuração de formato criado deve ser definida em configurações específicas de um domínio. Por exemplo, para começar a usar uma configuração de formato de ER para pagamentos de fornecedores eletrônicos no formato BACS, a configuração de formato deve ser referenciada em métodos específicos de pagamento, conforme as ilustrações a seguir: 

[![Configuração de formato BACS (Reino Unido)](media/ger-bacs-uk-format-configuration.png) 

[![Referenciando o formato BACS (Reino Unido) em um método de pagamento](media/ger-bacs-uk-format-method.png) 

Execute a guia de tarefa **ER Usar formato para gerar documento eletrônico para pagamentos** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

## <a name="handling-er-components"></a>Manusear componentes ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Como publicar o componente de ER no LCS para oferecê-lo externamente (localização)

O proprietário de um componente criado é capaz de usar o ER para publicar a versão concluída de um componente de ER (modelo ou formato) para o LCS. Um repositório do tipo **Projeto de LCS**do provedor atual de configuração de ER é necessário para isso. Quando o status da versão concluída de um componente mudar de **CONCLUÍDO** para **COMPARTILHADO**, esta versão será publicada no LCS. Quando um componente for publicado no LCS, o proprietário desse componente se tornará um prestador do serviço para dar suporte a esse componente. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico legalmente necessário (por exemplo, de acordo com o cenário de localização), esse serviço assumirá para manter esse formato compatível com as alterações legislativas e emitir novas versões deles sempre que as novas exigências legislativas precisarem de suporte. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Carregamento ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importação do componente de ER do LCS para usá-lo internamente

ER permite importar componentes ER de LCS para a instância atual do Dynamics 365 for Operations. Um repositório do tipo **Projeto de LCS**é necessário para isso. Quando um componente de ER for importado do LCS para a instância atual do Dynamics 365 for Operations, o proprietário dessa instância se tornará um consumidor do serviço que é fornecido pelo proprietário (autor) de um componente importado. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico específico a partir do Dynamics 365 for Operations em um formato específico de certo país/região (cenário de localização), supõem-se que o consumo deste serviço terá a capacidade de obter as atualizações desse formato para mantê-la compatível com as exigências legislativas. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Importar ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Como criar um formato selecionando outro formato como base (personalização)

Permite ER de criar (derivado) um novo componente da versão atual de um componente (base) que foi importado de LCS. Por exemplo, um usuário deseja derivar um novo formato para implementar alguns requisitos especiais para um documento eletrônico (por exemplo, um campo adicional ou uma descrição extensa) para oferecer suporte a um cenário de personalização. Execute a guia de tarefa **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Atualização de um formato selecionando uma nova versão do formato base (rebase)

O ER permite adotar automaticamente alterações na última versão do componente base na versão de rascunho atual do componente derivado. Esse processo é conhecido como *troca de base*. Por exemplo, as novas alterações de regulamentação (apresentadas na última versão do componente do formato importado do LCS) podem ser automaticamente adotadas na própria versão personalizada desse formato do documento eletrônico. As alterações que não podem ser mescladas automaticamente são consideradas conflitos. Esses conflitos são apresentados para resolução manual na ferramenta de designer para o componente apropriado. Execute a guia de tarefa **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Lista de configurações de ER são entregues na solução Dynamics 365 for Operations
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



<a name="see-also"></a>Consulte também
--------

[Requisitos de localização – criar uma configuração de relatórios eletrônica](electronic-reporting-configuration.md)

[Gerenciar o ciclo de vida da configuração de relatório eletrônico](general-electronic-reporting-manage-configuration-lifecycle.md)




