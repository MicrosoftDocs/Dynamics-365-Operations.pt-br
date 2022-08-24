---
title: Visão geral de Relatório eletrônico (ER)
description: Este artigo oferece uma visão geral da ferramenta ER. Ele descreve os principais conceitos, os cenários com suporte e os formatos que fazem parte da solução.
author: kfend
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941,  ""intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: e94846dd565abb6de2c1f07532d285e28307e9a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269681"
---
# <a name="electronic-reporting-er-overview"></a>Visão geral de Relatório eletrônico (ER)

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral da ferramenta ER (Relatório Eletrônico). Ele inclui informações sobre os principais conceitos, os cenários com suporte do ER e uma lista de formatos projetados e liberados como parte da solução ER.

O ER é uma ferramenta configurável que ajuda a criar e a manter pagamentos e relatórios eletrônicos regulatórios. Ele se baseia nos três conceitos a seguir:

- Configuração em vez de codificação:

    - A configuração pode ser feita por um usuário comercial e não exige um desenvolvedor.
    - O modelo de dados é definido em termos comerciais.
    - Os editores visuais são usados para criar todos os componentes da configuração de ER.
    - O idioma usado para a transformação de dados é semelhante ao idioma usado no Microsoft Excel.

- Uma configuração para várias versões do Dynamics 365 Finance:

    - Gerencie um modelo de dados específico de domínio definido em termos comerciais.
    - Isole os detalhes da versão do aplicativo em mapeamentos de modelos de dados dependentes de versão.
    - Manter uma configuração de formato para vários lançamentos da versão atual, com base no modelo de dados.

- Atualização fácil ou automática:

    - O controle de versão de configurações de ER é compatível.
    - A biblioteca de ativos do Microsoft Dynamics Lifecycle Services (LCS) pode ser usada como um repositório para configurações de ER, para a troca de versão.
    - As localizações baseadas nas configurações originais de ER podem ser introduzidas como versões filhas.
    - Uma árvore de configuração de ER é fornecida como uma ferramenta que ajuda a controlar dependências para versões.
    - As diferenças na localização ou na configuração delta são registradas para habilitar a atualização automática para uma nova versão da configuração original de ER.
    - É fácil resolver manualmente conflitos descobertos durante a atualização automática de versões de localização.

O ER permite definir estruturas em formato eletrônico e descrever como as estruturas devem ser preenchidas usando dados e algoritmos. Você pode usar um idioma de fórmula semelhante ao da linguagem do Excel para transformação de dados. Para tornar o mapeamento de banco de dados para formato mais gerenciável, reutilizável e independente das alterações de formato, um conceito de modelo de dados intermediário é introduzido. Esse conceito permite que os detalhes da implementação sejam ocultados do mapeamento de formato e permite que um único modelo de dados seja reutilizado para vários mapeamentos de formato.

Você pode usar ER para configurar formatos de documentos eletrônicos de entrada e de saída de acordo com os requisitos legais de vários países e regiões. ER permite que você gerencie esses formatos durante seu ciclo de vida. Por exemplo, você pode adotar novos requisitos normativos e gerar documentos de negócios no formato exigido para trocar informações, eletronicamente, com outras pessoas, bancos e órgãos do governo.

O mecanismo de ER se destina a usuários de negócios e não aos desenvolvedores. Como você configura formatos, em vez de códigos, os processos de criação e ajuste de formatos para documentos eletrônicos são mais rápidos e mais fáceis.

O ER é compatível com os formatos de planilha TEXT, XML, JSON, PDF, Microsoft Word, Microsoft Excel e OPENXML.

## <a name="capabilities"></a>Capacidades

O mecanismo ER tem os seguintes recursos:

- Ele representa uma única ferramenta compartilhada para relatórios eletrônicos em domínios diferentes e substitui mais de 20 mecanismos diferentes que geram algum tipo de relatório eletrônico para o aplicativo de finanças e operações.
- Isso torna o formato do relatório isolado da implementação atual. Em outras palavras, o formato é aplicável a várias versões.
- Ele suporta a criação de um formato personalizado que é baseado no formato original. Ele também inclui recursos para atualizar automaticamente o formato personalizado quando o formato original é alterado devido aos requisitos de localização/personalização.
- Ele se torna o padrão principal de suporte de requisitos de localização no relatório eletrônico para a Microsoft e parceiros da Microsoft.
- Ele oferece suporte à capacidade de distribuir formatos a parceiros e clientes através do Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Conceitos principais

### <a name="main-data-flow"></a>Fluxo de dados principal

[![Fluxo de dados principal de ER.](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="component"></a>Componente

O ER oferece suporte aos seguintes tipos de componentes:

- Modelo de dados
- Mapeamento de modelo
- Formatar
- Metadados

Para obter mais informações, consulte [Componentes do Relatório eletrônico](er-overview-components.md).

### <a name="configuration"></a><a name="Configuration"></a>Configuração

Uma configuração ER é o wrapper de um componente ER específico. Esse componente pode ser um componente de modelo de dados ou um componente de formato. Uma configuração pode incluir versões diferentes de um componente ER. Cada configuração é marcada como propriedade de um provedor de configuração específico. A versão **Rascunho** de um componente de uma configuração está disponível para edição quando o proprietário da configuração foi selecionado como provedor ativo nas configurações ER do aplicativo.

Cada configuração de modelo contém um componente do modelo de dados. Uma nova configuração de formato pode ser derivada de uma configuração de modelo de dados específicos. Na árvore de configuração, a configuração de formato criada aparece como um filho da configuração do modelo de dados original.

A configuração de formato criada contém um componente de formato. O componente modelo de dados da configuração original de modelo é inserido automaticamente no componente formato da configuração de formato filho criada como uma fonte de dados padrão.

Uma configuração de ER é compartilhada para empresas do aplicativo.

### <a name="provider"></a><a name="Provider"></a>Provedor

O provedor de ER é a identificação de uma parte que é usada para indicar o autor (proprietário) de cada configuração de ER. ER permite que você gerencie a lista de provedores de configuração. As configurações de formato que são liberadas para documentos eletrônicos como parte da solução de finanças e operações são marcadas como pertencentes ao provedor de configuração da **Microsoft**.

Para aprender a registrar um novo provedor de ER, execute a guia de tarefas **ER Criar um provedor de configuração e marcá-lo como ativo** (parte do processo comercial **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="repository"></a><a name="Repository"></a>Repositório

Um repositório armazena as configurações de RE. Os tipos de repositórios de ER a seguir têm suporte no momento: 

- Biblioteca compartilhada do LCS
- Projeto do LCS
- Sistema de arquivos
- RCS
- Recursos de operações
- Repositório global

Um repositório da **biblioteca compartilhada do LCS** fornece acesso à lista de configurações na biblioteca de ativos compartilhados no Lifecycle Services (LCS). Esse tipo repositório de ER só pode ser registrado para o provedor Microsoft. Por meio da biblioteca de ativos compartilhados do LCS, você pode importar as versões mais recentes das configurações de ER para a instância atual.

Um repositório de **Projeto LCS** fornece acesso à lista de configurações de um projeto LCS específico (biblioteca de ativos do projeto LCS) selecionado quando o repositório foi registrado. O ER permite carregar configurações compartilhadas da instância atual para um repositório específico do **Projeto do LCS**. Você também pode importar configurações de um repositório do **Projeto LCS** para a instância atual de seus aplicativos de finanças e operações.

Um repositório do **Sistema de arquivos** fornece acesso à lista de configurações localizadas como arquivos xml na pasta específica do sistema de arquivos local do computador onde o serviço AOS está hospedado. A pasta desejada é selecionada no estágio de registro do repositório. Você também pode importar configurações de um repositório do **Sistema de arquivos** na instância atual. 

Observe que esse tipo de repositório pode ser acessado nos seguintes ambientes:

- Ambientes hospedados na nuvem implantados para fins de desenvolvimento (contendo modelos de teste de pacotes integrados)
- Ambientes implantados localmente (on-premises)

Para obter mais informações, consulte [Importar configurações do ER (Relatório eletrônico)](./electronic-reporting-import-ger-configurations.md).

Um repositório **RCS** fornece acesso à lista de configurações de uma instância específica de [Serviço de configuração (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) que foi selecionada na fase de registro do repositório. O ER permite que você importe configurações concluídas ou compartilhadas da instância selecionada do RCS para a instância atual para que você possa usá-las em relatórios eletrônicos.

Para obter mais informações, consulte [Importar configurações do ER (relatório eletrônico) de RCS](./rcs-download-configurations.md).

Um repositório **Repositório global** permite acessar a lista de configurações no repositório global no [Serviço de configuração](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Esse tipo repositório de ER só pode ser registrado para o provedor Microsoft. No repositório global, você pode importar as versões mais recentes de configurações de ER para a instância atual.

Para obter mais informações, consulte [Importar configurações do ER (relatório eletrônico) do repositório global do serviço de configuração](./er-download-configurations-global-repo.md).

Um repositório de **Recursos de operações** dá acesso à lista de configurações que a Microsoft, como provedora de configuração de ER, libera inicialmente como parte da solução do aplicativo. Essas configurações podem ser importadas para a instância atual e usadas para relatórios eletrônicos ou para a reprodução de exemplos de guias da tarefa. Elas também podem ser usadas para localizações e personalizações adicionais. Observe que as versões mais recentes fornecidas pelas configurações de ER da Microsoft devem ser importadas da biblioteca de ativos compartilhados do LCS usando o repositório de ER correspondente.

Os repositórios de **Projeto LCS**, **Sistema de arquivo** e **Serviços de configuração regulatória (RCS)** podem ser registrados individualmente para cada provedor de configuração da instância atual. Cada repositório pode ser dedicado a um provedor de configuração específico.

## <a name="supported-scenarios"></a>Cenários com suporte

### <a name="building-a-data-model"></a>Criação de um modelo de dados

O ER fornece um designer de modelo que você pode usar para criar um modelo de dados para um domínio comercial específico. Todas as entidades comerciais específicas de domínio e relações entre elas são apresentadas em um modelo de dados como uma estrutura hierárquica. 

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar modelo de dados de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="translating-data-model-content"></a>Traduzindo o conteúdo do modelo de dados

O conteúdo do modelo de dados (rótulos e descrições) pode ser traduzido para outros idiomas aos quais o aplicativo oferece suporte. Talvez você queira traduzir o conteúdo do modelo de dados pelos seguintes motivos:

- No momento da criação, para tornar um conteúdo mais inteligível para criadores de formato que falam outros idiomas, e que usarão o modelo de dados para mapeamento de dados de componentes de formato.
- No tempo execução, para tornar o conteúdo mais amigável, apresentando avisos e ajuda de parâmetros em tempo de execução, bem como mensagens de validação configuradas (erros e avisos), no idioma de preferência do usuário conectado.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configurando mapeamentos de modelo de dados de documentos de saída

O ER fornece um designer de mapeamento do modelo que permite que os usuários mapeiem modelos de dados que eles criaram da fontes de dados específica do aplicativo. Com base no mapeamento, os dados serão importados, em tempo de execução, das fontes de dados selecionadas para o modelo de dados. O modelo de dados é usado como uma fonte abstrata de dados de formatos ER que gera documentos eletrônicos de saída. 

Para familiarizar-se com este cenário em detalhes, execute os guias de tarefa **ER Definir o mapeamento do modelo e selecionar fontes de dados** e **ER Mapear modelo de dados para fontes de dados selecionadas** (parte do processo empresarial **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configurando mapeamentos de modelo de dados de documentos de entrada

ER fornece um designer de mapeamento do modelo que permite que os usuários mapeiem modelos de dados que eles criaram para destinos específicos. Por exemplo, os modelos de dados podem ser mapeados para os componentes de dados atualizáveis (tabelas, entidades de dados e exibições). Com base no mapeamento, os dados serão atualizados em tempo de execução usando os dados do modelo de dados. Como armazenamento abstrato do formato ER, o modelo de dados é preenchido com dados importados de um documento eletrônico de entrada. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Armazenamento do componente de modelo designado como uma configuração de modelo

O ER pode armazenar um modelo de dados designado com os mapeamentos de dados configurados como uma configuração de modelo da instância atual. A ilustração a seguir mostra um exemplo desse tipo de configuração do modelo de dados (o pagamento dados do modelo de configuração).

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Mapear modelo de dados para fontes de dados selecionadas** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Como criar um formato que usa um modelo de dados como base

O ER oferece suporte a um designer de formato que você pode usar para criar o formato de um documento eletrônico para o domínio comercial selecionado, escolhendo o componente modelo como base. O mesmo designer de formato de ER oferece a capacidade de mapear o formato criado para o mapeamento do modelo de dados do domínio selecionado como uma fonte de dados. 

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar formato de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Criando uma configuração para gerar documentos eletrônicos em formato de planilha do OPENXML

O designer de formato ER pode ser usado para criar um documento eletrônico em formato de planilha do OPENXML. 

Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Criar uma configuração ER para gerar relatórios no formato OPENXML** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**). Como parte da etapa de guia de tarefas para importar um modelo, use o arquivo de Excel [Modelo de relatório de pagamento (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) como modelo.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Criando uma configuração para gerar documentos eletrônicos em formato de documento do Word

O designer de formato ER pode ser usado para criar um documento eletrônico em formato de documento do Word. A ilustração a seguir mostra um exemplo desse tipo de formato. Observe que esse formato reutiliza a configuração ER existente que foi originalmente criada para gerar a saída de relatório no formato OPENXML.

Para se familiarizar com os detalhes deste cenário, reproduza a guia de tarefas Criar uma configuração ER para gerar relatórios no formato Microsoft WORD (parte do processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)). Como parte da etapa de guia de tarefas para importar um modelo, use os seguintes arquivos de Word como modelos para o formato ER:

- [Modelo de relatório de pagamento (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Modelo limitado de relatório de pagamento (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Criar uma configuração para importar dados de documentos eletrônicos de entrada

O designer de formato ER pode ser usado para descrever um documento eletrônico planejado para importar dados em XML ou o formato de texto. O formato criado é usado para analisar um documento de entrada. O designer de mapeamento de formato ER pode ser usado para definir a associação dos elementos do formato criado com o modelo de dados. 

Para se familiarizar com os detalhes deste cenário, reproduza a guia de tarefas Criar configurações ER necessárias para importar os dados de um arquivo externo (parte do processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)). Usar os seguintes arquivos para reproduzir esta guia:

- [Configuração de modelo de dados de ER (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [Configuração de formato ER (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Exemplo de documento de entrada no formato XML (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Exemplo de pasta de trabalho para gerenciar dados do documento de entrada (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Armazenamento do componente do formato designado na configuração de formato

O ER pode armazenar um formato designado com os mapeamentos de dados configurados como uma configuração de formato da instância atual. A ilustração anterior mostra um exemplo desse tipo de configuração de formato (**BACS (Reino Unido)**, que é um filho da configuração **Modelo de pagamento**). Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **ER Projetar formato de domínio específico** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Configuração do Finance para começar a usar o formato criado internamente

O aplicativo pode ser configurado para começar a usar o formato criado para a geração de relatórios eletrônicos. A referência à configuração de formato criado deve ser definida em configurações específicas de um domínio. Por exemplo, para começar a usar uma configuração de formato de ER para pagamentos de fornecedores eletrônicos no formato BACS, a configuração de formato deve ser referenciada em métodos específicos de pagamento.

Execute a guia de tarefa **ER Usar formato para gerar documento eletrônico para pagamentos** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

## <a name="handling-er-components"></a>Manusear componentes ER

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Como publicar o componente de ER no LCS para oferecê-lo externamente (localização)

O proprietário de um componente criado é capaz de usar o ER para publicar a versão concluída de um componente de ER (modelo ou formato) para o LCS. Um repositório do tipo **Projeto de LCS** do provedor atual de configuração ER é necessário para isso. Quando o status da versão concluída de um componente mudar de **CONCLUÍDO** para **COMPARTILHADO**, esta versão será publicada no LCS. Quando um componente for publicado no LCS, o proprietário desse componente se tornará um prestador do serviço para dar suporte a esse componente. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico legalmente necessário (por exemplo, de acordo com o cenário de localização), esse serviço assumirá para manter esse formato compatível com as alterações legislativas e emitir novas versões deles sempre que as novas exigências legislativas precisarem de suporte. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Carregamento ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importação do componente de ER do LCS para usá-lo internamente

O ER permite importar componentes ER de LCS para a instância atual. Um repositório do tipo **Projeto de LCS** é necessário para isso. Quando um componente de ER for importado do LCS para a instância atual, o proprietário dessa instância se tornará um consumidor do serviço que é fornecido pelo proprietário (autor) de um componente importado. Por exemplo, se esse componente de formato for designado para gerar um documento eletrônico específico por meio do aplicativo em um formato específico de certo país/região (cenário de localização), supõem-se que o consumo deste serviço terá a capacidade de obter as atualizações desse formato para mantê-la compatível com as exigências legislativas. Para se familiarizar com os detalhes deste cenário, rode o guia de tarefa **Importar ER de uma configuração no Lifecycle Services** (parte do processo de negócio **7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Como criar um formato selecionando outro formato como base (personalização)

Permite ER de criar (derivado) um novo componente da versão atual de um componente (base) que foi importado de LCS. Por exemplo, um usuário deseja derivar um novo formato para implementar alguns requisitos especiais para um documento eletrônico (por exemplo, um campo adicional ou uma descrição extensa) para oferecer suporte a um cenário de personalização. Execute a guia de tarefa **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)**) para você familiarizar-se com este cenário em detalhes.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Atualização de um formato selecionando uma nova versão do formato base (rebase)

O ER permite adotar automaticamente alterações na última versão do componente base na versão de rascunho atual do componente derivado. Esse processo é conhecido como *troca de base*. Por exemplo, as novas alterações de regulamentação (apresentadas na última versão do componente do formato importado do LCS) podem ser automaticamente adotadas na própria versão personalizada desse formato do documento eletrônico. As alterações que não podem ser mescladas automaticamente são consideradas conflitos. Esses conflitos são apresentados para resolução manual na ferramenta de designer para o componente apropriado. Reproduza o guia de tarefas **ER Atualizar o formato adotando uma nova versão base dele** (parte do **processo comercial 7.5.5.3 Adquirir/Desenvolver componente de solução/serviço de TI alterado (10683)**) para se familiarizar com este cenário em detalhes.

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Lista de configurações de ER que foram lançadas no Finance

A lista de configurações de er para finanças é constantemente atualizada. Abra o [repositório global](er-download-configurations-global-repo.md) para revisar a lista de configurações de ER que têm suporte no momento. Na guia rápida **Detalhes de descontinuação**, você pode analisar as informações sobre as configurações que foram descontinuadas ou que não são mais mantidas. 

![Conteúdo do repositório global na página Repositório de configuração.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Recursos adicionais

- [Componentes de Relatório eletrônico](er-overview-components.md)
- [Criar configurações de Relatório eletrônico (ER)](electronic-reporting-configuration.md)
- [Gerenciar o ciclo de vida da configuração de relatório eletrônico (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

