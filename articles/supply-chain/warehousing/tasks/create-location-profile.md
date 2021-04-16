---
title: Criar um perfil de localização
description: Este tópico explica como criar um perfil de localização no Dynamics 365 Supply Chain Management.
author: ShylaThompson
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 101d80216f786eb8edb687031e4deac8cc3033ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831017"
---
# <a name="create-a-location-profile"></a>Criar um perfil de localização

[!include [banner](../../includes/banner.md)]

Este tópico explica como criar um perfil de localização no Dynamics 365 Supply Chain Management. Cada local no depósito precisa ter um perfil de local associado a ele, que descreve as propriedades do local, por exemplo, se o local permite itens mistos. Neste procedimento é criaremos um perfil para um local que não exija o controle de matrícula. Nós habilitaremos misturados itens, e o status de estoque e permitimos misturados, a contagem cíclica. Você pode usar este procedimento na empresa USMF de dados de demonstração.


1. No Painel de Navegação, vá para **Módulos > Gerenciamento de depósito > Configuração > Depósito > Perfis de localização**.
2. Selecione **Novo**.
3. No campo **ID do perfil de localização**, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Formato de local**, insira ou selecione um valor.
6. No campo **Tipo de local**, insira ou selecione um valor.
7. No campo **ID do perfil do gerenciamento de doca**, insira ou selecione um valor.
8. Selecione **Sim** no campo **Permitir itens misturados**.
9. Selecione **Sim** no campo **Permitir status de estoque misturados**.
10. Selecione **Sim** no campo **Permitir contagem cíclica**.
11. Selecione **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]