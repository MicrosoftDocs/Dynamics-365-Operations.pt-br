---
title: Consultas e relatórios de materiais perigosos
description: Este tópico explica como trabalhar com os vários relatórios relacionados a materiais perigosos. Muitos desses relatórios são necessários para permanecer em conformidade com várias regulamentações de materiais perigosos durante a remessa e o armazenamento.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 1bb96d117eb3bb2b54be1a376c8789ad73d5fec8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983357"
---
# <a name="hazardous-materials-inquiries-and-reports"></a>Consultas e relatórios de materiais perigosos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O Microsoft Dynamics 365 Supply Chain Management fornece vários relatórios relacionados a materiais perigosos. Muitos desses relatórios são necessários para permanecer em conformidade com várias regulamentações de materiais perigosos durante a remessa e o armazenamento.

Todos esses relatórios, exceto o relatório **Mercadorias perigosas de multimodais**, usam o modo de entrega definido para a remessa para encontrar a regulamentação que deve ser usada para imprimir o texto de remessa dos itens. O modo de entrega é associado à transportadora e ao serviço da transportadora. Portanto, você deve configurar uma transportadora e um serviço de transportadora e vinculá-los a um modo de entrega. O modo de entrega está relacionado à regulamentação do material perigoso.

A ilustração a seguir mostra a sequência de atividades que ocorrem quando o sistema gera os relatórios de materiais perigosos.

![Sequência de atividades para relatórios de materiais perigosos](media/hazmat-report-sequence.png "Sequência de atividades para relatórios de materiais perigosos")

## <a name="set-up-hazardous-materials-reporting"></a><a name="set-up"></a>Configurar relatório de materiais perigosos

Normalmente, se enviar itens que contenham materiais perigosos, você deverá gerar relatórios específicos para ajudar a preservar a segurança e obedecer a regulamentações de transporte de materiais perigosos. Para configurar seus relatórios, siga estas etapas:

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
2. Abra a guia **Relatórios**. Na FastTab **Parâmetro do relatório de materiais perigosos**, defina os campos a seguir.

    | Seção | Campo | descrição |
    |---|---|---|
    | Mercadorias perigosas multimodais | Código de regulamentação | Selecione a regulamentação que deverá ser usada quando um relatório de **Mercadorias perigosas multimodais** for gerado. |
    | Limites de estoque de material perigoso | Código de regulamentação | Selecione a regulamentação que deverá ser usada quando os limites de estoque forem avaliados. |
    | Transporte de mercadoria por estrada | Produto do grupo de CMR | CMR significa "substâncias carcinogênicas, mutagênicas e reprotóxicas". Defina esta opção como **Sim** para configurar o sistema para imprimir avisos e mensagens específicos relacionados ao manuseio dessas substâncias. |
    | Transporte de mercadoria por estrada | Descrição do grupo de materiais perigosos | Insira o texto de avisos específicos relacionados a CMR e ao transporte de mercadorias por estrada. O texto será é incluído no relatório. |
    | Declaração das transportadoras | Aviso | Insira o texto de uma mensagem de aviso que deve ser impressa no formulário declaração da transportadora (por exemplo, "Aviso: mercadorias perigosas, inflamável"). |
    | Declaração das transportadoras | Declaração de rodapé | Insira o texto de uma mensagem que deve ser impressa na parte inferior do documento da declaração de remessa. |
    | Idioma do relatório de bens perigosos | Idioma do relatório doméstico de bens perigosos | Selecione o idioma padrão para os relatórios de materiais perigosos associados a remessas nacionais. |
    | Idioma do relatório de bens perigosos | Idioma do relatório de exportação de bens perigosos | Selecione o idioma padrão para os relatórios de materiais perigosos associados a remessas internacionais. |

## <a name="hazardous-materials-report"></a>Relatório de materiais perigosos

O relatório **Materiais perigosos** mostra uma lista de todos os itens que foram configurados e definidos para que tenham informações de mercadorias perigosas. Você pode usar esse relatório para monitorar e revisar as informações que devem ser mantidas. A página do relatório mostra uma seleção limitada de campos da configuração de material perigoso. No entanto, é possível personalizá-la para adicionar mais campos conforme necessário.

Para exibir esse relatório, acesse **Gerenciamento de informações do produto \> Consultas e relatórios \> Documentação de remessa de material perigoso \> Materiais perigosos**.

## <a name="hazardous-material-stock-limit-report"></a><a name="stock-limit-report"></a>Relatório de limite de estoque de material perigoso

O relatório **Limite de estoque de material perigoso** permite que você monitore os níveis de estoque dos materiais perigosos em seus locais de depósito, para garantir que eles permaneçam dentro dos limites estabelecidos e seguros. Esses limites são provenientes dos limites definidos para cada produto liberado.

Para exibir esse relatório, acesse **Gerenciamento de informações do produto \> Consultas e relatórios \> Documentação de remessa perigosa \> Limites de materiais perigosos**.

Para obter mais informações sobre como definir limites de estoque em um produto liberado, consulte [Definir limites de estoque para produtos perigosos](hazmat-items.md#stock-limits).

A regulamentação usada para limites de estoque está definida na página **Parâmetros de gerenciamento de depósito**. Acesse **Gerenciamento de depósito \> Configurar \> Parâmetros de gerenciamento de depósito** e, na guia **Relatórios**, em **Limite estoque de materiais perigosos**, especifique um código de regulamentação. Para obter mais informações, consulte a seção [Configurar relatório de materiais perigosos](#set-up) anteriormente neste tópico.

## <a name="verified-gross-mass-report"></a>Relatório de massa bruta verificada

O relatório **Massa bruta verificada** permite que você imprima as informações sobre o peso de uma remessa.

Para gerar e imprimir esse relatório, acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas** e abra a remessa relevante. Em seguida, no Painel de Ações, na guia **Remessas**, no grupo **Documentos de materiais perigosos**, selecione **Massa bruta verificada**.

## <a name="multimodal-dangerous-goods-report"></a>Relatório de mercadorias perigosas multimodais

O relatório **Mercadorias perigosas multimodais** é fornecido para remessas que devem ser movidas transportadas usando uma combinação de métodos de transporte. Em geral, ele é usado quando uma remessa é transportada primeiro por estrada e depois por mar.

Para gerar e imprimir esse relatório, acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas** e abra a remessa relevante. Em seguida, no Painel de Ações, na guia **Remessas**, no grupo **Documentos de materiais perigosos**, selecione **Mercadorias perigosas multimodais**.

Quando você gera esse relatório, as informações são salvas para que possa editá-las e/ou reimprimir o relatório se necessário. Para editar um relatório gerado, acesse **Gerenciamento de depósito \> Consultas e relatórios \> Documentação de remessa de material perigoso \> Mercadorias perigosas multimodais** e localize o relatório relevante na lista. Depois que concluir a edição do conteúdo conforme necessário, selecione **Imprimir** no Painel de Ações para imprimir o relatório.

## <a name="shippers-declaration-report"></a>Relatório de declaração das transportadoras

O relatório **Declaração das transportadoras** permite que você imprima as informações relacionadas a uma declaração dos materiais incluídos na remessa.

Para gerar e imprimir esse relatório, acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas** e abra a remessa relevante. Em seguida, no Painel de Ações, na guia **Remessas**, no grupo **Documentos de materiais perigosos**, selecione **Declaração das transportadoras**.

## <a name="carriage-of-merchandise-by-road-report"></a>Relatório de transporte de mercadoria por estrada

O relatório **Transporte de mercadoria por estrada** é semelhante a um conhecimento de embarque, mas geralmente é usado para transporte rodoviário na Europa, conforme o Acordo relativo às regulamentações de transporte internacional de mercadorias perigosas por rodovias (ADR). Esse relatório usa o texto impresso da remessa para um item, a menos que você defina o campo **Descrição do grupo de materiais perigosos** na página **Parâmetros de gerenciamento de depósito**.

Para gerar e imprimir esse relatório, acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas** e abra a remessa relevante. Em seguida, no Painel de Ações, na guia **Remessas**, no grupo **Documentos de materiais perigosos**, selecione **Transporte de mercadoria por estrada**.

Quando você gera esse relatório, as informações são salvas para que possa editá-las e/ou reimprimir o relatório se necessário. Para editar um relatório gerado, acesse **Gerenciamento de depósito \> Consultas e relatórios \> Documentação de remessa de material perigoso \> Transporte de mercadoria por estrada** e localize o relatório relevante na lista. Depois que concluir a edição do conteúdo conforme necessário, selecione **Imprimir** no Painel de Ações para imprimir o relatório.

## <a name="shipment-summary-report"></a>Relatório de resumo de remessas

O relatório **Resumo da remessa** fornece informações resumidas pela categoria de transporte relacionada aos itens liberados.

Para gerar e imprimir esse relatório, acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas** e abra a remessa relevante. Em seguida, no Painel de Ações, na guia **Remessas**, no grupo **Documentos de materiais perigosos**, selecione **Resumo da remessa**.

## <a name="bill-of-lading-report"></a>relatório de conhecimento de embarque

Quando o recurso materiais perigosos está ativado no sistema, o relatório de **conhecimento de embarque** inclui uma coluna de **Materiais perigosos** que indica se uma carga inclui materiais perigosos. Esse relatório está disponível na página **Todas as cargas**, como de costume.

## <a name="packing-list-report"></a>Relatório de lista de remessa

Quando o recurso materiais perigosos está ativado no sistema, as listas de remessa incluem informações adicionais relacionadas ao texto impresso da remessa de um item. Esse relatório está disponível na página **Todas as cargas**, como de costume.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]