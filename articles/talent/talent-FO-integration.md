---
title: FAQ sobre a integração do Dynamics 365 for Talent com o Dynamics 365 for Finance and Operations
description: Este tópico explica quais dados são sincronizados em uma de integração do Talent com o Finance and Operations.
author: andreabichsel
manager: AnnBe
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-12-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cb9e01316f4b154a3e9a73042eaf0492f016c46c
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742690"
---
# <a name="dynamics-365-for-talent-to-dynamics-365-for-finance-and-operations-integration-faq"></a>FAQ sobre a integração do Dynamics 365 for Talent com o Dynamics 365 for Finance and Operations

[!include [banner](includes/banner.md)]

Esse tópico responde perguntas comuns associadas a quais dados são sincronizados quando o Dynamics 365 for Talent é integrado ao Dynamics 365 for Finance and Operations.

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>Todos os dados são sincronizados ou apenas algumas entidades de dados?

Com o Core Human Resources (HR), um subconjunto de dados é sincronizado. Para uma lista das entidades, consulte [Integração do Dynamics 365 for Talent com o Dynamics 365 for Finance and Operations](talent-financeandoperations-integration.md).

Para o Attract e o Onboard, todos os dados são nativos do Common Data Service.

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>Posso criar um novo mapeamento sem usar os modelos?

Os modelos são o ponto de partida. Você pode criar seu próprio modelo, mas um modelo sempre é necessário para criar um projeto de integração. Para obter mais informações sobre o integrador de dados (DI), modelos e projetos, consulte [Integrar dados ao Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="can-i-map-financial-dimensions-to-transfer-between-talent-and-finance-and-operations"></a>Posso mapear dimensões financeiras para a transferência entre o Talent e o Finance and Operations?

No momento, as dimensões financeiras não estão no Common Data Service e, por isso, não fazem parte do modelo padrão. Essa entidade é planejada, mas atualmente não existe um cronograma de versões disponível.

Para dados que residem no Finance and Operations mas que não existem no Talent, vincule os dois sistemas usando **Configurar links** no Talent. Para obter mais informações sobre como configurar links entre o Talent e o Finance and Operations, consulte [Novidades ou alterações no Dynamics 365 for Talent Core HR (31 de outubro de 2018)](whats-new-talent-october-31.md).

![Mapear dimensões financeiras](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-and-operations-why"></a>Por vezes, quando importo funcionários, eles entram como trabalhadores inativos no Finance and Operations. Por quê?

Esse erro pode ocorrer caso os funcionários não tenham um registro de detalhe de emprego ativo no Talent. Para resolver isso, vá para **Gerenciamento de pessoal \> Funcionários \> Histórico de emprego \> Gerenciador de data** e verifique se há um registro ativo de detalhe de emprego.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>Se eu selecionar mapear somente um subconjunto de campos, as alterações feitas nos campos não mapeados dispararão uma sincronização?

A sincronização de dados segue uma agenda de execução. A integração selecionará um registro se qualquer campo no registro for alterado independentemente de pertencer ao mapeamento de integração.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>Como posso enviar apenas alterações de trabalhadores ativos e não os registros de trabalhadores demitidos?

Usando a "Consulta avançada", você pode filtrar e remodelar ao dados de origem antes de passá-los para o destino.

![Consulta avançada de trabalhadores ativos](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-and-operations-for-a-specific-entity"></a>Posso especificar quais campos enviar ao Finance and Operations de uma entidade específica?

Os campos podem ser adicionados ou removidos da tarefa de integração. Nem todos os campos de dados que existem na entidade do Common Data Service serão preenchidos do Core HR.
Dados adicionais podem ser preenchidos por PowerApps.

![Adicionar ou remover campos a e de uma tarefa de integração](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-talent-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>Configurei a integração como um trabalho em lotes, mas o Talent perdeu a conexão com o sistema de destino. Como posso enviar o mesmo conjunto de alterações para o sistema de destino?

Nenhuma configuração especial é necessária para tratamento de exceções. O Integrador de dados automaticamente captura e relata os erros que ocorrem na origem e no destino e permite tentativas manuais. Entretanto, não permite a correção manual de dados. Se as atualizações de dados forem necessárias, deverão ocorrer na origem ou no destino.

## <a name="can-i-set-up-bi-directional-integration"></a>Posso configurar uma integração bidirecional?

Não, a integração atualmente só tem uma direção (Talent para Finance and Operations). Contudo, há um modelo padrão disponível para enviar dados do Talent para o Finance and Operations.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>Posso permitir a exclusão de registro como parte da minha integração?

Não, o Integrador de dados não capturará registros excluídos para transferências de dados. Somente a criação e a as atualizações de dados (UPSERT) estão incluídas no momento.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>Posso executar novamente a execução com erro? Em caso afirmativo, será enviado um arquivo completo ou somente as alterações?

A primeira execução do Integrador de dados é sempre uma execução completa. As execuções subsequentes são baseadas no controle de alterações. Quando uma execução com erro é executada, ela extrai os registros do escopo da execução e envia as alterações mais recentes do Common Data Service.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>Quando salvo o projeto, aparece o erro: “Projeto tem erros de mapeamento.” O que devo fazer?

Verifique a instalação de suas chaves de integração, faça as alterações necessárias à instalação, depois, atualize as entidades no projeto.

Quando o modelo padrão é usado, as chaves de integração são importadas automaticamente. Esse problema pode ocorrer quando novas tarefas são adicionadas ao modelo existente.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>Se tenho um número N de entidades legais onde os trabalhadores têm empregos, preciso criar um mapeamento para cada um deles?

Sim, para cada entidade legal no Finance and Operations, você precisará de um projeto de integração separado na integração dos dados.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Preciso transferir dados que não são parte do modelo padrão fornecido pela Microsoft. Posso fazer isso?

Sim, campos podem ser adicionados ou removidos do modelo existente. O modelo pode ser modificado para incluir dados adicionais de outras entidades do Common Data Service. A entidade deve estar no Common Data Service para ser incluída no modelo. 

## <a name="i-just-created-new-finance-and-operations-and-talent-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>Acabo de criar novos ambientes do Finance and Operations e do Talent, e aparece o erro “O valor dos dados viola as restrições de integridade.” Por quê?

Os motivos para esse erro podem incluir:

- A transferência de dados resultou na extração de registros duplicados na origem (Common Data Service).

- A transferência de dados tem valores nulos para campos necessários no Finance and Operations. Verifique os dados que estão no Common Data Service e que atendam aos requisitos do Finance and Operations.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>Se houver erros de execução e a ID do funcionário não for sincronizada, como poderei localizar o trabalho do histórico que tem o registro do funcionário com falha?

O Integrador de dados criará vários projetos no Finance and Operations. A relação entre a tarefa do Integrador de dados e o projeto do Finance and Operations é de um para um.

Rastreie o tempo do histórico da execução do Integrador de dados e procure o índice -1 projeto no Finance and Operations. Se o número de tarefas for 9 no Integrador de dados, o índice no Finance and Operations será 8.

1. Capture o índice da tarefa do Integrador de dados (neste exemplo é o "9").

![Capture o índice da tarefa do Integrador de dados](media/CaptureTaskIndex.png)

2. Rastreie o tempo de execução do projeto.

![Rastreie o tempo de execução do projeto](media/CaptureTimeOfExecution.png)

3. No Finance and Operations, identifique o índice - 1. Neste exemplo, o projeto com sufixo “8"e tempo de execução do índice "0" projeto corresponde ao tempo de execução na Etapa 2.

![Identificar o item](media/IdentifyIndex.png)

## <a name="after-integrating-talent-and-finance-and-operations-i-dont-see-my-talent-data-in-finance-and-operations-what-do-i-do"></a>Depois que integrei o Talent ao Finance and Operations, não vejo os dados do Talent no Finance and Operations. O que devo fazer?

A integração ao Finance and Operations é um processo de duas etapas. Primeiro, verifique se os dados do Talent estão atualizados e disponíveis no Common Data Service. Esta é uma sincronização praticamente em tempo real e pode ser verificada no PowerApps olhando os dados nas entidades de dados.

![Dados no Common Data Service](media/DataInCDS.png)

Se os dados não estão aparecendo conforme esperado no Common Data Service, verifique se a entidade é compatível com a integração. Para incluir dados adicionais no Common Data Service, a Microsoft deverá fazer uma alteração.

Se a entidade é compatível e os dados estão disponíveis no Common Data Service, verifique se o mapeamento está correto no integrador de dados. Se o mapeamento do integrador parecer correto, verifique se os trabalhos de gerenciamento de dados foram executados com êxito. Podem ocorrer erros durante a execução de trabalhos em lotes. Para obter mais informações sobre o Gerenciamento de dados, consulte [Gerenciamento de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json).

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-and-operations-what-should-i-do"></a>Os endereços de meus funcionários ficaram incorretos depois que importei esses dados para o Finance and Operations. O que devo fazer?

A sequência numérica para **ID do local** usa o mesmo em padrão tanto no Talent como no Finance and Operations. A sequência numérica deve ser exclusiva nos dois lados para que não haja colisão de endereços ao integrar os dados do Common Data Service com o Finance and Operations.

Durante a implementação do Talent, verifique se as sequências numéricas não são as mesmas no Talent e no Finance and Operations. Garanta que todas as sequências numéricas não sejam idênticas onde os dados podem ser mantidos em ambos os sistemas.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>Ao criar meu conjunto de conexão, não consigo ver a conexão na lista suspensa Conexão. O que devo fazer?

Certifique-se de, ao criar suas conexões, escolher o Dynamics 365 for Finance and Operations (atualmente em exibição) e o Common Data Service.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>Ao sincronizar empregos, recebo erros “CompanyInfo_FK não existe “ou “O valor '12/31/2154 11:59:59 pm' no campo 'Data final do emprego' não foi encontrado na tabela 'Emprego' relacionada'". O que devo fazer?

Garanta que esteja mapeando para as entidades legais corretas. A sincronização da entidade legal não faz parte do modelo padrão, por isso espera-se que cada entidade legal presente no Talent e no Common Data Service também esteja presente no Finance and Operations.
Além disso, verifique se está selecionando as entidades legais corretas para o Conjunto de conexão associado.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-and-operations-appears-to-be-empty-what-should-i-do"></a>Depois de configurar meu projeto, o mapeamento de campos para o Finance and Operations parece estar vazio. O que devo fazer?

Atualize as entidades de dados no Finance and Operations em **Gerenciamento de dados \> Parâmetros de estrutura \> Configurações da entidade \> Atualizar a lista de entidades.** Isso deve demorar uns minutos, depois você deverá ver os mapeamentos. O problema ocorre quando novos projetos são criados.

![Mapeamento de campos ausente](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>Recursos adicionais

- Integrador de dados (DI): 

  - [Integrar dados ao Common Data Service](https://docs.microsoft.com/powerapps/administrator/data-integrator)

  - [Gerenciamento e soluções de problemas de erro do Integrador de dados](https://docs.microsoft.com/powerapps/administrator/data-integrator-error-management)

  - [Respondendo às solicitações de DSR para logs gerados pelo sistemas no PowerApps, Microsoft Flow e Common Data Service](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- Gerenciamento de dados:

  - [Gerenciamento de dados](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json)
