---
title: Devolver produtos controlados por número de série no POS
description: Este artigo descreve os recursos para validar itens serializados como parte do processo de devolução no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9fa7e47b6d650370afe4b98d7eca01253bd1bc36
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268465"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Devolver produtos controlados por número de série no POS

[!include [banner](includes/banner.md)]

Este artigo descreve os recursos para validar itens serializados como parte do processo de devolução no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Na versão 10.0.20 e posterior do Commerce, um novo recurso chamado **Experiência de processamento de devolução unificado para POS** está disponível. Para usar a validação de número de série durante o processamento de ordem de devolução no POS, você deve ativar este recurso. Para mais informações sobre outras funcionalidades que este recurso oferece quando é ativado, consulte [Criar devoluções no POS)](POS-returns.md).
>
> Depois que o recurso é ativado, não é possível desativá-lo.

## <a name="options-for-validating-serialized-returns"></a>Opções para validar devoluções serializadas

Quando o recurso **Experiência de processamento de devolução unificado para POS** é ativado, as organizações podem realizar uma validação das devoluções de itens controlados por número de série no POS. Esta funcionalidade pode avisar os usuários se o número de série está sendo devolvido difere do número de série original que foi vendido. No Commerce versão 10.0.20 e posterior, a mensagem que os usuários recebem é somente uma mensagem de aviso. Os usuários podem continuar processando uma devolução com base em um número de série que seja diferente do número de série original que foi vendido.

Para configurar a validação do número de série para uma organização após o recurso **Experiência de processamento de devolução unificado para POS** for ativado, Acesse **Retail e Commerce \> Configuração do headquarters \> Parâmetros \> Parâmetros do CommerceParâmetros** no Commerce headquarters. Na guia **Inventário**, na Guia Rápida **Armazenar operações de inventário**, defina a opção **Habilitar validar de números de série nas devoluções do POS** como **Sim**.

## <a name="process-returns-for-serialized-items-in-pos"></a>Processar devoluções para itens serializados no POS

Se a opção **Habilitar validar de números de série nas devoluções do POS** tiver sido definida como **Sim**, quando um item controlado por número de série é devolvida no POS, o usuário pode digitar o número de série para a linha de devolução no painel de detalhes na página **Produtos que podem ser devolvidos**. Se o número de série inserido não corresponder ao número de série original que foi vendido para a transação de vendas, o usuário receberá uma mensagem de aviso. No entanto, o aplicativo não impede que o usuário continue publicando a devolução.

> [!NOTE]
> No momento, o POS é compatível com a validação de números de série somente nas linhas de devolução em que a quantidade comprada original não seja maior que um. Se a linha de ordem de venda original tiver sido criada em um canal que não é do POS, e se a quantidade comprada do item serializado em uma determinada linha de venda for maior que um, o item não poderá ser retornado corretamente no POS.

## <a name="additional-resources"></a>Recursos adicionais

[Criar devoluções no POS](POS-returns.md)
