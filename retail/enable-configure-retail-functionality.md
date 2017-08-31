---
title: Inicialize dados semente em um novo ambiente de varejo
description: "Este artigo descreve os dados que são criados como parte do processo de inicialização para o Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 0ee002d733882734c9f5a21e0467cacd1b3ff318
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Inicialize dados semente em um novo ambiente de varejo

[!include[banner](includes/banner.md)]


Este artigo descreve os dados que são criados como parte do processo de inicialização para o Microsoft Dynamics 365 for Retail.

Depois que a solução Retail for implantada no Microsoft Dynamics Lifecycle Services (LCS), você deverá inicializar a configuração de varejo para criar os dados básicos de configuração. **Importante:** antes que você inicialize a configuração de varejo, verifique se especificou um idioma e um endereço postal para cada entidade legal em que configurará as lojas de varejo. Essa etapa deve ser concluída para cada entidade legal usada no varejo. Para inicializar a configuração de varejo, execute estas etapas:

1.  Inicie o cliente do Dynamics 365 for Retail.
2.  Clique em **Varejo** &gt; **Configuração da sede** &gt; **Parâmetros** &gt; **Parâmetros de varejo**.
3.  Clique em **Inicializar**.

A inicialização cria os seguintes dados de configuração padrão:

-   Trabalhos e subtrabalhos do agendador de varejo
-   Esquema do canal de varejo
-   Agendas de distribuição do varejo
-   Layouts de tela padrão, que inclui grades de botões, imagens e temas
-   Informações sobre fuso horário
-   Operações de PDV (ponto de venda)
-   Permissões do PDV
-   Relatórios do canal
-   Metadados de atributo
-   Modelos de validação de entidade
-   Trabalhos em lotes para limpar o histórico da sessão do Commerce Data Exchange

Além disso, os registros relacionados à PCI (indústria de pagamento por cartão) estão habilitados para o banco de dados do Dynamics 365 for Retail. **Observação:** há uma opção para configurar separadamente o agendador do Retail. Esta opção permite redefinir a configuração do agendador do Retail para suas configurações padrão. Depois que a inicialização for concluída, você deve configurar os dados adicionais de varejo. Eis alguns exemplos:

-   Parâmetros de varejo
-   Parâmetros do agendador do Retail
-   Canais de varejo
-   Registros e dispositivos
-   Sortimentos





