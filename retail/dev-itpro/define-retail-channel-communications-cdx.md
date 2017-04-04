---
title: "Defina a comunicação de canal de varejo (Commerce Data Exchange)"
description: "Este artigo fornece uma visão geral de comércio de troca de dados e dos seus componentes. A parte que explica cada componente faz na transferência de dados entre o Microsoft Dynamics 365 para operações e canais de varejo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Defina a comunicação de canal de varejo (Commerce Data Exchange)

Este artigo fornece uma visão geral de comércio de troca de dados e dos seus componentes. A parte que explica cada componente faz na transferência de dados entre o Microsoft Dynamics 365 para operações e canais de varejo.

<a name="overview"></a>Visão Geral
--------

Comércio troca de dados é um sistema que transfira dados entre o dynamics 365 para operações e canais de varejo, como lojas ou online repositórios físicas. O base de dados que armazena dados de um canal é separado de varejo 365 dinâmica de dados de operações. O banco de dados do canal retém somente os dados necessários para as transações de varejo. Os dados mestre são configurados em dynamics 365 para operações e distribuídos para canais. Os dados transacionais são criados no sistema de (POS) da venda ou online, o armazenamento e carregado no dynamics 365 para as operações. A distribuição dos dados é assíncrona. Ou seja, o processo de obter e empacotar os dados na origem ocorre de forma separada do processo de recebimento e aplicação de dados no destino. Para algumas situações, como pesquisas de preço e de estoque, os dados devem ser recuperados em tempo real. Para dar suporte estes cenários, comércio troca de dados também incluem um serviço que habilita a comunicação de tempo real entre o dynamics 365 para operações e um canal. 

[atualizar-varejo- gráfico![(]. /media/updated-retail-graphic.png)](. /media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async Service
O controle de alterações do Microsoft SQL Server em dynamics 365 de dados de operações é usado para determinar as alterações dos dados que devem ser enviadas para os canais. Com base em um plano de distribuição, o dynamics 365 para os pacotes de operações que dados e os salva no depósito central (armazenamento do blob de Azure). Um processo em lote separado usa o Commerce Data Exchange: Biblioteca do cliente Async para inserir este pacote de dados no banco de dados do canal. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Agendador do Retail

Os trabalhos do agendados são o mecanismo para distribuir dados aos locais. Os trabalhos são compostos de subtrabalhos, que especificam as tabelas e os campos de tabela que contêm os dados de distribuição. O dynamics 365 para operações inclui os trabalhos e subtrabalhos predefinidos do agendador que atendam a requisitos de replicações da maioria de organizações. Os seguintes tipos de trabalho pré-definido são criados:

-   ** O download ** de download – trabalhos a enviam dados que foram alterados do 365 para as operações canalizem bases de dados. As alterações nos registros são rastreadas com o controle de alterações do SQL Server.
-   ** Carregamento de trabalho (Trabalho P) ** – o carregamento receber transações de venda de um canal em dynamics 365 de dados de operações. Os trabalhos P carregam os dados de forma incremental. Quando um trabalho P é executado, a biblioteca do cliente Async verifica o contador de replicações para os registros que já foram recebidos de um local. Um registro é carregado apenas se o seu contador de replicações for superior ao maior valor encontrado. Os trabalhos P não carregam os dados carregados anteriormente.

A agenda de distribuição é usada para executar a transferência de dados, manual ou planejar um trabalho em lotes em dynamics 365 para as operações. Um plano de distribuição pode conter um ou mais grupos de dados de canal, e um ou vários trabalhos do agendador.

## <a name="realtime-service"></a>Serviço Realtime
Commerce troca de dados: O serviço de tempo real é um serviço que fornece integrado comunicação de tempo real entre o dynamics 365 para operações e canais de varejo. O serviço de tempo real habilita computadores individuais POS e as lojas online para recuperar dados específicos do 365 para operações em tempo real. Embora a mais de operações principais podem ser realizadas no base de dados de canal local, os seguintes cenários exigem acesso direto aos dados que são armazenados em dynamics 365 para operações:

-   Emissão e resgate de vales-presentes.
-   Resgate de pontos de fidelidade.
-   Emissão e resgate de memorandos de crédito.
-   Criação e atualização de registros de cliente.
-   Criação, atualização, e conclusão de ordens de venda.
-   Recebimento de estoque em relação a uma ordem de compra ou ordem de transferência.
-   Execução de contagens de estoque.
-   Recuperação das transações de venda nas lojas e conclusão de transações de devolução.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

Um perfil predefinido de serviço de tempo real é criado.


