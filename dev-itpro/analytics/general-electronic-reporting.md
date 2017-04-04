---
title: "Visão geral do relatório eletrônico"
description: "Este artigo fornece uma visão geral ferramenta ER (Relatório eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
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
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: b3e8174d07c9b9fd4210486c369c640fe07c49eb
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-overview"></a>Visão geral do relatório eletrônico

Este artigo fornece uma visão geral ferramenta ER (Relatório eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER.

Relatório eletrônico (ER) é uma ferramenta que você pode usar para configurar formatos para documentos eletrônicos de acordo com os requisitos legais de vários países/regiões. ER permite que você gerencie esses formatos durante seu ciclo de vida. Por exemplo, você pode adotar novos requisitos normativos e pode gerar documentos de negócios no formato exigido eletronicamente e trocar informações com outras pessoas, bancos e órgãos do governo. O mecanismo de ER se destina a usuários de negócios e não aos desenvolvedores. Como você configura formatos, não códigos, os processos de criação e ajuste de formatos para documentos eletrônicos são mais rápidos e mais fáceis. ER atualmente suporta os formatos de planilha texto, XML e OPENXML. No entanto, uma interface de extensão oferece suporte a mais formatos.

## <a name="capabilities"></a>Capacidades
O mecanismo ER tem os seguintes recursos:

-   Representa um único ferramenta comuns para o relatório eletrônico em domínios diferentes, e a mais de 20 que tornam diferentes mecanismos qualquer tipo de relatório eletrônico para Microsoft Dynamics 365 para as operações.
-   Faz um formato de relatórios atual dinâmica isolados de 365 para a implementação de operações. (Ou seja o formato é aplicável para versões diferentes do 365 para as operações.)
-   Ele suporta a criação de um formato personalizado que é baseado no formato original. Ele inclui recursos para atualizar automaticamente o formato personalizado quando ocorrem alterações no formato original porque os requisitos de localização/personalização são introduzidos.
-   Ele se torna o padrão principal de suporte de requisitos de localização no relatório eletrônico para a Microsoft e parceiros da Microsoft.
-   Ele oferece suporte à capacidade de formatos distribuídos para clientes e parceiros através do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Conceitos
### <a name="components"></a>Componentes

O ER dá suporte dois tipos de componentes **Modelo de dados** e **Formato**.

#### <a name="data-model-components"></a>Componentes do modelo de dados

Um componente do modelo de dados é uma representação abstrata da estrutura de dados a ser usada para descrever uma área de domínio comercial com detalhamento suficiente para atender aos requisitos de relatórios neste domínio. Um componente de modelo de dados é composto pelas seguintes partes:

-   Um modelo de dados como um conjunto de entidades comerciais específicas de domínio, bem como a definição hierarquicamente estruturada de relações entre essas entidades
-   Mapeamento um modelo que vincula selecionou 365 para dynamics a fontes de dados de operações aos elementos individuais de um modelo de dados que especificasse, em tempo de execução, o fluxo de dados e as regras de população de dados comerciais a um componente do modelo de dados.

Uma entidade comercial do modelo de dados é representada por um contêiner (registro). As propriedades da entidade comercial são representadas como itens de dados (campos). Cada item de dados tem um nome exclusivo, um rótulo, uma descrição e um valor. O valor de cada item de dados pode ser projetado para que seja reconhecido como cadeia de caracteres, inteiro, real, data, enumeração, booliano e assim por diante. Além disso, ele pode ser outro registro ou registros de lista. Um único componente do modelo de dados pode conter várias hierarquias de entidades comerciais específicas de domínio, bem como mapeamentos de modelo para dar suporte a um fluxo de dados específico de relatório em tempo de execução. As hierarquias são diferenciadas por um único registro que foi selecionado como uma raiz de mapeamento de modelo. Por exemplo, o modelo de dados da área de domínio de pagamento pode dar suporte aos seguintes mapeamentos:

-   Empresa -&gt; fornecedor -&gt; transações de pagamento de domínio de CR
-   Cliente -&gt; a empresa -&gt; transações de pagamento de domínio de CR

Observe que as entidades de negócios (por exemplo, transações de pagamento e de empresa) são projetadas uma vez. Mapeamentos diferentes, em seguida, reutilize-os. Um mapeamento de modelo tem os seguintes recursos:

-   Pode usar o dynamics 365 para diferentes tipos de dados de operações como fontes de dados para um modelo de dados. Por exemplo, ele pode usar tabelas, entidades de dados, métodos ou enumerações.
-   Ele suporta parâmetros de entrada do usuário que podem ser definidos como fontes para um modelo de dados quando alguns dados devem ser especificados em tempo de execução.
-   Suporte a transformação de dados dynamics 365 para as operações necessárias em grupos, em filtro, em, classificação e somar dados, e também em acrescentar-los com campos calculados lógicos criados por O Microsoft Excel- como fórmulas (para obter mais detalhes, consulte [designer de fórmulas eletrônico] no relatório (general-electronic-reporting-formula-designer.md)).

[![como Excel- o editor de fórmula (]. /media/pic-formula-1024x615.png)](. O componente do modelo de dados de /media/pic-formula.png A) é criado para cada domínio comercial a ser usado como um suprimento unificada dados do relatório os isolados subordinados físico de implementação do 365 para fontes de dados de operações, e representar conceitos e funcionalidades de domínio- específicos em um formulário que torne o design inicial e a manutenção adicional de um formato de relatórios mais eficientes.

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
-   ** CONCLUÍDO ** a versão pode ser convertida em COMPARTILHADO ** ** versão. Essa versão é publicado em LCS e usada em processos globais de relatório.
-   A versão **COMPARTILHADA** pode ser convertida em uma versão **DESCONTINUADA**. Essa versão pode ser excluída.

As versões com CONCLUÍDO ** ** ou COMPARTILHADO ** ** status estão disponíveis o outro para troca de dados. Um componente que tem esse status pode ter essas ações executadas neles:

-   Podem ser serializados em formato XML e exportados do 365 para operações como um arquivo no formato XML.
-   Podem ser reserialized de um arquivo XML e sers em dynamics 365 para operações como uma nova versão de um componente de ER.

#### <a name="component-date-effectivity"></a>Efetivação de data de componente

Versão do componente ER com efetivação de data. A data** Efetiva a partir de **pode ser definida para que um componente ER especifique a data em que esse componente entra em vigor para os processos de relatório. O dynamics 365 para a data da sessão de operações usadas para definir se um componente é válida para a entrega. Se mais de uma versão é válida para uma data específica, a última versão é usada para processos de relatório.

#### <a name="component-access"></a>Acesso ao componente

O acesso aos componentes no formato ER depende da definição de códigos de país/região ISO. Quando essa configuração está em branco para uma versão selecionada da definição de formato, um componente de um formato pode ser acessado de qualquer dynamics 365 para a empresa de operações em tempo de execução. Quando o contém essa configuração país ISO/códigos de região, um componente formatar está disponível do 365 para as empresas de operações com o endereço primário definido para um de país ISO de um componente de formato/códigos de região. Versões diferentes de um componente de formato de dados podem ter diferentes configurações de códigos de país/região ISO.

#### <a name="configuration"></a>Configuração

A configuração de ER é o wrapper de determinado componente ER: **Modelo de dados** ou **Formato**. Uma configuração pode incluir versões diferentes de determinado componente ER. Cada configuração é marcada como propriedade de um fornecedor de configuração específico. ** RASCUNHO ** a versão de um componente de uma configuração podem ser editadas quando o proprietário de configuração foi selecionado como um provedor ativo nas configurações de ER em dynamics 365 para as operações. Cada configuração de modelo contém um componente do **Modelo de dados**. Uma nova configuração de formato pode ser originada (derivada) de uma configuração de modelo de dados específico. A configuração de formato criada será apresentada na árvore de configuração como um filho da configuração do modelo de dados original. A configuração de formato criada contém um componente de **Formato **. O componente **Modelo de dados** da configuração original de modelo será inserido automaticamente no componente **Formato** da configuração de formato filho criada como uma fonte de dados padrão. Uma configuração de ER será compartilhado para dynamics 365 para empresas de operações.

#### <a name="provider"></a>Provedor

O provedor de ER é a identificação de uma parte que é usada para indicar o autor (proprietário) de cada configuração de ER. ER permite que você gerencie a lista de provedores de configuração. Formatar as configurações que serão liberadas para documentos eletrônicos como parte do 365 para operações a solução é marcada como A Microsoft não ** ** pela administradora de configuração.

#### <a name="repository"></a>Repositório

Um repositório armazena as configurações de RE. Os seguintes tipos de lojas de ER são suportados em: ** Recursos de operações e ** ** projeto de LCS **. ** Recursos de operações ** um repositório fornece acesso à lista de definições que serão liberadas como parte do 365 para a solução operações pela Microsoft como um provedor de configuração de ER. Essas configurações podem ser importados em dynamics atual 365 para operações como exemplo instância e usado para o relatório eletrônico. Elas também podem ser usadas para localizações/personalizações adicionais. Um repositório de **projeto do LCS** fornece acesso à lista de configurações de projeto do LCS (biblioteca de ativos do projeto do LCS) que foi selecionado na fase de registro do repositório. Permite O ER carregar configurações compartilhadas do atual 365 para a instância a um determinado ** projeto de operações de armazenamento. LCS ** Você também pode importar as configurações de um detalhe ** projeto de LCS ** armazenamento atual em dynamics 365 para a instância de operações. ** Projeto de LCS ** exigidos os armazenamentos podem ser registrados separadamente para cada fornecedor de configuração dinâmica atual 365 para a instância de operações. Cada repositório pode ser dedicado a um provedor de configuração específico.

## <a name="supported-scenarios"></a>Cenários com suporte
### <a name="building-a-data-model"></a>Criação de um modelo de dados

O ER fornece um designer de modelo que você pode usar para criar um modelo de dados para um domínio comercial específico. Todas as entidades comerciais específicas de domínio e relações entre elas são apresentadas em um modelo de dados como uma estrutura hierárquica. A ilustração a seguir mostra um exemplo desse tipo de modelo de dados (o pagamento dados do modelo de domínio). [exemplo![de um modelo de dados (]. /media/pic-data-model-1024x550.png)](. /media/pic-data-model.png) A se familiarizarem com os detalhes desse cenário, execute ** modelo de dados específico de domínio de Design de ER ** a guia da tarefa (parte ** 7.5.4.3 adquire/desenvolve os componentes de serviços/solução de 10677 (TI) ** de processo comercial.)

### <a name="translating-data-model-content"></a>Traduzindo o conteúdo do modelo de dados

O conteúdo do modelo de dados (rótulos e descrições) pode ser convertida em outros idiomas que o dynamics 365 de operações oferece suporte. Talvez você queira traduzir o conteúdo do modelo de dados pelos seguintes motivos:

-   No momento da criação, para tornar um conteúdo mais inteligível para criadores de formato que falam apenas outro idioma, e que usarão um modelo de dados para mapeamento de dados de componentes de formato
-   Em tempo de execução, para que o conteúdo mais amigáveis experimentando e avisos de ajudá-los para parâmetros de tempo de execução, e também informações configuradas de validação (avisos e erros), no idioma do dynamics atualmente feita logon 365 para o usuário de operações preferir

A ilustração a seguir mostra um exemplo de como modelo de dados de conteúdo pode ser traduzido do inglês para japonês. [conteúdo do modelo de dados do![em inglês (]. /media/pic-translate-en-1024x495.png)](. /media/pic-translate-en.png) [conteúdo do modelo de dados![traduzido o japonês (]. /media/pic-translate-ja-1024x495.png)](. /media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Configuração de mapeamentos do modelo de dados

O designer ER fornece um modelo de mapeamento deixe que os métodos de dados mapa de usuários que tenham criado o dynamics específica 365 de fontes de dados de operações. O exemplo desse mapeamento de modelo de dados é mostrado na imagem a seguir (o mapeamento de modelo **Transferência de Crédito SEPA** do modelo de dados de domínio de pagamento). [exemplo![de um mapeamento do modelo de dados (]. /media/pic-model-mapping-1024x551.png)](. /media/pic-model-mapping.png) A se familiarizarem com os detalhes desse cenário, execute o ER ** define mapeamento modelo e fontes de dados selecionadas ** e ** modelo de dados de ER mapa de fontes de dados selecionadas ** guias da tarefa (parte ** 7.5.4.3 adquire/desenvolve os componentes de serviços/solução de 10677 (TI) ** de processo comercial.)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Armazenamento do componente de modelo designado como uma configuração de modelo

O ER pode armazenar um modelo de dados criada com dados associados de mapeamentos como uma configuração do modelo atual 365 para a instância de operações. A ilustração a seguir mostra um exemplo desse tipo de configuração do modelo de dados (o pagamento dados do modelo de configuração). [exemplo![de configuração de um modelo de dados (]. /media/pic-model-configuration-1024x585.png)](. /media/pic-model-configuration.png) A se familiarizarem com os detalhes desse cenário, execute ** modelo de dados de ER mapa de fontes de dados selecionadas ** a guia da tarefa (parte ** 7.5.4.3 adquire/desenvolve os componentes de serviços/solução de 10677 (TI) ** de processo comercial.)

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Como criar um formato que usa um modelo de dados como base

O ER oferece suporte a um designer de formato para criar um formato de um documento eletrônico específico para o domínio comercial selecionado, escolhendo o componente modelo como base. O mesmo designer de formato de ER oferece a capacidade de mapear o formato criado para o mapeamento do modelo de dados do domínio selecionado como uma fonte de dados. A ilustração a seguir mostra um exemplo desse tipo de formato (a configuração de formato que oferece suporte a **BACS** formato de pagamento para o Brasil). [exemplo![de formato com um modelo de dados como base. (]/media/pic-format-1024x690.png)](. /media/pic-format.png) A se familiarizarem com os detalhes desse cenário, execute ** formato de domínio específico Design de ER ** a guia da tarefa (parte ** 7.5.4.3 adquire/desenvolve os componentes de serviços/solução de 10677 (TI) ** de processo comercial.)

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Criando uma configuração para gerar documentos eletrônicos em formato de planilha do OPENXML

Designer de formato ER pode ser usado para criar um determinado documento eletrônico em formato de planilha do OPENXML. A ilustração a seguir mostra um exemplo deste tipo de formatos (uma configuração de formato para gerar a planilha de OPENXML com detalhes de um diário de pagamento selecionado): [![(PIC-ER-FORMATO- Excel]. /media/pic-er-format-excel.jpg)](. /media/pic-er-format-excel.jpg) A se familiarizarem com os detalhes desse cenário, execute o ER ** criar uma configuração de relatórios no formato de OPENXML ** a guia da tarefa (parte ** 7.5.4.3 adquire/desenvolve os componentes de serviços/solução de 10677 (TI) ** de processo comercial.) Use indicado abaixo de arquivo excel como um modelo de criação formato de ER para concluir a etapa de um método de formato deste guia de tarefas: [Modelo de relatório de pagamento (SampleVendPaymWsReport.xlsx])(https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Armazenamento do componente do formato designado na configuração de formato

O ER um formato pode armazenar criado com os mapeamentos configurados de dados como uma configuração de formato do atual 365 para a instância de operações. A ilustração anterior mostra um exemplo desse tipo de configuração de formato (**BACS (Reino Unido)**, que é um filho da configuração **Modelo de pagamento **). Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar formato de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Configurando o dynamics 365 para as operações iniciem internamente para usar um formato criado

O dynamics 365 para operações pode ser configurada para começar para usar um formato criado para gerar relatórios eletrônicos. A referência à configuração de formato criado deve ser definida em configurações específicas de um domínio. Por exemplo, para iniciar usar uma configuração de formato de ER para pagamentos eletrônicos de fornecedor em A BACS de formato, o formato deverá ser referenciado em métodos de pagamento específicos, como mostra as ilustrações: 

[![Configuração de formato de A BACS (RU)](media/ger-bacs-uk-format-configuration.png) 

[![Referenciando formato do BACS (RU) em um método de pagamento](media/ger-bacs-uk-format-method.png) 

Execute a guia de tarefa **ER Usar formato para gerar documento eletrônico para pagamentos** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

## <a name="handling-er-components"></a>Manusear componentes ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Como publicar o componente de ER no LCS para oferecê-lo externamente (localização)

O proprietário de um componente criado é capaz de usar o ER para publicar a versão concluída de um componente de ER (modelo ou formato) para o LCS. Um repositório do tipo **Projeto de LCS **do provedor atual de configuração de ER é necessário para isso. Quando o status da versão concluída de um componente mudar de **CONCLUÍDO** para **COMPARTILHADO**, esta versão será publicada no LCS. Quando um componente for publicado no LCS, o proprietário desse componente se tornará um prestador do serviço para dar suporte a esse componente. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico legalmente necessário (por exemplo, de acordo com o cenário de localização), esse serviço assumirá para manter esse formato compatível com as alterações legislativas e emitir novas versões deles sempre que as novas exigências legislativas precisarem de suporte. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Carregamento ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importação do componente de ER do LCS para usá-lo internamente

Permite O ER importar componentes de ER do dynamics LCS atual 365 para a instância de operações. Um repositório do tipo **Projeto de LCS **é necessário para isso. Quando um componente de ER foi importado do dynamics LCS atual 365 para operações como nenhuma exemplo, o responsável de instância será um consumo de serviço que está proporcionado pelo proprietário (autor) de componentes importado. Por exemplo, se um componente formatar está criado para gerar um documento eletrônico específico do 365 para as operações em um formato país/região específico cenário (local), presume-se que o consumo de serviço poderá obter todas as atualizações que foram feitas nesse formato, para manter o legislativos compatível com os requisitos. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Importar ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Como criar um formato selecionando outro formato como base (personalização)

Permite ER de criar (derivado) um novo componente da versão atual de um componente (base) que foi importado de LCS. Por exemplo, um usuário deseja derivar um novo formato para implementar alguns requisitos especiais para um documento eletrônico (por exemplo, um campo adicional ou uma descrição extensa) para oferecer suporte a um cenário de personalização. Execute a guia de tarefa **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Atualização de um formato selecionando uma nova versão do formato base (rebase)

O ER permite adotar automaticamente alterações na última versão do componente base na versão de rascunho atual do componente derivado. Esse processo é conhecido como *troca de base*. Por exemplo, as novas alterações de regulamentação (apresentadas na última versão do componente do formato importado do LCS) podem ser automaticamente adotadas na própria versão personalizada desse formato do documento eletrônico. As alterações que não podem ser mescladas automaticamente são consideradas conflitos. Esses conflitos são apresentados para resolução manual na ferramenta de designer para o componente apropriado. Execute a guia de tarefa **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Lista de configurações de ER que são emitidos em dynamics 365 para a solução de operações
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


