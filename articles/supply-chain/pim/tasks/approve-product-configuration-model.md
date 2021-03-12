---
title: Aprovar um modelo da configuração do produto
description: Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b548e2369f30e998ecde45408ff45893b88f9a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987095"
---
# <a name="approve-a-product-configuration-model"></a>Aprovar um modelo da configuração do produto

[!include [banner](../../includes/banner.md)]

Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível. Este procedimento usa o modelo de alto-falante avançado na empresa de dados de demonstração USMF. Observe que esse modelo já foi aprovado, mas o procedimento o conduz por todo o processo.

1. Clique em Definição de modelo de variante de produto.
2. Clique em Modelos de configuração do produto.
3. Na lista, localize e selecione o PDV desejado.
    * Selecione o modelo alto-falante avançado para este procedimento.  
4. Clique em Versões.
5. Clique em Novo.
6. No campo Número do produto, insira ou selecione um valor.
    * A referência a um produto representa uma versão do modelo de configuração do produto. Somente os produtos mestre que têm a tecnologia de configuração com base restrição aparecerão na lista.  
7. No campo De data, insira uma data.
    * Selecione quando a versão do modelo de produto estará disponível.  
8. No campo Para data, insira uma data.
    * Selecione uma data final na qual essa versão do modelo de produto irá expirar ou selecione Nunca.  
9. Clique em Aprovar para abrir a caixa de diálogo suspensa.
10. No campo Aprovado por, insira ou selecione um valor.
    * Selecione a pessoa é responsável pela aprovação de modelos de produto para uso nas operações.  
11. Clique em OK.
12. No campo Método de precificação, selecione uma opção.
    * Ative a versão do modelo de produto. Só é possível ter um produto ativo para um modelo de produto por vez.  
13. Feche a página.

