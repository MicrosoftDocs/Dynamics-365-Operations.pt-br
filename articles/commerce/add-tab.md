---
title: Módulo de guia
description: Este tópico abrange os módulos de guia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c9d897113442f14b95539efb9fec9482be96447a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410133"
---
# <a name="tab-module"></a>Módulo de guia

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de guia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Os módulos de guia são módulos semelhantes aos usados para organizar as informações em uma página de site em guias. Eles podem ser usados em qualquer página em que as informações devem ser apresentadas nas guias.

Em cada módulo de guia, um ou mais módulos de item de guia podem ser adicionados. Cada módulo de item da guia representa uma única guia. Em cada módulo de item de guia, um ou mais módulos podem ser adicionados. Não há restrições quanto aos tipos de módulos que podem ser adicionados a um módulo de item de guia.

A imagem a seguir mostra um exemplo de um módulo de guia em uma página de site. Neste exemplo, a guia **Remessa** foi selecionada.

![Exemplo de um módulo de guia](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Propriedades do módulo de guia

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Título | Texto | Esta propriedade especifica um cabeçalho de texto opcional para o módulo de guia. |
| Índice da Guia Ativo | Número | Esta propriedade especifica a guia que deve estar ativa por padrão quando uma página é carregada. Se nenhum valor for fornecido, o primeiro item da guia ficará ativo por padrão. |

## <a name="tab-item-module-properties"></a>Propriedades do módulo de item de guia

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Cargo | Texto | Esta propriedade especifica o texto do título para o módulo de item de guia. |

## <a name="add-a-tab-module-to-a-page"></a>Adicionar um módulo de guia a uma página

Para adicionar um módulo de guia a uma página e definir as propriedades, siga estas etapas.

1. Use o modelo de marketing da Fabrikam (ou qualquer modelo que não tenha restrições) para criar uma nova página denominada **Página Armazenar políticas**.
1. No slot **Principal** da **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Guia** e, depois, **OK**.
1. No painel de propriedades do módulo de guia, selecione **Título** ao lado do símbolo de lápis.
1. Na caixa de diálogo **Título**, em **Texto do Título**, insira o texto do título (por exemplo, **Políticas**). Em seguida, selecione **OK**.
1. No slot **Guia**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item da guia** e, depois, **OK**.
1. No painel de propriedades do módulo de item de guia, em **Título**, digite o texto do título (por exemplo, **Entrega**).
1. No slot **Item de guia**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.
1. No painel de propriedades do módulo de bloco de texto, em **Texto rico**, insira um parágrafo de texto.
1. No slot **Guia**, adicione mais alguns módulos de itens de guia com títulos. Em cada módulo de item de guia, adicione um módulo de bloco de texto que tenha conteúdo.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. A página mostrará um módulo de guia que contém módulos de itens de guia com o conteúdo adicionado.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de Accordion](add-accordion.md)

[Módulo de bloco de texto](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]