---
title: "Migrar produtos e gerenciamento de depósito de AX 2012 para Finance and Operations"
description: "Este tópico fornece uma visão geral das opções de migração de gerenciamento do produto e de depósito."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 4d94a5b2cc0e9ea144fbefc97cc27a2920016358
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2018

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Migrar produtos e gerenciamento de depósito de AX 2012 para Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico fornece uma visão geral das opções de migração do gerenciamento de produtos e armazéns no Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

<a name="introduction"></a>Introdução
------------

Durante uma atualização para Finanças e Operações, os produtos são bloqueados se estiverem associados a um grupo de dimensões de armazenamento que tenha configurações que não correspondam aos requisitos de configurações de grupo de dimensões de armazenamento no Finance and Operations. No entanto, após a atualização, você pode usar um conjunto de opções de migração no processo **Alterar grupo de dimensão de armazenamento para itens** para desbloquear produtos que foram bloqueados durante a atualização. Em seguida, você pode processar transações para esses produtos. Alguns de seus itens podem já estar associados a grupos de dimensões de armazenamento, onde as dimensões de inventário Site, Armazenamento e Localização estão ativas e são rastreadas fisicamente. Nesse caso, você pode usar o processo **Alterar grupo de dimensão de armazenamento para itens** para habilitar os itens a serem usados nos processos de gerenciamento de depósito. Esse recurso é útil se você quiser usar a funcionalidade de gerenciamento do armazenamento para itens existentes.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Atualizando para Finanças e Operações, quando o AX 2012 R3 WMSII é usado
Finanças e Operações, não oferece mais suporte ao módulo convencional **WMSII** do Microsoft Dynamics AX 2012. Em vez disso, você pode usar o novo módulo **Gerenciamento de depósito**. Nas versões anteriores, as dimensões de inventário Localização e ID de palete podem ser selecionadas para o inventário financeiro. No entanto, como parte do processo de atualização, a dimensão do inventário ID de palete não pode mais ser ativada para inventário financeiro. Todos os produtos que estão associados a um grupo de dimensões de armazenamento que usam a dimensão de inventário ID de palete serão bloqueados e não serão processados.

### <a name="enabling-items-in-finance-and-operations"></a>Ativando itens no Finance and Operations

No Finance and Operations, os itens que serão utilizados como parte dos processos de gerenciamento de armazéns devem estar associados a um grupo de dimensão de armazenamento onde o parâmetro **Usar processos de gerenciamento de depósito** é selecionado. Quando esta configuração é selecionada, as dimensões de estoque Site, Armazenamento, Estoque, Localização e Placa da licença se tornam ativas. Você pode mudar para esse tipo de grupo de dimensão de armazenamento apenas para itens que já estão associados a grupos de dimensões de armazenamento onde a dimensão de estoque Localização está ativa.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Itens bloqueados para atualizações de estoque

Para ver a lista de produtos lançados que foram bloqueados durante a atualização e não podem ser processados, clique em **Gerenciamento de estoque** &gt; **Configuração** &gt; **Estoque** &gt; **Itens bloqueados para atualizações de estoque**.

### <a name="reapplying-blocked-products"></a>Reaplicando produtos bloqueados

Para desbloquear produtos que foram bloqueados durante a atualização, você deve selecionar um novo grupo de dimensão de armazenamento para os produtos. Observe que você pode alterar o grupo de dimensões de armazenamento, mesmo que existam operações de inventário abertas. Para usar itens que foram bloqueados durante a atualização, você tem duas opções:

-   Altere o grupo de dimensões de armazenamento do item para um grupo de dimensões de armazenamento que usa apenas as dimensões de estoque Site, Depósito e Localização. Como resultado dessa alteração, a dimensão do estoque ID de palete não é mais utilizada.
-   Altere o grupo de dimensões de armazenamento do item para um grupo de dimensões de armazenamento que usa os processos de gerenciamento do depósito. Como resultado dessa alteração, a dimensão do estoque da placa de licença é usada agora.

### <a name="migration-processes"></a>Processos de migração

No Finance and Operations, o rastreamento de itens faz parte dos processos de gerenciamento de depósito. Para esses processos, todos os depósitos e seus locais devem estar associados a um perfil de localização. Conceitualmente, se você quiser usar processos de gerenciamento de depósito, dois processos devem ser tratados:

-   Os depósitos existentes devem ser habilitados para usar processos de gerenciamento de armazém.
-   Os produtos lançados existentes devem estar associados a um novo grupo de dimensão de armazenamento que usa processos de gerenciamento de depósito.

Se os grupos de dimensão de armazenamento de origem usarem a dimensão de estoque ID de palete, os locais do estoque existente disponível que usaram a dimensão de estoque ID de palete devem estar associados a um perfil de localização onde o parâmetro **Usar monitoramento de placa de licença** está selecionado. Se os depósitos existentes não precisarem ser habilitados para usar processos de gerenciamento de depósito, você pode alterar os grupos de dimensões de armazenamento do estoque existente disponível para grupos que manipulam apenas as dimensões de estoque Site, Depósito e Localização.

### <a name="using-the-warehouse-management-processes"></a>Usando processos de gerenciamento de depósito

Para usar produtos lançados no módulo **Gerenciamento de depósito**, os produtos devem usar um grupo de dimensão de estoque onde o parâmetro **Usar processos de gerenciamento de depósito** está selecionado.

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Permitir que depósitos usem processos de gerenciamento de depósito

1.  Crie pelo menos um novo perfil de localização.
2.  Clique em **Gerenciamento de depósito** &gt; **Configuração** &gt; **Habilitar processos de gerenciamento de depósito** &gt; **Habilitar configuração de depósito**.
3.  Na página **Habilitar configuração de depósito**, adicione os depósitos que devem ser habilitados. Você pode concluir esta etapa na página ou diretamente usando a integração do Microsoft Office.
4.  Atribua um perfil de local a todos os locais. Você pode facilmente completar esta etapa usando a integração do Microsoft Office diretamente da página. Você pode exportar e importar os dados ou usar o processamento da entidade de dados em [Gerenciamento de dados](../../dev-itpro/data-entities/data-entities.md).
5.  Valide as alterações. Como parte do processo de validação, ocorrem várias validações de integridade de dados. Como parte de um processo de atualização maior, os problemas que ocorrem podem ter que ser ajustados na implementação de origem. Neste caso, será necessária uma atualização adicional de dados.
6.  Processe as alterações.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Altere o grupo de dimensões de armazenamento para itens, de modo que ele use processos de gerenciamento de depósito

1.  Crie um novo valor **Status de estoque**, e a atribua a ele o valor **ID padrão do status de estoque** nas configurações dos **Parâmetros de gerenciamento de depósito**.
2.  Crie um novo grupo de dimensão de estoque onde o parâmetro **Usar processos de gerenciamento de depósito** está selecionado.
3.  Na página **Hierarquia de reserva**, defina uma nova hierarquia de reserva de acordo com os grupos de dimensão de rastreamento e de armazenamento de item.
4.  Crie um ou mais grupos de sequência de unidade incluindo pelo menos as mesmas unidades usadas para as unidades de estoque de itens.
5.  Clique em **Gerenciamento de depósito** &gt; **Configuração** &gt; **Habilitar processos de gerenciamento de depósito** &gt; **Alterar grupo de dimensão de estoque para itens**.
6.  Na página **Alterar grupo de dimensão de estoque para itens**, adicione os números de item, os grupos de dimensões de estoque, e os grupos de sequências unitários. Você pode concluir este passo diretamente na página, usando a integração do Microsoft Office ou usando o processo de entidade de dados em [Gerenciamento de dados](../../dev-itpro/data-entities/data-entities.md).
7.  Valide as alterações. Como parte do processo de validação, ocorrem várias validações de integridade de dados. Como parte de um processo de atualização maior, os problemas que ocorrem podem ter que ser ajustados na implementação de origem. Neste caso, será necessária uma atualização adicional de dados.
8.  Processe as alterações. Uma atualização das dimensões do estoque pode demorar um pouco. Você pode monitorar o progresso usando as tarefas de trabalhos em lote.



