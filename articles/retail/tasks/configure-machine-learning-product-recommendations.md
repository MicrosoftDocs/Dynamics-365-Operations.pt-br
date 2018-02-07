--- 
title: " Configurar recomendações de produto fornecidas pelo aprendizado de máquina"
description: "Este processo atualiza os dados no Repositório de Entidades que é usado pelo sistema de aprendizado de máquina que fornece recomendações de produto e habilita as recomendações de produto nos PDV clientes."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e32c7cf1283487cb7a52f7d8e261b6b587b76364
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="configure-machine-learning-powered-product-recommendations"></a> Configurar recomendações de produto fornecidas pelo aprendizado de máquina

[!include[task guide banner](../includes/task-guide-banner.md)]

Este processo atualiza os dados no Repositório de Entidades que é usado pelo sistema de aprendizado de máquina que fornece recomendações de produto e habilita as recomendações de produto nos PDV clientes. Este procedimento usa a empresa USRT nos dados de demonstração.

1. Vá para Administração do sistema > Configuração > Repositório de Entidades.
2. Na lista, localize e selecione o registro 'RetailSales'.
3. Clique em Atualizar.
4. Clique em OK.
5. Feche a página.
6. Vá para Varejo e comércio > Configuração da sede > Parâmetros > Parâmetros de varejo.
7. Clique na guia Aprendizado de Máquina.
8. Selecione 'Sim' no campo Habilitar recomendações de produtos.
    * Se você receber a mensagem "Não foi possível recuperar os modelos de recomendações", é porque você atualizou o Repositório de Entidades muito recentemente e o sistema pode não ter finalizado a assimilação dos novos dados. Aguarde duas a três horas e tente novamente.  
9. Clique em Salvar.
10. Feche a página.


