---
title: Medidas de ativos
description: O tópico explica como criar a medida de ativos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 37f47b3d9ba0344b96db5626359e2a99a1a40f9c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018512"
---
# <a name="counters"></a>Contadores

[!include [banner](../../includes/banner.md)]

O tópico explica como criar a tipos de contador no Gerenciamento de Ativos. Os tipos de contador são usados para fazer registros de contador em ativos, por exemplo, em relação ao número de horas de produção ou à quantidade produzida no ativo. Os tipos de ativos são relacionados aos tipos de contador. Isso significa que um contador só poderá ser usada em um ativo se o contador estiver configurado no tipo de ativo usado no ativo.

Para efetuar registros de contador, primeiro crie os tipos de contador que você deseja usar em **Contadores**. Em seguida, você pode criar registros de contador em ativos em **Contadores**. 

Os contadores podem ser usados em planos de manutenção. Uma linha do plano de manutenção pode ser do tipo "Contador", por exemplo, em relação ao número de horas de produção ou à quantidade produzida. 

Um registro de contador pode ser atualizado de forma manual ou automática com base nas horas de produção ou na quantidade produzida. Um contador pode ser configurado para usar um entre três métodos de atualização (selecionado no campo **Atualizar** em **Contadores**):
  
- Manual - você deve registrar manualmente valores de contador.  
- Horas de produção - o contador é atualizado automaticamente com base no número de horas de produção.  
- Quantidade produzida - o contador é atualizado automaticamente com base no número da quantidade produzida.  

>[!NOTE]
>Se a quantidade produzida for utilizada, *todos* os itens registrados serão incluídos no registro de contador, com a quantidade de acertos e a quantidade de erros. É sempre possível fazer registros manuais de contadores, se necessário.

## <a name="create-counter-types-for-asset-counter-registrations"></a>Crie tipos de contador para registros de contador de ativos

1. Selecione **Gerenciamento de ativos** > **Configuração** > **Tipos de ativos** > **Contadores**.
2. Selecione **Novo** para criar um novo tipo de contador.
3. Insira uma ID no campo **Contador** e um nome de contador no campo **Nome**.
4. Na Guia Rápida **Geral**, selecione uma unidade de contador no campo **Unidade**.
5. No campo **Atualizar**, selecione o método de atualização a ser usado para o contador.
6. Selecione "Sim" no botão de alternância **Herdar valores do contador** se os ativos filho em uma estrutura de ativos herdarem automaticamente registros de contador criados em ativos pai.
7. No campo **Total agregado**, selecione o método da soma a ser usado para um contador por meio deste tipo de contador. A "soma" é a seleção padrão usada para adicionar continuamente valores registrados ao valor total. A "média" poderá ser usada se um contador for configurado para monitorar um limite, por exemplo, em relação a temperatura, a vibrações ou ao uso e desgaste em um ativo. 
8. No campo **Desvio acima de**, insira o nível superior em porcentagem para validar se os registros manuais de contador estão em um intervalo esperado. A validação é baseada em um aumento linear em registros existentes de contador.
9. No campo **Desvio abaixo de**, insira o nível inferior em porcentagem para validar se os registros manuais de contador estão em um intervalo esperado. A validação é baseada em uma redução linear em registros existentes de contador.
10. No campo **Tipo**, selecione o tipo de mensagem (informações, aviso, erro) a ser mostrado se ocorrerem desvios fora do intervalo definido quando você fizer o registro manual de contadores.
11. Na Guia Rápida **Tipos de ativo**, adicione os tipos de ativo que devem poder usar o contador.
12. Na Guia Rápida **Contadores de ativos relacionados**, adicione o contador a ser atualizado automaticamente quando esse contador for atualizado.


>[!NOTE]
>Um contador relacionado só será automaticamente atualizado se o contador relacionado tiver o tipo de ativo, ao qual ele está relacionado, na configuração do contador. Por exemplo: você configura um contador para "Horas de produção" e adiciona o tipo de ativo "Motor de Caminhão". Quando esse contador é atualizado, um contador relacionado "Óleo" também é atualizado com os mesmos valores de contador. A configuração em **Contadores** inclui a configuração em "Horas". Além disso, no contador "Óleo", o tipo de ativo "Motor de Caminhão" deve ser adicionado à Guia Rápida **Tipos de ativo** para garantir a relação do contador. Consulte as capturas de tela a seguir para obter um exemplo da configuração de contadores de Horas e Óleo.

Quando tipos de ativo forem adicionados a um tipo de contador, digite **Contadores**. Assim, o contador será automaticamente adicionado aos tipos de ativos na Guia Rápida **Contadores** em [Tipos de ativo](../setup-for-objects/object-types.md).

![Figura 1](media/071-setup-for-objects.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]