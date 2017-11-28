---
title: "Atualizar custos padrão para um novo item fabricado"
description: "Este artigo oferece diretrizes para a atualização de custos padrão para um novo item fabricado."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1cfb04a98f7d01f7766bea97157ca3c44c51e326
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Atualizar custos padrão para um novo item fabricado

[!include[banner](../includes/banner.md)]


Este artigo oferece diretrizes para a atualização de custos padrão para um novo item fabricado. 

As diretrizes a seguir pressupõem o uso de uma abordagem de duas versões para atualizar os custos padrão. Nessa abordagem, uma versão de custo contém os primeiros custos padrão originalmente definidos para o período de congelamento, e a segunda versão de custo contém as atualizações incrementais que pertencem aos novos itens fabricados. As atualizações incrementais são inseridas como registros de custo na segunda versão de custo e, eventualmente, são habilitadas. A abordagem de duas versões requer que você defina uma segunda versão de custo. Veja as diretrizes para a definição desta versão de avaliação de custo:

-   Atribua um tipo de custo de **Custo padrão**.
-   Atribua um identificador significativo que indique o conteúdo da versão de avaliação de custo, como **ATUALIZAÇÕES-2016**.
-   No grupo de campos **Permitir tipos de preço**, verifique se **Preço de custo** está definido como **Sim**.
-   Permita que os registros de custo sejam inseridos para todos os sites (isto é, deixe o campo **Local**em branco). Se você inserir um site, os registros de custo poderão ser inseridos somente para esse site.
-   Use um princípio de fallback **Ativo**.

Para adicionar novos itens de fabricação por todo o período de congelamento, siga estas etapas.

1.  Use a página **Configuração da versão**de avaliação de custo para permitir que os registros de custo sejam inseridos na segunda versão de avaliação de custo que contém as atualizações incrementais. Impeça a ativação de custos pendentes, em que a ativação será permitida depois que os custos pendentes forem definidos por completo e de forma precisa. Indique uma data inicial em branco como uma diretiva na versão de custo e, em seguida, insira a data inicial ao inserir cada registro de custo. A data de início deve representar a data antes de os novos itens serem comprados ou fabricados.
2.  Use a página **Preço de item** para inserir registros de custo para novos itens comprados. Para cada registro de custo, insira a versão de custo que contém atualizações incrementais e use uma data de início anterior à data de fabricação esperada para novos itens fabricados.
3.  Calcule o custo de novos itens fabricados usando a página **Cálculo**. Abra a página **Cálculo** da página **Manutenção de versão de avaliação de custo** e selecione a versão de avaliação de custo que contém as atualizações incrementais. Use o critério de seleção para especificar o novo item fabricado e qualquer um dos seus componentes fabricados. Em uma estrutura de produto de vários níveis, talvez também seja necessário especificar qualquer item pai que contém os novos itens fabricados como um componente. Insira uma data de início para o cálculo de BOM (lista de materiais) que corresponda ao início da fabricação para os novos itens fabricados. A data de início deve estar dentro das datas de efetivação para as versões de BOM e de roteiro do item. **Observação:** um registro de custo ausente pode indicar um novo item fabricado. Os cálculos de BOM podem ser limitados a itens que têm custos ausentes.
4.  Verifique se os custos calculados para os novos itens fabricados estão completos e precisos. Use a página **Completo** para rever os custos calculados de cada registro de custo de item e examine todas as mensagens de aviso do log de informações. Como alternativa, use a página **Cálculo** para examinar os custos calculados.
5.  Use a página **Configuração de versão de avaliação de custo** para alterar o sinalizador de bloqueio para permitir a ativação dos registros de custos pendentes na segunda versão de avaliação de custo.
6.  Use a página **Preços ativos** (aberta da página **Manutenção de versão de avaliação de custo**) para habilitar todos os registros de custos pendentes na segunda versão de avaliação de custo. Você também pode habilitar os registros de custo pendente para itens individuais clicando no botão **Ativar** na página **Preço de item**.
7.  Use a página **Configuração de versão de avaliação de custo** para alterar os sinalizadores de bloqueio incluídos na segunda versão de avaliação de custo para impedir a manutenção adicional de dados. As diretivas de bloqueio impedem a entrada de novos custos pendentes e a ativação de custos pendentes.





