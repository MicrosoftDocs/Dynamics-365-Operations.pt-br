---
title: Previsão de fluxo de caixa (versão preliminar)
description: Este tópico descreve o recurso de previsão de fluxo de caixa.
author: ShivamPandey-msft
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6e4713aa4662714d1b2a3eeb62adce8608907054
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811402"
---
# <a name="cash-flow-forecast-preview"></a>Previsão de fluxo de caixa (versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O fluxo de caixa é fundamental para qualquer negócio. Mesmo empresas lucrativas podem enfrentar insolvência se não mantiverem o fluxo de caixa para atender às necessidades imediatas. O recurso de previsão de fluxo de caixa nos insights de finanças pode ajudar as empresas a monitorar e gerenciar seus saldos de caixa com eficácia. Esse recurso usa o aprendizado de máquina para ajudar as empresas a prever fluxos de caixa com mais precisão do que antes. Também pode ajudar os gerentes a tomar decisões que otimizam as oportunidades no contexto da posição de caixa atual. 

Para a maioria das empresas, o gerenciamento de fluxo de caixa e a execução de previsões de fluxo de caixa é um processo tedioso, repetitivo e manual. A maioria das empresas confia em soluções do Microsoft Excel que têm graus de complexidade variáveis. Os desafios da previsão de fluxo de caixa com precisão incluem o seguinte:

- Os dados não estão disponíveis para tomadores de decisão porque estão dispersos em vários lugares, incluindo: 
  - O sistema de planejamento de recursos corporativos ou contábeis
  - Software de planejamento financeiro
  - Excel
  - Aplicativos de software adicionais 
- A previsão se baseia no conhecimento interno que reside em "silos" em cada domínio ou departamento.
- Medir a precisão da previsão de fluxo de caixa depois que as finanças são concretizadas é incerto e difícil.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>Detalhes do recurso de previsões de fluxo de caixa
O recurso de previsões de fluxo de caixa inclui a funcionalidade a seguir. 

- Facilita a integração de dados de fluxo de caixa de sistemas externos para o Dynamics 365 Finance. As previsões de fluxo de caixa também podem usar a estrutura de importação-exportação de dados. Esta estrutura facilita a integração com o Excel/OData. Também é possível combinar dados de várias fontes para criar uma solução de fluxo de caixa abrangente. 

- Introduz a posição de caixa à vista inteligente. A posição de pagamento à vista é criada com base no comportamento de pagamento do cliente para prever quando uma empresa pode esperar dinheiro chegar em suas contas. Ele também analisa os padrões históricos de fornecedores de pagamento para prever quando futuras faturas e ordens futuras provavelmente devem ser pagas. 

- Introduz a previsão de fluxo de caixa inteligente para previsões de longo prazo, usando a previsão de série de tempo por meio da integração automatizada com o AI Builder.

- Oferece a capacidade de salvar as previsões ou posições de fluxo de caixa específicas, editá-las e comparar e medir facilmente o desempenho de previsão para os dados financeiro reais.

- Habilita o análise hipotética por meio da comparação de instantâneo. Por exemplo, você pode criar vários instantâneos que representem os modos de exibição otimista, pessimista e mais realista do fluxo de caixa e depois comparar e exibir as diferenças.

- Fornece a capacidade de exibir a previsão de fluxo de caixa em várias moedas, entre as entidades legais e filtrar e exibir o fluxo de caixa relacionado a uma conta bancária. 

- Permite filtrar e exibir contas bancárias relacionadas a dimensões financeiras.

A funcionalidade de previsão de fluxo de caixa no Dynamics 365 Finance permitirá que sua organização transforme uma projeção de fluxo de caixa tediosa, complexa e repetitiva a um processo simples e automatizado. Automatizar os aspectos mais tediosos da previsão de fluxo de caixa permite que você se concentre na tomada de decisões críticas para impulsionar os resultados comerciais desejados.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Configurando dimensões para previsão de fluxo de caixa
Uma nova guia na página **Configuração de previsão de fluxo de caixa** permite controlar as dimensões financeiras a serem usadas para filtragem no espaço de trabalho **Previsão de fluxo de caixa**. Esta guia só será exibida quando o recurso de previsões de fluxo de caixa estiver habilitado. 

Na guia **Dimensões**, escolha na lista de dimensões a ser usada para filtragem e use as teclas de seta para movê-las para a coluna à direita. Somente duas dimensões podem ser selecionadas para filtrar dados de previsão de fluxo de caixa. 

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]