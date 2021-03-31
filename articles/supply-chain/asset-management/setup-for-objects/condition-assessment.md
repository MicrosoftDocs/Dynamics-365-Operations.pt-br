---
title: Avaliação de condição
description: Este tópico explica como criar um modelo de avaliação de condição e um registro em um ativo no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d84520413659db32713711ad5ac980f1e8b5519
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217164"
---
# <a name="condition-assessment"></a>Avaliação de condição

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como criar um modelo de avaliação de condição e um registro em um ativo no Gerenciamento de Ativos. A avaliação da condição é executada em intervalos regulares e a finalidade principal é criar e manter dados de condição em ativos. Sob uma perspectiva de manutenção preventiva, é importante monitorar informações como a condição atual e o tempo de vida útil restante. Além disso, se você realizar a avaliação da condição em intervalos regulares, poderá monitorar e comparar condições nas máquinas da sua fábrica.

A avaliação da condição pode ser usada para medir e monitorar muitas condições no seu equipamento. Exemplo: você pode medir vibrações em suas máquinas. Após registrar medidas de vibração em Gerenciamento de Ativos em vários tipos de equipamento, você poderá procurar a avaliação recém-registrada e exibir medidas de vibração.

A avaliação da condição é criada em ativos. Você configura um modelo de avaliação de condição em um tipo de ativo antes de executar o procedimento de avaliação de condição. O motivo para usar modelos para a avaliação de condição é evitar a variação de dados de condição em ativos semelhantes. A sequência para configurar e usar a avaliação da condição em Gerenciamento de Ativos é: primeiro, configure os métodos de avaliação de condições. Em seguida, você associa modelos com tipos de ativo no formulário **Tipos de ativo**. Finalmente, você pode criar registros de avaliação de condição em um ativo no formulário **Ativo**.

## <a name="create-a-condition-assessment-template"></a>Crie um modelo de avaliação de condição

1. Selecione **Gerenciamento de ativos** > **Configuração** > **Tipos de ativo** > **Avaliação de condição**.
2. Selecione **Novo** para criar um novo modelo.
3. Insira uma ID para o modelo no campo **Modelo**.
4. Insira um nome para o modelo no campo **Nome**.
5. Na Guia Rápida **Linhas de avaliação de condição**, adicione linhas necessárias para a avaliação da condição, incluindo a seleção do tipo de condição apropriado e da unidade de medida.
6. Na Guia Rápida **Tipos de ativo**, adicione os tipos de ativo que devem utilizar o modelo de avaliação de condição.
7. Nos campos **Linhas** e **Tipos de ativo** no grupo **Detalhes** na parte superior da tela, você verá o número de linhas de avaliação e tipos de ativo relacionados ao modelo de avaliação de condição selecionado.


## <a name="create-condition-assessment-registration-on-an-asset"></a>Crie o registro de avaliação de condição em um ativo

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os Ativos**.
2. Na lista, selecione o ativo para o qual deseja criar um registro de avaliação de condição.
3. Na guia **Geral**, clique em **Avaliação de condição**.
4. Clique em **Novo** para criar um novo registro.
5. Selecione a data para a avaliação de condição no campo **Data**.
6. Selecione o nome do trabalhador que realizou o registro de avaliação no campo **Trabalhador**.
7. No campo **Linhas**, você verá o número de linhas de avaliação definidas na avaliação de condição.
8. Selecione um modelo para a avaliação de condição no campo **Modelo**. O nome do modelo é inserido automaticamente no campo **Nome**; as linhas de registro relacionadas são inseridas na Guia Rápida **Linhas de avaliação de condição**.
9. Você pode inserir notas em relação à avaliação de condição selecionada na Guia Rápida **Notas**.
10. Para cada linha de avaliação de condição, insira dados de medida no campo **Valor**.
11. Você pode inserir um comentário sobre a linha de registro selecionada na Guia Rápida **Linhas de avaliação de condição** > campo **Comentários**. Se você adicionar um comentário em uma linha, a caixa de seleção **Comentário** será marcada automaticamente.

Após fazer um registro de avaliação de condição em um ativo, você poderá imprimir um relatório de avaliação de condição.

>[!NOTE]
>Você também pode registrar a avaliação de condição em uma ordem de serviço (botão **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** > **Avaliação de condição**.)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]