---
title: Numeração de documentos e comprovantes cronologicamente
description: Este artigo explica como configurar e usar números cronológicos para documentos aplicáveis e comprovantes relacionados.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.custom: 401195
ms.search.form: NumberSequenceGroup
ms.openlocfilehash: 1a1b8887eff625d9e4095380fbb7c8963682ef3c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272418"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Numerar documentos e comprovantes cronologicamente

[!include [banner](../includes/banner.md)]


Em alguns países, há um requisito legal para numerar documentos e comprovantes relacionados em ordem cronológica. A cronologia deve ter suporte de períodos. Todos os números pertencentes a períodos anteriores devem ser menores que os números pertencentes a períodos posteriores. Para atender a esse requisito, a funcionalidade de numeração cronológica foi implementada. Este artigo explica como configurar e usar números cronológicos para documentos aplicáveis e comprovantes relacionados.

## <a name="prerequisites"></a>Pré-requisitos

No espaço de trabalho Gerenciamento de recursos, ative o recurso **Numeração cronológica**. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Configurar numeração cronológica

A numeração cronológica afeta os documentos a seguir.

**Contas a receber**
- Fatura de cliente
- Comprovante de fatura de cliente
- Nota de crédito de venda
- Comprovante de nota de crédito de venda
- Fatura de texto livre
- Comprovante de fatura de texto livre
- Nota de crédito em texto livre
- Comprovante de nota de crédito em texto livre
- Guia de Remessa
- Comprovante de guia de remessa
- Comprovante de correção da guia de remessa
- Comprovante de nota de juros
- Comprovante de carta de cobrança

**Contas a pagar**
- Comprovante de fatura
- Comprovante de nota de crédito
- Comprovante de recebimento de produtos

**Gerenciamento de projetos**
- Fatura
- Comprovante de fatura
- Nota de Crédito
- Comprovante de nota de crédito 

### <a name="define-number-sequences"></a>Definir sequências numéricas

Para definir as sequências numéricas, acesse **Administração da organização** > **Sequências numéricas** > **Sequências numéricas**. É possível definir as sequências numéricas necessárias para cobrir os períodos afetados para os documentos necessários. 

Especifique uma empresa para cada sequência numérica. Os segmentos das sequências numéricas devem ser definidos para que forneçam ordem cronológica para períodos. Por exemplo, os nomes de segmento podem conter um prefixo especial que identifica um período específico.

![Configuração da sequência numérica.](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Configurar grupos de sequências numéricas

Para configurar grupos de sequências numéricas, acesse **Contas a receber** > **Configuração** > **Parâmetros de contas a receber**. Na guia **Sequências numéricas**, defina quantos grupos de sequências numéricas forem necessários para cobrir os períodos afetados. 

Para cada grupo, na seção **Referência**, selecione uma das referências de documento com suporte e, no campo **Código de sequência numérica**, consulte uma sequência numérica criada anteriormente para o período relacionado.

![Configuração do grupo de sequências numéricas.](media/chrono-num-sequence-group.jpg)

Da mesma forma, configure grupos de sequências numéricas nos módulos **Contas a pagar** e **Gerenciamento de projetos e contabilidade**.

### <a name="configure-number-sequence-groups-chronology"></a>Configurar cronologia de grupos de sequências numéricas

Para configurar a cronologia de grupos de sequências numéricas, acesse **Administração da organização** > **Sequências numéricas** > **Cronologia de grupos de sequências numéricas**. Defina as condições de aplicabilidade para grupos de sequências numéricas.

![Configuração de números cronológicos.](media/chrono-num-sequence-group-period.jpg)

| Campo            | descrição                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Efetivação  | A data de início da aplicabilidade do grupo de sequências numéricas. |
| Vencimento      | A data de término da aplicabilidade do grupo de sequências numéricas. Se nenhuma data de término for aplicada, selecione **Nunca**. |
| Grupo de sequências numéricas | Grupo de sequências numéricas que será usado para gerar números de documento durante o período. |
| Grupo de sequências numéricas original | Esse código de grupo de sequências numéricas é usado para filtragem adicional dos casos em que documentos já têm um grupo de sequências numéricas *permanente* específico atribuído. Um valor vazio é considerado um valor específico. Se você precisar ignorar um grupo atribuído preliminar, use a opção **Padrão** para essa configuração. |
| Padrão | Se ela estiver ativada, o sistema ignorará o grupo preliminar de sequências numéricas de documentos atribuídos e usará somente as datas de início e de término dos períodos para análise de aplicabilidade. Se ela estiver desativada, o sistema usará a combinação total **Efetivação** + **Expiração** + **Grupo de sequências numéricas original** para seleção. |

## <a name="document-posting"></a>Lançamento de documento
Quando você lança um documento, o grupo de sequências numéricas apropriado é atribuído ao documento, com base na data de lançamento do documento. Depois, ele é usado para gerar um número de documento com base na sequência numérica detectada. O sistema fornece uma mensagem sobre a atribuição de grupo de sequências numéricas.

![Número do documento.](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> Em alguns países, há uma lógica específica já implementada para a numeração de documentos. Nesse caso, a lógica específica do país substituirá o recurso **Numeração cronológica**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
