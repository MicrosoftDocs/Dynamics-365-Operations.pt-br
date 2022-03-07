---
title: Criar uma classe de trabalho
description: Este procedimento mostra como configurar uma classe de trabalho.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49b110b93e6f0f886d180f9f2725245faad7afab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239029"
---
# <a name="create-a-work-class"></a>Criar uma classe de trabalho

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar uma classe de trabalho. Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de trabalho que um funcionário do depósito pode processar em um dispositivo móvel. As linhas que um funcionário pode processar são determinadas pelas classes de trabalho nos itens de menu do dispositivo móvel aos quais o funcionário do depósito tem acesso e pela classe de trabalho que está especificada nas linhas de trabalho. Classes de trabalho também podem ser usadas para validar o local de colocação para uma linha da ordem de trabalho. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados. Esse procedimento é destinado ao gerente do depósito.

1. Vá para Gerenciamento de depósito > Configuração > Trabalho > Classes de trabalho.
2. Clique em Novo.
3. No campo ID de classe de trabalho, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo de ordem de trabalho, selecione uma opção.
6. Clique em Novo.
7. No campo Tipo de localização, digite um valor.
    * Se você selecionar um tipo de localização, isso define uma restrição sobre onde os itens podem ser colocados depois que foram separados. Essa configuração é usada quando uma diretiva de localização tenta resolver a localização, ou se um funcionário do depósito fornece manualmente a localização do item de menu do dispositivo móvel.  
8. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]