---
title: Bancada de criação de carga
description: Este tópico descreve como trabalhar com a bancada de criação de carga.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 306ca4f77d9c1d4879d750992e51c8b83917839e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574848"
---
# <a name="load-building-workbench"></a>Bancada de criação de carga

[!include [banner](../../includes/banner.md)]

A bancada de criação de carga permite aplicar estratégias de criação de carga ao criar cargas.

## <a name="create-a-load-building-strategy"></a>Elaborar uma estratégia de criação de carga

Você usa as estratégias de criação de carga para criar cargas automaticamente. Esse recurso pode ser benéfico nas seguintes situações:

- Se você remete um conjunto específico de produtos regularmente, as estratégias de carga ajudam a poupar tempo, porque não é necessário criar a mesma carga todas as vezes.
- Se você deseja evitar cargas meio cheias para maximizar a eficiência, as estratégias de carga podem ajudar a preencher cada carga o máximo possível.

Uma classe de estratégia de criação de carga chamada `TMSLoadBuildingVolumeStrategy` fornece uma estratégia de criação de carga denominada *Estratégia de criação de carga com base no volume*. Essa estratégia permite usar os valores máximos especificados para a altura e o peso do modelo de carga ou substituí-los pelas configurações por meio da inserção de novos valores. Essa estratégia é a única que está incluída pronta para uso. (No entanto, você pode ter algumas estratégias personalizadas).

Para usar a estratégia pronta para uso *Estratégia de criação de carga com base no volume*, selecione-a no campo **Estratégia de criação de carga** na página **Bancada de criação de carga** (**Gerenciamento de transporte &gt; Planejamento &gt; Bancada de criação de carga**).

Para elaborar uma estratégia de criação de carga, siga estas etapas.

1. Acesse **Gerenciamento de transporte &gt; Configuração &gt; Criação de carga &gt; Estratégias de criação de carga**.
1. No Painel de Ações, selecione **Gerar lista de classes** para verificar se você tem as versões mais recentes de todas as classes disponíveis.
1. No Painel de Ações, selecione **Novo**.
1. Insira um nome exclusivo para a estratégia, selecione a classe de estratégia de criação de carga e insira uma descrição.
1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, selecione **Parâmetros**.
1. Na página **Parâmetros da estratégia de criação de carga**, selecione **Capacidade de volume** na lista e, em seguida, no campo **Valor**, insira a porcentagem da capacidade de volume total da carga que deve ser aplicada para a nova estratégia de criação de carga.
1. Selecione **Capacidade de peso** na lista e, em seguida, no campo **Valor**, insira a porcentagem da capacidade de peso total da carga que deve ser aplicada para a nova estratégia de criação de carga.
1. Feche a página **Parâmetros da estratégia de criação de carga**.
1. Feche a página **Estratégias de criação de carga**.

Agora você pode atribuir a estratégia de criação de carga a um modelo de criação de carga. Como alternativa, você pode usá-la diretamente na bancada de planejamento de carga.

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a>Usar uma estratégia de criação de carga na bancada de criação de carga

1. Acesse **Gerenciamento de transporte &gt; Planejamento &gt; Bancada de criação de carga**.
1. Siga uma destas etapas:

    - Selecione uma estratégia no campo **Estratégia de criação de carga**.
    - Se você definiu um modelo de criação de carga e atribuiu a estratégia de criação de carga a ele, no Painel de Ações, na guia **Gerenciar modelos**, selecione **Aplicar modelo**. Em seguida, na caixa de diálogo suspensa **Aplicar modelo de criação de carga**, selecione um modelo no campo **Nome do modelo de criação de carga**.

1. Na FastTab **Sequência de modelos de carga**, selecione um ou mais [modelos de carga](load-template.md). A bancada tentará ajustar a carga nesses tipos de contêineres, na sequência especificada aqui. Normalmente, você deve colocar os contêineres menores no topo da lista para garantir que o menor contêiner possível seja selecionado primeiro.
1. No Painel de Ações, selecione **Propor cargas**.
1. Revise as cargas propostas e as linhas de cargas propostas.
1. No Painel de Ações, selecione **Criar cargas** para criar cargas com base nas linhas do documento de origem na FastTab **Linhas de cargas propostas**.
1. Feche a página **Bancada de criação de carga**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]