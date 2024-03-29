---
title: Planejamento mestre com contratos comerciais de compra
description: Este artigo descreve como o planejamento mestre pode encontrar o fornecedor e/ou prazo de entrega para uma ordem planejada, com base no melhor preço ou prazo de entrega encontrado nos contratos comerciais de compra.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c36827738b13d5ca71da910d32e8877c1a408f62
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740976"
---
# <a name="master-planning-with-purchase-trade-agreements"></a>Planejamento mestre com contratos comerciais de compra

[!include [banner](../../includes/banner.md)]

Este artigo descreve como o planejamento mestre pode encontrar o fornecedor e/ou prazo de entrega para uma ordem planejada, com base no melhor preço ou prazo de entrega encontrado entre todos os contratos comerciais de compra especificados para um determinado produto.

## <a name="turn-the-purchase-trade-agreements-for-planning-optimization-feature-on-or-off"></a>Ativar ou desativar os Contratos comerciais de compra para o recurso Otimização de Planejamento

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Contratos comerciais de compra para Otimização de Planejamento* no espaço de trabalho [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prepare-your-system-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Preparar o sistema para avaliar contratos comerciais de compra durante planejamento mestre

Siga estas etapas para configurar o sistema para aplicar o planejamento mestre que avalia os contratos comerciais de compra.

1. Acesse **Planejamento mestre \> Configurar \> Parâmetros de planejamento mestre**. Na guia **Ordens planejadas**, na seção **Fornecedor**, defina os seguintes valores:

    - **Localizar contrato comercial** – defina essa opção como **Sim** para incluir contratos comerciais de compra no planejamento mestre.
    - **Critérios de pesquisa** – selecione o fator que você deseja priorizar para cada contrato comercial de compra: **Prazo de entrega mínimo** ou **Preço unitário mínimo**.

1. Ir para **Compras e fornecimento \> Configuração \> Preços e descontos \> Ativar preço/desconto** e verifique se a opção **Fornecedor** está definida como **Sim**.
1. Acesse **Gerenciamento de informações do produto \> Configuração \> Grupos de dimensões e variantes \> Grupos de dimensões de armazenamento** e selecione um grupo de dimensões de armazenamento que se aplique aos produtos para os quais o planejamento mestre deve avaliar os contratos comerciais de compra. Verifique se cada dimensão de armazenamento relevante neste grupo tem uma marca de seleção na coluna **Para preços de compra**. Repita esta etapa para cada grupo de dimensões de armazenamento relevante.

## <a name="prepare-a-released-product-to-evaluate-purchase-trade-agreements-during-master-planning"></a>Preparar um produto lançado para avaliar contratos comerciais de compra durante o planejamento mestre

Depois que o sistema for preparado conforme descrito na seção anterior, siga estas etapas para verificar se cada produto que você deseja usar com esse recurso está configurado corretamente.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados** e abra um produto de destino.
1. Na Guia Rápida **Compra**, verifique se nenhum fornecedor foi atribuído no campo **Fornecedor**.
1. No Painel de Ação, na guia **Plano**, no grupo **Cobertura**, selecione **Cobertura de item** para abrir a página **Cobertura de item** para o produto selecionado. Verifique as seguintes configurações:

    - Na guia **Geral**, você pode configurar substituições de fornecedores. Se desejar que o planejamento mestre use contratos comerciais de compra para selecionar um fornecedor, você deverá impedir substituições de fornecedores desmarcando a caixa de seleção **Usar configuração específica**.
    - Na guia **Prazo de entrega**, você pode configurar substituições de prazo de entrega. Se desejar que o planejamento mestre use contratos comerciais de compra para selecionar prazos de entrega, você deverá impedir substituições de prazo de entrega. Desmarque a caixa de seleção para cada tipo de prazo de entrega que você deseja selecionar usando contratos comerciais de compra (**Compra**, **Produção** e/ou **Transferência**).

1. Feche a página **Cobertura de item** para retornar à página de detalhes do produto selecionado.
1. No Painel de Ações, na guia **Plano**, no grupo **Previsão**, selecione **Previsão de fornecimento** para abrir a página **Previsão de fornecimento**. Verifique se nenhuma linha mostrada aqui tem um valor na coluna **Conta de fornecedor**.
1. Feche a página **Previsão de fornecimento** para retornar à página de detalhes do produto selecionado.
1. No Painel de Ações, na guia **Compra**, no grupo **Contratos comerciais**, selecione **Exibir contratos comerciais**. Verifique se todos os contratos comerciais de compra relevantes estão listados. Verifique também se a opção **Desconsiderar prazo de entrega** está definida como **Não** para cada contrato onde você deseja que o planejamento mestre use o prazo de entrega especificado para esse contrato.
1. No Painel de Ações, na guia **Plano**, no grupo **Configurações da ordem**, selecione **Configurações padrão da ordem** para abrir a página **Configurações padrão da ordem** para o produto selecionado. Na Guia Rápida **Ordem de compra**, exiba o valor do campo **Prazo de entrega da compra**. Se nenhuma substituição de prazo de entrega da cobertura de item for definida, o planejamento mestre usará esse valor ao selecionar contratos comerciais em que a opção **Desconsiderar prazo de entrega** será definida como **Sim**. Portanto, você deve ajustar esse valor conforme necessário.
1. Repita esse procedimento para cada produto relevante.

> [!NOTE]
> O planejamento mestre dá suporte a contratos comerciais de compra de várias moedas. Ao procurar um contrato comercial usando a opção **Preço unitário mínimo**, o sistema considerará comprar linhas de contrato comercial com moedas diferentes, desde que uma taxa de câmbio tenha sido definida entre a moeda da linha do contrato comercial e a moeda contábil da entidade legal. Caso contrário, a linha de contrato comercial será ignorada e você verá um erro durante o planejamento mestre. Portanto, o planejamento mestre incluirá informações de todas as linhas de contrato comercial de compra relevantes, nas quais os preços podem ser convertidos na moeda contábil. É importante observar que as regras de arredondamento não serão consideradas durante a conversão de preço em linha do contrato comercial.

## <a name="examples-of-how-master-planning-finds-vendor-and-lead-times"></a>Exemplos de como o planejamento mestre localiza o fornecedor e os prazos de entrega

A tabela a seguir fornece exemplos que mostram como várias configurações para um produto liberado e seus contratos comerciais de compra associados afetam os valores que são encontrados para a ordem de compra planejada resultante. Os valores em **negrito** nas duas colunas mais à direita são os valores selecionados pelo planejamento mestre. Os valores em **_negrito e itálico_** nas outras colunas são as configurações que produziram os valores resultantes para cada linha.

| Produto liberado: Fornecedor | Configurações de ordem padrão: Prazo de entrega | Cobertura de item: Substituir fornecedor | Cobertura de item: Substituir prazo de entrega | Contrato comercial: Fornecedor | Contrato comercial: Prazo de entrega | Contrato comercial: Ignorar prazo de entrega | Fornecedor resultante | Prazo de entrega resultante |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ***US001** _ | _*_1_*_ | Não | Não | US003 | 3 | Não | _ *US001** | **1** |
| US001 | 1 | ***Sim: US002** _ | _*_Sim: 2_*_ | US003 | 3 | Não | _ *US002** | **2** |
| *(Em branco)* | 1 | Não | Não | ***US003** _ | _*_3_*_ | Não | _ *US003** | **3** |
| *(Em branco)* | ***1** _ | Não | Não | _*_US003_*_ | 3 | Sim | _ *US003** | **1** |
| *(Em branco)* | ***1** _ | _*_Sim: US002_*_ | Não | US003 | 3 | Não | _ *US002** | **1** |
| *(Em branco)* | ***1** _ | _*_Sim: US002_*_ | Não | US003 | 3 | Não | _ *US002** | **1** |
| *(Em branco)* | 1 | Não | Sim: 2 | ***US003** _ | _*_3_*_ | Não | _ *US003** | **3** |
| *(Em branco)* | 1 | Não | ***Sim: 2** _ | _*_US003_*_ | 3 | Sim | _ *US003** | **2** |

## <a name="additional-resources"></a>Recursos adicionais

- [Contratos de compra](../../procurement/purchase-agreements.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
