---
title: Medidas de ativos
description: O tópico explica como criar a medida de ativos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783077"
---
# <a name="asset-measures"></a>Medidas de ativos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

O tópico explica como criar a medida de ativos no Gerenciamento de Ativos. Os tipos de medidas de ativos são usados para fazer registros de medidas em ativos, por exemplo, em relação ao número de horas de produção ou à quantidade produzida no ativo. Os tipos de ativos são relacionados aos tipos de medida de ativos. Isso significa que uma medida de ativo só poderá ser usada em um ativo se a medida de ativo estiver configurada no tipo de ativo usado no ativo.

Para efetuar registros de medida em ativos, primeiro crie os tipos de medida de ativos que você deseja usar em **Contadores**. Em seguida, você pode criar registros de medida em ativos em **Medidas de ativos**. 

As medidas de ativos podem ser usadas em planos de manutenção. Uma linha do plano de manutenção pode ser do tipo "Contador", por exemplo, em relação ao número de horas de produção ou à quantidade produzida. 

Um registro de medida de ativos pode ser atualizado de forma manual ou automática com base nas horas de produção ou na quantidade produzida. Uma medida de ativos pode ser configurada para usar um entre três métodos de atualização (selecionado no campo **Atualizar** em **Contadores**):
  
- Manual - você deve registrar manualmente valores de medida de ativos.  
- Horas de produção - o contador é atualizado automaticamente com base no número de horas de produção.  
- Quantidade produzida - o contador é atualizado automaticamente com base no número da quantidade produzida.  

>[!NOTE]
>Se a quantidade produzida for utilizada, *todos* os itens registrados serão incluídos no registro de medida, com a quantidade de acertos e a quantidade de erros. É sempre possível fazer registros manuais de medida de ativos, se necessário.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Crie tipos de contador para registros de contador de ativos

1. Selecione **Gerenciamento de ativos** > **Configuração** > **Tipos de ativos** > **Contadores**.
2. Selecione **Novo** para criar um novo tipo de medida de ativo.
3. Insira uma ID no campo **Contador** e um nome de contador no campo **Nome**.
4. Na Guia Rápida **Geral**, selecione uma unidade de medida no campo **Unidade**.
5. No campo **Atualizar**, selecione o método de atualização a ser usado para a medida do ativo.
6. Selecione "Sim" no botão de alternância **Herdar valores do contador** se os ativos filho em uma estrutura de ativos herdarem automaticamente registros de medida de ativos criados em ativos pai.
7. No campo **Total agregado**, selecione o método da soma a ser usado para uma medida de ativo por meio deste tipo de medida de ativo. A "soma" é a seleção padrão usada para adicionar continuamente valores registrados ao valor total. A "média" poderá ser usada se uma medida de ativos for configurada para monitorar um limite, por exemplo, em relação a temperatura, a vibrações ou ao uso e desgaste em um ativo. 
8. No campo **Desvio acima de**, insira o nível superior em porcentagem para validar se o registro manual de medida de ativo está em um intervalo esperado. A validação é baseada em um aumento linear em registros existentes de medida de ativos.
9. No campo **Desvio abaixo de**, insira o nível inferior em porcentagem para validar se o registro manual de medida de ativo está em um intervalo esperado. A validação é baseada em uma redução linear em registros existentes de medida de ativos.
10. No campo **Tipo**, selecione o tipo de mensagem (informações, aviso, erro) a ser mostrado se ocorrerem desvios fora do intervalo definido quando você fizer o registro manual de medida de ativos.
11. Na Guia Rápida **Tipos de ativo**, adicione os tipos de ativo que devem poder usar a medida de ativos.
12. Na Guia Rápida **Medidas de ativos relacionadas**, adicione as medidas de ativos a serem atualizadas automaticamente quando essa medida de ativos for atualizada.


>[!NOTE]
>Uma medida de ativos relacionada será atualizada automaticamente somente se a medida de ativos relacionada tiver o tipo de ativo, ao qual ela está relacionada, na configuração da medida de ativos. Por exemplo: você configura uma medida de ativos para "Horas de produção" e adiciona o tipo de ativo "Mecanismo de Caminhão". Quando essa medida de ativos é atualizada, um contador relacionado "Óleo" também é atualizado com os mesmos valores de medida de ativos. A configuração em **Contadores** inclui a configuração em "Horas". Além disso, na medida de ativos "Óleo", o tipo de ativo "Mecanismo de Caminhão" deve ser adicionado à Guia Rápida **Tipos de ativo** para garantir a relação da medida de ativo. Consulte as capturas de tela a seguir para obter um exemplo da configuração de medidas do ativos de Horas e Óleo.

Quando tipos de ativo forem adicionados a uma medida de ativo, digite **Contadores**. Assim, a medida de ativos será automaticamente adicionada aos tipos de ativos na Guia Rápida **Contadores** em [Tipos de ativo](../setup-for-objects/object-types.md).

![Figura 1](media/071-setup-for-objects.png)


