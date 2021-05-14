---
title: Aprovar um modelo da configuração do produto
description: Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920498"
---
# <a name="approve-a-product-configuration-model"></a>Aprovar um modelo da configuração do produto

[!include [banner](../../includes/banner.md)]

Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível. Este procedimento usa o modelo de alto-falante avançado na empresa de dados de demonstração USMF. Observe que esse modelo já foi aprovado, mas o procedimento o conduz por todo o processo.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Na lista, localize e selecione o registro desejado.
    * Selecione o modelo alto-falante avançado para este procedimento.  
1. Selecione **Versões**.
1. Selecione **Novo**.
1. No campo **Número do produto**, insira ou selecione um valor.
    * A referência a um produto representa uma versão do modelo de configuração do produto. Somente os produtos mestre que têm a tecnologia de configuração com base restrição aparecerão na lista.  
1. No campo **Data inicial**, insira uma data.
    * Selecione quando a versão do modelo de produto estará disponível.  
1. No campo **Data final**, insira uma data.
    * Selecione uma data final na qual essa versão do modelo de produto irá expirar ou selecione Nunca.  
1. Selecione **Aprovar** para abrir a caixa de diálogo suspensa.
1. No campo **Aprovado por** insira ou selecione um valor.
    * Selecione a pessoa é responsável pela aprovação de modelos de produto para uso nas operações.  
1. Selecione **OK**.
1. No campo **Método de precificação**, selecione uma opção.
    * Ative a versão do modelo de produto. Só é possível ter um produto ativo para um modelo de produto por vez.  
1. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]