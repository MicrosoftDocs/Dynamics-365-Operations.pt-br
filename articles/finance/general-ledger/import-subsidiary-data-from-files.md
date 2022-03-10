---
title: Importar dados da subsidiária de arquivos
description: Este tópico explica como preparar dados de sistemas externos para que possam ser importados para o Microsoft Dynamics 365 Finance.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 4be1e748724331c4e2089da8a08a9ac7e5cf88a2ac6d3d89b37b9fcd4480f516
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727291"
---
# <a name="import-subsidiary-data-from-files"></a>Importar dados da subsidiária de arquivos

[!include [banner](../includes/banner.md)]

Este tópico explica como preparar dados de sistemas externos para que possam ser importados para o Microsoft Dynamics 365 Finance. Use a página **Consolidar com importação** (**Consolidações \> Consolidar com importação**) para preparar a transferência de dados da subsidiária dos sistemas externos.

1. Crie uma entidade legal subsidiária para a consolidação. Para obter informações sobre como criar entidades legais, consulte [Criar uma entidade legal](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Para obter mais informações, consulte [Preparar uma entidade legal para uso no processo de consolidação](prepare-company-for-consolidation.md) e [Configurar uma entidade legal subsidiária para consolidação](set-up-subsidiary-company-for-consolidation.md).

2. Prepare um arquivo que conterá os dados importados. Para obter mais informações sobre o processo de importação, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
3. Exporte os dados para um arquivo seguindo as etapas no procedimento "Processo de importação/exportação de dados" em [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md). Você pode usar esse procedimento para consolidar dados de outra instância do Dynamics 365 Finance ou do Dynamics 365 Business Central. Se você estiver importando dados de sistemas externos, os dados deverão estar no formato descrito em [Exportar dados da subsidiária para arquivos](export-subsidiary-data-to-file.md).
4. Acesse **Consolidações \> Consolidar com importação**. Na página **Consolidar com importação**, na guia **Critérios**, especifique os detalhes do relatório e/ou da importação definindo os campos a seguir.

    | Campo                                 | Valor para o relatório | Valor para a importação |
    |---------------------------------------|----------------------|----------------------|
    | Descrição                           | Não Aplicável | Insira uma descrição para identificar a importação. |
    | Conta principal                          | Defina o intervalo de contas que o relatório deve incluir. Se você não definir um intervalo, todas as contas serão incluídas. | Defina o intervalo de contas que a importação deve incluir. Se você não definir um intervalo, todas as contas serão incluídas. |
    | Período de consolidação                  | Defina o intervalo de datas a ser consolidado. | Defina o intervalo de datas a ser consolidado. |
    | Incluir valores reais                | Defina esta opção como **Sim** para incluir dados reais. | Defina esta opção como **Sim** para incluir dados reais. |
    | Incluir valores de orçamento                | Defina esta opção como **Sim** para incluir valores de orçamento em consolidações. | Defina esta opção como **Sim** para incluir valores de orçamento em consolidações. |
    | Recriar saldos durante a consolidação | Defina esta opção como **Sim** se o processo de recriação precisar limpar completamente o saldo e os novos registros e recrie o saldo do início do tempo. | Defina esta opção como **Sim** se o processo de recriação precisar limpar completamente o saldo e os novos registros e recrie o saldo do início do tempo. |
    | Modelos de orçamento                         | Não Aplicável | Se você optou por importar valores de orçamento, insira os modelos de orçamento a serem consolidados. |
    | Tipo de taxa de orçamento                      | Não Aplicável | Insira o tipo de taxa de câmbio de orçamento. |

6. Se você tiver moedas contábeis diferentes, use os campos na guia **Conversão de moeda** para configurar a conversão feita durante a consolidação.

    | Campo                      | Descrição |
    |----------------------------|-------------|
    | Entidade legal de origem        | Selecione a entidade legal da qual você está importando. |
    | Moeda contábil da origem | A moeda padrão é a moeda associada à entidade legal de origem selecionada no campo **Entidade legal de origem**. |
    | Da conta e Para conta       | Defina o intervalo de contas a ser importado da entidade legal de origem. |
    | Tipo de taxa de câmbio         | Selecione o tipo de taxa de câmbio. Os tipos de taxa de câmbio são atribuídos quando você cria uma conta principal. Para saber mais, consulte [Criar uma conta principal](tasks/create-main-account.md). |
    | Aplicar taxa de câmbio de   | Insira uma data para aplicar a taxa de câmbio efetiva nessa data. Como alternativa, insira o valor que deve ser usado como a taxa de câmbio. |
    | Taxa de câmbio              | O valor padrão depende do tipo de taxa de câmbio que você selecionou no campo **Tipo de taxa de câmbio**. Se você tiver inserido uma taxa de câmbio definida pelo usuário, poderá definir uma taxa. |

7. Defina a opção **Executar em segundo plano** como **Sim** para permitir que o processo de importação seja executado em segundo plano.
8. Defina a opção **Processamento em lotes** como **Sim** para executar a consolidação como um trabalho em lotes em uma hora específica. Para executar a consolidação imediatamente, selecione **OK**. 

As transações e os saldos especificados para consolidação nas subsidiárias são adicionados às contas apropriadas na entidade legal consolidada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]