---
title: Exportar dados da subsidiária para arquivos
description: Este tópico explica como preparar a exportação de dados do Microsoft Dynamics 365 Finance e, depois, importá-los para uma entidade legal consolidada.
author: jinniew
manager: AnnBe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 33c17cc2c1dcaa57244bf0bfaa661b11b221e2f6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205490"
---
# <a name="export-subsidiary-data-to-files"></a>Exportar dados da subsidiária para arquivos

[!include [banner](../includes/banner.md)]

Use a página **Exportar** (**Administração do sistema \> Espaços de trabalho \> Importação/Exportação**) para preparar a exportação de dados da subsidiária para arquivos que podem ser importados em uma entidade legal consolidada. Para obter mais informações sobre os processos de importação e exportação, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

1. Crie uma entidade legal para o processo de consolidação. Para obter informações sobre como criar entidades legais, consulte [Criar uma entidade legal](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md). Para obter mais informações, consulte [Preparar uma entidade legal para uso no processo de consolidação](prepare-company-for-consolidation.md) e [Configurar uma entidade legal subsidiária para consolidação](set-up-subsidiary-company-for-consolidation.md). 

2. Acesse **Consolidações \> Exportar saldos da empresa**. Na página **Exportar saldos da empresa**, na guia **Critérios**, especifique os detalhes da consolidação definindo os campos a seguir.

    | Campo                             | Descrição |
    |-----------------------------------|-------|
    | Conta principal                      | Especifique as contas a serem consolidadas. Para incluir todas as contas, deixe este campo em branco. |
    | Usar conta de consolidação         | Se você especificou contas de consolidação, defina esta opção como **Sim**. |
    | Selecionar conta de consolidação de | Selecione **Conta principal** ou **Grupo de contas de consolidação**. |
    | Grupo de contas de consolidação       | Selecione um grupo de contas de consolidação para a conta de consolidação selecionada. |
    | Período de consolidação              | Especifique a datas "de" e "até" para a consolidação. |
    | Incluir valores reais            | Defina esta opção como **Sim** para incluir valores reais. |
    | Incluir valores de orçamento            | Defina esta opção como **Sim** para incluir valores de orçamento em consolidações. |
    | Modelos de orçamento                     | Especifique o modelo de orçamento a ser incluído. |

3. Na guia **Dimensões financeiras**, especifique os detalhes da consolidação:

    - Especifique as informações de dimensão financeira que devem ser transferidas das transações nas contas de subsidiárias para as transações na entidade legal consolidada.
    - Selecione dimensões financeiras na lista.
    - Identifique a especificação correta para cada dimensão financeira consolidada. As opções disponíveis incluem **Dimensão**, **Dimensão do grupo**, **Contas da empresa** e **Conta**.

        > [!NOTE]
        > A opção **Dimensão de grupo** permite definir o valor de dimensão usado pelo grupo de empresas que está sendo consolidado.

    - Especifique a ordem de segmento para consolidação.

4. Na guia **Entidades legais**, siga estas etapas para especificar a entidade legal que você está exportando:

    1. Selecione **Novo**.
    2. No campo **Entidade legal de origem**, insira a entidade legal.

        Se os mesmos critérios se aplicarem a várias subsidiárias no mesmo banco de dados, você poderá transferir dados dessas subsidiárias para arquivos de exportação separados em uma única operação:

        1. Crie uma linha para cada entidade legal subsidiária em que contas devam ser exportadas para arquivos. Posteriormente, esses arquivos serão importados para a entidade legal consolidada.
        2. Para cada subsidiária, insira o nome da subsidiária e o nome do arquivo de exportação que será criado durante o trabalho de exportação.

    3. No campo **Tipo de contas das diferenças de conversão**, selecione **Lucros e perdas** ou **Balanço**.
    4. Insira um nome de arquivo para o arquivo de exportação que será criado.

5. Selecione **OK** para executar a exportação.

Quando a exportação for concluída, você receberá uma mensagem mostrando o número de registros salvos em cada arquivo. Você poderá importar os arquivos para a entidade legal consolidada.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]