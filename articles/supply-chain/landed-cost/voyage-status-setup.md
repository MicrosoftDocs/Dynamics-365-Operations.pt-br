---
title: Configuração de status de viagem
description: Este tópico descreve como estabelecer os valores de status que os usuários podem atribuir a viagens.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: b7180cc9ab2d13f2260635d717adb7aab2177ab9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500877"
---
# <a name="voyage-status-setup"></a>Configuração de status de viagem

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Na página **Status de viagem**, você estabelece o conjunto de valores de status que os usuários podem atribuir a viagens. Os usuários podem atribuir valores de status de viagem a todos os níveis de uma viagem: viagem, contêiner de remessa, fólio, ordem de compra e item (linhas de compra e linhas de ordem de transferência). Eles são usados para duas finalidades:

- Informar o usuário sobre o status da viagem, o contêiner de remessa, o fólio, a ordem de compra ou o item (linhas de compra e linhas de ordem de transferência).
- Limitar o uso da área de custo impedindo a modificação ou a exclusão.

Para configurar seus status de viagem, vá para **Custo de entrega \> Configuração \> Status de viagem**. Lá, você pode adicionar, remover e editar os status usando os botões no Painel de Ações.

Cada área de custo tem seu próprio conjunto e hierarquia de status de viagem. Portanto, na página **Status de viagem**, no campo **Área de custo**, você deve primeiro selecionar a área de custo que deseja exibir ou para a qual deseja criar status de viagem. Em seguida, para cada status de viagem, defina os campos descritos na tabela a seguir, conforme necessário. Observe que o status de uma viagem também pode ser alterado automaticamente por eventos do sistema, como as regras que foram estabelecidas usando o centro de controle de acompanhamento.

| Campo | descrição |
|---|---|
| Status da viagem | Insira o nome do status de viagem. |
| descrição | Insira uma descrição do status de viagem. |
| Modificar | Marque esta caixa de seleção se os usuários tiverem permissão para modificar viagens com este status. |
| Delete | Marque esta caixa de seleção se os usuários tiverem permissão para excluir viagens com este status. |
| Obrigatório | Marque esta caixa de seleção para tornar o status de viagem obrigatório, para que ele não possa ser ignorado. |
| Item pai | Use este campo para estabelecer uma hierarquia entre os valores de status. Os status de viagem podem ser alterados (de forma manual ou automática) somente para baixo na hierarquia, do status pai para um de seus status filho.

> [!NOTE]
> Você deve configurar somente os status de viagem específicos que sua organização usa. Os status de viagem comuns incluem *Confirmado*, *Mercadorias em trânsito*, *Recebido*, *Pronto para avaliação de custo* e *Orçado*. No entanto, outros status podem estar presentes.
