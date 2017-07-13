---
title: "Defina a comunicação de canal de varejo (Commerce Data Exchange)"
description: "Este artigo fornece uma visão geral de comércio de troca de dados e dos seus componentes. Ele explica a parte que cada componente tem na transferência de dados entre o Microsoft Dynamics 365 for Retail e os canais de varejo."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 68252e52da47b89166627edbf2aa530e762354c6
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Defina a comunicação de canal de varejo (Commerce Data Exchange)

[!include[banner](../includes/banner.md)]


Este artigo fornece uma visão geral de comércio de troca de dados e dos seus componentes. Ele explica a parte que cada componente tem na transferência de dados entre o Microsoft Dynamics 365 for Retail e os canais de varejo.

<a name="overview"></a>Visão Geral
--------

O Commerce Data Exchange é um sistema que transfere dados entre o Dynamics 365 for Retail e os canais de varejo, como lojas online ou lojas físicas. O banco de dados que armazena dados para um canal de varejo é separado do banco de dados do Dynamics 365 for Retail. O banco de dados do canal retém somente os dados necessários para as transações de varejo. Os dados mestre são configurados no Dynamics 365 for Retail e distribuídos para os canais. Os dados de transação são criados no sistema de ponto de venda (POS) ou no armazenamento online, e carregados no Dynamics 365 for Retail. A distribuição dos dados é assíncrona. Ou seja, o processo de obter e empacotar os dados na origem ocorre de forma separada do processo de recebimento e aplicação de dados no destino. Para algumas situações, como pesquisas de preço e de estoque, os dados devem ser recuperados em tempo real. Para oferecer suporte a estes cenários, o Commerce Data Exchange também inclui um serviço que permite a comunicação em tempo real entre o Dynamics 365 for Retail e um canal. 

[![updated-retail-graphic](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async Service
O controle de alterações do Microsoft SQL Server no banco de dados do Dynamics 365 for Retail é usado para determinar as alterações nos dados que devem ser enviadas para os canais. Com base em um plano de distribuição, o Dynamics 365 for Retail empacota esses dados e os salva no armazenamento central (armazenamento blob do Azure). Um processo em lote separado usa o Commerce Data Exchange: Biblioteca do cliente Async para inserir este pacote de dados no banco de dados do canal. 

[![Serviço Async](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Agendador do Retail

Os trabalhos do agendados são o mecanismo para distribuir dados aos locais. Os trabalhos são compostos de subtrabalhos, que especificam as tabelas e os campos de tabela que contêm os dados de distribuição. O Dynamics 365 for Retail inclui os trabalhos e subtrabalhos predefinidos do agendador que atendem aos requisitos de replicações da maioria das organizações. Os seguintes tipos de trabalho pré-definido são criados:

-   **Trabalhos de download** – Os trabalhos de download enviam os dados que foram alteradas do Dynamics 365 for Retail para os bancos de dados do canal. As alterações nos registros são rastreadas com o controle de alterações do SQL Server.
-   **Trabalhos de upload (trabalhos P)** – Os trabalhos de upload carregam as transações de venda de um canal no banco de dados do Dynamics 365 for Retail. Os trabalhos P carregam os dados de forma incremental. Quando um trabalho P é executado, a biblioteca do cliente Async verifica o contador de replicações para os registros que já foram recebidos de um local. Um registro é carregado apenas se o seu contador de replicações for superior ao maior valor encontrado. Os trabalhos P não carregam os dados carregados anteriormente.

A agenda de distribuição é usada para executar a transferência de dados, manualmente ou por agendamento de um trabalho em lotes no Dynamics 365 for Retail. Um plano de distribuição pode conter um ou mais grupos de dados de canal, e um ou vários trabalhos do agendador.

## <a name="realtime-service"></a>Realtime Service
Commerce Data Exchange: o Real-time Service é um serviço integrado que fornece comunicação em tempo real entre o Dynamics 365 for Retail e os canais de varejo. O Real-time Service permite que computadores PDV individuais e lojas online recuperem dados específicos do Dynamics 365 for Retail em tempo real. Embora a maioria das operações principais possa ser executada no banco de dados do canal local, os seguintes cenários precisam de acesso direto aos dados que são armazenados no Dynamics 365 for Retail:

-   Emissão e resgate de vales-presentes.
-   Resgate de pontos de fidelidade.
-   Emissão e resgate de memorandos de crédito.
-   Criação e atualização de registros de cliente.
-   Criação, atualização, e conclusão de ordens de venda.
-   Recebimento de estoque em relação a uma ordem de compra ou ordem de transferência.
-   Execução de contagens de estoque.
-   Recuperação das transações de venda nas lojas e conclusão de transações de devolução.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Um perfil de Serviço em tempo real predefinido é criado.




