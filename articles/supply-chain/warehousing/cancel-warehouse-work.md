---
title: Cancelar trabalho de depósito para tratamento de exceções
description: Este artigo descreve a funcionalidade Cancelar trabalho, que permite a supervisores de depósito tratar o trabalho bloqueado.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b1e2036e4e7a8a47d6df029f285df7aca0fa74e6
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403645"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Cancelar trabalho de depósito para tratamento de exceções

[!include [banner](../includes/banner.md)]

A funcionalidade cancelar trabalho no Microsoft Dynamics 365 Supply Chain Management permite que o usuário administrador cancele um trabalho de depósito específico em andamento, mas que tenha sido bloqueado pelo sistema ou que não possa ser concluído devido a circunstâncias excepcionais. Essa funcionalidade é uma alternativa atraente e segura aos scripts corretivos em SQL que corrigem dados inconsistentes. Mas, enquanto os scripts são normalmente solicitados de profissionais de TI, a funcionalidade cancelar trabalho pode ser usada por usuários na empresa com direitos de administrador.

Você pode acessar a funcionalidade cancelar trabalho em **Gerenciamento de depósito** \> **Tarefas periódicas** \> **Limpar \> Cancelar trabalho**. Na caixa de diálogo **Cancelar trabalho**, especifique a ID do trabalho a ser cancelado e então selecione **OK**.

## <a name="warehouse-work-that-can-be-canceled"></a>O trabalho de depósito que pode ser cancelado

Durante as operações de separação de depósito, um trabalhador poderá encontrar situações onde foram registradas quantidades como selecionadas de um local de armazenamento para seu local de usuário, mas não poderá registrar a operação de colocação. Os dados de depósito inconsistentes são geralmente, mas nem sempre, o motivo pelo qual o trabalho é bloqueado.

Diferente da funcionalidade cancelar normal, que pode ser acessada usando o botão **Cancelar** no cabeçalho do trabalho, a funcionalidade cancelar trabalho não exige que a última linha de trabalho concluído seja uma linha de trabalho do tipo **colocar**. Em outras palavras, para a funcionalidade cancelar trabalho, a lógica de cancelamento poderá ser executada mesmo se a quantidade do item em uma linha de trabalho estiver em um local do usuário.

> [!NOTE]
> Para trabalhos que devam ser cancelados por motivos operacionais, os usuários do depósito deverão continuar a usar a funcionalidade cancelar normal na página do trabalho.

Somente o trabalho do tipo **Vendas**, **Emissão de transferência**, **Separação da matéria-prima** ou **Reabastecimento** pode ser cancelado usando a funcionalidade cancelar trabalho. A lógica de cancelamento não será executada para o trabalho de separação de matéria-prima congelado ou o trabalho que pode ser cancelado usando a funcionalidade cancelar normal (consulte a observação anterior).

Para desbloquear o trabalho, o sistema cancela todas as linhas de trabalho restantes e corrige os dados de depósito associados à ID do trabalho que o usuário especificou. Todas as operações de manuseio de depósito comuns que envolvem a quantidade de itens afetados podem então ser retomadas.

Para colocar o item afetado em um determinado local depois que o trabalho tiver sido cancelado, o usuário deverá usar uma operação de movimentos de estoque ou de ajuste de quantidade em um dispositivo móvel.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]